<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>HYPACK XYZ VDATUM Z Adjuster</title>

<style>

    * {
        box-sizing: border-box;
    }

    body {
        font-family: Arial, Helvetica, sans-serif;
        background: #f2f4f7;
        margin: 0;
        padding: 30px;
        color: #222;
    }

    .container {
        max-width: 850px;
        margin: auto;
        background: white;
        padding: 30px;
        border-radius: 12px;
        box-shadow: 0 3px 15px rgba(0,0,0,0.12);
    }

    h1 {
        margin-top: 0;
        color: #1f4e79;
        text-align: center;
    }

    .description {
        text-align: center;
        color: #555;
        margin-bottom: 30px;
    }

    .section {
        border: 1px solid #d9d9d9;
        border-radius: 8px;
        padding: 20px;
        margin-bottom: 20px;
        background: #fafafa;
    }

    .section h2 {
        margin-top: 0;
        font-size: 19px;
        color: #1f4e79;
    }

    label {
        display: block;
        font-weight: bold;
        margin-bottom: 8px;
    }

    input[type="file"] {
        width: 100%;
        padding: 10px;
        background: white;
        border: 1px solid #bbb;
        border-radius: 5px;
    }

    .file-name {
        margin-top: 8px;
        color: #555;
        font-size: 14px;
        word-break: break-all;
    }

    button {
        width: 100%;
        padding: 14px;
        border: none;
        border-radius: 6px;
        background: #1f6feb;
        color: white;
        font-size: 17px;
        font-weight: bold;
        cursor: pointer;
    }

    button:hover {
        background: #1557b0;
    }

    button:disabled {
        background: #999;
        cursor: not-allowed;
    }

    #status {
        margin-top: 20px;
        padding: 15px;
        background: #eef5ff;
        border-left: 5px solid #1f6feb;
        border-radius: 5px;
        white-space: pre-line;
    }

    #progressContainer {
        display: none;
        margin-top: 15px;
    }

    progress {
        width: 100%;
        height: 22px;
    }

    #preview {
        margin-top: 20px;
        display: none;
    }

    #preview h3 {
        color: #1f4e79;
    }

    pre {
        background: #111;
        color: #eee;
        padding: 15px;
        border-radius: 6px;
        overflow-x: auto;
        font-size: 13px;
        line-height: 1.5;
    }

    .formula {
        background: #fff;
        border: 1px solid #ddd;
        padding: 12px;
        border-radius: 6px;
        font-family: Consolas, monospace;
        text-align: center;
        font-size: 16px;
        margin-top: 10px;
    }

    .note {
        font-size: 13px;
        color: #666;
        margin-top: 10px;
        line-height: 1.5;
    }

</style>
</head>

<body>

<div class="container">

    <h1>HYPACK XYZ VDATUM Z Adjuster</h1>

    <div class="description">
        Match each survey XYZ point to the closest VDATUM XY point
        and calculate the new Z value.
    </div>


    <!-- VDATUM FILE -->

    <div class="section">

        <h2>1. Select VDATUM XYZ File</h2>

        <label for="vdatumFile">
            VDATUM MLLW XYZ File
        </label>

        <input
            type="file"
            id="vdatumFile"
            accept=".xyz,.txt"
        >

        <div id="vdatumName" class="file-name">
            No VDATUM file selected
        </div>

        <div class="note">
            This file provides the Z value used for the closest XY match.
        </div>

    </div>


    <!-- SECOND / SURVEY FILE -->

    <div class="section">

        <h2>2. Select Survey / Second XYZ File</h2>

        <label for="surveyFile">
            XYZ Data File to Process
        </label>

        <input
            type="file"
            id="surveyFile"
            accept=".xyz,.txt"
        >

        <div id="surveyName" class="file-name">
            No survey file selected
        </div>

        <div class="note">
            X and Y from this file are retained.
            Its Z value will be adjusted using the closest VDATUM point.
        </div>

    </div>


    <!-- FORMULA -->

    <div class="section">

        <h2>Calculation</h2>

        <div class="formula">
            New Z = Survey Z + VDATUM Z
        </div>

        <div class="note">
            For every survey point, the closest VDATUM point is found
            using X and Y coordinates.
        </div>

    </div>


    <!-- PROCESS -->

    <button id="processButton">
        Process XYZ File
    </button>


    <div id="progressContainer">

        <progress
            id="progressBar"
            value="0"
            max="100">
        </progress>

        <div id="progressText">
            0%
        </div>

    </div>


    <!-- STATUS -->

    <div id="status">
        Select both files to begin.
    </div>


    <!-- PREVIEW -->

    <div id="preview">

        <h3>Output Preview</h3>

        <pre id="previewText"></pre>

    </div>

</div>


<script>

/* =========================================================
   GLOBAL VARIABLES
   ========================================================= */

let vdatumPoints = [];
let kdTree = null;


/* =========================================================
   FILE NAME DISPLAY
   ========================================================= */

document.getElementById("vdatumFile").addEventListener(
    "change",
    function () {

        if (this.files.length > 0) {

            document.getElementById("vdatumName").textContent =
                this.files[0].name;

        } else {

            document.getElementById("vdatumName").textContent =
                "No VDATUM file selected";

        }

    }
);


document.getElementById("surveyFile").addEventListener(
    "change",
    function () {

        if (this.files.length > 0) {

            document.getElementById("surveyName").textContent =
                this.files[0].name;

        } else {

            document.getElementById("surveyName").textContent =
                "No survey file selected";

        }

    }
);


/* =========================================================
   PARSE XYZ FILE
   ========================================================= */

function parseXYZ(text) {

    const lines = text.split(/\r?\n/);

    const points = [];

    for (let i = 0; i < lines.length; i++) {

        const line = lines[i].trim();

        if (!line) {
            continue;
        }

        const parts = line.split(/\s+/);

        if (parts.length < 3) {
            continue;
        }

        const x = Number(parts[0]);
        const y = Number(parts[1]);
        const z = Number(parts[2]);

        if (
            Number.isFinite(x) &&
            Number.isFinite(y) &&
            Number.isFinite(z)
        ) {

            points.push({
                x: x,
                y: y,
                z: z
            });

        }

    }

    return points;
}


/* =========================================================
   KD TREE NODE
   ========================================================= */

class KDNode {

    constructor(point, axis) {

        this.point = point;

        this.axis = axis;

        this.left = null;

        this.right = null;

    }

}


/* =========================================================
   BUILD KD TREE
   ========================================================= */

function buildKDTree(points, depth = 0) {

    if (points.length === 0) {
        return null;
    }

    const axis = depth % 2;

    points.sort(function(a, b) {

        if (axis === 0) {
            return a.x - b.x;
        } else {
            return a.y - b.y;
        }

    });


    const middle = Math.floor(points.length / 2);

    const node = new KDNode(
        points[middle],
        axis
    );


    const leftPoints =
        points.slice(0, middle);

    const rightPoints =
        points.slice(middle + 1);


    node.left =
        buildKDTree(leftPoints, depth + 1);

    node.right =
        buildKDTree(rightPoints, depth + 1);


    return node;
}


/* =========================================================
   DISTANCE SQUARED
   ========================================================= */

function distanceSquared(a, b) {

    const dx = a.x - b.x;

    const dy = a.y - b.y;

    return dx * dx + dy * dy;

}


/* =========================================================
   FIND CLOSEST POINT
   ========================================================= */

function nearestPoint(
    node,
    target,
    best = null,
    bestDistance = Infinity
) {

    if (node === null) {

        return {
            point: best,
            distance: bestDistance
        };

    }


    const currentDistance =
        distanceSquared(
            target,
            node.point
        );


    if (currentDistance < bestDistance) {

        best = node.point;

        bestDistance = currentDistance;

    }


    const axis = node.axis;


    let difference;


    if (axis === 0) {

        difference =
            target.x - node.point.x;

    } else {

        difference =
            target.y - node.point.y;

    }


    let nearBranch;

    let farBranch;


    if (difference < 0) {

        nearBranch = node.left;

        farBranch = node.right;

    } else {

        nearBranch = node.right;

        farBranch = node.left;

    }


    let result =
        nearestPoint(
            nearBranch,
            target,
            best,
            bestDistance
        );


    best = result.point;

    bestDistance = result.distance;


    if (
        difference * difference
        < bestDistance
    ) {

        result =
            nearestPoint(
                farBranch,
                target,
                best,
                bestDistance
            );

        best = result.point;

        bestDistance = result.distance;

    }


    return {
        point: best,
        distance: bestDistance
    };

}


/* =========================================================
   UPDATE STATUS
   ========================================================= */

function setStatus(message) {

    document.getElementById("status").textContent =
        message;

}


/* =========================================================
   PROCESS FILES
   ========================================================= */

document.getElementById("processButton")
.addEventListener(
    "click",
    async function () {

        const vdatumFile =
            document.getElementById("vdatumFile")
            .files[0];

        const surveyFile =
            document.getElementById("surveyFile")
            .files[0];


        if (!vdatumFile) {

            alert(
                "Please select the VDATUM XYZ file."
            );

            return;

        }


        if (!surveyFile) {

            alert(
                "Please select the survey / second XYZ file."
            );

            return;

        }


        const button =
            document.getElementById(
                "processButton"
            );


        button.disabled = true;


        document.getElementById(
            "progressContainer"
        ).style.display = "block";


        document.getElementById(
            "preview"
        ).style.display = "none";


        try {

            /* ==========================================
               READ VDATUM FILE
               ========================================== */

            setStatus(
                "Reading VDATUM file..."
            );


            const vdatumText =
                await vdatumFile.text();


            vdatumPoints =
                parseXYZ(vdatumText);


            if (vdatumPoints.length === 0) {

                throw new Error(
                    "No valid XYZ points were found in the VDATUM file."
                );

            }


            setStatus(
                "VDATUM points loaded: " +
                vdatumPoints.length.toLocaleString() +
                "\n\nBuilding nearest-point search tree..."
            );


            /*
             * Build KD tree.
             *
             * slice() creates arrays during the
             * construction, so yield occasionally
             * to keep browser responsive.
             */

            await new Promise(
                resolve => setTimeout(resolve, 50)
            );


            kdTree =
                buildKDTree(
                    vdatumPoints
                );


            /* ==========================================
               READ SURVEY FILE
               ========================================== */

            setStatus(
                "Reading survey XYZ file..."
            );


            const surveyText =
                await surveyFile.text();


            const surveyLines =
                surveyText.split(/\r?\n/);


            let outputLines = [];

            let validPoints = 0;

            let unchangedLines = 0;

            let maxDistance = 0;

            let previewLines = [];


            /* ==========================================
               PROCESS EACH SURVEY POINT
               ========================================== */

            for (
                let i = 0;
                i < surveyLines.length;
                i++
            ) {

                const originalLine =
                    surveyLines[i];


                const line =
                    originalLine.trim();


                /*
                 * Preserve blank lines.
                 */

                if (!line) {

                    outputLines.push(
                        originalLine
                    );

                    unchangedLines++;

                    continue;

                }


                const parts =
                    line.split(/\s+/);


                /*
                 * If not an XYZ line,
                 * preserve it unchanged.
                 */

                if (parts.length < 3) {

                    outputLines.push(
                        originalLine
                    );

                    unchangedLines++;

                    continue;

                }


                const x =
                    Number(parts[0]);

                const y =
                    Number(parts[1]);

                const z =
                    Number(parts[2]);


                if (
                    !Number.isFinite(x) ||
                    !Number.isFinite(y) ||
                    !Number.isFinite(z)
                ) {

                    outputLines.push(
                        originalLine
                    );

                    unchangedLines++;

                    continue;

                }


                /* ======================================
                   FIND CLOSEST VDATUM POINT
                   ====================================== */

                const target = {
                    x: x,
                    y: y
                };


                const nearest =
                    nearestPoint(
                        kdTree,
                        target
                    );


                const vdatumPoint =
                    nearest.point;


                const distance =
                    Math.sqrt(
                        nearest.distance
                    );


                if (distance > maxDistance) {

                    maxDistance =
                        distance;

                }


                /* ======================================
                   NEW Z CALCULATION
                   ====================================== */

                const newZ =
                    z + vdatumPoint.z;


                /*
                 * X = survey X
                 * Y = survey Y
                 * Z = survey Z + VDATUM Z
                 *
                 * X and Y rounded to 2 decimals.
                 * Z rounded to 2 decimals.
                 */

                const outputLine =
                    x.toFixed(2) +
                    " " +
                    y.toFixed(2) +
                    " " +
                    newZ.toFixed(2);


                outputLines.push(
                    outputLine
                );


                validPoints++;


                /*
                 * Keep first 10 valid points
                 * for preview.
                 */

                if (
                    previewLines.length < 10
                ) {

                    previewLines.push(
                        outputLine
                    );

                }


                /* ======================================
                   UPDATE PROGRESS
                   ====================================== */

                if (
                    i % 5000 === 0
                ) {

                    const percent =
                        (
                            i /
                            surveyLines.length
                        ) * 100;


                    document.getElementById(
                        "progressBar"
                    ).value =
                        percent;


                    document.getElementById(
                        "progressText"
                    ).textContent =
                        Math.round(percent) +
                        "%";


                    setStatus(
                        "Processing survey points...\n" +
                        "Points processed: " +
                        validPoints.toLocaleString() +
                        "\n" +
                        "Progress: " +
                        Math.round(percent) +
                        "%"
                    );


                    /*
                     * Allow browser to update screen.
                     */

                    await new Promise(
                        resolve =>
                            setTimeout(
                                resolve,
                                0
                            )
                    );

                }

            }


            /* ==========================================
               COMPLETE
               ========================================== */

            document.getElementById(
                "progressBar"
            ).value = 100;


            document.getElementById(
                "progressText"
            ).textContent = "100%";


            /*
             * Join lines using newline.
             */

            const outputText =
                outputLines.join("\n");


            /* ==========================================
               CREATE DOWNLOAD FILE
               ========================================== */

            const blob =
                new Blob(
                    [outputText],
                    {
                        type:
                            "text/plain;charset=utf-8"
                    }
                );


            const url =
                URL.createObjectURL(blob);


            const link =
                document.createElement("a");


            link.href = url;


            /*
             * Remove extension from
             * original survey filename.
             */

            const originalName =
                surveyFile.name;


            const baseName =
                originalName.replace(
                    /\.(xyz|txt)$/i,
                    ""
                );


            link.download =
                baseName +
                "_VDATUM_ADJUSTED.xyz";


            document.body.appendChild(link);


            link.click();


            document.body.removeChild(link);


            URL.revokeObjectURL(url);


            /* ==========================================
               STATUS
               ========================================== */

            setStatus(
                "PROCESSING COMPLETE\n\n" +

                "VDATUM points: " +
                vdatumPoints.length.toLocaleString() +

                "\nSurvey points processed: " +
                validPoints.toLocaleString() +

                "\nUnchanged/non-XYZ lines: " +
                unchangedLines.toLocaleString() +

                "\nMaximum XY matching distance: " +
                maxDistance.toFixed(3) +

                "\n\nCalculation:\n" +
                "New Z = Survey Z + VDATUM Z" +

                "\n\nOutput:\n" +
                baseName +
                "_VDATUM_ADJUSTED.xyz"
            );


            /* ==========================================
               PREVIEW
               ========================================== */

            document.getElementById(
                "preview"
            ).style.display = "block";


            document.getElementById(
                "previewText"
            ).textContent =
                previewLines.join("\n");


        }

        catch (error) {

            console.error(error);


            setStatus(
                "ERROR:\n\n" +
                error.message
            );


            alert(
                "An error occurred:\n\n" +
                error.message
            );

        }


        finally {

            button.disabled = false;

        }

    }
);

</script>

</body>
</html>
