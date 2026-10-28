<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FREE HYDRO-CAD Tools</title>
<style>
:root{--ink:#0b4f7a;--sea:#0a6ea5;--sea-d:#085888;--paper:#eef6fb;--line:#cfe1ec;--mut:#546e80;
      --ok:#0a6b43;--okbg:#e6f5ec;--bad:#a32017;--badbg:#fdeceb;--tint:#e1f1fa}
*{box-sizing:border-box}
body{margin:0;background:var(--paper);color:#14303f;font:16px/1.5 "Segoe UI",system-ui,-apple-system,Roboto,Arial,sans-serif}
.wrap{max-width:1100px;margin:0 auto}
.top{position:relative;width:min(1060px,calc(100% - 40px));margin:0 auto;background:linear-gradient(180deg,#3fa6df 0%,#8fd2f1 60%,#cfeefb 100%);overflow:hidden}
.top .sky{position:absolute;inset:0;width:100%;height:100%;pointer-events:none}
.top .wrap{position:relative;padding:26px 20px 6px}
h1{margin:0;font-size:1.75rem;font-weight:800;color:#06385a;letter-spacing:.3px}
.surf{position:relative;display:block;width:100%;height:46px;margin-bottom:-1px}
.sea{position:relative;background:#0a6ea5}
.sea .wrap{padding:0 20px}
.tabs{display:flex;gap:8px;overflow-x:hidden;flex-wrap:wrap;padding-top:4px;padding-bottom:4px;align-items:flex-end}
.tab-button{flex:1 1 auto;margin:0;padding:11px 18px;border:0;border-radius:8px 8px 0 0;background:transparent;color:#dff2fb;font:600 15px/1.2 inherit;cursor:pointer}
.tab-button:hover{color:#fff;background:rgba(255,255,255,.12)}
.tab-button.active{background:var(--paper);color:var(--ink)}
main{max-width:1100px;margin:0 auto;padding:22px 20px 48px}
.tab-content{display:none}
.tab-content.active{display:block}
.convert-sub-tabs{display:flex;gap:8px;flex-wrap:wrap;margin:0 0 18px;padding:6px;background:#dceef8;border:1px solid var(--line);border-radius:10px}
.convert-sub-button{flex:1 1 140px;padding:10px 16px;border:1px solid transparent;border-radius:7px;background:transparent;color:var(--ink);font-weight:700;cursor:pointer}
.convert-sub-button:hover{background:rgba(10,110,165,.10)}
.convert-sub-button.active{background:var(--sea);color:#fff}
.convert-sub-content{display:none}
.convert-sub-content.active{display:block}
.section{background:#fff;border:1px solid var(--line);border-radius:10px;padding:22px;margin-bottom:16px}
.section h2{margin:0 0 2px;font-size:1.15rem;color:var(--ink)}
.description{margin:0;color:var(--mut);font-size:.92rem}
label{display:block;margin:18px 0 6px;font-weight:600;font-size:.9rem;color:#2c4252}
input[type=file],input[type=number],select{width:100%;padding:10px 12px;font:inherit;font-size:15px;color:inherit;background:#fff;border:1px solid var(--line);border-radius:8px}
input[type=file]::file-selector-button{margin-right:12px;padding:7px 14px;border:0;border-radius:6px;background:var(--ink);color:#fff;font:600 14px inherit;cursor:pointer}
.hint{margin:8px 0 0;color:var(--mut);font-size:.86rem}
.file-name{margin-top:6px;color:var(--mut);font-size:.86rem}
.check{display:flex;align-items:center;gap:10px;margin-top:18px;font-weight:600;cursor:pointer}
.check input{width:18px;height:18px;accent-color:var(--sea)}
.formula{margin-top:18px;padding:10px 14px;border-radius:8px;background:var(--tint);color:var(--ink);font:600 15px Consolas,Menlo,monospace}
button{font:inherit;font-weight:600;padding:11px 20px;border:1px solid transparent;border-radius:8px;cursor:pointer}
button:disabled{opacity:.45;cursor:not-allowed}
.actionRow{display:flex;gap:10px;flex-wrap:wrap;margin-top:20px}
.processBtn{background:var(--sea);color:#fff}
.processBtn:hover:not(:disabled){background:var(--sea-d)}
.downloadBtn{display:none;background:var(--ink);color:#fff}
.downloadBtn:hover,.zipDownloadBtn:hover{opacity:.88}
.zipDownloadBtn{display:none;background:var(--ink);color:#fff}
.clearBtn{background:transparent;color:var(--mut);border-color:var(--line)}
.clearBtn:hover{color:var(--ink);border-color:var(--mut)}
.info,.success,.error{margin-top:16px;padding:12px 14px;border-radius:8px}
.info{background:var(--tint)}
.success{background:var(--okbg);color:var(--ok)}
.error{background:var(--badbg);color:var(--bad)}
.result{margin-top:16px;padding:12px 14px;background:var(--paper);border:1px solid var(--line);border-radius:8px;font:13px/1.5 Consolas,Menlo,monospace;white-space:pre-wrap;max-height:260px;overflow:auto}
.result:empty{display:none}
#ciProgress{display:none;width:100%;height:14px;margin-top:16px;accent-color:var(--sea)}
#vdatumProgressContainer{display:none;margin-top:16px}
#vdatumProgressBar{width:100%;height:14px;accent-color:var(--sea)}
#vdatumProgressText{margin-top:4px;text-align:center;font-weight:600;font-size:.9rem}
#vdatumDownloadSection{display:none;margin-top:16px;padding:16px;border-radius:8px;background:var(--tint)}
#vdatumDownloadSection h3{margin:0 0 4px;font-size:1rem}
#vdatumDownloadButton{margin-top:0;background:var(--ink);color:#fff}
#vdatumSaveAsButton{display:none;margin-top:0;background:var(--ink);color:#fff}
#vdatumZipDownloadButton{margin-top:0}
#cvPreview{overflow-x:auto}
#cvPreview h3{margin:18px 0 6px;font-size:.95rem;color:var(--ink)}
#cvPreview table{width:100%;border-collapse:collapse;font-size:13px}
#cvPreview th,#cvPreview td{padding:6px 8px;border-bottom:1px solid var(--line);text-align:right}
#cvPreview th{color:var(--mut);font-weight:600}
.footer{display:flex;justify-content:flex-end;margin-top:4px}
button:focus-visible,select:focus-visible,input:focus-visible{outline:3px solid var(--sea);outline-offset:2px}
.file-picker-input{position:absolute!important;width:1px!important;height:1px!important;padding:0!important;margin:-1px!important;overflow:hidden!important;clip:rect(0,0,0,0)!important;white-space:nowrap!important;border:0!important}
.file-picker-label{display:inline-block;margin:0;padding:11px 20px;border-radius:8px;background:var(--ink);color:#fff;font-weight:600;cursor:pointer}
.file-picker-label:hover{opacity:.9}
.file-picker-label:focus-within{outline:3px solid var(--sea);outline-offset:2px}
@media(max-width:560px){.tab-button{padding:10px 12px;font-size:14px}.section{padding:16px}}

    .combine-file-row {
      display: flex;
      gap: 20px;
      margin-bottom: 12px;
      align-items: flex-end;
    }
    .combine-file-item {
      flex: 1;
      min-width: 0;
    }
    .combine-file-item label {
      display: block;
      margin-bottom: 6px;
    }
    .combine-file-item input[type="file"] {
      width: 100%;
      box-sizing: border-box;
    }
    @media (max-width: 700px) {
      .combine-file-row {
        flex-direction: column;
        gap: 10px;
        align-items: stretch;
      }
    }
/* ---- Water / Land Clip ---- */
.wc-grid{display:grid;grid-template-columns:1fr 1fr;gap:0 20px}
@media(max-width:700px){.wc-grid{grid-template-columns:1fr}}
.wc-details{margin-top:18px;border:1px solid var(--line);border-radius:8px;padding:10px 14px;background:#f8fbfd}
.wc-details summary{cursor:pointer;font-weight:600;color:var(--ink)}
.wc-details label{margin-top:12px}
#wcTol{width:100%;accent-color:var(--sea)}
#wcProgress{display:none;width:100%;height:14px;margin-top:16px;accent-color:var(--sea)}
#wcTools{display:none;margin-top:16px}
.wc-toolbar{display:flex;flex-wrap:wrap;gap:10px;align-items:center;margin-bottom:10px}
.wc-toolbar select{width:auto;flex:0 0 auto}
.wc-toolbar .clearBtn{padding:9px 14px}
.wc-toolbar-label{font-weight:600;font-size:.9rem;color:#2c4252}
.wc-seg{display:flex;flex-wrap:wrap;gap:4px;padding:4px;background:#dceef8;border:1px solid var(--line);border-radius:9px}
.wc-tool{padding:8px 14px;background:transparent;color:var(--ink);border-radius:6px;font-size:.9rem}
.wc-tool:hover{background:rgba(10,110,165,.10)}
.wc-tool.active{background:var(--sea);color:#fff}
.wc-chip{display:inline-block;width:14px;height:14px;border-radius:3px;border:1px solid #fff;vertical-align:-2px;margin-left:4px;background:#ccc}
#wcWrap{border:1px solid var(--line);border-radius:8px;overflow:auto;max-height:78vh;background:#fff}
#wcCv{display:block;margin:0 auto;cursor:crosshair;image-rendering:pixelated}
/* ---- Extract XYZ: XYZ -> Border ---- */
.bd-row{display:flex;gap:10px;align-items:stretch;flex-wrap:wrap}
.bd-row input{flex:1 1 220px;width:auto}
.bd-row .clearBtn{flex:0 0 auto}
#bdWrap{display:none;position:relative;margin-top:16px;border:1px solid var(--line);border-radius:8px;overflow:hidden;background:#fff}
#bdCv{display:block;width:100%;height:520px;cursor:grab;touch-action:none}
#bdLegend{position:absolute;left:10px;top:8px;padding:4px 9px;border-radius:6px;background:rgba(255,255,255,.88);color:var(--mut);font-size:12.5px}
#bdLegend i{display:inline-block;vertical-align:middle;margin:0 5px 0 10px}
#bdLegend i:first-child{margin-left:0}
#bdLegend i.pt{width:6px;height:6px;border-radius:3px;background:#9aa4ae}
#bdLegend i.ln{width:18px;height:3px;background:#d62828}
/* ---- Create Contours tab ---- */
.ct-layout{display:grid;grid-template-columns:minmax(300px,370px) 1fr;gap:16px;align-items:start}
@media(max-width:900px){.ct-layout{grid-template-columns:1fr}}
.ct-right{min-width:0}
.ct-h3{margin:24px 0 0;padding-bottom:6px;border-bottom:1px solid var(--line);font-size:.95rem;color:var(--ink)}
.ct-grid2{display:grid;grid-template-columns:1fr 1fr;gap:0 12px}
.ct-grid2>div{min-width:0}
#contourTab input[type=text]{width:100%;padding:10px 12px;font:inherit;font-size:15px;color:inherit;background:#fff;border:1px solid var(--line);border-radius:8px}
#contourTab input:disabled,#contourTab select:disabled{background:#f1f6f9;color:#8aa0ae}
#contourTab .check{margin-top:12px;font-weight:500}
.ct-swatch{width:100%;height:42px;padding:3px;border:1px solid var(--line);border-radius:8px;background:#fff}
.ct-settings .actionRow .processBtn{flex:1}
#ct_progress{height:7px;margin-top:14px;background:#dceef8;border-radius:6px;overflow:hidden}
#ct_bar{height:100%;width:0;background:var(--sea);transition:width .2s}
.ct-status{margin-top:14px;padding:12px 14px;border-radius:8px;background:var(--tint);color:var(--ink);font-size:.9rem;white-space:pre-wrap}
.ct-status.good{background:var(--okbg);color:var(--ok)}
.ct-status.bad{background:var(--badbg);color:var(--bad)}
#ct_viewWrap{position:relative;margin-top:12px;border:1px solid var(--line);border-radius:8px;overflow:hidden;background:#fbfcfd}
#ct_cv{display:block;width:100%;height:540px;cursor:grab;touch-action:none}
#ct_viewHint{position:absolute;left:8px;top:6px;padding:3px 8px;border-radius:6px;background:rgba(255,255,255,.88);color:var(--mut);font-size:12px}
#ct_summary{margin-top:16px}

/* ---- Create Contours: compact layout ---- */
#contourTab .ct-layout{grid-template-columns:1fr;gap:10px}
#contourTab .section{padding:12px 14px;margin-bottom:0}
#contourTab .section h2{font-size:1rem}
#contourTab .description{font-size:.8rem}
#contourTab label{margin:6px 0 2px;font-size:.76rem;line-height:1.25}
#contourTab input[type=number],#contourTab input[type=text],#contourTab select{height:28px;padding:3px 7px;font-size:13px;border-radius:5px}
#contourTab input[type=file]{width:auto;max-width:100%;padding:3px 6px;font-size:13px;border-radius:5px}
#contourTab input[type=file]::file-selector-button{padding:3px 10px;font-size:12px;border-radius:4px}
#contourTab .ct-h3{margin:0 0 2px;padding-bottom:3px;font-size:.84rem}
#contourTab .hint{margin:5px 0 0;font-size:.7rem;line-height:1.3}
#contourTab .check{margin-top:7px;gap:6px;font-size:.8rem}
#contourTab .check input{width:15px;height:15px}
#contourTab .ct-grid2{gap:0 8px;align-items:end}
#contourTab button{padding:6px 14px;font-size:13px;border-radius:6px}
#contourTab .actionRow{margin-top:10px;gap:8px}
#contourTab .ct-settings .actionRow .processBtn{flex:0 0 auto}
.ct-file-row{display:flex;flex-wrap:wrap;align-items:center;gap:8px}
.ct-groups,.ct-out{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:10px;margin-top:10px}
.ct-out{grid-template-columns:repeat(3,minmax(0,1fr));margin-top:6px}
.ct-group{min-width:0;padding:8px 10px;border:1px solid var(--line);border-radius:8px;background:#f8fbfd}
@media(max-width:900px){.ct-groups,.ct-out{grid-template-columns:repeat(2,minmax(0,1fr))}}
@media(max-width:520px){.ct-groups,.ct-out{grid-template-columns:1fr}}
#contourTab #ct_progress{height:5px;margin-top:8px}
#contourTab .ct-status{margin-top:8px;padding:6px 10px;font-size:.8rem}
#contourTab #ct_summary{margin-top:8px;padding:8px 10px;font-size:12px;max-height:150px}
</style>
</head>
<body>
<header class="top">
  <svg class="sky" viewBox="0 0 800 160" preserveAspectRatio="xMaxYMin slice" aria-hidden="true">
    <g fill="#fff" opacity=".85">
      <ellipse cx="600" cy="38" rx="46" ry="13"/><ellipse cx="632" cy="30" rx="30" ry="14"/><ellipse cx="572" cy="34" rx="26" ry="10"/>
      <ellipse cx="730" cy="78" rx="34" ry="9"/><ellipse cx="752" cy="72" rx="20" ry="10"/>
      <ellipse cx="430" cy="22" rx="30" ry="8" opacity=".7"/>
    </g>
    <circle cx="690" cy="26" r="16" fill="#fff6c9" opacity=".9"/>
  </svg>
  <div class="wrap"><h1>FREE HYDRO-CAD Tools</h1></div>
  <svg class="surf" viewBox="0 0 1440 46" preserveAspectRatio="none" aria-hidden="true">
    <path d="M0 22 C120 6 240 6 360 22 S600 38 720 22 S960 6 1080 22 S1320 38 1440 22 V46 H0 Z" fill="#5db9e6" opacity=".75"/>
    <path d="M0 30 C140 14 260 14 400 30 S640 46 780 30 S1020 14 1160 30 S1340 42 1440 30 V46 H0 Z" fill="#0a6ea5"/>
  </svg>
  <div class="sea"><div class="wrap">
    <nav class="tabs">
      <button class="tab-button active" onclick="openTab('vdatumTab', this)">VDATUM</button>
      <button class="tab-button" onclick="openTab('zAdjustTab', this)">Z Adjust</button>
      <button class="tab-button" onclick="openTab('combineXYZTab', this)">Combine XYZ</button>
      <button class="tab-button" onclick="openTab('cvTab', this)">Convert Data</button>
      <button class="tab-button" onclick="openTab('ciTab', this)">Convert Image</button>
      <button class="tab-button" onclick="openTab('mtxChnTab', this)">Extract XYZ</button>
      <button class="tab-button" onclick="openTab('contourTab', this)">Create Cont/Colors</button>
    </nav>
  </div></div>
</header>

<main>

<div id="vdatumTab" class="tab-content active">
  <div class="section">
    <h2>VDATUM Z Adjustment</h2>
    <p class="description">Matches each survey point to the nearest VDATUM point.</p>
    <label for="vdatumFile">VDATUM MLLW XYZ file in Elevation</label>
    <input type="file" id="vdatumFile" accept=".xyz,.txt">
    <div id="vdatumName" class="file-name">No VDATUM file selected</div>
    <label for="surveyFile">Survey NAVD88 XYZ files in Depth</label>
    <input type="file" id="surveyFile" class="file-picker-input" accept=".xyz,.txt" multiple>
    <label for="surveyFile" class="file-picker-label">Choose Files</label>
    <div id="surveyName" class="file-name">No survey files selected</div>
    <label class="check"><input type="checkbox" id="vdatumRound"> Round X Y to 2 decimals, Z to 1 decimal</label>
    <div class="formula">New Z = Survey Z + VDATUM Z</div>
    <div class="actionRow">
      <button id="vdatumProcessButton" class="processBtn">Process</button>
      <button id="vdatumDownloadButton" class="downloadBtn">Download</button>
      <button id="vdatumSaveAsButton" class="downloadBtn">Save As</button>
      <button id="vdatumZipDownloadButton" class="zipDownloadBtn">Download ZIP</button>
      <button id="vdatumRefreshButton" class="clearBtn">Clear</button>
    </div>
    <div id="vdatumProgressContainer">
      <progress id="vdatumProgressBar" value="0" max="100"></progress>
      <div id="vdatumProgressText">0%</div>
    </div>
    <div id="vdatumStatus" class="result"></div>
    <div id="vdatumDownloadSection">
      <div id="vdatumOutputFileName" class="file-name"></div>
    </div>
  </div>
</div>

<div id="zAdjustTab" class="tab-content">
  <div class="section">
    <h2>Z Adjust / Invert</h2>
    <p class="description">Shift, invert and round Z values.</p>
    <label for="zAdjustFile">XYZ/TXT files in Depth</label>
    <input type="file" id="zAdjustFile" class="file-picker-input" accept=".txt,.xyz" multiple>
    <label for="zAdjustFile" class="file-picker-label">Choose Files</label>
    <p id="zAdjustFileNames" class="file-name">No files selected</p>
    <label for="zAdjustment">Z adjustment</label>
    <input type="number" id="zAdjustment" value="0" step="0.01" placeholder="1.5 or -2.2">
    <p class="hint">Positive adds, negative subtracts.</p>
    <label class="check"><input type="checkbox" id="invertZAdjust"> Invert Z values</label>
    <label class="check"><input type="checkbox" id="zRound" checked> Round X Y to 2 decimals, Z to 1 decimal</label>
    <div class="actionRow">
      <button id="zProcessBtn" class="processBtn">Process</button>
      <button id="zDownloadBtn" class="downloadBtn">Download</button>
      <button id="zDownloadZipBtn" class="zipDownloadBtn">Download ZIP</button>
    </div>
    <div id="zStatus"></div>
    <div id="zResult" class="result"></div>
  </div>
</div>

<div id="combineXYZTab" class="tab-content">
  <div class="section">
    <h2>Combine XYZ</h2>
    <p class="description">Choose files using the six individual slots or use Choose Files to select many XYZ files at once. Files are combined in selection order.</p>

    <div class="actionRow" style="margin-top:14px">
      <input type="file" id="combineManyFiles" class="file-picker-input" accept=".xyz,.txt,.csv,.pts,.dat" multiple>
      <label for="combineManyFiles" class="file-picker-label">Choose Files</label>
    </div>
    <p id="combineManyFileNames" class="file-name">No additional files selected</p>

    <div class="combine-file-row">
      <div class="combine-file-item">
        
        <input type="file" id="combineFile1" accept=".xyz,.txt,.csv,.pts,.dat">
      </div>
      <div class="combine-file-item">
        
        <input type="file" id="combineFile4" accept=".xyz,.txt,.csv,.pts,.dat">
      </div>
    </div>

    <div class="combine-file-row">
      <div class="combine-file-item">
        
        <input type="file" id="combineFile2" accept=".xyz,.txt,.csv,.pts,.dat">
      </div>
      <div class="combine-file-item">
        
        <input type="file" id="combineFile5" accept=".xyz,.txt,.csv,.pts,.dat">
      </div>
    </div>

    <div class="combine-file-row">
      <div class="combine-file-item">
        
        <input type="file" id="combineFile3" accept=".xyz,.txt,.csv,.pts,.dat">
      </div>
      <div class="combine-file-item">
        
        <input type="file" id="combineFile6" accept=".xyz,.txt,.csv,.pts,.dat">
      </div>
    </div>

    <label class="check"><input type="checkbox" id="combineRemoveOverlap"> Remove overlap points</label>
    <div id="combineOverlapMethods" style="margin:10px 0 0 28px;padding:12px 14px;background:#eef6fb;border:1px solid #cfe1ec;border-radius:8px">
      <label class="check" style="margin-top:0"><input type="radio" name="combineOverlapMethod" id="combineOverlapMinimum" value="minimum" checked> 1. Remove overlap points - Z minimum (shallowest, closest to zero)</label>
      <label class="check"><input type="radio" name="combineOverlapMethod" id="combineOverlapAverage" value="average"> 2. Remove overlap points - Z average</label>
      <label class="check"><input type="radio" name="combineOverlapMethod" id="combineOverlapSecond" value="second"> 3. Remove overlap points - Z second file</label>
      <label for="combineOverlapDistance" style="margin-top:14px">Overlap distance (ft)</label>
      <input type="number" id="combineOverlapDistance" min="0" step="0.01" placeholder="Automatic (average point spacing of the first file)">
    </div>
    <p class="hint">A point of a later file is an overlap when it lies within the overlap distance of a point of the first file. By default the distance is the average spacing between neighbouring points of the first file (the average closest-point distance), so it adapts to the survey density. Overlapping points of the later file are removed, and the first file's XY coordinates are never changed. Each first-file point that has a later-file point within that distance takes: <b>1.</b> the shallower Z (closest to zero) of the two points, <b>2.</b> the average Z of the two points, or <b>3.</b> the later file's Z. Later-file points outside the overlap are kept.</p>

    <label for="combineZAdjustment">Z adjustment</label>
    <input type="number" id="combineZAdjustment" value="0" step="0.01" placeholder="1.5 or -2.2">
    <p class="hint">Positive adds, negative subtracts.</p>
    <label class="check"><input type="checkbox" id="combineInvertZ"> Invert Z values</label>
    <label class="check"><input type="checkbox" id="combineRound" checked> Round XY to 2 decimals, Z to 1 decimal</label>

    <div class="actionRow">
      <button id="combineProcessBtn" class="processBtn">Process</button>
      <button id="combineDownloadBtn" class="downloadBtn">Download XYZ</button>
    </div>

    <div id="combineStatus"></div>
  </div>
</div>

<div id="cvTab" class="tab-content">
  <nav class="convert-sub-tabs" aria-label="Convert Data tools">
    <button type="button" class="convert-sub-button active" onclick="openConvertSubTab('convertXYZPane', this)">Convert XYZ</button>
    <button type="button" class="convert-sub-button" onclick="openConvertSubTab('convertRAWPane', this)">Convert RAW</button>
    <button type="button" class="convert-sub-button" onclick="openConvertSubTab('convertHSXPane', this)">Convert HSX</button>
  </nav>
  <div id="convertXYZPane" class="convert-sub-content active">
  <div class="section">
    <h2>Convert XYZ</h2>
    <p class="description">NAD83, US survey feet. Z is unchanged.</p>
    <label for="cvDir">Conversion</label>
    <select id="cvDir">
      <option value="NJ>NYLI">NJ 2900 &rarr; NY Long Island 3104</option>
      <option value="SAME">No Selection — Keep Same Coordinates</option>
      <option value="NYLI>NJ">NY Long Island 3104 &rarr; NJ 2900</option>
      <option value="NJ>NYE">NJ 2900 &rarr; NY East 3101</option>
      <option value="NYE>NJ">NY East 3101 &rarr; NJ 2900</option>
      <option value="NYE>NYLI">NY East 3101 &rarr; NY Long Island 3104</option>
      <option value="NYLI>NYE">NY Long Island 3104 &rarr; NY East 3101</option>
    </select>
    <p id="cvNote" class="hint" style="display:none">Same projection, so X Y stay the same.</p>
    <label for="cvFile">Input files</label>
    <input type="file" id="cvFile" class="file-picker-input" accept=".txt,.xyz,.csv,.pts,.dat" multiple>
    <label for="cvFile" class="file-picker-label">Choose Files</label>
    <p id="cvFileNames" class="file-name">No files selected</p>
    <label class="check"><input type="checkbox" id="cvRound"> Round X Y to 2 decimals, Z to 1 decimal</label>
    <p class="hint">Columns are detected automatically. Projection only; no datum shift applied.</p>
    <div class="actionRow">
      <button id="cvConvertBtn" class="processBtn" disabled>Convert All</button>
      <button id="cvDownloadBtn" class="downloadBtn">Download</button>
      <button id="cvDownloadZipBtn" class="zipDownloadBtn">Download ZIP</button>
    </div>
    <div id="cvStatus"></div>
    <div id="cvPreview"></div>
  </div>

  </div>
  <div id="convertRAWPane" class="convert-sub-content">
  <div class="section">
    <h2>Convert RAW</h2>
    <p class="description">Convert HYPACK RAW navigation coordinates between the same six NAD83 State Plane options. Z and survey measurements are unchanged.</p>
    <label for="rawDir">Conversion</label>
    <select id="rawDir">
      <option value="NJ>NYLI">NJ 2900 &rarr; NY Long Island 3104</option>
      <option value="NYLI>NJ">NY Long Island 3104 &rarr; NJ 2900</option>
      <option value="NJ>NYE">NJ 2900 &rarr; NY East 3101</option>
      <option value="NYE>NJ">NY East 3101 &rarr; NJ 2900</option>
      <option value="NYE>NYLI">NY East 3101 &rarr; NY Long Island 3104</option>
      <option value="NYLI>NYE">NY Long Island 3104 &rarr; NY East 3101</option>
    </select>
    <label for="rawFile">RAW files</label>
    <input type="file" id="rawFile" class="file-picker-input" accept=".raw" multiple>
    <label for="rawFile" class="file-picker-label">Choose Files</label>
    <p id="rawFileNames" class="file-name">No files selected</p>
    <label class="check"><input type="checkbox" id="rawRound"> Round X Y to 2 decimals, Z to 1 decimal</label>
    <div class="actionRow">
      <button id="rawConvertBtn" class="processBtn" disabled>Convert All RAW</button>
      <button id="rawDownloadBtn" class="downloadBtn">Download</button>
      <button id="rawDownloadZipBtn" class="zipDownloadBtn">Download ZIP</button>
    </div>
    <div id="rawStatus"></div>
  </div>

  </div>
  <div id="convertHSXPane" class="convert-sub-content">
  <div class="section">
    <h2>Convert HSX</h2>
    <p class="description">Convert HYPACK HSX navigation coordinates between the same six NAD83 State Plane options. Soundings and other measurements are unchanged.</p>
    <label for="hsxDir">Conversion</label>
    <select id="hsxDir">
      <option value="NJ>NYLI">NJ 2900 &rarr; NY Long Island 3104</option>
      <option value="NYLI>NJ">NY Long Island 3104 &rarr; NJ 2900</option>
      <option value="NJ>NYE">NJ 2900 &rarr; NY East 3101</option>
      <option value="NYE>NJ">NY East 3101 &rarr; NJ 2900</option>
      <option value="NYE>NYLI">NY East 3101 &rarr; NY Long Island 3104</option>
      <option value="NYLI>NYE">NY Long Island 3104 &rarr; NY East 3101</option>
    </select>
    <label for="hsxFile">HSX files</label>
    <input type="file" id="hsxFile" class="file-picker-input" accept=".hsx" multiple>
    <label for="hsxFile" class="file-picker-label">Choose Files</label>
    <p id="hsxFileNames" class="file-name">No files selected</p>
    <label class="check"><input type="checkbox" id="hsxRound"> Round X Y to 2 decimals, Z to 1 decimal</label>
    <div class="actionRow">
      <button id="hsxConvertBtn" class="processBtn" disabled>Convert All HSX</button>
      <button id="hsxDownloadBtn" class="downloadBtn">Download</button>
      <button id="hsxDownloadZipBtn" class="zipDownloadBtn">Download ZIP</button>
    </div>
    <div id="hsxStatus"></div>
  </div>
  </div>
</div>

<div id="ciTab" class="tab-content">
  <nav class="convert-sub-tabs" aria-label="Convert Image tools">
    <button type="button" class="convert-sub-button active" onclick="openConvertSubTab('ciGeoPane', this)">Re-georeference</button>
    <button type="button" class="convert-sub-button" onclick="openConvertSubTab('ciClipPane', this)">Water / Land Clip</button>
    <button type="button" class="convert-sub-button" onclick="openConvertSubTab('ciGoogPane', this)">GeoRef Google Image</button>
  </nav>
  <div id="ciGeoPane" class="convert-sub-content active">
  <div class="section">
    <h2>Convert Image</h2>
    <p class="description">Re-georeference a TIFF using embedded GeoTIFF georeferencing or an optional TFW. NAD83, US survey feet.</p>
    <label for="ciDir">Conversion</label>
    <select id="ciDir">
      <option value="SAME" selected>No Selection — Keep Same Coordinates</option>
      <option value="NYLI>NJ">NY Long Island 3104 &rarr; NJ 2900</option>
      <option value="NJ>NYLI">NJ 2900 &rarr; NY Long Island 3104</option>
      <option value="NYLI>NYE">NY Long Island 3104 &rarr; NY East 3101</option>
      <option value="NYE>NYLI">NY East 3101 &rarr; NY Long Island 3104</option>
      <option value="NJ>NYE">NJ 2900 &rarr; NY East 3101</option>
      <option value="NYE>NJ">NY East 3101 &rarr; NJ 2900</option>
    </select>
    <label for="ciImg">Image (TIF, JPG, PNG, BMP, GIF, WebP)</label>
    <input type="file" id="ciImg" accept=".tif,.tiff,.jpg,.jpeg,.png,.bmp,.gif,.webp,image/*">
    <label for="ciTfw">World file (TFW / JGW / PGW / WLD) — optional for TIFF with GeoTIFF tags, required for JPG / PNG</label>
    <input type="file" id="ciTfw" accept=".tfw,.wld,.jgw,.jpgw,.pgw,.pngw,.bpw,.gfw,.txt">
    <p class="hint">If the TIFF contains embedded GeoTIFF georeferencing, no TFW is required. The embedded CRS is detected automatically. JPG / PNG / BMP images are converted to TIFF inside your browser first and need their world file.</p>
    <label for="ciMode">Output</label>
    <select id="ciMode">
      <option value="rot">Rotated TFW + NEW TIFF</option>
      <option value="north">North-up image + TFW (resampled)</option>
      <option value="geotiff">GeoTIFF (embedded georeferencing, no TFW)</option>
    </select>
    <div class="actionRow">
      <button id="ciConvertBtn" class="processBtn" disabled>Convert</button>
      <button id="ciDlTfw" class="downloadBtn">Download TFW</button>
      <button id="ciDlTif" class="downloadBtn">Download TIF</button>
      <button id="ciDlGeo" class="downloadBtn">Download GeoTIFF</button>
    </div>
    <progress id="ciProgress" value="0" max="100"></progress>
    <div id="ciStatus"></div>
    <div id="ciResult" class="result"></div>
  </div>
  </div>
  <div id="ciClipPane" class="convert-sub-content">
  <div class="section">
    <h2>Water / Land Clip</h2>
    <p class="description">Find the water in an ortho image, check and correct it, then download a clipped TIFF and matching TFW. Runs fully in your browser.</p>
    <div class="wc-grid">
      <div><label for="wcTif">Image (TIF, JPG, PNG, BMP, GIF, WebP)</label><input type="file" id="wcTif" accept=".tif,.tiff,.jpg,.jpeg,.png,.bmp,.gif,.webp,image/*"></div>
      <div><label for="wcTfw">World file (TFW / JGW / PGW / WLD) — optional</label><input type="file" id="wcTfw" accept=".tfw,.tifw,.wld,.tiffw,.jgw,.jpgw,.pgw,.pngw,.bpw,.gfw,.txt"></div>
      <div><label for="wcKeep">Keep</label><select id="wcKeep"><option value="land">Land only (remove water)</option><option value="water">Water only (remove land)</option></select></div>
      <div><label for="wcBg">Removed area</label><select id="wcBg"><option value="alpha">Transparent (RGBA)</option><option value="black">Black, marked as no-data (RGB)</option></select></div>
      <div><label for="wcComp">TIFF compression</label><select id="wcComp"><option value="lzw">LZW (works in most programs)</option><option value="deflate">Deflate (smaller file)</option><option value="none">None (largest, most compatible)</option></select></div>
    </div>
    <p class="hint">If the TIFF contains embedded GeoTIFF georeferencing, no TFW is required.</p>
    <details class="wc-details" open><summary>Detection settings</summary>
      <div class="wc-grid">
        <div style="grid-column:1/-1"><label for="wcPreset">Method (choose Custom to show all the settings)</label>
          <select id="wcPreset">
            <option value="auto">Auto – recommended (finds shaded water too)</option>
            <option value="strict">Strict – only clear, evenly coloured water</option>
            <option value="shaded">Shaded / dark water between piers and shores</option>
            <option value="smooth">Smooth – clean, rounded outline</option>
            <option value="fine">Fine detail – keeps small docks, narrow gaps</option>
            <option value="aggressive">Aggressive – remove as much water as possible (may eat some land)</option>
            <option value="custom">Custom (your own settings – shows all sliders)</option>
          </select>
          <p class="hint">If water is left behind, try <b>Shaded</b> or <b>Aggressive</b>. If land is being removed, try <b>Strict</b> or lower the tolerance.</p></div>
        <div style="grid-column:1/-1"><label for="wcInland">Which water to remove</label><select id="wcInland"><option value="main" selected>Only water connected to the main water body (sea / river) – keep separate inland ponds and lakes</option><option value="all">All water, including separate ponds and lakes</option></select><p class="hint">A pond or lake that is not connected to the main water (and does not reach the image edge) is kept as land.</p></div>
        <div id="wcCustomBox" style="display:none;grid-column:1/-1"><div class="wc-grid">
        <div><label for="wcTol">Water colour tolerance: <span id="wcTolV">1.15</span></label><input id="wcTol" type="range" min="0.5" max="2.5" step="0.05" value="1.15"><p class="hint">Higher catches shaded or muddy water; lower avoids dark land.</p></div>
        <div><label for="wcGrow">Grow into shaded water: <span id="wcGrowV">2.5</span></label><input id="wcGrow" type="range" min="0" max="4" step="0.1" value="2.5"><p class="hint">Spreads from sure water into darker water next to it (shadows, channels between terminals). 0 = off.</p></div>
        <div><label for="wcTex">Texture limit: <span id="wcTexV">6</span></label><input id="wcTex" type="range" min="2" max="20" step="0.5" value="6"><p class="hint">Water is smooth. Raise it for rough or wavy water; lower to keep busy land.</p></div>
        <div><label for="wcLuma">Brightness sensitivity: <span id="wcLumaV">1.00</span></label><input id="wcLuma" type="range" min="0" max="1.5" step="0.05" value="1"><p class="hint">Lower = accept darker or lighter water of the same colour.</p></div>
        <div><label for="wcClasses">Water colours to look for</label><select id="wcClasses"><option value="1">1 – single water colour</option><option value="2">2 colours</option><option value="3" selected>3 colours</option><option value="4">4 colours</option></select><p class="hint">Use more when the water has deep, shallow and shaded tones.</p></div>
        <div><label><input type="checkbox" id="wcHue" checked> Blue / green water only</label><p class="hint">Ignores grey, brown and red areas, so roofs and ships are not mistaken for water.</p></div>
        <div><label for="wcOpen">Remove specks / thin lines (size): <span id="wcOpenV">1</span></label><input id="wcOpen" type="range" min="0" max="4" step="1" value="1"><p class="hint">Higher removes boat wakes, thin streaks and noise.</p></div>
        <div><label for="wcShore">Shore adjust (pixels): <span id="wcShoreV">0</span></label><input id="wcShore" type="range" min="-4" max="4" step="1" value="0"><p class="hint">+ moves the water edge toward land (removes a leftover dark rim); − moves it toward the water.</p></div>
        <div><label for="wcEdge">Edge smoothness: <span id="wcEdgeV">1</span></label><input id="wcEdge" type="range" min="0" max="4" step="1" value="1"><p class="hint">0 = sharp pixel edge, higher = softer shoreline.</p></div>
        <div><label for="wcMinW">Ignore water patches smaller than (sq ft)</label><input id="wcMinW" type="number" min="0" step="1000" value="20000"><p class="hint">Removes dark roofs, roads or shadows that look like water.</p></div>
        <div><label for="wcFill">Fill gaps inside water smaller than (sq ft)</label><input id="wcFill" type="number" min="0" step="100" value="500"><p class="hint">Glare, buoys and small boats. Docks and piers stay land.</p></div>
        </div></div>
      </div>
    </details>
    <div class="actionRow">
      <button id="wcDetect" class="processBtn" disabled>Detect water</button>
      <button id="wcDlTif" class="downloadBtn">Download TIF</button>
      <button id="wcDlTfw" class="downloadBtn">Download TFW</button>
    </div>
    <progress id="wcProgress" value="0" max="100"></progress>
    <div id="wcStatus"><div class="info">Choose a TIFF file to begin.</div></div>
    <div id="wcTools">
      <div class="wc-toolbar">
        <span class="wc-toolbar-label">Click on the preview to</span>
        <div class="wc-seg" role="group" aria-label="Correction tool">
          <button type="button" class="wc-tool active" data-tool="remove">Remove wrong water</button>
          <button type="button" class="wc-tool" data-tool="add">Add missed water</button>
          <button type="button" class="wc-tool" data-tool="pick">Pick water colour <span id="wcChip" class="wc-chip"></span></button>
        </div>
      </div>
      <div class="wc-toolbar">
        <select id="wcView"><option value="overlay">Show water in blue</option><option value="result">Show clipped result</option></select>
        <select id="wcZoom"><option value="1">Fit</option><option value="2">Zoom 2×</option><option value="4">Zoom 4×</option></select>
        <button type="button" id="wcUndo" class="clearBtn" disabled>Undo last click</button>
        <button type="button" id="wcClearEd" class="clearBtn" disabled>Clear corrections</button>
      </div>
      <div id="wcWrap"><canvas id="wcCv"></canvas></div>
      <p class="hint">Red dots = removed patches, green = added water. Undo removes the last click.</p>
    </div>
  </div>
  </div>
  <div id="ciGoogPane" class="convert-sub-content">
<style>
#gsRoot{--bg:#eef5fb;--card:#fff;--ink:#12324a;--mut:#5b7488;--line:#cfdde9;--acc:#0b6fb8;color:var(--ink);font:14px/1.45 system-ui,Segoe UI,Arial,sans-serif}
#gsRoot .gs-card{background:#fff;border:1px solid var(--line);border-radius:10px;padding:14px;margin-bottom:12px}
#gsRoot h2{font-size:15px;margin:0 0 8px}
#gsRoot label{display:block;margin:8px 0 3px;color:var(--mut);font-size:12px}
#gsRoot input,#gsRoot select{width:100%;padding:7px;border:1px solid var(--line);border-radius:6px;font:inherit;background:#fff;color:var(--ink)}
#gsRoot button{background:var(--acc);color:#fff;border:0;border-radius:6px;padding:9px 14px;font:inherit;cursor:pointer;margin:10px 6px 0 0}
#gsRoot button.s{background:#e3eef7;color:var(--ink)}
#gsRoot button[disabled]{opacity:.45;cursor:default}
#gsRoot canvas{max-width:100%;border:1px solid var(--line);border-radius:6px;background:#dde7ef}
#gsRoot #gs_pk{max-width:none}
#gsRoot .gs-2{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:700px){#gsRoot .gs-2{grid-template-columns:1fr}}
#gsRoot .gs-hint{font-size:12px;color:var(--mut);margin:6px 0 0}
#gsRoot .gs-grid{display:grid;grid-template-columns:50px 1fr 1fr 52px 1.4fr 1.4fr 64px;gap:5px;align-items:center;font-size:12px;color:var(--mut)}
#gsRoot .gs-grid input{margin:0;padding:5px}
#gsRoot .gs-grid button{margin:0;padding:5px 6px}
#gsRoot .gs-act{background:#fff8d6;outline:2px solid #f2c200;border-radius:4px}
#gsMsg{margin-top:8px;font-size:13px;color:var(--mut);white-space:pre-line}

</style>
<div id="gsRoot">
<div class="gs-card"><h2>1. Picture from Google Earth</h2>
<input type="file" id="gs_img" accept=".jpg,.jpeg,.png,.tif,.tiff,image/*">
<p class="gs-hint">Save the image in Google Earth Pro with your placemarks (A, B, C…) visible. A straight-down view (press <b>U</b>) gives the best result.</p></div>
<div class="gs-card"><h2>2. Points (placemarks) and their real coordinates</h2>
<div class="gs-2"><div><label>Placemarks file (.kmz / .kml) – optional, fills the coordinates</label><input type="file" id="gs_kml" accept=".kml,.kmz"></div>
<div><label>Coordinates of the points are in</label><select id="gs_ctype"><option value="ll">Latitude / Longitude</option><option value="nyli">NY Long Island 3104 (US ft)</option><option value="nye">NY East 3101 (US ft)</option><option value="nj">NJ 2900 (US ft)</option></select></div></div>
<p class="gs-hint">Type your <b>real (survey) coordinates</b> for each point, or load the placemarks file. Then mark each point on the picture: <b>Find pins</b> does it automatically, or click the tip of each placemark on the picture (zoom in with the zoom box).</p>
<div id="gs_rows" style="margin-top:8px"></div>
<button class="s" id="gs_add">+ Add point</button><button class="s" id="gs_del">− Remove last</button><button id="gs_find">Find pins in picture</button>
<div class="gs-2"><div><label>Zoom</label><select id="gs_zoom"><option value="1">Fit to width</option><option value="2">2×</option><option value="4">4×</option><option value="8">8×</option></select></div><div><label>Next click sets</label><div id="gs_now" style="font-weight:700;font-size:17px;padding:4px 0">–</div></div></div>
<div id="gs_wrap" style="max-height:520px;overflow:auto;border:1px solid var(--line);border-radius:6px;margin-top:6px;background:#dde7ef"><canvas id="gs_pk" width="10" height="10" style="cursor:crosshair;border:0;border-radius:0"></canvas></div></div>
<div class="gs-card"><h2>3. Georeference</h2>
<div class="gs-2"><div><label>How to fit the picture</label><select id="gs_fit"><option value="sim">Rotate + scale + shift only (keeps the picture shape) – recommended</option><option value="auto">Also correct distortion (5+ points, automatic)</option></select></div><div><label>Output coordinate system</label><select id="gs_zone"><option value="nyli">NY Long Island 3104 (US ft)</option><option value="nye">NY East 3101 (US ft)</option><option value="nj">NJ 2900 (US ft)</option></select></div></div>
<button id="gs_go">Georeference</button><button class="s" id="gs_clear">Clear all</button>
<div id="gs_info" style="margin-top:8px;font-size:13px"></div><div id="gsMsg"></div>
<canvas id="gs_cv" width="640" height="360" style="width:100%;margin-top:8px"></canvas>
<div><button id="gs_d1" disabled>Download GeoTIFF</button><button class="s" id="gs_d2" disabled>Download TIFF + TFW + PRJ</button></div></div>
</div>
  </div>
</div>

<div id="mtxChnTab" class="tab-content">
  <div class="section">
    <h2>Extract XYZ</h2>
    <p class="description">Choose an extraction type: MTX corners, CHN nodes, channel DXF nodes, Google KML/KMZ line nodes converted to NYLI feet, contour DXF vertices, HYPACK sounding DXF points, or an outer border (.brd/.dxf) traced around XYZ points.</p>

    <label for="extractType">Extraction</label>
    <select id="extractType">
      <option value="mtx">MTX &rarr; Four Corner XYZ</option>
      <option value="chn">CHN &rarr; XYZ Nodes</option>
      <option value="dxf">DXF chn---&gt;XYZ nodes</option>
      <option value="googleLines">Google Lines ----&gt; XYZ nodes (NYLI)</option>
      <option value="contourDxf">Contour DXF ---&gt;XYZ Points</option>
      <option value="soundingDxf">Sounding DXF ---&gt;XYZ Points</option>
      <option value="border">XYZ ----&gt; Border .brd/.dxf</option>
    </select>

    <div id="extractStdPanel">
    <div id="mtxZRow">
      <label for="extractMtxZ">Corner Z</label>
      <input type="number" id="extractMtxZ" value="0" step="0.1">
    </div>

    <label for="extractFile">File</label>
    <input type="file" id="extractFile" accept=".mtx,.txt">
    <div id="extractFileName" class="file-name">No file selected</div>

    <div class="actionRow">
      <button id="extractProcessBtn" class="processBtn" disabled>Process</button>
      <button id="extractDownloadBtn" class="downloadBtn">Download XYZ</button>
      <button id="extractClearBtn" class="clearBtn">Clear</button>
    </div>

    <div id="extractStatus"></div>
    <div id="extractResult" class="result"></div>
    </div>
    <div id="bdPanel" style="display:none">
      <label for="bdFile">XYZ file</label>
      <input type="file" id="bdFile" accept=".xyz,.txt,.csv,.pts,.dat">
      <div id="bdFileName" class="file-name">No file selected</div>
      <label for="bdMax">Maximum line segment length (ft)</label>
      <div class="bd-row"><input type="number" id="bdMax" min="0.01" step="0.1" placeholder="Blank = automatic"><button type="button" id="bdUseAuto" class="clearBtn" disabled>Use automatic value</button></div>
      <p class="hint">Blank = automatic, calculated from your point spacing (usually 1–3× the average spacing). Smaller hugs the data more tightly into bays and gaps; larger gives a smoother outline. The border only uses real survey points, never crosses itself and never cuts through narrow channels.</p>
      <div class="actionRow">
        <button id="bdProcessBtn" class="processBtn" disabled>Create border</button>
        <button id="bdDlBrd" class="downloadBtn">Download BRD</button>
        <button id="bdDlDxf" class="downloadBtn">Download DXF</button>
        <button id="bdClearBtn" class="clearBtn">Clear</button>
      </div>
      <div id="bdStatus"></div>
      <div id="bdResult" class="result"></div>
      <div id="bdWrap"><canvas id="bdCv"></canvas><div id="bdLegend"><i class="pt"></i>survey points<i class="ln"></i>border · scroll to zoom, drag to pan, double-click to fit</div></div>
    </div>
  </div>
</div>

<div id="contourTab" class="tab-content">
  <nav class="convert-sub-tabs" aria-label="Create Cont/Colors tools">
    <button type="button" class="convert-sub-button active" onclick="openConvertSubTab('ctPane', this)">Create contours</button>
    <button type="button" class="convert-sub-button" onclick="openConvertSubTab('cbPane', this)">Create Color Bars</button>
  </nav>
  <div id="ctPane" class="convert-sub-content active">
  <div class="ct-layout">
  <div class="section ct-settings">
    <h2>Create Contours</h2>
    <p class="description">TIN model contours from XYZ survey points, with smoothed-TIN contouring and labeled DXF output. Runs offline.</p>

    <label for="ct_file">XYZ file</label>
    <input type="file" id="ct_file" accept=".xyz,.txt,.csv,.asc,.pts,.dat">

    <div class="ct-groups">
    <div class="ct-group">
    <h3 class="ct-h3">TIN model</h3>
    <div class="ct-grid2">
      <div><label for="ct_maxEdge">Max triangle side (ft)</label><input type="number" id="ct_maxEdge" min="0" step="1" placeholder="Auto"></div>
      <div><label for="ct_trim">Remove long triangles</label><select id="ct_trim"><option value="all" selected>Everywhere (HYPACK style)</option><option value="outer">Outer edge only</option><option value="none">Keep all (convex)</option></select></div>
    </div>
    <p class="hint">Blank = automatic, from your point spacing. Longer triangles are removed so contours are not drawn across gaps.</p>

    </div>
    <div class="ct-group">
    <h3 class="ct-h3">Contours</h3>
    <div class="ct-grid2">
      <div><label for="ct_step">Contour interval (ft)</label><input type="number" id="ct_step" min="0.01" step="0.1" value="1"></div>
      <div><label for="ct_major">Major contour every</label><input type="number" id="ct_major" min="0" step="1" value="5"></div>
    </div>
    <label for="ct_customLevels">Custom values</label>
    <input type="text" id="ct_customLevels" placeholder="e.g. 3 7 9 3.5" title="Draw contours only at these Z values, separated by spaces. Blank = use the contour interval.">
    <p class="hint">Blank = contours at every interval. Values are Z as in the file.</p>
    <label for="ct_exportType">Export type</label>
    <select id="ct_exportType"><option value="3d">3D Contour (elevation on vertices)</option><option value="2d">2D Contour (flat polylines)</option></select>

    </div>
    <div class="ct-group">
    <h3 class="ct-h3">Smoothing</h3>
    <label for="ct_preset">Smoothing preset</label>
    <select id="ct_preset"><option value="none">None — raw linear TIN</option><option value="light">Light</option><option value="medium" selected>Medium (recommended)</option><option value="strong">Strong</option><option value="custom">Custom</option></select>
    <div class="ct-grid2">
      <div><label for="ct_subdiv">TIN smoothing level</label><select id="ct_subdiv"><option value="1">0 – off (linear)</option><option value="2">1</option><option value="3">2</option><option value="4">3</option><option value="6">4</option><option value="8">5</option></select></div>
      <div><label for="ct_noise">Noise filter radius (ft)</label><input type="number" id="ct_noise" min="0" step="0.5"></div>
      <div><label for="ct_passes">Line smoothing passes</label><select id="ct_passes"><option>0</option><option>1</option><option>2</option><option>3</option><option>4</option></select></div>
      <div><label for="ct_tol">Simplify tolerance (ft)</label><input type="number" id="ct_tol" min="0" step="0.01"></div>
    </div>
    <label for="ct_minLoop">Remove closed contours shorter than (ft)</label>
    <input type="number" id="ct_minLoop" min="0" step="1" value="0">
    <p class="hint">The noise filter slightly rounds off small shoals; check critical depths.</p>

    </div>
    <div class="ct-group">
    <h3 class="ct-h3">Export</h3>
    <label class="check"><input type="checkbox" id="ct_contours" checked> Export contours and labels</label>
    <label class="check"><input type="checkbox" id="ct_boundary"> Export TIN boundary</label>
    <label for="ct_hcf">Colour file (HYPACK .hcf)</label>
    <input type="file" id="ct_hcf" accept=".hcf,.txt">
    <div id="ct_hcfBar" style="display:none;height:9px;margin-top:5px;border-radius:3px;border:1px solid var(--line)"></div>
    <p class="hint" id="ct_hcfInfo">Optional. Gives each contour layer the colour for its Z value. Without it: minor white/black, major red.</p>
    </div>
    </div>

    <div class="actionRow">
      <button id="ct_generate" class="processBtn" disabled>Generate contours</button>
    </div>
    <div id="ct_progress"><div id="ct_bar"></div></div>
    <div id="ct_status" class="ct-status">Choose an XYZ file to begin.</div>
  </div>

  <div class="ct-right">
  <div class="section">
    <h2>Output options &amp; download</h2>
    <div class="ct-out">
    <div class="ct-group">
      <h3 class="ct-h3">File</h3>
      <label for="ct_outName">File name</label>
      <input type="text" id="ct_outName" value="contours" maxlength="80">
      <p class="hint">".dxf" is added automatically. AutoCAD R12 ASCII DXF — opens in AutoCAD, BricsCAD, HYPACK, Global Mapper, QGIS and most CAD programs.</p>
    </div>
    <div class="ct-group">
      <h3 class="ct-h3">Labels</h3>
      <label for="ct_labelMode">Label</label>
      <select id="ct_labelMode"><option value="all" selected>All contours</option><option value="major">Major contours only</option><option value="custom">Custom values</option><option value="none">No labels (lines not broken)</option></select>
      <div class="ct-grid2">
        <div><label for="ct_labelSpacing">Spacing along line (ft)</label><input type="number" id="ct_labelSpacing" min="1" step="1" value="200"></div>
        <div><label for="ct_labelHeight">Text height</label><input type="number" id="ct_labelHeight" min="0.1" step="0.1" value="3"></div>
        <div><label for="ct_decimals">Decimals</label><select id="ct_decimals"><option>0</option><option selected>1</option><option>2</option><option>3</option></select></div>
        <div><label for="ct_labelGap">Gap under label (ft)</label><input type="number" id="ct_labelGap" min="0" step="0.5" value="10"></div>
      </div>
      <div class="ct-grid2">
        <div><label class="check"><input type="checkbox" id="ct_labelsOnLine" checked> Place labels on the line and break the line under the text</label></div>
        <div><label for="ct_labelValues">Custom</label><input type="text" id="ct_labelValues" placeholder="e.g. 2 5 5.5 7 27" title="Contour values to label, separated by spaces. Blank = all contours."></div>
      </div>
    </div>
    <div class="ct-group">
      <h3 class="ct-h3">Values</h3>
      <div class="ct-grid2">
        <div><label for="ct_zSign">Elevation sign</label><select id="ct_zSign"><option value="1">As in the file</option><option value="-1">Invert (depth &rarr; negative)</option></select></div>
        <div><label for="ct_coordDecimals">Coordinate decimals</label><select id="ct_coordDecimals"><option>2</option><option selected>3</option><option>4</option></select></div>
      </div>
    </div>
    </div>
    <div class="actionRow">
      <button id="ct_download" class="downloadBtn">Download DXF</button>
      <button id="ct_reset" class="clearBtn" type="button">Reset options</button>
    </div>
    <div id="ct_summary" class="result">No file loaded.</div>
  </div>
  </div>
  </div>
  </div>
<div id="cbPane" class="convert-sub-content">
<style>#cbPane{margin:0;font:14px/1.45 system-ui,Segoe UI,Arial,sans-serif;background:var(--bg);color:var(--ink)}
#cbPane header{background:linear-gradient(#bfe3ff,#2f8fd0);padding:18px 16px;color:#fff;text-align:center}
#cbPane header h1{margin:0;font-size:22px}
#cbPane header p{margin:4px 0 0;opacity:.9}
#cbPane .cb-main{max-width:1000px;margin:14px auto;padding:0 16px;display:grid;grid-template-columns:1fr 1fr;gap:14px}
@media(max-width:760px){#cbPane .cb-main{grid-template-columns:1fr}}
#cbPane .card{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:14px}
#cbPane h2{font-size:15px;margin:0 0 10px}
#cbPane label{display:block;margin:8px 0 3px;color:var(--mut);font-size:12px}
#cbPane input,#cbPane select{width:100%;padding:7px;border:1px solid var(--line);border-radius:6px;font:inherit}
#cbPane .row{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}
#cbPane .row2{display:grid;grid-template-columns:1fr 1fr;gap:8px}
#cbPane button{background:var(--acc);color:#fff;border:0;border-radius:6px;padding:9px 14px;font:inherit;cursor:pointer;margin-top:12px;margin-right:6px}
#cbPane button.s{background:#e3eef7;color:var(--ink)}
#cbPane #cb_msg{margin-top:10px;font-size:13px;color:var(--mut);white-space:pre-line}
#cbPane canvas{width:100%;height:auto;border:1px solid var(--line);border-radius:6px;background:#fff}
#cbPane .chk{display:flex;gap:6px;align-items:center;margin-top:8px;color:var(--ink);font-size:13px}
#cbPane .chk input{width:auto}
#cbPane{--card:#fff;--ink:#12324a;--mut:#5b7488;--line:#cfdde9;--acc:#0b6fb8;font-size:14px}
#cbPane .cb-main{max-width:none;margin:0;padding:0}
#cbPane button.s{background:#e3eef7;color:#12324a}
</style>
<div class="cb-main">
<section class="card">
<h2>1. Values</h2>
<label>Source</label>
<select id="cb_mode"><option value="depth">Depth XYZ file (red = min Z, blue = max Z)</option><option value="elev">Elevation XYZ file (red = max Z, blue = min Z)</option><option value="manual">Enter values manually</option></select>
<div id="cb_fileBox"><label>XYZ file (X Y Z, space / comma / tab)</label><input type="file" id="cb_file" accept=".xyz,.txt,.csv,.pts,.dat"></div>
<div class="row"><div><label>Red value (min)</label><input id="cb_vmin" type="number" step="any" value="0"></div>
<div><label>Blue value (max)</label><input id="cb_vmax" type="number" step="any" value="50"></div>
<div><label>Interval</label><input id="cb_step" type="number" step="any" value="8" min="0.0001"></div></div>
<div class="chk"><input type="checkbox" id="cb_round"><label style="margin:0;color:inherit">Round file min/max out to a multiple of the interval (off = exact file min/max)</label></div>
<div class="chk"><input type="checkbox" id="cb_flip"><label style="margin:0;color:inherit">Swap colours (blue at red value)</label></div>
<div class="chk"><input type="checkbox" id="cb_open" checked><label style="margin:0;color:inherit">Open end classes (&gt;= / &lt;) like the sample legend</label></div>
<label>Optional HYPACK .hcf / Surfer .clr colour file (default: built-in red→yellow→green→cyan→blue)</label>
<input type="file" id="cb_hcf" accept=".hcf,.clr,.txt">
<p style="font-size:12px;color:var(--mut)">Examples: <b>0, 50, 8</b> · <b>-50, 0, 8</b> · depth <b>-5, 50, 8</b> · elevation <b>5, -50, 8</b>. The interval is the size of each colour class.</p>
</section>
<section class="card">
<h2>2. Output</h2>
<div class="row2"><div><label>Origin X (top-left)</label><input id="cb_ox" type="number" step="any" value="0"></div><div><label>Origin Y (top-left)</label><input id="cb_oy" type="number" step="any" value="0"></div>
<div><label>Box height (width &amp; text follow)</label><input id="cb_bw" type="number" step="any" value="38"></div><div><label>Box width</label><input id="cb_bh" type="number" step="any" value="50"></div>
<div><label>Text height</label><input id="cb_th" type="number" step="any" value="18"></div><div><label>Label decimals</label><input id="cb_dec" type="number" min="0" max="4" value="2"></div>
<div><label>Layer</label><input id="cb_layer" value="ColorBar" readonly></div><div><label>File name</label><input id="cb_fname" value="COLOR_BAR"></div></div>
<canvas id="cb_cv" width="420" height="420"></canvas>
<button id="cb_dl">Download DXF</button><button class="s" id="cb_dlh">Download HCF</button><button class="s" id="cb_clr">Clear All</button>
<div id="cb_msg"></div>
</section>
</div>
<script>(function(){
const $=id=>document.getElementById(id);
let fileMin=null,fileMax=null,ramp=null;
// built-in ramp (HYPACK MCT style): fraction 0..1 -> [r,g,b]
const STOPS=[[0,[255,0,0]],[.248,[255,255,0]],[.5,[0,255,0]],[.748,[0,255,255]],[1,[0,0,255]]];
function lerpStops(st,t){t=Math.max(0,Math.min(1,t));for(let i=1;i<st.length;i++){if(t<=st[i][0]){const a=st[i-1],b=st[i],f=(t-a[0])/(b[0]-a[0]||1);return a[1].map((v,k)=>Math.round(v+(b[1][k]-v)*f));}}return st[st.length-1][1];}
function colorAt(t){return ramp?lerpStops(ramp,t):lerpStops(STOPS,t);}
function toInt(c){return c[0]+c[1]*256+c[2]*65536;}
const hex=c=>'#'+c.map(v=>v.toString(16).padStart(2,'0')).join('');
// parse optional HCF
$('cb_hcf').onchange=async e=>{const f=e.target.files[0];if(!f){ramp=null;draw();return;}
 const L=(await f.text()).split(/\r?\n/).map(s=>s.trim());let pts=[],mn=NaN,mx=NaN,kind='HCF';
 if(/^ColorMap/i.test(L[0])||/\.clr$/i.test(f.name)){ // Surfer .clr : percent R G B
  kind='CLR';const q=[];
  for(const ln of L){const p=ln.split(/\s+/).map(Number);if(p.length>=4&&p.slice(0,4).every(isFinite))q.push([p[0],[p[1],p[2],p[3]]]);}
  if(q.length>=2){q.sort((x,y)=>x[0]-y[0]);const red=c=>c[0]-c[2];
   if(red(q[0][1])<red(q[q.length-1][1])){const t=q.map(z=>[100-z[0],z[1]]).reverse();q.length=0;t.forEach(z=>q.push(z));} // red end first
   const a=q[0][0],b=q[q.length-1][0];pts=q.map(z=>[(z[0]-a)/(b-a||1),z[1]]);}
  if(pts.length>=2)ramp=pts;
 }else{
  const n=+L[0];mn=+L[1];mx=+L[2];
  for(let i=4;i<L.length&&pts.length<n;i++){const p=L[i].split(/\s+/);if(p.length<2)break;const d=+p[0],ci=+p[1];if(isNaN(d)||isNaN(ci))break;pts.push([d,[ci&255,(ci>>8)&255,(ci>>16)&255]]);}
  if(pts.length>=2){const a=pts[0][0],b=pts[pts.length-1][0];ramp=pts.map(p=>[(p[0]-a)/(b-a||1),p[1]]);}
 }
 if(pts.length<2){$('cb_msg').textContent='Could not read colour file; using default ramp.';ramp=null;}
 else{if(isFinite(mn)&&isFinite(mx)&&mn!==mx){$('cb_vmin').value=mn;$('cb_vmax').value=mx;}
  $('cb_msg').textContent=kind+' colours loaded ('+pts.length+' colours'+(kind==='CLR'?', red end first; set min / max / interval yourself':'')+').';}
 draw();};
$('cb_file').onclick=e=>{e.target.value='';};
$('cb_file').onchange=e=>{const f=e.target.files[0];if(!f)return;const r=new FileReader();
 r.onload=()=>{const t=r.result;let mn=Infinity,mx=-Infinity,n=0,pos=0,len=t.length;
  while(pos<len){let e2=t.indexOf('\n',pos);if(e2<0)e2=len;const line=t.substring(pos,e2);pos=e2+1;
   const p=line.trim().split(/[\s,;]+/);if(p.length<3)continue;const z=parseFloat(p[2]);if(!isFinite(z)||isNaN(parseFloat(p[0])))continue;n++;if(z<mn)mn=z;if(z>mx)mx=z;}
  if(!n){$('cb_msg').textContent='No XYZ rows found.';return;}
  fileMin=mn;fileMax=mx;if($('cb_mode').value==='manual')$('cb_mode').value='depth';$('cb_fileBox').style.display='';$('cb_msg').textContent=n+' points. Min Z = '+mn+', Max Z = '+mx+' (filled in automatically).';applyFile();};
 r.readAsText(f);};
function applyFile(){if(fileMin===null)return;const m=$('cb_mode').value,s=+$('cb_step').value||1,rd=$('cb_round').checked;
 let lo=fileMin,hi=fileMax;if(rd){lo=Math.floor(lo/s)*s;hi=Math.ceil(hi/s)*s;}
 lo=+lo.toFixed(4);hi=+hi.toFixed(4);
 if(m==='depth'){$('cb_vmin').value=lo;$('cb_vmax').value=hi;}else{$('cb_vmin').value=hi;$('cb_vmax').value=lo;}
 draw();}
$('cb_bh').addEventListener('input',()=>{const h=+$('cb_bh').value;if(h>0){$('cb_bw').value=+(h*0.76).toFixed(4);$('cb_th').value=+(h*0.36).toFixed(4);draw();}});
$('cb_mode').onchange=()=>{$('cb_fileBox').style.display=$('cb_mode').value==='manual'?'none':'';applyFile();draw();};
['vmin','vmax','step','flip','open','round','dec','bw','bh'].forEach(i=>$('cb_'+i).oninput=()=>{if(i==='step'||i==='round')applyFile();draw();});
function fmt(v){return v.toFixed(Math.max(0,Math.min(4,+$('cb_dec').value||0)));}
function classes(){
 const a=+$('cb_vmin').value,b=+$('cb_vmax').value,s=Math.abs(+$('cb_step').value);
 if(!isFinite(a)||!isFinite(b)||!(s>0)||a===b)return null;
 const dec=Math.max(0,Math.min(4,+$('cb_dec').value||0)),eps=Math.pow(10,-dec),open=$('cb_open').checked,flip=$('cb_flip').checked;
 const lo=Math.min(a,b),hi=Math.max(a,b),n=Math.min(500,Math.max(1,Math.ceil((hi-lo)/s-1e-9)));
 const list=[]; // ascending by value
 if(open)list.push({label:'< '+fmt(lo)});
 for(let i=0;i<n;i++){const l=lo+i*s,h=i===n-1?hi:lo+(i+1)*s;list.push({label:fmt(l)+' - '+fmt(h-eps)});}
 if(open)list.push({label:'>= '+fmt(hi)});
 // display order top->bottom: red end first
 if(a>b)list.reverse();
 const N=list.length;
 list.forEach((k,i)=>{let t=N>1?i/(N-1):0;if(flip)t=1-t;k.rgb=colorAt(t);});
 return list;}
function draw(){const cv=$('cb_cv'),g=cv.getContext('2d');g.fillStyle='#232a31';g.fillRect(0,0,cv.width,cv.height);const c=classes();
 if(!c){g.fillStyle='#f88';g.fillText('Check values',10,20);return;}
 const bw=+$('cb_bw').value||38,bh=+$('cb_bh').value||50,th=+$('cb_th').value||18;
 const sc=Math.min(1.4,(cv.height-30)/(c.length*bh)),w=bw*sc,h=bh*sc,x0=40;
 g.font=(th*sc*1.35)+'px Arial';g.textBaseline='middle';
 c.forEach((k,i)=>{const y=15+i*h;g.fillStyle=hex(k.rgb);g.fillRect(x0,y,w,h+0.6);g.fillStyle='#fff';g.fillText(k.label,x0+w+bh*.32*sc,y+h/2);});}
const ACI=(()=>{const t=[[0,0,0],[255,0,0],[255,255,0],[0,255,0],[0,255,255],[0,0,255],[255,0,255],[255,255,255],[128,128,128],[192,192,192]];
 const hsv=(h,s,v)=>{const c=v*s,x=c*(1-Math.abs((h/60)%2-1)),m=v-c;let r,g,b;if(h<60)[r,g,b]=[c,x,0];else if(h<120)[r,g,b]=[x,c,0];else if(h<180)[r,g,b]=[0,c,x];else if(h<240)[r,g,b]=[0,x,c];else if(h<300)[r,g,b]=[x,0,c];else[r,g,b]=[c,0,x];return[r+m,g+m,b+m].map(q=>Math.round(q*255));};
 const V=[1,.8,.6,.5,.3];for(let n=10;n<250;n++){const h=Math.floor((n-10)/10)*15,k=(n-10)%10;t[n]=hsv(h,k%2?0.5:1,V[k>>1]);}
 [51,76,102,128,153,178].forEach((g,i)=>t[250+i]=[g,g,g]);return t;})();
function nearestACI(rgb){let best=7,bd=1e9;for(let i=1;i<256;i++){if(i===7||i===8||i===9)continue;const q=ACI[i],d=(q[0]-rgb[0])**2+(q[1]-rgb[1])**2+(q[2]-rgb[2])**2;if(d<bd){bd=d;best=i;}}return best;}
const TPL_PRE=["  0", "SECTION", "  2", "HEADER", "  9", "$ACADVER", "  1", "AC1032", "  9", "$ACADMAINTVER", " 90", "       55", "  9", "$DWGCODEPAGE", "  3", "ANSI_1252", "  9", "$LASTSAVEDBY", "  1", "janaka", "  9", "$REQUIREDVERSIONS", "160", "                 0", "  9", "$INSBASE", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$EXTMIN", " 10", "1913532.56", " 20", "14802744.55010417", " 30", "0.0", "  9", "$EXTMAX", " 10", "1913887.913645833", " 20", "14802865.45010417", " 30", "0.0", "  9", "$LIMMIN", " 10", "0.0", " 20", "0.0", "  9", "$LIMMAX", " 10", "12.0", " 20", "9.0", "  9", "$ORTHOMODE", " 70", "     0", "  9", "$REGENMODE", " 70", "     1", "  9", "$FILLMODE", " 70", "     1", "  9", "$QTEXTMODE", " 70", "     0", "  9", "$MIRRTEXT", " 70", "     1", "  9", "$LTSCALE", " 40", "1.0", "  9", "$ATTMODE", " 70", "     1", "  9", "$TEXTSIZE", " 40", "0.2", "  9", "$TRACEWID", " 40", "0.05", "  9", "$TEXTSTYLE", "  7", "Standard", "  9", "$CLAYER", "  8", "0", "  9", "$CELTYPE", "  6", "ByLayer", "  9", "$CECOLOR", " 62", "   256", "  9", "$CELTSCALE", " 40", "1.0", "  9", "$DISPSILH", " 70", "     0", "  9", "$DIMSCALE", " 40", "1.0", "  9", "$DIMASZ", " 40", "0.18", "  9", "$DIMEXO", " 40", "0.0625", "  9", "$DIMDLI", " 40", "0.38", "  9", "$DIMRND", " 40", "0.0", "  9", "$DIMDLE", " 40", "0.0", "  9", "$DIMEXE", " 40", "0.18", "  9", "$DIMTP", " 40", "0.0", "  9", "$DIMTM", " 40", "0.0", "  9", "$DIMTXT", " 40", "0.18", "  9", "$DIMCEN", " 40", "0.09", "  9", "$DIMTSZ", " 40", "0.0", "  9", "$DIMTOL", " 70", "     0", "  9", "$DIMLIM", " 70", "     0", "  9", "$DIMTIH", " 70", "     1", "  9", "$DIMTOH", " 70", "     1", "  9", "$DIMSE1", " 70", "     0", "  9", "$DIMSE2", " 70", "     0", "  9", "$DIMTAD", " 70", "     0", "  9", "$DIMZIN", " 70", "     0", "  9", "$DIMBLK", "  1", "", "  9", "$DIMASO", " 70", "     1", "  9", "$DIMSHO", " 70", "     1", "  9", "$DIMPOST", "  1", "", "  9", "$DIMAPOST", "  1", "", "  9", "$DIMALT", " 70", "     0", "  9", "$DIMALTD", " 70", "     2", "  9", "$DIMALTF", " 40", "25.4", "  9", "$DIMLFAC", " 40", "1.0", "  9", "$DIMTOFL", " 70", "     0", "  9", "$DIMTVP", " 40", "0.0", "  9", "$DIMTIX", " 70", "     0", "  9", "$DIMSOXD", " 70", "     0", "  9", "$DIMSAH", " 70", "     0", "  9", "$DIMBLK1", "  1", "", "  9", "$DIMBLK2", "  1", "", "  9", "$DIMSTYLE", "  2", "Standard", "  9", "$DIMCLRD", " 70", "     0", "  9", "$DIMCLRE", " 70", "     0", "  9", "$DIMCLRT", " 70", "     0", "  9", "$DIMTFAC", " 40", "1.0", "  9", "$DIMGAP", " 40", "0.09", "  9", "$DIMJUST", " 70", "     0", "  9", "$DIMSD1", " 70", "     0", "  9", "$DIMSD2", " 70", "     0", "  9", "$DIMTOLJ", " 70", "     1", "  9", "$DIMTZIN", " 70", "     0", "  9", "$DIMALTZ", " 70", "     0", "  9", "$DIMALTTZ", " 70", "     0", "  9", "$DIMUPT", " 70", "     0", "  9", "$DIMDEC", " 70", "     4", "  9", "$DIMTDEC", " 70", "     4", "  9", "$DIMALTU", " 70", "     2", "  9", "$DIMALTTD", " 70", "     2", "  9", "$DIMTXSTY", "  7", "Standard", "  9", "$DIMAUNIT", " 70", "     0", "  9", "$DIMADEC", " 70", "     0", "  9", "$DIMALTRND", " 40", "0.0", "  9", "$DIMAZIN", " 70", "     0", "  9", "$DIMDSEP", " 70", "    46", "  9", "$DIMATFIT", " 70", "     3", "  9", "$DIMFRAC", " 70", "     0", "  9", "$DIMLDRBLK", "  1", "", "  9", "$DIMLUNIT", " 70", "     2", "  9", "$DIMLWD", " 70", "    -2", "  9", "$DIMLWE", " 70", "    -2", "  9", "$DIMTMOVE", " 70", "     0", "  9", "$DIMFXL", " 40", "1.0", "  9", "$DIMFXLON", " 70", "     0", "  9", "$DIMJOGANG", " 40", "0.7853981633974483", "  9", "$DIMTFILL", " 70", "     0", "  9", "$DIMTFILLCLR", " 70", "     0", "  9", "$DIMARCSYM", " 70", "     0", "  9", "$DIMLTYPE", "  6", "", "  9", "$DIMLTEX1", "  6", "", "  9", "$DIMLTEX2", "  6", "", "  9", "$DIMTXTDIRECTION", " 70", "     0", "  9", "$LUNITS", " 70", "     2", "  9", "$LUPREC", " 70", "     4", "  9", "$SKETCHINC", " 40", "0.1", "  9", "$FILLETRAD", " 40", "0.0", "  9", "$AUNITS", " 70", "     0", "  9", "$AUPREC", " 70", "     0", "  9", "$MENU", "  1", ".", "  9", "$ELEVATION", " 40", "0.0", "  9", "$PELEVATION", " 40", "0.0", "  9", "$THICKNESS", " 40", "0.0", "  9", "$LIMCHECK", " 70", "     0", "  9", "$CHAMFERA", " 40", "0.0", "  9", "$CHAMFERB", " 40", "0.0", "  9", "$CHAMFERC", " 40", "0.0", "  9", "$CHAMFERD", " 40", "0.0", "  9", "$SKPOLY", " 70", "     0", "  9", "$TDCREATE", " 40", "2460951.678398484", "  9", "$TDUCREATE", " 40", "2460951.845065151", "  9", "$TDUPDATE", " 40", "2460951.678398797", "  9", "$TDUUPDATE", " 40", "2460951.845065463", "  9", "$TDINDWG", " 40", "0.0000000116", "  9", "$TDUSRTIMER", " 40", "0.0000000116", "  9", "$USRTIMER", " 70", "     1", "  9", "$ANGBASE", " 50", "0.0", "  9", "$ANGDIR", " 70", "     0", "  9", "$PDMODE", " 70", "     0", "  9", "$PDSIZE", " 40", "0.0", "  9", "$PLINEWID", " 40", "0.0", "  9", "$SPLFRAME", " 70", "     0", "  9", "$SPLINETYPE", " 70", "     6", "  9", "$SPLINESEGS", " 70", "     8", "  9", "$HANDSEED", "  5", "B7", "  9", "$SURFTAB1", " 70", "     6", "  9", "$SURFTAB2", " 70", "     6", "  9", "$SURFTYPE", " 70", "     6", "  9", "$SURFU", " 70", "     6", "  9", "$SURFV", " 70", "     6", "  9", "$UCSBASE", "  2", "", "  9", "$UCSNAME", "  2", "", "  9", "$UCSORG", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$UCSXDIR", " 10", "1.0", " 20", "0.0", " 30", "0.0", "  9", "$UCSYDIR", " 10", "0.0", " 20", "1.0", " 30", "0.0", "  9", "$UCSORTHOREF", "  2", "", "  9", "$UCSORTHOVIEW", " 70", "     0", "  9", "$UCSORGTOP", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$UCSORGBOTTOM", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$UCSORGLEFT", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$UCSORGRIGHT", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$UCSORGFRONT", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$UCSORGBACK", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSBASE", "  2", "", "  9", "$PUCSNAME", "  2", "", "  9", "$PUCSORG", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSXDIR", " 10", "1.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSYDIR", " 10", "0.0", " 20", "1.0", " 30", "0.0", "  9", "$PUCSORTHOREF", "  2", "", "  9", "$PUCSORTHOVIEW", " 70", "     0", "  9", "$PUCSORGTOP", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSORGBOTTOM", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSORGLEFT", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSORGRIGHT", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSORGFRONT", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PUCSORGBACK", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$USERI1", " 70", "     0", "  9", "$USERI2", " 70", "     0", "  9", "$USERI3", " 70", "     0", "  9", "$USERI4", " 70", "     0", "  9", "$USERI5", " 70", "     0", "  9", "$USERR1", " 40", "0.0", "  9", "$USERR2", " 40", "0.0", "  9", "$USERR3", " 40", "0.0", "  9", "$USERR4", " 40", "0.0", "  9", "$USERR5", " 40", "0.0", "  9", "$WORLDVIEW", " 70", "     1", "  9", "$SHADEDGE", " 70", "     3", "  9", "$SHADEDIF", " 70", "    70", "  9", "$TILEMODE", " 70", "     1", "  9", "$MAXACTVP", " 70", "    64", "  9", "$PINSBASE", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  9", "$PLIMCHECK", " 70", "     0", "  9", "$PEXTMIN", " 10", "1.000000000000000E+20", " 20", "1.000000000000000E+20", " 30", "1.000000000000000E+20", "  9", "$PEXTMAX", " 10", "-1.000000000000000E+20", " 20", "-1.000000000000000E+20", " 30", "-1.000000000000000E+20", "  9", "$PLIMMIN", " 10", "0.0", " 20", "0.0", "  9", "$PLIMMAX", " 10", "12.0", " 20", "9.0", "  9", "$UNITMODE", " 70", "     0", "  9", "$VISRETAIN", " 70", "     1", "  9", "$PLINEGEN", " 70", "     0", "  9", "$PSLTSCALE", " 70", "     1", "  9", "$TREEDEPTH", " 70", "  3020", "  9", "$CMLSTYLE", "  2", "Standard", "  9", "$CMLJUST", " 70", "     0", "  9", "$CMLSCALE", " 40", "1.0", "  9", "$PROXYGRAPHICS", " 70", "     1", "  9", "$MEASUREMENT", " 70", "     0", "  9", "$CELWEIGHT", "370", "    -1", "  9", "$ENDCAPS", "280", "     0", "  9", "$JOINSTYLE", "280", "     0", "  9", "$LWDISPLAY", "290", "     0", "  9", "$INSUNITS", " 70", "     2", "  9", "$HYPERLINKBASE", "  1", "", "  9", "$STYLESHEET", "  1", "", "  9", "$XEDIT", "290", "     1", "  9", "$CEPSNTYPE", "380", "     0", "  9", "$PSTYLEMODE", "290", "     1", "  9", "$FINGERPRINTGUID", "  2", "{dfc3ab61-fc39-42eb-ade3-5ae9daffb09a}", "  9", "$VERSIONGUID", "  2", "{FAEB1C32-E019-11D5-929B-00C0DF256EC4}", "  9", "$EXTNAMES", "290", "     1", "  9", "$PSVPSCALE", " 40", "0.0", "  9", "$OLESTARTUP", "290", "     0", "  9", "$SORTENTS", "280", "   127", "  9", "$INDEXCTL", "280", "     0", "  9", "$HIDETEXT", "280", "     1", "  9", "$XCLIPFRAME", "280", "     2", "  9", "$HALOGAP", "280", "     0", "  9", "$OBSCOLOR", " 70", "   257", "  9", "$OBSLTYPE", "280", "     0", "  9", "$INTERSECTIONDISPLAY", "280", "     0", "  9", "$INTERSECTIONCOLOR", " 70", "   257", "  9", "$DIMASSOC", "280", "     2", "  9", "$PROJECTNAME", "  1", "", "  9", "$CAMERADISPLAY", "290", "     0", "  9", "$LENSLENGTH", " 40", "50.0", "  9", "$CAMERAHEIGHT", " 40", "0.0", "  9", "$STEPSPERSEC", " 40", "2.0", "  9", "$STEPSIZE", " 40", "6.0", "  9", "$3DDWFPREC", " 40", "2.0", "  9", "$PSOLWIDTH", " 40", "0.25", "  9", "$PSOLHEIGHT", " 40", "4.0", "  9", "$LOFTANG1", " 40", "1.570796326794897", "  9", "$LOFTANG2", " 40", "1.570796326794897", "  9", "$LOFTMAG1", " 40", "0.0", "  9", "$LOFTMAG2", " 40", "0.0", "  9", "$LOFTPARAM", " 70", "     7", "  9", "$LOFTNORMALS", "280", "     1", "  9", "$LATITUDE", " 40", "37.795", "  9", "$LONGITUDE", " 40", "-122.394", "  9", "$NORTHDIRECTION", " 40", "0.0", "  9", "$TIMEZONE", " 70", " -8000", "  9", "$LIGHTGLYPHDISPLAY", "280", "     1", "  9", "$TILEMODELIGHTSYNCH", "280", "     1", "  9", "$CMATERIAL", "347", "44", "  9", "$SOLIDHIST", "280", "     0", "  9", "$SHOWHIST", "280", "     1", "  9", "$DWFFRAME", "280", "     2", "  9", "$DGNFRAME", "280", "     2", "  9", "$REALWORLDSCALE", "290", "     1", "  9", "$INTERFERECOLOR", " 62", "   256", "  9", "$CSHADOW", "280", "     0", "  9", "$SHADOWPLANELOCATION", " 40", "0.0", "  0", "ENDSEC", "  0", "SECTION", "  2", "CLASSES", "  0", "CLASS", "  1", "ACDBDICTIONARYWDFLT", "  2", "AcDbDictionaryWithDefault", "  3", "ObjectDBX Classes", " 90", "        0", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "VISUALSTYLE", "  2", "AcDbVisualStyle", "  3", "ObjectDBX Classes", " 90", "     4095", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "MATERIAL", "  2", "AcDbMaterial", "  3", "ObjectDBX Classes", " 90", "     1153", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "SCALE", "  2", "AcDbScale", "  3", "ObjectDBX Classes", " 90", "     1153", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "TABLESTYLE", "  2", "AcDbTableStyle", "  3", "ObjectDBX Classes", " 90", "     4095", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "MLEADERSTYLE", "  2", "AcDbMLeaderStyle", "  3", "ACDB_MLEADERSTYLE_CLASS", " 90", "     4095", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "SUN", "  2", "AcDbSun", "  3", "SCENEOE", " 90", "     1153", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "DICTIONARYVAR", "  2", "AcDbDictionaryVar", "  3", "ObjectDBX Classes", " 90", "        0", " 91", "        3", "280", "     0", "281", "     0", "  0", "CLASS", "  1", "CELLSTYLEMAP", "  2", "AcDbCellStyleMap", "  3", "ObjectDBX Classes", " 90", "     1152", " 91", "        3", "280", "     0", "281", "     0", "  0", "ENDSEC", "  0", "SECTION", "  2", "TABLES", "  0", "TABLE", "  2", "VPORT", "  5", "8", "330", "0", "100", "AcDbSymbolTable", " 70", "     1", "  0", "VPORT", "  5", "29", "330", "8", "100", "AcDbSymbolTableRecord", "100", "AcDbViewportTableRecord", "  2", "*Active", " 70", "     0", " 10", "0.0", " 20", "0.0", " 11", "1.0", " 21", "1.0", " 12", "10.42990654205607", " 22", "4.5", " 13", "0.0", " 23", "0.0", " 14", "0.5", " 24", "0.5", " 15", "0.5", " 25", "0.5", " 16", "0.0", " 26", "0.0", " 36", "1.0", " 17", "0.0", " 27", "0.0", " 37", "0.0", " 40", "9.0", " 41", "1.972972972850329", " 42", "50.0", " 43", "0.0", " 44", "0.0", " 50", "0.0", " 51", "0.0", " 71", "     0", " 72", "   100", " 73", "     1", " 74", "     3", " 75", "     0", " 76", "     0", " 77", "     0", " 78", "     0", "281", "     0", " 65", "     1", "110", "0.0", "120", "0.0", "130", "0.0", "111", "1.0", "121", "0.0", "131", "0.0", "112", "0.0", "122", "1.0", "132", "0.0", " 79", "     0", "146", "0.0", "348", "2F", " 60", "     3", " 61", "     5", "292", "     1", "282", "     1", "141", "0.0", "142", "0.0", " 63", "   250", "361", "5D", "  0", "ENDTAB", "  0", "TABLE", "  2", "LTYPE", "  5", "5", "330", "0", "100", "AcDbSymbolTable", " 70", "     6", "  0", "LTYPE", "  5", "14", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "ByBlock", " 70", "     0", "  3", "", " 72", "    65", " 73", "     0", " 40", "0.0", "  0", "LTYPE", "  5", "15", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "ByLayer", " 70", "     0", "  3", "", " 72", "    65", " 73", "     0", " 40", "0.0", "  0", "LTYPE", "  5", "16", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "Continuous", " 70", "     0", "  3", "Solid line", " 72", "    65", " 73", "     0", " 40", "0.0", "  0", "LTYPE", "  5", "5E", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "ACAD_ISO02W100", " 70", "     0", "  3", "ISO dash __ __ __ __ __ __ __ __ __ __ __ __ __", " 72", "    65", " 73", "     2", " 40", "15.0", " 49", "12.0", " 74", "     0", " 49", "-3.0", " 74", "     0", "  0", "LTYPE", "  5", "5F", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "ACAD_ISO07W100", " 70", "     0", "  3", "ISO dot . . . . . . . . . . . . . . . . . . . .", " 72", "    65", " 73", "     2", " 40", "3.0", " 49", "0.0", " 74", "     0", " 49", "-3.0", " 74", "     0", "  0", "LTYPE", "  5", "60", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "ACAD_ISO10W100", " 70", "     0", "  3", "ISO dash dot __ . __ . __ . __ . __ . __ . __ .", " 72", "    65", " 73", "     4", " 40", "18.0", " 49", "12.0", " 74", "     0", " 49", "-3.0", " 74", "     0", " 49", "0.0", " 74", "     0", " 49", "-3.0", " 74", "     0", "  0", "LTYPE", "  5", "61", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "ACAD_ISO12W100", " 70", "     0", "  3", "ISO dash double-dot __ . . __ . . __ . . __ . .", " 72", "    65", " 73", "     6", " 40", "21.0", " 49", "12.0", " 74", "     0", " 49", "-3.0", " 74", "     0", " 49", "0.0", " 74", "     0", " 49", "-3.0", " 74", "     0", " 49", "0.0", " 74", "     0", " 49", "0.0", " 74", "     0", "  0", "LTYPE", "  5", "62", "330", "5", "100", "AcDbSymbolTableRecord", "100", "AcDbLinetypeTableRecord", "  2", "Hidden", " 70", "     0", "  3", "- - - - - - - - - - - - - - - - - - - - -", " 72", "    65", " 73", "     2", " 40", "0.1875", " 49", "0.125", " 74", "     0", " 49", "-0.0625", " 74", "     0", "  0", "ENDTAB", "  0", "TABLE", "  2", "LAYER", "  5", "2", "330", "0", "100", "AcDbSymbolTable", " 70", "     4", "  0", "LAYER", "  5", "10", "330", "2", "100", "AcDbSymbolTableRecord", "100", "AcDbLayerTableRecord", "  2", "0", " 70", "     0", " 62", "     7", "  6", "Continuous", "370", "    -3", "390", "F", "347", "46", "348", "0", "  0", "LAYER", "  5", "63", "330", "2", "100", "AcDbSymbolTableRecord", "100", "AcDbLayerTableRecord", "  2", "Targets", " 70", "     0", " 62", "     7", "  6", "Continuous", "370", "    -3", "390", "F", "347", "46", "348", "0", "  0", "LAYER", "  5", "64", "330", "2", "100", "AcDbSymbolTableRecord", "100", "AcDbLayerTableRecord", "  2", "Blocks", " 70", "     0", " 62", "     7", "  6", "Continuous", "370", "    -3", "390", "F", "347", "46", "348", "0", "  0", "LAYER", "  5", "65", "330", "2", "100", "AcDbSymbolTableRecord", "100", "AcDbLayerTableRecord", "  2", "ColorBar", " 70", "     0", " 62", "     7", "  6", "Continuous", "370", "    -3", "390", "F", "347", "46", "348", "0", "  0", "ENDTAB", "  0", "TABLE", "  2", "STYLE", "  5", "3", "330", "0", "100", "AcDbSymbolTable", " 70", "     1", "  0", "STYLE", "  5", "11", "330", "3", "100", "AcDbSymbolTableRecord", "100", "AcDbTextStyleTableRecord", "  2", "Standard", " 70", "     0", " 40", "0.0", " 41", "1.0", " 50", "0.0", " 71", "     0", " 42", "0.2", "  3", "txt", "  4", "", "  0", "ENDTAB", "  0", "TABLE", "  2", "VIEW", "  5", "6", "330", "0", "100", "AcDbSymbolTable", " 70", "     0", "  0", "ENDTAB", "  0", "TABLE", "  2", "UCS", "  5", "7", "330", "0", "100", "AcDbSymbolTable", " 70", "     0", "  0", "ENDTAB", "  0", "TABLE", "  2", "APPID", "  5", "9", "330", "0", "100", "AcDbSymbolTable", " 70", "     1", "  0", "APPID", "  5", "12", "330", "9", "100", "AcDbSymbolTableRecord", "100", "AcDbRegAppTableRecord", "  2", "ACAD", " 70", "     0", "  0", "ENDTAB", "  0", "TABLE", "  2", "DIMSTYLE", "  5", "A", "330", "0", "100", "AcDbSymbolTable", " 70", "     1", "100", "AcDbDimStyleTable", "  0", "DIMSTYLE", "105", "27", "330", "A", "100", "AcDbSymbolTableRecord", "100", "AcDbDimStyleTableRecord", "  2", "Standard", " 70", "     0", "178", "     0", "340", "11", "  0", "ENDTAB", "  0", "TABLE", "  2", "BLOCK_RECORD", "  5", "1", "330", "0", "100", "AcDbSymbolTable", " 70", "     1", "  0", "BLOCK_RECORD", "  5", "1F", "330", "1", "100", "AcDbSymbolTableRecord", "100", "AcDbBlockTableRecord", "  2", "*Model_Space", "340", "22", " 70", "     2", "280", "     1", "281", "     0", "  0", "BLOCK_RECORD", "  5", "1B", "330", "1", "100", "AcDbSymbolTableRecord", "100", "AcDbBlockTableRecord", "  2", "*Paper_Space", "340", "1E", " 70", "     0", "280", "     1", "281", "     0", "  0", "BLOCK_RECORD", "  5", "23", "330", "1", "100", "AcDbSymbolTableRecord", "100", "AcDbBlockTableRecord", "  2", "*Paper_Space0", "340", "26", " 70", "     0", "280", "     1", "281", "     0", "  0", "ENDTAB", "  0", "ENDSEC", "  0", "SECTION", "  2", "BLOCKS", "  0", "BLOCK", "  5", "20", "330", "1F", "100", "AcDbEntity", "  8", "0", "100", "AcDbBlockBegin", "  2", "*Model_Space", " 70", "     0", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  3", "*Model_Space", "  1", "", "  0", "ENDBLK", "  5", "21", "330", "1F", "100", "AcDbEntity", "  8", "0", "100", "AcDbBlockEnd", "  0", "BLOCK", "  5", "1C", "330", "1B", "100", "AcDbEntity", " 67", "     1", "  8", "0", "100", "AcDbBlockBegin", "  2", "*Paper_Space", " 70", "     0", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  3", "*Paper_Space", "  1", "", "  0", "ENDBLK", "  5", "1D", "330", "1B", "100", "AcDbEntity", " 67", "     1", "  8", "0", "100", "AcDbBlockEnd", "  0", "BLOCK", "  5", "24", "330", "23", "100", "AcDbEntity", "  8", "0", "100", "AcDbBlockBegin", "  2", "*Paper_Space0", " 70", "     0", " 10", "0.0", " 20", "0.0", " 30", "0.0", "  3", "*Paper_Space0", "  1", "", "  0", "ENDBLK", "  5", "25", "330", "23", "100", "AcDbEntity", "  8", "0", "100", "AcDbBlockEnd", "  0", "ENDSEC", "  0", "SECTION", "  2", "ENTITIES"];
const TPL_SUF=["  0", "ENDSEC", "  0", "SECTION", "  2", "OBJECTS", "  0", "DICTIONARY", "  5", "C", "330", "0", "100", "AcDbDictionary", "281", "     1", "  3", "ACAD_DETAILVIEWSTYLE", "350", "B5", "  3", "ACAD_GROUP", "350", "D", "  3", "ACAD_LAYOUT", "350", "1A", "  3", "ACAD_MATERIAL", "350", "43", "  3", "ACAD_MLEADERSTYLE", "350", "5B", "  3", "ACAD_MLINESTYLE", "350", "17", "  3", "ACAD_PLOTSETTINGS", "350", "19", "  3", "ACAD_PLOTSTYLENAME", "350", "E", "  3", "ACAD_SCALELIST", "350", "47", "  3", "ACAD_SECTIONVIEWSTYLE", "350", "B6", "  3", "ACAD_TABLESTYLE", "350", "59", "  3", "ACAD_VISUALSTYLE", "350", "2A", "  3", "ACDB_RECOMPOSE_DATA", "350", "B2", "  3", "AcDbVariableDictionary", "350", "AE", "  0", "SUN", "  5", "5D", "330", "29", "100", "AcDbSun", " 90", "        1", "290", "     0", " 63", "     7", "421", " 16777215", " 40", "1.0", "291", "     1", " 91", "  2455826", " 92", " 54000000", "292", "     0", " 70", "     2", " 71", "   256", "280", "     1", "  0", "DICTIONARY", "  5", "B5", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  0", "DICTIONARY", "  5", "D", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  0", "DICTIONARY", "  5", "1A", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "Layout1", "350", "1E", "  3", "Layout2", "350", "26", "  3", "Model", "350", "22", "  0", "DICTIONARY", "  5", "43", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "ByBlock", "350", "45", "  3", "ByLayer", "350", "44", "  3", "Global", "350", "46", "  0", "DICTIONARY", "  5", "5B", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "Standard", "350", "5C", "  0", "DICTIONARY", "  5", "17", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "Standard", "350", "18", "  0", "DICTIONARY", "  5", "19", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  0", "ACDBDICTIONARYWDFLT", "  5", "E", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "Normal", "350", "F", "100", "AcDbDictionaryWithDefault", "340", "F", "  0", "DICTIONARY", "  5", "47", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "A0", "350", "48", "  3", "A1", "350", "49", "  3", "A2", "350", "4A", "  3", "A3", "350", "4B", "  3", "A4", "350", "4C", "  3", "A5", "350", "4D", "  3", "A6", "350", "4E", "  3", "A7", "350", "4F", "  3", "A8", "350", "50", "  3", "A9", "350", "51", "  3", "B1", "350", "52", "  3", "B2", "350", "53", "  3", "B3", "350", "54", "  3", "B4", "350", "55", "  3", "B5", "350", "56", "  3", "B6", "350", "57", "  3", "B7", "350", "58", "  0", "DICTIONARY", "  5", "B6", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  0", "DICTIONARY", "  5", "59", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "Standard", "350", "5A", "  0", "DICTIONARY", "  5", "2A", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "2dWireframe", "350", "2F", "  3", "Basic", "350", "32", "  3", "Brighten", "350", "36", "  3", "ColorChange", "350", "3A", "  3", "Conceptual", "350", "34", "  3", "Dim", "350", "35", "  3", "EdgeColorOff", "350", "3D", "  3", "Facepattern", "350", "39", "  3", "Flat", "350", "2B", "  3", "FlatWithEdges", "350", "2C", "  3", "Gouraud", "350", "2D", "  3", "GouraudWithEdges", "350", "2E", "  3", "Hidden", "350", "31", "  3", "JitterOff", "350", "3B", "  3", "Linepattern", "350", "38", "  3", "OverhangOff", "350", "3C", "  3", "Realistic", "350", "33", "  3", "Shaded", "350", "42", "  3", "Shaded with edges", "350", "41", "  3", "Shades of Gray", "350", "3E", "  3", "Sketchy", "350", "3F", "  3", "Thicken", "350", "37", "  3", "Wireframe", "350", "30", "  3", "X-Ray", "350", "40", "  0", "XRECORD", "  5", "B2", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbXrecord", "280", "     1", " 90", "        1", "330", "5A", "  0", "DICTIONARY", "  5", "AE", "102", "{ACAD_REACTORS", "330", "C", "102", "}", "330", "C", "100", "AcDbDictionary", "281", "     1", "  3", "CANNOSCALE", "350", "AF", "  3", "CMLEADERSTYLE", "350", "B4", "  3", "CTABLESTYLE", "350", "B3", "  0", "LAYOUT", "  5", "1E", "102", "{ACAD_REACTORS", "330", "1A", "102", "}", "330", "1A", "100", "AcDbPlotSettings", "  1", "", "  2", "none_device", "  4", "", "  6", "", " 40", "0.0", " 41", "0.0", " 42", "0.0", " 43", "0.0", " 44", "0.0", " 45", "0.0", " 46", "0.0", " 47", "0.0", " 48", "0.0", " 49", "0.0", "140", "0.0", "141", "0.0", "142", "1.0", "143", "1.0", " 70", "   688", " 72", "     0", " 73", "     0", " 74", "     5", "  7", "", " 75", "    16", " 76", "     0", " 77", "     2", " 78", "   300", "147", "1.0", "148", "0.0", "149", "0.0", "100", "AcDbLayout", "  1", "Layout1", " 70", "     1", " 71", "     1", " 10", "0.0", " 20", "0.0", " 11", "12.0", " 21", "9.0", " 12", "0.0", " 22", "0.0", " 32", "0.0", " 14", "1.000000000000000E+20", " 24", "1.000000000000000E+20", " 34", "1.000000000000000E+20", " 15", "-1.000000000000000E+20", " 25", "-1.000000000000000E+20", " 35", "-1.000000000000000E+20", "146", "0.0", " 13", "0.0", " 23", "0.0", " 33", "0.0", " 16", "1.0", " 26", "0.0", " 36", "0.0", " 17", "0.0", " 27", "1.0", " 37", "0.0", " 76", "     0", "330", "1B", "  0", "LAYOUT", "  5", "26", "102", "{ACAD_REACTORS", "330", "1A", "102", "}", "330", "1A", "100", "AcDbPlotSettings", "  1", "", "  2", "none_device", "  4", "", "  6", "", " 40", "0.0", " 41", "0.0", " 42", "0.0", " 43", "0.0", " 44", "0.0", " 45", "0.0", " 46", "0.0", " 47", "0.0", " 48", "0.0", " 49", "0.0", "140", "0.0", "141", "0.0", "142", "1.0", "143", "1.0", " 70", "   688", " 72", "     0", " 73", "     0", " 74", "     5", "  7", "", " 75", "    16", " 76", "     0", " 77", "     2", " 78", "   300", "147", "1.0", "148", "0.0", "149", "0.0", "100", "AcDbLayout", "  1", "Layout2", " 70", "     1", " 71", "     2", " 10", "0.0", " 20", "0.0", " 11", "0.0", " 21", "0.0", " 12", "0.0", " 22", "0.0", " 32", "0.0", " 14", "0.0", " 24", "0.0", " 34", "0.0", " 15", "0.0", " 25", "0.0", " 35", "0.0", "146", "0.0", " 13", "0.0", " 23", "0.0", " 33", "0.0", " 16", "1.0", " 26", "0.0", " 36", "0.0", " 17", "0.0", " 27", "1.0", " 37", "0.0", " 76", "     0", "330", "23", "  0", "LAYOUT", "  5", "22", "102", "{ACAD_REACTORS", "330", "1A", "102", "}", "330", "1A", "100", "AcDbPlotSettings", "  1", "", "  2", "none_device", "  4", "Letter_(8.50_x_11.00_Inches)", "  6", "", " 40", "6.35", " 41", "6.35", " 42", "6.35000508", " 43", "6.35000508", " 44", "215.9", " 45", "279.4", " 46", "0.0", " 47", "0.0", " 48", "0.0", " 49", "0.0", "140", "0.0", "141", "0.0", "142", "1.0", "143", "1.0", " 70", "  1712", " 72", "     0", " 73", "     0", " 74", "     0", "  7", "", " 75", "     0", " 76", "     0", " 77", "     2", " 78", "   300", "147", "1.0", "148", "0.0", "149", "0.0", "100", "AcDbLayout", "  1", "Model", " 70", "     1", " 71", "     0", " 10", "0.0", " 20", "0.0", " 11", "12.0", " 21", "9.0", " 12", "0.0", " 22", "0.0", " 32", "0.0", " 14", "1913532.56", " 24", "14802744.55010417", " 34", "0.0", " 15", "1913887.913645833", " 25", "14802865.45010417", " 35", "0.0", "146", "0.0", " 13", "0.0", " 23", "0.0", " 33", "0.0", " 16", "1.0", " 26", "0.0", " 36", "0.0", " 17", "0.0", " 27", "1.0", " 37", "0.0", " 76", "     0", "330", "1F", "331", "29", "  0", "MATERIAL", "  5", "45", "102", "{ACAD_REACTORS", "330", "43", "102", "}", "330", "43", "100", "AcDbMaterial", "  1", "ByBlock", " 72", "     1", " 94", "      127", "  0", "MATERIAL", "  5", "44", "102", "{ACAD_REACTORS", "330", "43", "102", "}", "330", "43", "100", "AcDbMaterial", "  1", "ByLayer", " 72", "     1", " 94", "      127", "  0", "MATERIAL", "  5", "46", "102", "{ACAD_REACTORS", "330", "43", "102", "}", "330", "43", "100", "AcDbMaterial", "  1", "Global", " 72", "     1", " 94", "      127", "  0", "MLEADERSTYLE", "  5", "5C", "102", "{ACAD_REACTORS", "330", "5B", "102", "}", "330", "5B", "100", "AcDbMLeaderStyle", "179", "     2", "170", "     2", "171", "     1", "172", "     0", " 90", "        2", " 40", "0.0", " 41", "0.0", "173", "     1", " 91", "-1056964608", "340", "14", " 92", "       -2", "290", "     1", " 42", "0.09", "291", "     1", " 43", "0.36", "  3", "Standard", "341", "0", " 44", "0.18", "300", "", "342", "11", "174", "     1", "178", "     6", "175", "     1", "176", "     0", " 93", "-1056964608", " 45", "0.18", "292", "     0", "297", "     0", " 46", "0.18", "343", "0", " 94", "-1056964608", " 47", "1.0", " 49", "1.0", "140", "1.0", "293", "     1", "141", "0.0", "294", "     1", "177", "     0", "142", "1.0", "295", "     0", "296", "     0", "143", "0.125", "271", "     0", "272", "     9", "273", "     9", "298", "     0", "  0", "MLINESTYLE", "  5", "18", "102", "{ACAD_REACTORS", "330", "17", "102", "}", "330", "17", "100", "AcDbMlineStyle", "  2", "Standard", " 70", "     0", "  3", "", " 62", "   256", " 51", "90.0", " 52", "90.0", " 71", "     2", " 49", "0.5", " 62", "   256", "  6", "BYLAYER", " 49", "-0.5", " 62", "   256", "  6", "BYLAYER", "  0", "ACDBPLACEHOLDER", "  5", "F", "102", "{ACAD_REACTORS", "330", "E", "102", "}", "330", "E", "  0", "SCALE", "  5", "48", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1:1", "140", "1.0", "141", "1.0", "290", "     1", "  0", "SCALE", "  5", "49", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1/128\" = 1'-0\"", "140", "0.0078125", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "4A", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1/64\" = 1'-0\"", "140", "0.015625", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "4B", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1/32\" = 1'-0\"", "140", "0.03125", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "4C", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1/16\" = 1'-0\"", "140", "0.0625", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "4D", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "3/32\" = 1'-0\"", "140", "0.09375", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "4E", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1/8\" = 1'-0\"", "140", "0.125", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "4F", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "3/16\" = 1'-0\"", "140", "0.1875", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "50", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1/4\" = 1'-0\"", "140", "0.25", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "51", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "3/8\" = 1'-0\"", "140", "0.375", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "52", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1/2\" = 1'-0\"", "140", "0.5", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "53", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "3/4\" = 1'-0\"", "140", "0.75", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "54", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1\" = 1'-0\"", "140", "1.0", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "55", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1-1/2\" = 1'-0\"", "140", "1.5", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "56", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "3\" = 1'-0\"", "140", "3.0", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "57", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "6\" = 1'-0\"", "140", "6.0", "141", "12.0", "290", "     0", "  0", "SCALE", "  5", "58", "102", "{ACAD_REACTORS", "330", "47", "102", "}", "330", "47", "100", "AcDbScale", " 70", "     0", "300", "1'-0\" = 1'-0\"", "140", "12.0", "141", "12.0", "290", "     0", "  0", "TABLESTYLE", "  5", "5A", "102", "{ACAD_REACTORS", "330", "59", "102", "}", "102", "{ACAD_XDICTIONARY", "360", "B0", "102", "}", "330", "59", "100", "AcDbTableStyle", "  3", "Standard", " 70", "     0", " 71", "     0", " 40", "0.06", " 41", "0.06", "280", "     0", "281", "     0", "  7", "Standard", "140", "0.18", "170", "     2", " 62", "     0", " 63", "   257", "283", "     0", " 90", "        4", " 91", "        0", "  1", "", "274", "    -2", "284", "     1", " 64", "     0", "275", "    -2", "285", "     1", " 65", "     0", "276", "    -2", "286", "     1", " 66", "     0", "277", "    -2", "287", "     1", " 67", "     0", "278", "    -2", "288", "     1", " 68", "     0", "279", "    -2", "289", "     1", " 69", "     0", "  7", "Standard", "140", "0.25", "170", "     5", " 62", "     0", " 63", "   257", "283", "     0", " 90", "        4", " 91", "        0", "  1", "", "274", "    -2", "284", "     1", " 64", "     0", "275", "    -2", "285", "     1", " 65", "     0", "276", "    -2", "286", "     1", " 66", "     0", "277", "    -2", "287", "     1", " 67", "     0", "278", "    -2", "288", "     1", " 68", "     0", "279", "    -2", "289", "     1", " 69", "     0", "  7", "Standard", "140", "0.18", "170", "     5", " 62", "     0", " 63", "   257", "283", "     0", " 90", "        4", " 91", "        0", "  1", "", "274", "    -2", "284", "     1", " 64", "     0", "275", "    -2", "285", "     1", " 65", "     0", "276", "    -2", "286", "     1", " 66", "     0", "277", "    -2", "287", "     1", " 67", "     0", "278", "    -2", "288", "     1", " 68", "     0", "279", "    -2", "289", "     1", " 69", "     0", "  0", "VISUALSTYLE", "  5", "2F", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "2dWireframe", " 70", "     4", "177", "     3", "291", "     0", " 70", "    58", " 90", "        0", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "32", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Basic", " 70", "     7", "177", "     3", "291", "     1", " 70", "    58", " 90", "        1", "176", "     1", " 90", "        0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        0", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "36", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Brighten", " 70", "    12", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "50.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "3A", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "ColorChange", " 70", "    16", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     8", "420", "  8421504", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     8", "420", "  8421504", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "34", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Conceptual", " 70", "     9", "177", "     3", "291", "     0", " 70", "    58", " 90", "        3", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "179.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "35", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Dim", " 70", "    11", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "-50.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "3D", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "EdgeColorOff", " 70", "    22", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     0", " 90", "        2", "176", "     0", " 90", "        0", "176", "     0", " 90", "        0", "176", "     0", " 40", "0.6", "176", "     0", " 40", "30.0", "176", "     0", " 62", "     7", "420", " 16777215", "176", "     0", " 90", "        1", "176", "     0", " 90", "        4", "176", "     0", " 62", "     7", "176", "     0", " 62", "   257", "176", "     0", " 90", "        1", "176", "     0", " 90", "        1", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        8", "176", "     2", " 62", "     7", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        1", "176", "     0", " 90", "        6", "176", "     0", " 90", "        2", "176", "     0", " 62", "     7", "176", "     0", " 90", "        5", "176", "     0", " 90", "        0", "176", "     0", " 90", "        0", "176", "     0", "290", "     0", "176", "     0", " 90", "        1", "176", "     0", " 40", "0.0", "176", "     0", " 90", "        0", "176", "     0", "290", "     0", "176", "     0", "290", "     1", "176", "     0", "290", "     1", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 40", "0.0", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        0", "176", "     0", " 62", "    18", "420", "        0", "176", "     0", " 90", "       50", "176", "     0", " 90", "        3", "176", "     0", " 62", "     5", "420", "      255", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 90", "       50", "176", "     0", " 90", "       50", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     0", "  1", "strokes_ogs.tif", "176", "     0", "290", "     0", "176", "     0", " 40", "1.0", "176", "     0", " 40", "1.0", "176", "     0", "  0", "VISUALSTYLE", "  5", "39", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Facepattern", " 70", "    15", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "2B", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Flat", " 70", "     0", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "       13", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "2C", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "FlatWithEdges", " 70", "     1", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        0", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "       13", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "2D", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Gouraud", " 70", "     2", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "       13", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "2E", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "GouraudWithEdges", " 70", "     3", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        0", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "       13", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "31", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Hidden", " 70", "     6", "177", "     3", "291", "     0", " 70", "    58", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 40", "40.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "3B", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "JitterOff", " 70", "    20", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     0", " 90", "        2", "176", "     0", " 90", "        0", "176", "     0", " 90", "        0", "176", "     0", " 40", "0.6", "176", "     0", " 40", "30.0", "176", "     0", " 62", "     7", "420", " 16777215", "176", "     0", " 90", "        1", "176", "     0", " 90", "        4", "176", "     0", " 62", "     7", "176", "     0", " 62", "   257", "176", "     0", " 90", "        1", "176", "     0", " 90", "        1", "176", "     0", " 40", "1.0", "176", "     0", " 90", "       10", "176", "     2", " 62", "     7", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        1", "176", "     0", " 90", "        6", "176", "     0", " 90", "        2", "176", "     0", " 62", "     7", "176", "     0", " 90", "        5", "176", "     0", " 90", "        0", "176", "     0", " 90", "        0", "176", "     0", "290", "     0", "176", "     0", " 90", "        1", "176", "     0", " 40", "0.0", "176", "     0", " 90", "        0", "176", "     0", "290", "     0", "176", "     0", "290", "     1", "176", "     0", "290", "     1", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 40", "0.0", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        0", "176", "     0", " 62", "    18", "420", "        0", "176", "     0", " 90", "       50", "176", "     0", " 90", "        3", "176", "     0", " 62", "     5", "420", "      255", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 90", "       50", "176", "     0", " 90", "       50", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     0", "  1", "strokes_ogs.tif", "176", "     0", "290", "     0", "176", "     0", " 40", "1.0", "176", "     0", " 40", "1.0", "176", "     0", "  0", "VISUALSTYLE", "  5", "38", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Linepattern", " 70", "    14", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        7", "176", "     1", " 90", "        7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "3C", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "OverhangOff", " 70", "    21", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     0", " 90", "        2", "176", "     0", " 90", "        0", "176", "     0", " 90", "        0", "176", "     0", " 40", "0.6", "176", "     0", " 40", "30.0", "176", "     0", " 62", "     7", "420", " 16777215", "176", "     0", " 90", "        1", "176", "     0", " 90", "        4", "176", "     0", " 62", "     7", "176", "     0", " 62", "   257", "176", "     0", " 90", "        1", "176", "     0", " 90", "        1", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        9", "176", "     2", " 62", "     7", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        1", "176", "     0", " 90", "        6", "176", "     0", " 90", "        2", "176", "     0", " 62", "     7", "176", "     0", " 90", "        5", "176", "     0", " 90", "        0", "176", "     0", " 90", "        0", "176", "     0", "290", "     0", "176", "     0", " 90", "        1", "176", "     0", " 40", "0.0", "176", "     0", " 90", "        0", "176", "     0", "290", "     0", "176", "     0", "290", "     1", "176", "     0", "290", "     1", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 40", "0.0", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        0", "176", "     0", " 62", "    18", "420", "        0", "176", "     0", " 90", "       50", "176", "     0", " 90", "        3", "176", "     0", " 62", "     5", "420", "      255", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 90", "       50", "176", "     0", " 90", "       50", "176", "     0", "290", "     0", "176", "     0", " 90", "       50", "176", "     0", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     0", "  1", "strokes_ogs.tif", "176", "     0", "290", "     0", "176", "     0", " 40", "1.0", "176", "     0", " 40", "1.0", "176", "     0", "  0", "VISUALSTYLE", "  5", "33", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Realistic", " 70", "     8", "177", "     3", "291", "     0", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        2", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "       13", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "42", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Shaded", " 70", "    27", "177", "     3", "291", "     0", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        0", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     8", "420", "  7895160", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        5", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "41", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Shaded with edges", " 70", "    26", "177", "     3", "291", "     0", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "       10", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        5", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "3E", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Shades of Gray", " 70", "    23", "177", "     3", "291", "     0", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 62", "     7", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "40.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "3F", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Sketchy", " 70", "    24", "177", "     3", "291", "     0", " 70", "    58", " 90", "        1", "176", "     1", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 62", "     7", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "40.0", "176", "     1", " 90", "       11", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        6", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "37", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Thicken", " 70", "    13", "177", "     3", "291", "     1", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "       12", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        5", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "30", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "Wireframe", " 70", "     5", "177", "     3", "291", "     0", " 70", "    58", " 90", "        0", "176", "     1", " 90", "        2", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", " 40", "0.6", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        4", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "   257", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "VISUALSTYLE", "  5", "40", "102", "{ACAD_REACTORS", "330", "2A", "102", "}", "330", "2A", "100", "AcDbVisualStyle", "  2", "X-Ray", " 70", "    25", "177", "     3", "291", "     0", " 70", "    58", " 90", "        2", "176", "     1", " 90", "        2", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "0.5", "176", "     1", " 40", "30.0", "176", "     1", " 62", "     7", "420", " 16777215", "176", "     1", " 90", "        1", "176", "     1", " 90", "        0", "176", "     1", " 62", "     7", "176", "     1", " 62", "   257", "176", "     1", " 90", "        1", "176", "     1", " 90", "        1", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        8", "176", "     1", " 62", "     7", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        1", "176", "     1", " 90", "        6", "176", "     1", " 90", "        2", "176", "     1", " 62", "     7", "176", "     1", " 90", "        3", "176", "     1", " 90", "        0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", " 90", "       13", "176", "     1", " 40", "0.0", "176", "     1", " 90", "        0", "176", "     1", "290", "     0", "176", "     1", "290", "     1", "176", "     1", "290", "     1", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 40", "0.0", "176", "     1", " 40", "1.0", "176", "     1", " 90", "        0", "176", "     1", " 62", "    18", "420", "        0", "176", "     1", " 90", "       50", "176", "     1", " 90", "        3", "176", "     1", " 62", "     5", "420", "      255", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", " 90", "       50", "176", "     1", "290", "     0", "176", "     1", " 90", "       50", "176", "     1", " 62", "   256", "176", "     0", " 40", "1.0", "176", "     0", " 90", "        2", "176", "     1", "  1", "strokes_ogs.tif", "176", "     1", "290", "     0", "176", "     1", " 40", "1.0", "176", "     1", " 40", "1.0", "176", "     1", "  0", "DICTIONARYVAR", "  5", "AF", "102", "{ACAD_REACTORS", "330", "AE", "102", "}", "330", "AE", "100", "DictionaryVariables", "280", "     0", "  1", "1:1", "  0", "DICTIONARYVAR", "  5", "B4", "102", "{ACAD_REACTORS", "330", "AE", "102", "}", "330", "AE", "100", "DictionaryVariables", "280", "     0", "  1", "Standard", "  0", "DICTIONARYVAR", "  5", "B3", "102", "{ACAD_REACTORS", "330", "AE", "102", "}", "330", "AE", "100", "DictionaryVariables", "280", "     0", "  1", "Standard", "  0", "DICTIONARY", "  5", "B0", "330", "5A", "100", "AcDbDictionary", "280", "     1", "281", "     1", "  3", "ACAD_ROUNDTRIP_2008_TABLESTYLE_CELLSTYLEMAP", "360", "B1", "  0", "CELLSTYLEMAP", "  5", "B1", "102", "{ACAD_REACTORS", "330", "B0", "102", "}", "330", "B0", "100", "AcDbCellStyleMap", " 90", "        3", "300", "CELLSTYLE", "  1", "TABLEFORMAT_BEGIN", " 90", "        5", "170", "     1", " 91", "        0", " 92", "    32768", " 62", "   257", " 93", "        1", "300", "CONTENTFORMAT", "  1", "CONTENTFORMAT_BEGIN", " 90", "        0", " 91", "        0", " 92", "        4", " 93", "        0", "300", "", " 40", "0.0", "140", "1.0", " 94", "        5", " 62", "     0", "340", "11", "144", "0.25", "309", "CONTENTFORMAT_END", "171", "     1", "301", "MARGIN", "  1", "CELLMARGIN_BEGIN", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", "309", "CELLMARGIN_END", " 94", "        6", " 95", "        1", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        2", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        4", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        8", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "       16", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "       32", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", "309", "TABLEFORMAT_END", "  1", "CELLSTYLE_BEGIN", " 90", "        1", " 91", "        1", "300", "_TITLE", "309", "CELLSTYLE_END", "300", "CELLSTYLE", "  1", "TABLEFORMAT_BEGIN", " 90", "        5", "170", "     1", " 91", "        0", " 92", "        0", " 62", "   257", " 93", "        1", "300", "CONTENTFORMAT", "  1", "CONTENTFORMAT_BEGIN", " 90", "        0", " 91", "        0", " 92", "        4", " 93", "        0", "300", "", " 40", "0.0", "140", "1.0", " 94", "        5", " 62", "     0", "340", "11", "144", "0.18", "309", "CONTENTFORMAT_END", "171", "     1", "301", "MARGIN", "  1", "CELLMARGIN_BEGIN", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", "309", "CELLMARGIN_END", " 94", "        6", " 95", "        1", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        2", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        4", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        8", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "       16", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "       32", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", "309", "TABLEFORMAT_END", "  1", "CELLSTYLE_BEGIN", " 90", "        2", " 91", "        1", "300", "_HEADER", "309", "CELLSTYLE_END", "300", "CELLSTYLE", "  1", "TABLEFORMAT_BEGIN", " 90", "        5", "170", "     1", " 91", "        0", " 92", "        0", " 62", "   257", " 93", "        1", "300", "CONTENTFORMAT", "  1", "CONTENTFORMAT_BEGIN", " 90", "        0", " 91", "        0", " 92", "        4", " 93", "        0", "300", "", " 40", "0.0", "140", "1.0", " 94", "        2", " 62", "     0", "340", "11", "144", "0.18", "309", "CONTENTFORMAT_END", "171", "     1", "301", "MARGIN", "  1", "CELLMARGIN_BEGIN", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", " 40", "0.06", "309", "CELLMARGIN_END", " 94", "        6", " 95", "        1", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        2", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        4", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "        8", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "       16", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", " 95", "       32", "302", "GRIDFORMAT", "  1", "GRIDFORMAT_BEGIN", " 90", "        0", " 91", "        1", " 62", "     0", " 92", "       -2", "340", "14", " 93", "        0", " 40", "0.045", "309", "GRIDFORMAT_END", "309", "TABLEFORMAT_END", "  1", "CELLSTYLE_BEGIN", " 90", "        3", " 91", "        2", "300", "_DATA", "309", "CELLSTYLE_END", "  0", "ENDSEC", "  0", "EOF", ""];
function makeDXF(c){
 const ox=+$('cb_ox').value,oy=+$('cb_oy').value,bw=+$('cb_bw').value,bh=+$('cb_bh').value,th=+$('cb_th').value,L='ColorBar';
 let h=0x1000;const H=()=>(h++).toString(16).toUpperCase();
 const e=[];const p=(code,v)=>{e.push(String(code).padStart(3,' '));e.push(String(v));};
 const f6=v=>(+v).toFixed(4);
 let xmin=ox,xmax=ox+bw,ymax=oy,ymin=oy-c.length*bh;
 c.forEach((k,i)=>{const yt=oy-i*bh,yb=yt-bh,x0=ox,x1=ox+bw;
  p(0,'SOLID');p(5,H());p(330,'1F');p(100,'AcDbEntity');p(8,L);p(62,nearestACI(k.rgb));p(420,k.rgb[0]*65536+k.rgb[1]*256+k.rgb[2]);p(100,'AcDbTrace');
  p(10,f6(x0));p(20,f6(yt));p(30,'0.0');p(11,f6(x1));p(21,f6(yt));p(31,'0.0');p(12,f6(x0));p(22,f6(yb));p(32,'0.0');p(13,f6(x1));p(23,f6(yb));p(33,'0.0');
  const txt='{\\fArial|b0|i0|c1|p0;'+k.label.replace(/ /g,'\\~')+'}';
  const wid=th*0.62*k.label.length+th;xmax=Math.max(xmax,x1+bh*.32+wid);
  p(0,'MTEXT');p(5,H());p(330,'1F');p(100,'AcDbEntity');p(8,L);p(62,7);p(100,'AcDbMText');
  p(10,f6(x1+bh*.32));p(20,f6(yt-bh/2));p(30,'0.0');p(40,f6(th));p(41,f6(wid));p(46,'0.0');p(71,4);p(72,1);p(1,txt);p(73,1);p(44,'1.0');});
 const pre=TPL_PRE.slice();
 for(let i=0;i<pre.length-1;i++){
  if(pre[i]==='$EXTMIN'){pre[i+2]=f6(xmin);pre[i+4]=f6(ymin);pre[i+6]='0.0';}
  if(pre[i]==='$EXTMAX'){pre[i+2]=f6(xmax);pre[i+4]=f6(ymax);pre[i+6]='0.0';}
  if(pre[i]==='$HANDSEED'){pre[i+2]=h.toString(16).toUpperCase();}}
 return pre.concat(e,TPL_SUF).join('\r\n');}
function makeHCF(){const a=+$('cb_vmin').value,b=+$('cb_vmax').value;if(!isFinite(a)||!isFinite(b)||a===b)return null;
 const lo=Math.min(a,b),hi=Math.max(a,b),n=250,stp=(hi-lo)/n,flip=$('cb_flip').checked,rev=(b<a);const rows=[];
 for(let i=0;i<=n-1;i++){const d=lo+i*stp;let t=i/(n-1);if(rev)t=1-t;if(flip)t=1-t;rows.push(d.toFixed(2)+' '+toInt(colorAt(t)));}
 rows.push((hi+0.01).toFixed(2)+' '+toInt(colorAt((rev!==flip)?0:1)));
 const tail=[0,0,255,65535,65280,16776960,16711680,7237120,8551700,10524205,11446358,13158500,16777175,16750140,65280,4605440,65535,16432845,240,12505830,3298675,170677,85852];
 return [rows.length,lo.toFixed(2),hi.toFixed(2),stp.toFixed(2),...rows,...tail].join('\r\n')+'\r\n';}
function save(name,text){const u=URL.createObjectURL(new Blob([text],{type:'text/plain'}));const a=document.createElement('a');a.href=u;a.download=name;document.body.appendChild(a);a.click();setTimeout(()=>{a.remove();URL.revokeObjectURL(u);},500);}
$('cb_dl').onclick=()=>{const c=classes();if(!c){$('cb_msg').textContent='Check min / max / interval values.';return;}save(($('cb_fname').value||'COLOR_BAR')+'.dxf',makeDXF(c));$('cb_msg').textContent=c.length+' colour classes written.';};
$('cb_dlh').onclick=()=>{const t=makeHCF();if(!t){$('cb_msg').textContent='Check values.';return;}save(($('cb_fname').value||'COLOR_BAR')+'.hcf',t);};
$('cb_clr').onclick=()=>{
 fileMin=fileMax=null;ramp=null;
 $('cb_file').value='';$('cb_hcf').value='';$('cb_mode').value='depth';
 const d={vmin:0,vmax:50,step:8,ox:0,oy:0,bh:50,bw:38,th:18,dec:2,layer:'ColorBar',fname:'COLOR_BAR'};
 for(const k in d)if($('cb_'+k))$('cb_'+k).value=d[k];
 $('cb_round').checked=false;$('cb_flip').checked=false;$('cb_open').checked=true;
 $('cb_fileBox').style.display='';$('cb_msg').textContent='';draw();};
$('cb_fileBox').style.display='';draw();
})();</script>
</div>
</div>

<div class="footer"><button id="clearAllBtn" class="clearBtn">Clear all</button></div>

</main>

<script src="https://cdn.jsdelivr.net/npm/jszip@3.10.1/dist/jszip.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/geotiff@2.1.3/dist-browser/geotiff.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/proj4js/2.11.0/proj4.js"></script>
<script>

// Accept XYZ rows separated by spaces, tabs, or commas; all generated XYZ rows use spaces.
function splitXYZColumns(line) {
    return String(line).trim().split(/[\s,]+/).filter(Boolean);
}

function roundHalfUp(v, d) {
    const f = Math.pow(10, d);
    return (Math.sign(v) * Math.round(Math.abs(v) * f + 1e-9) / f).toFixed(d);
}



/* ============================================================
   TAB CONTROL
============================================================ */

function openConvertSubTab(paneId, button) {
    const container = (button && button.closest(".tab-content")) || document.getElementById("cvTab");
    container.querySelectorAll(".convert-sub-content").forEach(function(pane) {
        pane.classList.remove("active");
    });
    container.querySelectorAll(".convert-sub-button").forEach(function(btn) {
        btn.classList.remove("active");
    });
    document.getElementById(paneId).classList.add("active");
    button.classList.add("active");
}

function openTab(tabId, button) {

    document
        .querySelectorAll(".tab-content")
        .forEach(function(tab) {
            tab.classList.remove("active");
        });

    document
        .querySelectorAll(".tab-button")
        .forEach(function(btn) {
            btn.classList.remove("active");
        });

    document
        .getElementById(tabId)
        .classList.add("active");

    button.classList.add("active");
}




/* ============================================================
   GLOBAL VARIABLES
============================================================ */

let mtxOutputText = "";
let mtxOriginalFileName = "";

let chnOutputText = "";
let chnOriginalFileName = "";



/* ============================================================
   EXTRACT XYZ - SIMPLE UNIFIED TOOL
============================================================ */

let extractOutputText = "";
let extractOriginalFileName = "";

const extractType = document.getElementById("extractType");
const extractFile = document.getElementById("extractFile");
const extractProcessBtn = document.getElementById("extractProcessBtn");
const extractDownloadBtn = document.getElementById("extractDownloadBtn");
const extractClearBtn = document.getElementById("extractClearBtn");
const extractStatus = document.getElementById("extractStatus");
const extractResult = document.getElementById("extractResult");
const extractFileName = document.getElementById("extractFileName");
const mtxZRow = document.getElementById("mtxZRow");
const extractMtxZ = document.getElementById("extractMtxZ");

function updateExtractFileType(){
    const type = extractType.value;
    if(type === "mtx") {
        extractFile.accept = ".mtx,.txt";
        mtxZRow.style.display = "block";
    } else if(type === "chn") {
        extractFile.accept = ".chn,.txt";
        mtxZRow.style.display = "none";
    } else if(type === "googleLines") {
        extractFile.accept = ".kml,.xml,.kmz";
        mtxZRow.style.display = "none";
    } else {
        extractFile.accept = ".dxf";
        mtxZRow.style.display = "none";
    }
    extractFile.value = "";
    extractFileName.textContent = "No file selected";
    extractProcessBtn.disabled = true;
    extractDownloadBtn.style.display = "none";
    extractStatus.innerHTML = "";
    extractResult.textContent = "";
    extractOutputText = "";
    extractOriginalFileName = "";
}

extractType.addEventListener("change", updateExtractFileType);

extractFile.addEventListener("change", function(){
    if(this.files.length){
        extractFileName.textContent = this.files[0].name;
        extractProcessBtn.disabled = false;
    } else {
        extractFileName.textContent = "No file selected";
        extractProcessBtn.disabled = true;
    }
    extractDownloadBtn.style.display = "none";
    extractStatus.innerHTML = "";
    extractResult.textContent = "";
    extractOutputText = "";
});

extractProcessBtn.addEventListener("click", async function(){
    if(!extractFile.files.length){
        alert("Please select a file.");
        return;
    }

    const type = extractType.value;
    const file = extractFile.files[0];
    extractOriginalFileName = file.name;
    extractOutputText = "";
    extractDownloadBtn.style.display = "none";
    extractResult.textContent = "";
    extractStatus.innerHTML = "<div class='info'>Processing...</div>";

    try {
        if(type === "mtx") {
            const z = Number(extractMtxZ.value);
            if(!Number.isFinite(z)) throw new Error("Please enter a valid Corner Z value.");

            const text = await file.text();
            const values = extractMTXValues(text);
            if(values.length < 7) throw new Error("Could not find the required 7 MTX values. Values found: " + values.length);

            const corners = calculateCorners(values[0], values[1], values[2], values[3], values[6], z);
            extractOutputText = corners.map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(1);
            }).join("\n")+"\n";

            extractResult.textContent = extractOutputText;
            extractStatus.innerHTML = "<div class='success'><strong>MTX processing complete.</strong><br><br>4 corner XYZ points created.</div>";
        }
        else if(type === "chn") {
            const text = await file.text();
            const points = extractCHNNodes(text);
            if(!points.length) throw new Error("No CHN nodes were found.");

            extractOutputText = points.map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n")+"\n";

            extractResult.textContent = points.slice(0,20).map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n") + (points.length>20 ? "\n\n... "+(points.length-20).toLocaleString()+" more points ..." : "");
            extractStatus.innerHTML = "<div class='success'><strong>CHN processing complete.</strong><br><br>Nodes extracted: "+points.length.toLocaleString()+"</div>";
        }
        else if(type === "dxf") {
            const text = await file.text();
            const nodes = processDXFText(text);
            if(!nodes.length) throw new Error("No channel XYZ nodes were found in the DXF file.");

            extractOutputText = nodes.map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n")+"\n";

            extractResult.textContent = nodes.slice(0,20).map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n") + (nodes.length>20 ? "\n\n... "+(nodes.length-20).toLocaleString()+" more points ..." : "");
            extractStatus.innerHTML = "<div class='success'><strong>DXF channel-node processing complete.</strong><br><br>Final unique channel nodes: "+nodes.length.toLocaleString()+"</div>";
        }
        else if(type === "googleLines") {
            let text;
            if (/\.kmz$/i.test(file.name)) {
                if (typeof JSZip === "undefined") throw new Error("KMZ support could not load. Check your internet connection and reload this page.");
                const zip = await JSZip.loadAsync(await file.arrayBuffer());
                const kmlEntries = Object.keys(zip.files).filter(function(name) {
                    return !zip.files[name].dir && /\.kml$/i.test(name);
                });
                if (!kmlEntries.length) throw new Error("No KML file was found inside this KMZ archive.");
                const preferred = kmlEntries.find(function(name) { return /(^|\/)doc\.kml$/i.test(name); }) || kmlEntries[0];
                text = await zip.file(preferred).async("text");
            } else {
                text = await file.text();
            }
            const nodes = processGoogleLinesKML(text);
            if(!nodes.length) throw new Error("No Google line nodes were found. Please select a KML, XML, or KMZ file containing one or more LineString geometries.");

            extractOutputText = nodes.map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n")+"\n";

            extractResult.textContent = nodes.slice(0,20).map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n") + (nodes.length>20 ? "\n\n... "+(nodes.length-20).toLocaleString()+" more nodes ..." : "");
            extractStatus.innerHTML = "<div class='success'><strong>Google Lines to NYLI XYZ processing complete.</strong><br><br>Unique nodes extracted: "+nodes.length.toLocaleString()+"<br>Output coordinate system: NAD83 / New York Long Island (EPSG:2263), US survey feet.</div>";
        }
        else if(type === "contourDxf") {
            const text = await file.text();
            const nodes = processContourDXFText(text);
            if(!nodes.length) throw new Error("No contour vertices were found. Check that the DXF contains standard contour geometry.");

            extractOutputText = nodes.map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\r\n")+"\r\n";

            extractResult.textContent = nodes.slice(0,20).map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n") + (nodes.length>20 ? "\n\n... "+(nodes.length-20).toLocaleString()+" more points ..." : "");
            extractStatus.innerHTML = "<div class='success'><strong>Contour DXF processing complete.</strong><br><br>Unique contour XYZ points: "+nodes.length.toLocaleString()+"</div>";
        }
        else if(type === "soundingDxf") {
            const text = await file.text();
            const result = processSoundingDXFText(text);
            const nodes = result.points;
            if(!nodes.length) throw new Error("No sounding XYZ points were found. This workflow expects HYPACK sounding DXF XDATA or supported point entities.");

            extractOutputText = nodes.map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\r\n")+"\r\n";

            extractResult.textContent = nodes.slice(0,20).map(function(p){
                return p.x.toFixed(3)+" "+p.y.toFixed(3)+" "+p.z.toFixed(3);
            }).join("\n") + (nodes.length>20 ? "\n\n... "+(nodes.length-20).toLocaleString()+" more points ..." : "");
            extractStatus.innerHTML = "<div class='success'><strong>Sounding DXF processing complete.</strong><br><br>Unique XYZ points: "+nodes.length.toLocaleString()+"<br>Using HYPACK sounding positions: "+result.hypack.toLocaleString()+"<br>Fallback TEXT positions: "+result.fallback.toLocaleString()+"</div>";
        }

        extractDownloadBtn.style.display = "inline-block";
    } catch(e) {
        console.error(e);
        extractStatus.innerHTML = "<div class='error'><strong>Error:</strong><br>" + String(e.message || e).replace(/[&<>]/g,function(c){return {'&':'&amp;','<':'&lt;','>':'&gt;'}[c];}) + "</div>";
    }
});

extractDownloadBtn.addEventListener("click", function(){
    if(!extractOutputText){
        alert("Please process a file first.");
        return;
    }
    const type = extractType.value;
    const base = extractOriginalFileName.replace(/\.[^/.]+$/, "");
    const suffix = type === "mtx" ? "_four_corners.xyz"
        : type === "googleLines" ? "_NYLI_nodes.xyz"
        : type === "contourDxf" ? "_contour_points.xyz"
        : type === "soundingDxf" ? "_sounding_points.xyz"
        : "_nodes.xyz";
    const url = URL.createObjectURL(new Blob([extractOutputText], {type:"text/plain;charset=utf-8"}));
    const a = document.createElement("a");
    a.href = url;
    a.download = base + suffix;
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    setTimeout(function(){URL.revokeObjectURL(url);},1000);
});

extractClearBtn.addEventListener("click", function(){
    extractFile.value = "";
    extractFileName.textContent = "No file selected";
    extractStatus.innerHTML = "";
    extractResult.textContent = "";
    extractDownloadBtn.style.display = "none";
    extractProcessBtn.disabled = true;
    extractOutputText = "";
    extractOriginalFileName = "";
});

updateExtractFileType();

/* ============================================================
   EXTRACT MTX VALUES
============================================================ */

function extractMTXValues(text) {


    const lines =
        text.split(/\r?\n/);


    let values = [];


    for (let line of lines) {


        line =
            line.trim();


        if (line === "") {

            continue;

        }


        /*
         * Remove comments.
         */

        line =
            line.replace(
                /#.*$/,
                ""
            );


        line =
            line.replace(
                /\/\/.*$/,
                ""
            );


        if (line.trim() === "") {

            continue;

        }


        /*
         * Find numbers.
         */

        const matches =
            line.match(
                /[-+]?(?:\d+(?:\.\d*)?|\.\d+)(?:[Ee][-+]?\d+)?/g
            );


        if (
            matches &&
            matches.length > 0
        ) {

            const value =
                Number(matches[0]);


            if (
                Number.isFinite(value)
            ) {

                values.push(value);

            }

        }

    }


    return values;

}



/* ============================================================
   CALCULATE FOUR CORNERS
============================================================ */

function calculateCorners(
    x0,
    y0,
    width,
    length,
    bearingDeg,
    z
) {


    /*
     * Bearing is clockwise from North.
     *
     * 0°   = North
     * 90°  = East
     * 180° = South
     * 270° = West
     */


    const bearing =
        bearingDeg *
        Math.PI /
        180;


    /*
     * First leg direction.
     */

    const ux =
        Math.sin(bearing);

    const uy =
        Math.cos(bearing);


    /*
     * Perpendicular direction.
     *
     * Clockwise numbering.
     */

    const vx =
        Math.cos(bearing);

    const vy =
        -Math.sin(bearing);


    /*
     * Corner 1
     */

    const p1 = {

        x: x0,
        y: y0,
        z: z

    };


    /*
     * Corner 2
     */

    const p2 = {

        x:
            x0 +
            length * ux,

        y:
            y0 +
            length * uy,

        z: z

    };


    /*
     * Corner 3
     */

    const p3 = {

        x:
            x0 +
            length * ux +
            width * vx,

        y:
            y0 +
            length * uy +
            width * vy,

        z: z

    };


    /*
     * Corner 4
     */

    const p4 = {

        x:
            x0 +
            width * vx,

        y:
            y0 +
            width * vy,

        z: z

    };


    return [
        p1,
        p2,
        p3,
        p4
    ];

}



/* ============================================================
   EXTRACT CHN NODES
============================================================ */

function extractCHNNodes(text) {

    const lines = text.split(/\r?\n/);

    let points = [];
    const seen = new Set();

    /*
     * HYPACK CHN structure:
     *
     * NODES <number of nodes>
     * X Y Z NodeNumber
     * X Y Z NodeNumber
     * ...
     *
     * The node section ends when FACES, SEGMENTS,
     * LABELS, ZONES, ELEVATION, or another section
     * begins.
     */

    let inNodesSection = false;
    let expectedNodes = 0;

    for (let line of lines) {

        line = line.trim();

        if (line === "") {
            continue;
        }

        /*
         * Start of NODES section.
         */

        const nodesMatch = line.match(/^NODES\s+(\d+)/i);

        if (nodesMatch) {

            inNodesSection = true;
            expectedNodes = Number(nodesMatch[1]);

            continue;
        }

        /*
         * Stop when another CHN section begins.
         */

        if (
            /^(FACES|SEGMENTS|LABELS|ZONES|ELEVATION|\[Settings\])/i.test(line)
        ) {

            if (inNodesSection) {
                break;
            }

            continue;
        }

        if (!inNodesSection) {
            continue;
        }

        /*
         * Convert commas and tabs to spaces.
         */

        const parts = line
            .replace(/,/g, " ")
            .trim()
            .split(/\s+/);

        if (parts.length < 4) {
            continue;
        }

        /*
         * Actual HYPACK CHN node format:
         *
         * X Y Z NodeNumber
         */

        const x = Number(parts[0]);
        const y = Number(parts[1]);
        const z = Number(parts[2]);
        const node = Number(parts[3]);

        /*
         * All four values must be numeric.
         */

        if (
            !Number.isFinite(x) ||
            !Number.isFinite(y) ||
            !Number.isFinite(z) ||
            !Number.isFinite(node)
        ) {
            continue;
        }

        /*
         * Node number must be an integer.
         */

        if (
            Math.abs(node - Math.round(node)) > 0.000001
        ) {
            continue;
        }

        /*
         * State Plane coordinate check.
         */

        if (
            Math.abs(x) < 100000 ||
            Math.abs(y) < 10000
        ) {
            continue;
        }

        /*
         * Prevent duplicate XYZ points.
         */

        const key =
            x.toFixed(6) +
            "|" +
            y.toFixed(6) +
            "|" +
            z.toFixed(6);

        if (seen.has(key)) {
            continue;
        }

        seen.add(key);

        /*
         * Save only X Y Z.
         */

        points.push({
            x: x,
            y: y,
            z: z
        });

        /*
         * If the declared number of nodes has
         * been reached, stop reading nodes.
         */

        if (
            expectedNodes > 0 &&
            points.length >= expectedNodes
        ) {
            break;
        }
    }

    return points;
}


/* ============================================================
   CONTOUR DXF -> XYZ POINTS
   Extracts all stored vertices from common contour entities.
============================================================ */

function processContourDXFText(text){
    const pairs = makePairs(text);
    const entities = splitEntities(pairs);
    const points = [];

    function addPoint(x,y,z){
        if(Number.isFinite(x) && Number.isFinite(y) && Number.isFinite(z)){
            points.push({x:x,y:y,z:z});
        }
    }
    function num(entity, code, fallback=null){
        const item = entity.find(p => p.code === code);
        if(!item) return fallback;
        const n = Number(item.value);
        return Number.isFinite(n) ? n : fallback;
    }

    for(let i=0;i<entities.length;i++){
        const entity = entities[i];
        const type = getEntityType(entity);

        if(type === "POINT"){
            addPoint(num(entity,10),num(entity,20),num(entity,30,0));
        } else if(type === "LINE"){
            addPoint(num(entity,10),num(entity,20),num(entity,30,0));
            addPoint(num(entity,11),num(entity,21),num(entity,31,0));
        } else if(type === "LWPOLYLINE"){
            const elevation = num(entity,38,0);
            let x = null, y = null;
            for(const p of entity){
                if(p.code === 10){
                    if(x !== null && y !== null) addPoint(x,y,elevation);
                    x = Number(p.value); y = null;
                } else if(p.code === 20 && x !== null){
                    y = Number(p.value);
                    addPoint(x,y,elevation);
                    x = null; y = null;
                }
            }
        } else if(type === "POLYLINE"){
            let j = i + 1;
            const vertices = [];
            for(;j<entities.length;j++){
                const nextType = getEntityType(entities[j]);
                if(nextType === "VERTEX"){
                    const v = entities[j];
                    addPoint(num(v,10),num(v,20),num(v,30,0));
                    vertices.push(v);
                } else if(nextType === "SEQEND"){
                    break;
                } else {
                    break;
                }
            }
            i = j;
        } else if(type === "VERTEX"){
            // Normally consumed with its parent POLYLINE; standalone records are still usable.
            addPoint(num(entity,10),num(entity,20),num(entity,30,0));
        } else if(type === "3DFACE"){
            for(let k=0;k<4;k++){
                addPoint(num(entity,10+k),num(entity,20+k),num(entity,30+k,0));
            }
        } else if(type === "SPLINE"){
            // DXF SPLINE control points are stored as repeated 10/20/30 groups.
            let x=null,y=null,z=0;
            for(const p of entity){
                if(p.code===10){
                    x=Number(p.value); y=null; z=0;
                } else if(p.code===20 && x!==null){
                    y=Number(p.value);
                } else if(p.code===30 && x!==null){
                    z=Number(p.value);
                    if(y!==null){addPoint(x,y,z);x=null;y=null;z=0;}
                }
            }
            if(x!==null && y!==null) addPoint(x,y,z);
        }
    }
    return removeDuplicates(points);
}

/* ============================================================
   SOUNDING DXF -> XYZ POINTS
   Prefer HYPACK XDATA sounding positions (1011/1021/1031)
   over shifted TEXT label insertion positions (10/20/30).
============================================================ */

function processSoundingDXFText(text){
    const pairs = makePairs(text);
    const entities = splitEntities(pairs);
    const points = [];
    let hypack = 0, fallback = 0;

    function num(entity, code, fallbackValue=null){
        const item = entity.find(p => p.code === code);
        if(!item) return fallbackValue;
        const n = Number(item.value);
        return Number.isFinite(n) ? n : fallbackValue;
    }
    function addPoint(x,y,z){
        if(Number.isFinite(x) && Number.isFinite(y) && Number.isFinite(z)){
            points.push({x:x,y:y,z:z});
        }
    }

    for(const entity of entities){
        const type = getEntityType(entity);
        if(type === "TEXT" || type === "MTEXT"){
            const hx = num(entity,1011);
            const hy = num(entity,1021);
            let hz = num(entity,1031);
            if(hx !== null && hy !== null){
                if(hz === null) hz = num(entity,30,0);
                addPoint(hx,hy,hz);
                hypack++;
            } else {
                const x = num(entity,10), y = num(entity,20), z = num(entity,30,0);
                addPoint(x,y,z);
                if(Number.isFinite(x) && Number.isFinite(y) && Number.isFinite(z)) fallback++;
            }
        } else if(type === "POINT"){
            addPoint(num(entity,10),num(entity,20),num(entity,30,0));
        }
    }

    return {points:removeDuplicates(points), hypack:hypack, fallback:fallback};
}

/* ============================================================
   GOOGLE KML LINE -> NYLI (EPSG:2263, US SURVEY FEET)
============================================================ */
function processGoogleLinesKML(text){
    if(typeof proj4 === "undefined") throw new Error("Coordinate conversion library did not load. Connect to the internet and reload the page.");
    // NAD83 / New York Long Island, US survey feet (EPSG:2263).
    const nyli = "+proj=lcc +lat_1=41.03333333333333 +lat_2=40.66666666666666 +lat_0=40.16666666666666 +lon_0=-74 +x_0=300000 +y_0=0 +datum=NAD83 +units=us-ft +no_defs";
    const xml = new DOMParser().parseFromString(text, "application/xml");
    if(xml.querySelector("parsererror")) throw new Error("The selected file is not valid KML/XML.");
    const lineStrings = Array.from(xml.getElementsByTagNameNS("*", "LineString"));
    const raw = [];
    lineStrings.forEach(function(line){
        const coordinateNodes = Array.from(line.getElementsByTagNameNS("*", "coordinates"));
        coordinateNodes.forEach(function(coordNode){
            (coordNode.textContent || "").trim().split(/\s+/).forEach(function(token){
                if(!token) return;
                const parts = token.split(",");
                if(parts.length < 2) return;
                const lon = Number(parts[0]);
                const lat = Number(parts[1]);
                const z = parts.length > 2 && parts[2] !== "" ? Number(parts[2]) : 0;
                if(!Number.isFinite(lon) || !Number.isFinite(lat) || !Number.isFinite(z)) return;
                const xy = proj4("EPSG:4326", nyli, [lon, lat]);
                raw.push({x:xy[0], y:xy[1], z:z});
            });
        });
    });
    // Remove duplicate vertices while retaining the original line/node order.
    const seen = new Set();
    return raw.filter(function(p){
        const key = p.x.toFixed(4)+"|"+p.y.toFixed(4)+"|"+p.z.toFixed(3);
        if(seen.has(key)) return false;
        seen.add(key);
        return true;
    });
}

/* ============================================================
   DXF PARSER USED BY UNIFIED EXTRACT XYZ TOOL
============================================================ */

function processDXFText(text){
    /*
      Extract channel-like DXF geometry, then discard unrelated drawing
      geometry by selecting the strongest spatial cluster. No fixed State
      Plane coordinate threshold is used.
    */
    const pairs = makePairs(text);
    const entities = splitEntities(pairs);
    const candidates = [];

    function value(entity, code, fallback=null){
        const item = entity.find(p => p.code === code);
        if(!item) return fallback;
        const n = Number(item.value);
        return Number.isFinite(n) ? n : fallback;
    }
    function addCandidate(entity, points){
        points = points.filter(p =>
            p && Number.isFinite(p.x) && Number.isFinite(p.y) && Number.isFinite(p.z)
        );
        if(points.length < 2) return;
        const layer = (entity.find(p => p.code === 8) || {value:""}).value.toUpperCase();
        const nonZeroZ = points.filter(p => Math.abs(p.z) > 1e-7).length;
        const zRange = Math.max(...points.map(p=>p.z)) - Math.min(...points.map(p=>p.z));
        candidates.push({
            points, layer,
            cx: points.reduce((s,p)=>s+p.x,0)/points.length,
            cy: points.reduce((s,p)=>s+p.y,0)/points.length,
            nonZeroZ,
            zRange,
            channelLayer: /CHAN|CHANNEL|TOE|SLOPE|BANK|DREDG|THALWEG|BOTTOM/.test(layer)
        });
    }

    for(let i=0;i<entities.length;i++){
        const entity = entities[i];
        const type = getEntityType(entity);

        if(type === "LINE"){
            const p1 = {x:value(entity,10), y:value(entity,20), z:value(entity,30,0)};
            const p2 = {x:value(entity,11), y:value(entity,21), z:value(entity,31,0)};
            addCandidate(entity,[p1,p2]);
        } else if(type === "LWPOLYLINE"){
            const elevation = value(entity,38,0);
            const vertices = [];
            let x=null, y=null;
            for(const p of entity){
                if(p.code===10){
                    x=Number(p.value); y=null;
                } else if(p.code===20 && x!==null){
                    y=Number(p.value);
                    if(Number.isFinite(x) && Number.isFinite(y)) vertices.push({x,y,z:elevation});
                    x=null; y=null;
                }
            }
            addCandidate(entity,vertices);
        } else if(type === "POLYLINE"){
            let flags = value(entity,70,0);
            const vertices=[];
            let j=i+1;
            for(;j<entities.length;j++){
                const t=getEntityType(entities[j]);
                if(t==="VERTEX"){
                    const v=entities[j];
                    const x=value(v,10), y=value(v,20), z=value(v,30,0);
                    if(x!==null && y!==null) vertices.push({x,y,z});
                } else if(t==="SEQEND") break;
                else break;
            }
            // Extract vertices from both 2D and 3D POLYLINE entities.
            addCandidate(entity,vertices);
            i=j;
        }
    }

    if(!candidates.length) return [];

    // Build a scale-relative spatial clustering threshold. This separates
    // paper-space/title-block geometry from model-space channel geometry
    // even when the drawing uses a different coordinate reference system.
    const allPoints = candidates.flatMap(c=>c.points);
    const minX=Math.min(...allPoints.map(p=>p.x)), maxX=Math.max(...allPoints.map(p=>p.x));
    const minY=Math.min(...allPoints.map(p=>p.y)), maxY=Math.max(...allPoints.map(p=>p.y));
    const diagonal=Math.hypot(maxX-minX,maxY-minY);
    const threshold=Math.max(10, diagonal*0.10);

    const visited=new Set();
    const clusters=[];
    for(let i=0;i<candidates.length;i++){
        if(visited.has(i)) continue;
        const stack=[i], cluster=[];
        visited.add(i);
        while(stack.length){
            const k=stack.pop(), c=candidates[k];
            cluster.push(c);
            for(let j=0;j<candidates.length;j++){
                if(visited.has(j)) continue;
                const other=candidates[j];
                if(Math.hypot(c.cx-other.cx,c.cy-other.cy)<=threshold){
                    visited.add(j);
                    stack.push(j);
                }
            }
        }
        clusters.push(cluster);
    }

    function clusterScore(cluster){
        let score=0;
        for(const c of cluster){
            score += 1;
            if(c.nonZeroZ) score += 5 + Math.min(c.nonZeroZ,5);
            if(c.zRange > 1e-6) score += 3;
            if(c.channelLayer) score += 8;
        }
        return score;
    }

    // Prefer the cluster most likely to represent channel/model geometry.
    // Non-zero elevations and channel-related layer names are strong clues;
    // if none exist, the largest connected geometry cluster wins.
    clusters.sort((a,b)=>clusterScore(b)-clusterScore(a));
    const selected=clusters[0];

    const points=[];
    for(const c of selected) points.push(...c.points);
    return removeDuplicates(points);
}
function makePairs(text){
    const lines=text.replace(/\r/g,"").split("\n"), pairs=[];
    for(let i=0;i+1<lines.length;i+=2){
        const code=Number(lines[i].trim());
        if(!Number.isFinite(code)) continue;
        pairs.push({code,value:lines[i+1].trim()});
    }
    return pairs;
}

function splitEntities(pairs){
    const entities=[]; let inside=false, current=null;
    for(const p of pairs){
        if(p.code===2 && p.value.toUpperCase()==="ENTITIES"){inside=true;continue;}
        if(!inside) continue;
        if(p.code===0 && p.value.toUpperCase()==="ENDSEC"){
            if(current) entities.push(current);
            break;
        }
        if(p.code===0){
            if(current) entities.push(current);
            current=[p];
        } else if(current) current.push(p);
    }
    return entities;
}

function getEntityType(e){
    const p=e.find(x=>x.code===0);
    return p ? p.value.toUpperCase() : "";
}

function parseLWPolyline(entity){
    const vertices=[]; let x=null,y=null,z=0;
    for(const p of entity){
        if(p.code===10){
            if(x!==null && y!==null) vertices.push({x,y,z});
            x=Number(p.value); y=null; z=0;
        } else if(p.code===20 && x!==null) y=Number(p.value);
        else if(p.code===30 && x!==null) z=Number(p.value);
    }
    if(x!==null && y!==null) vertices.push({x,y,z});
    return vertices;
}

function removeDuplicates(points){
    const result=[], seen=new Set();
    for(const p of points){
        const x=Number(p.x.toFixed(9)), y=Number(p.y.toFixed(9)), z=Number(p.z.toFixed(9));
        const key=x+"|"+y+"|"+z;
        if(!seen.has(key)){seen.add(key);result.push({x,y,z});}
    }
    return result;
}


/* ============================================================
   COMBINE XYZ
============================================================ */

let combineParts = [];
let combineOutputReady = false;

const combineProcessBtn = document.getElementById("combineProcessBtn");
const combineDownloadBtn = document.getElementById("combineDownloadBtn");
const combineStatus = document.getElementById("combineStatus");
const combineRemoveOverlap = document.getElementById("combineRemoveOverlap");
const combineOverlapMethods = document.getElementById("combineOverlapMethods");
const combineOverlapMinimum = document.getElementById("combineOverlapMinimum");
const combineOverlapAverage = document.getElementById("combineOverlapAverage");
const combineOverlapSecond = document.getElementById("combineOverlapSecond");
const combineOverlapDistance = document.getElementById("combineOverlapDistance");
function overlapRuleText(method) {
    return method === "average"
        ? "points of the later file within the overlap distance are removed; first-file Z becomes the average of the two nearest points; first-file XY unchanged."
        : method === "second"
        ? "points of the later file within the overlap distance are removed; first-file Z is replaced by the later file's Z; first-file XY unchanged."
        : "points of the later file within the overlap distance are removed; first-file Z becomes the shallower (closest to zero) of the two nearest points; first-file XY unchanged.";
}
const combineZAdjustment = document.getElementById("combineZAdjustment");
const combineInvertZ = document.getElementById("combineInvertZ");
const combineRound = document.getElementById("combineRound");
combineOverlapMethods.style.opacity = combineRemoveOverlap.checked ? "1" : "0.55";
combineRemoveOverlap.addEventListener("change", function () {
    combineOverlapMethods.style.opacity = this.checked ? "1" : "0.55";
});

function setCombineStatus(message, type) {
    combineStatus.className = type || "";
    combineStatus.textContent = message;
}

/*
   Combine overlapping survey points for safe navigation.
   Points with exactly matching XY coordinates are overlapping. Keep the point whose
   Z has the smallest absolute value (closest to zero), preserving its X/Y.
   This selects 10.1 over 10.2 and -10.1 over -10.2.
*/
function parseXYZForOverlap(text) {
    const points = [];
    const lines = text.split(/\r?\n/);
    for (const line of lines) {
        const trimmed = line.trim();
        if (!trimmed) continue;
        const parts = splitXYZColumns(trimmed);
        if (parts.length < 3) continue;
        const x = Number(parts[0]), y = Number(parts[1]), z = Number(parts[2]);
        if (Number.isFinite(x) && Number.isFinite(y) && Number.isFinite(z)) {
            points.push({x, y, z, line: trimmed, active: true});
        }
    }
    return points;
}

/* Spatial grid helpers (numeric keys, chained indices) */
function ovGridKey(ix, iy) { return ix * 67108864 + iy; }
function ovBuildGrid(xs, ys, cell, minX, minY) {
    const head = new Map(), next = new Int32Array(xs.length).fill(-1);
    for (let i = 0; i < xs.length; i++) {
        const k = ovGridKey(Math.floor((xs[i] - minX) / cell), Math.floor((ys[i] - minY) / cell));
        const h = head.get(k);
        next[i] = h === undefined ? -1 : h;
        head.set(k, i);
    }
    return {head, next, cell, minX, minY};
}
/* nearest point of the grid to (x, y) closer than maxDist (grid cell must be >= maxDist); skipZero ignores identical points */
function ovNearest(grid, xs, ys, x, y, maxDist, skipZero) {
    const ix = Math.floor((x - grid.minX) / grid.cell), iy = Math.floor((y - grid.minY) / grid.cell);
    let best = -1, bestD2 = maxDist * maxDist;
    for (let dx = -1; dx <= 1; dx++) for (let dy = -1; dy <= 1; dy++) {
        let i = grid.head.get(ovGridKey(ix + dx, iy + dy));
        while (i !== undefined && i !== -1) {
            const ex = xs[i] - x, ey = ys[i] - y, d2 = ex * ex + ey * ey;
            if (d2 <= bestD2 && !(skipZero && d2 === 0)) { bestD2 = d2; best = i; }
            i = grid.next[i];
        }
    }
    return best < 0 ? null : {index: best, dist: Math.sqrt(bestD2)};
}
/* Average distance from a point to its closest neighbour (sampled for very large files) */
function ovAverageSpacing(xs, ys) {
    const n = xs.length;
    if (n < 2) return 1;
    let minX = Infinity, minY = Infinity, maxX = -Infinity, maxY = -Infinity;
    for (let i = 0; i < n; i++) {
        if (xs[i] < minX) minX = xs[i]; if (xs[i] > maxX) maxX = xs[i];
        if (ys[i] < minY) minY = ys[i]; if (ys[i] > maxY) maxY = ys[i];
    }
    const extent = Math.max(maxX - minX, maxY - minY, 1e-9);
    let cell = Math.max(Math.sqrt(((maxX - minX) * (maxY - minY)) / n), extent / 6e7, 1e-6);
    let grid = ovBuildGrid(xs, ys, cell, minX, minY);
    for (let k = 0; k < 8 && n / grid.head.size > 30; k++) {      /* clustered data: use smaller cells */
        cell = Math.max(cell / 2, extent / 6e7);
        grid = ovBuildGrid(xs, ys, cell, minX, minY);
    }
    const step = Math.max(1, Math.floor(n / 30000));
    let sum = 0, count = 0;
    for (let i = 0; i < n; i += step) {
        const ix = Math.floor((xs[i] - minX) / cell), iy = Math.floor((ys[i] - minY) / cell);
        let best2 = Infinity;
        for (let r = 0; r <= 6; r++) {
            for (let dx = -r; dx <= r; dx++) for (let dy = -r; dy <= r; dy++) {
                if (Math.max(Math.abs(dx), Math.abs(dy)) !== r) continue;
                let j = grid.head.get(ovGridKey(ix + dx, iy + dy));
                while (j !== undefined && j !== -1) {
                    if (j !== i) {
                        const ex = xs[j] - xs[i], ey = ys[j] - ys[i], d2 = ex * ex + ey * ey;
                        if (d2 > 0 && d2 < best2) best2 = d2;
                    }
                    j = grid.next[j];
                }
            }
            if (best2 < Infinity && Math.sqrt(best2) <= r * cell) break;
        }
        if (best2 < Infinity) { sum += Math.sqrt(best2); count++; }
    }
    return count ? sum / count : 1;
}

function ovParseRows(text) {
    const rows = [];
    for (const rawLine of text.split(/\r?\n/)) {
        const line = rawLine.trim();
        if (!line) continue;
        const parts = splitXYZColumns(line);
        if (parts.length < 3) { rows.push({line: rawLine, isPoint: false}); continue; }
        const x = Number(parts[0]), y = Number(parts[1]), z = Number(parts[2]);
        if (!Number.isFinite(x) || !Number.isFinite(y) || !Number.isFinite(z)) { rows.push({line: rawLine, isPoint: false}); continue; }
        rows.push({line, isPoint: true, x, y, z, xText: parts[0], yText: parts[1]});
    }
    return rows;
}

/*
   Merge a later file into the points collected so far.
   - overlap = a later point within "distance" of any earlier point
     (distance = user value, or the average closest-point spacing of the earlier points)
   - overlapping later points are removed; earlier XY is never changed
   - each earlier point that has a later point within the distance gets its Z from that nearest later point:
       minimum : the Z with the smaller absolute value (shallowest)
       average : the average of the two Z values
       second  : the later file's Z
*/
function mergeOverlappingPoints(existingText, laterText, method, distanceOverride) {
    const earlier = ovParseRows(existingText || ""), later = ovParseRows(laterText || "");
    const ePts = earlier.filter(r => r.isPoint), lPts = later.filter(r => r.isPoint);
    const ex = Float64Array.from(ePts, p => p.x), ey = Float64Array.from(ePts, p => p.y);
    const lx = Float64Array.from(lPts, p => p.x), ly = Float64Array.from(lPts, p => p.y);

    const distance = distanceOverride > 0 ? distanceOverride : ovAverageSpacing(ex, ey);
    let removed = 0, zChanged = 0;

    if (ePts.length && lPts.length && distance > 0) {
        let minX = Infinity, minY = Infinity;
        for (let i = 0; i < ex.length; i++) { if (ex[i] < minX) minX = ex[i]; if (ey[i] < minY) minY = ey[i]; }
        for (let i = 0; i < lx.length; i++) { if (lx[i] < minX) minX = lx[i]; if (ly[i] < minY) minY = ly[i]; }
        const gE = ovBuildGrid(ex, ey, distance, minX, minY), gL = ovBuildGrid(lx, ly, distance, minX, minY);

        /* 1. earlier points take Z from their nearest later point (earlier XY untouched) */
        for (let i = 0; i < ePts.length; i++) {
            const hit = ovNearest(gL, lx, ly, ex[i], ey[i], distance, false);
            if (!hit) continue;
            const p = ePts[i], z1 = p.z, z2 = lPts[hit.index].z;
            let newZ = z1;
            if (method === "average") newZ = (z1 + z2) / 2;
            else if (method === "second") newZ = z2;
            else if (Math.abs(z2) < Math.abs(z1) - 1e-9) newZ = z2;
            if (Math.abs(newZ - z1) > 1e-12) { p.newZ = newZ; zChanged++; }
        }
        /* 2. later points inside the overlap are removed */
        for (let j = 0; j < lPts.length; j++) {
            if (ovNearest(gE, ex, ey, lx[j], ly[j], distance, false)) { lPts[j].drop = true; removed++; }
        }
    }

    const out = [];
    for (const r of earlier) {
        if (r.isPoint && r.newZ !== undefined) out.push(r.xText + " " + r.yText + " " + String(Number(r.newZ.toFixed(6))));
        else out.push(r.line);
    }
    for (const r of later) { if (!(r.isPoint && r.drop)) out.push(r.line); }
    return {text: out.join("\n"), removed, zChanged, distance, pointCount: ePts.length + lPts.length - removed};
}

function applyCombineZOptions(text) {
    const adjustment = Number(combineZAdjustment.value);
    if (!Number.isFinite(adjustment)) {
        throw new Error("Please enter a valid Z adjustment value.");
    }

    const lines = text.split(/\r?\n/);
    const output = [];
    let changed = 0;

    for (let i = 0; i < lines.length; i++) {
        const originalLine = lines[i];
        const line = originalLine.trim();

        if (!line) {
            output.push(originalLine);
            continue;
        }

        const parts = splitXYZColumns(line);
        if (parts.length < 3) {
            output.push(originalLine);
            continue;
        }

        const x = Number(parts[0]);
        const y = Number(parts[1]);
        const z = Number(parts[2]);

        if (!Number.isFinite(x) || !Number.isFinite(y) || !Number.isFinite(z)) {
            output.push(originalLine);
            continue;
        }

        let newZ = z + adjustment;
        if (combineInvertZ.checked) newZ = -newZ;

        if (combineRound.checked) {
            if (!combineRemoveOverlap.checked) {
                parts[0] = x.toFixed(2);
                parts[1] = y.toFixed(2);
            }
            parts[2] = roundHalfUp(newZ, 1);
        } else {
            if (!combineRemoveOverlap.checked) {
                parts[0] = String(x);
                parts[1] = String(y);
            }
            parts[2] = String(newZ);
        }

        output.push(parts.join(" "));
        changed++;
    }

    return { text: output.join("\n").replace(/\s+$/, ""), changed: changed };
}

function removeOverlapFromLaterFile(previousText, laterText) {
    const previousPoints = parseXYZForOverlap(previousText);
    const spatialHash = makeSpatialHash(previousPoints, 1.0);
    const lines = laterText.split(/\r?\n/);
    const output = [];
    let removed = 0;
    let valid = 0;

    for (let i = 0; i < lines.length; i++) {
        const originalLine = lines[i];
        const line = originalLine.trim();

        if (!line) {
            output.push(originalLine);
            continue;
        }

        const parts = splitXYZColumns(line);
        if (parts.length < 3) {
            output.push(originalLine);
            continue;
        }

        const x = Number(parts[0]);
        const y = Number(parts[1]);
        const z = Number(parts[2]);

        if (!Number.isFinite(x) || !Number.isFinite(y) || !Number.isFinite(z)) {
            output.push(originalLine);
            continue;
        }

        valid++;

        if (hasOverlap({x:x, y:y, z:z}, spatialHash, 0.0, 1.0)) {
            removed++;
        } else {
            output.push(originalLine);
        }
    }

    return {
        text: output.join("\n").replace(/\s+$/, ""),
        removed: removed,
        valid: valid,
        referencePoints: previousPoints.length
    };
}

const combineManyFiles = document.getElementById("combineManyFiles");
const combineManyFileNames = document.getElementById("combineManyFileNames");

combineManyFiles.addEventListener("change", function () {
    const selected = Array.from(this.files || []);
    combineManyFileNames.textContent = selected.length
        ? selected.length + " file(s) selected: " + selected.map(f => f.name).join(", ")
        : "No additional files selected";
    combineDownloadBtn.style.display = "none";
    combineOutputReady = false;
    combineParts = [];
});

combineProcessBtn.addEventListener("click", async function () {
    const files = [];

    // Preserve the existing six individual file slots.
    for (let i = 1; i <= 6; i++) {
        const input = document.getElementById("combineFile" + i);
        if (input.files.length) {
            files.push({ number: i, file: input.files[0] });
        }
    }

    // Append every file selected through the new Choose Files button.
    Array.from(combineManyFiles.files || []).forEach(function (file, index) {
        files.push({ number: "Additional " + (index + 1), file: file });
    });

    combineParts = [];
    combineOutputReady = false;
    combineDownloadBtn.style.display = "none";

    if (!files.length) {
        setCombineStatus("Please select at least one XYZ file.", "error");
        return;
    }

    try {
        combineProcessBtn.disabled = true;
        combineProcessBtn.textContent = "Processing...";

        let totalBytes = 0;
        let totalRemoved = 0;
        let totalZChanged = 0;
        let lastOverlapDistance = 0;
        let combinedRawText = "";

        for (let n = 0; n < files.length; n++) {
            const item = files[n];
            setCombineStatus(
                "Reading File " + item.number + ": " + item.file.name +
                "\n\nFiles processed: " + n + " of " + files.length,
                "info"
            );

            let text = await item.file.text();
            text = text.replace(/^\uFEFF/, "").trim();
            if (!text.length) {
                totalBytes += item.file.size;
                continue;
            }

            if (!combinedRawText) {
                combinedRawText = text;
            } else if (combineRemoveOverlap.checked) {
                const overlapMethod = combineOverlapAverage.checked ? "average" : combineOverlapSecond.checked ? "second" : "minimum";
                setCombineStatus(
                    "Checking File " + item.number + " for overlapping points...\n\n" + overlapRuleText(overlapMethod),
                    "info"
                );
                await new Promise(function(resolve) { setTimeout(resolve, 0); });
                const merged = mergeOverlappingPoints(combinedRawText, text, overlapMethod, Number(combineOverlapDistance.value));
                combinedRawText = merged.text;
                totalRemoved += merged.removed;
                totalZChanged += merged.zChanged;
                lastOverlapDistance = merged.distance;
                setCombineStatus(
                    "File " + item.number + " complete.\n\n" +
                    "Overlap distance: " + merged.distance.toFixed(3) + " ft\n" +
                    "Overlapping points removed: " + merged.removed.toLocaleString() + "\n" +
                    "First-file points with Z updated: " + merged.zChanged.toLocaleString(),
                    "info"
                );
            } else {
                combinedRawText += "\n" + text;
            }

            totalBytes += item.file.size;
            await new Promise(function(resolve) { setTimeout(resolve, 0); });
        }

        if (combinedRawText.trim()) {
            // Apply adjustment/inversion/rounding only after choosing the shallowest original Z.
            const adjusted = applyCombineZOptions(combinedRawText);
            combineParts = [adjusted.text];
        }

        if (!combineParts.length) {
            throw new Error("The selected files contain no data.");
        }

        combineOutputReady = true;
        combineDownloadBtn.style.display = "inline-block";

        let message =
            "Processing complete.\n\n" +
            "Files combined: " + files.length +
            "\nTotal input size: " +
            (totalBytes / 1024 / 1024).toFixed(2) + " MB";

        if (combineRemoveOverlap.checked) {
            message += "\nOverlap distance: " + lastOverlapDistance.toFixed(3) + " ft" +
                "\nOverlap points removed: " + totalRemoved.toLocaleString() +
                "\nFirst-file points with Z updated: " + totalZChanged.toLocaleString() +
                "\nRule: " + overlapRuleText(combineOverlapAverage.checked ? "average" : combineOverlapSecond.checked ? "second" : "minimum");
        }

        message += "\n\nReady to download.";

        setCombineStatus(message, "success");

    } catch (e) {
        combineParts = [];
        combineOutputReady = false;
        combineDownloadBtn.style.display = "none";
        setCombineStatus("Error:\n\n" + (e.message || e), "error");
    } finally {
        combineProcessBtn.disabled = false;
        combineProcessBtn.textContent = "Process";
    }
});

combineDownloadBtn.addEventListener("click", function () {
    if (!combineOutputReady || !combineParts.length) {
        alert("Please process the files first.");
        return;
    }

    const output = combineParts.join("\n") + "\n";
    const blob = new Blob([output], { type: "text/plain;charset=utf-8" });
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");

    a.href = url;
    a.download = combineRemoveOverlap.checked
        ? "combined_XYZ_overlap_removed.xyz"
        : "combined_XYZ.xyz";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);

    setTimeout(function() {
        URL.revokeObjectURL(url);
    }, 2000);
});



/* ============================================================
   CLEAR ALL
============================================================ */

document
.getElementById("clearAllBtn")
.addEventListener("click", function() {

    /* Extract XYZ */
    document.getElementById("extractType").value = "mtx";
    document.getElementById("extractMtxZ").value = "0";
    document.getElementById("extractFile").value = "";
    document.getElementById("extractFileName").textContent = "No file selected";
    document.getElementById("extractStatus").innerHTML = "";
    document.getElementById("extractResult").textContent = "";
    document.getElementById("extractDownloadBtn").style.display = "none";
    document.getElementById("extractProcessBtn").disabled = true;
    extractOutputText = "";
    extractOriginalFileName = "";
    updateExtractFileType();

    /* VDATUM */
    document.getElementById("vdatumFile").value = "";
    document.getElementById("surveyFile").value = "";
    document.getElementById("vdatumName").textContent = "No VDATUM file selected";
    document.getElementById("surveyName").textContent = "No survey files selected";
    document.getElementById("vdatumStatus").textContent = "Select both files to begin.";
    document.getElementById("vdatumDownloadSection").style.display = "none";
    if (typeof hideOutputButtons === "function") hideOutputButtons();
    document.getElementById("vdatumOutputFileName").textContent = "";
    document.getElementById("vdatumRound").checked = false;
    document.getElementById("vdatumProgressContainer").style.display = "none";
    document.getElementById("vdatumProgressBar").value = 0;
    document.getElementById("vdatumProgressText").textContent = "0%";
    vdatumPoints = [];
    kdTree = null;
    outputBlob = null;
    outputFileName = "";

    /* Combine XYZ */
    for (let i = 1; i <= 6; i++) {
        document.getElementById("combineFile" + i).value = "";
    }
    document.getElementById("combineManyFiles").value = "";
    document.getElementById("combineManyFileNames").textContent = "No additional files selected";
    combineParts = [];
    combineOutputReady = false;
    combineDownloadBtn.style.display = "none";
    combineStatus.className = "";
    combineStatus.textContent = "";

    /* Z adjustment */
    document.getElementById("zAdjustFile").value = "";
    document.getElementById("zAdjustFileNames").textContent = "No files selected";
    zOutputFiles = [];
    document.getElementById("zAdjustment").value = "0";
    document.getElementById("invertZAdjust").checked = false;
    document.getElementById("zStatus").innerHTML = "";
    document.getElementById("zResult").textContent = "";
    document.getElementById("zDownloadBtn").style.display = "none";
    document.getElementById("zDownloadZipBtn").style.display = "none";
    zOutputText = "";
    zOriginalFileName = "";

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
});




/* ================= VDATUM TOOL ================= */



/* =====================================================
   GLOBAL VARIABLES
   ===================================================== */

let vdatumPoints = [];

let kdTree = null;

let outputBlob = null;

let outputFileName = "";



/* =====================================================
   VDATUM FILE NAME DISPLAY
   ===================================================== */

document
.getElementById("vdatumFile")
.addEventListener(
    "change",
    function () {

        if (this.files.length > 0) {

            document
            .getElementById("vdatumName")
            .textContent =
                this.files[0].name;

        }

        else {

            document
            .getElementById("vdatumName")
            .textContent =
                "No VDATUM file selected";

        }

    }
);



/* =====================================================
   SURVEY FILE NAME DISPLAY
   ===================================================== */

document
.getElementById("surveyFile")
.addEventListener(
    "change",
    function () {

        if (this.files.length > 0) {

            document
            .getElementById("surveyName")
            .textContent =
                this.files.length + " survey file(s): " +
                Array.from(this.files).map(function(file) { return file.name; }).join(", ");

        }

        else {

            document
            .getElementById("surveyName")
            .textContent =
                "No survey files selected";

        }

    }
);



/* =====================================================
   PARSE XYZ FILE
   ===================================================== */

function parseXYZ(text) {

    const lines =
        text.split(/\r?\n/);


    const points = [];


    for (
        let i = 0;
        i < lines.length;
        i++
    ) {

        const line =
            lines[i].trim();


        if (!line) {

            continue;

        }


        const parts =
            splitXYZColumns(line);


        if (
            parts.length < 3
        ) {

            continue;

        }


        const x =
            Number(parts[0]);


        const y =
            Number(parts[1]);


        const z =
            Number(parts[2]);


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



/* =====================================================
   KD TREE NODE
   ===================================================== */

class KDNode {

    constructor(point, axis) {

        this.point = point;

        this.axis = axis;

        this.left = null;

        this.right = null;

    }

}



/* =====================================================
   BUILD KD TREE
   ===================================================== */

function buildKDTree(
    points,
    depth = 0
) {

    if (
        points.length === 0
    ) {

        return null;

    }


    const axis =
        depth % 2;


    points.sort(
        function(a, b) {

            if (
                axis === 0
            ) {

                return a.x - b.x;

            }


            return a.y - b.y;

        }
    );


    const middle =
        Math.floor(
            points.length / 2
        );


    const node =
        new KDNode(
            points[middle],
            axis
        );


    node.left =
        buildKDTree(
            points.slice(
                0,
                middle
            ),
            depth + 1
        );


    node.right =
        buildKDTree(
            points.slice(
                middle + 1
            ),
            depth + 1
        );


    return node;

}



/* =====================================================
   XY DISTANCE SQUARED
   ===================================================== */

function distanceSquared(
    a,
    b
) {

    const dx =
        a.x - b.x;


    const dy =
        a.y - b.y;


    return (
        dx * dx +
        dy * dy
    );

}



/* =====================================================
   FIND CLOSEST VDATUM POINT
   ===================================================== */

function nearestPoint(
    node,
    target,
    best = null,
    bestDistance = Infinity
) {


    if (
        node === null
    ) {

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


    if (
        currentDistance <
        bestDistance
    ) {

        best =
            node.point;

        bestDistance =
            currentDistance;

    }


    const axis =
        node.axis;


    let difference;


    if (
        axis === 0
    ) {

        difference =
            target.x -
            node.point.x;

    }

    else {

        difference =
            target.y -
            node.point.y;

    }


    let nearBranch;

    let farBranch;


    if (
        difference < 0
    ) {

        nearBranch =
            node.left;

        farBranch =
            node.right;

    }

    else {

        nearBranch =
            node.right;

        farBranch =
            node.left;

    }


    let result =
        nearestPoint(

            nearBranch,

            target,

            best,

            bestDistance

        );


    best =
        result.point;


    bestDistance =
        result.distance;


    if (

        difference *
        difference <
        bestDistance

    ) {

        result =
            nearestPoint(

                farBranch,

                target,

                best,

                bestDistance

            );


        best =
            result.point;


        bestDistance =
            result.distance;

    }


    return {

        point: best,

        distance: bestDistance

    };

}



/* =====================================================
   STATUS FUNCTION
   ===================================================== */

function setStatus(
    message
) {

    document
    .getElementById("vdatumStatus")
    .textContent =
        message;

}



/* =====================================================
   PROCESS BUTTON
   ===================================================== */

const vdatumSurveyInput = document.getElementById("surveyFile");
const vdatumSurveyName = document.getElementById("surveyName");
const downloadButton = document.getElementById("vdatumDownloadButton");
const saveAsButton = document.getElementById("vdatumSaveAsButton");
const zipDownloadButton = document.getElementById("vdatumZipDownloadButton");

function hideOutputButtons() {
    downloadButton.style.display = "none";
    saveAsButton.style.display = "none";
    zipDownloadButton.style.display = "none";
    document.getElementById("vdatumDownloadSection").style.display = "none";
}

function resetVdatumOutput() {
    hideOutputButtons();
    outputBlob = null;
    outputFileName = "";
    document.getElementById("vdatumOutputFileName").textContent = "";
}

document.getElementById("vdatumFile").addEventListener("change", function () {
    document.getElementById("vdatumName").textContent = this.files.length ? this.files[0].name : "No VDATUM file selected";
    resetVdatumOutput();
});

vdatumSurveyInput.addEventListener("change", function () {
    const files = Array.from(this.files || []);
    vdatumSurveyName.textContent = files.length
        ? files.length + " survey file(s): " + files.map(file => file.name).join(", ")
        : "No survey files selected";
    resetVdatumOutput();
});

document.getElementById("vdatumProcessButton").addEventListener("click", async function () {
    const vdatumFile = document.getElementById("vdatumFile").files[0];
    const surveyFiles = Array.from(vdatumSurveyInput.files || []);
    const roundOn = document.getElementById("vdatumRound").checked;
    const processButton = document.getElementById("vdatumProcessButton");
    const progress = document.getElementById("vdatumProgressBar");
    const progressText = document.getElementById("vdatumProgressText");
    const progressContainer = document.getElementById("vdatumProgressContainer");

    if (!vdatumFile) { alert("Please select the VDATUM MLLW XYZ file."); return; }
    if (!surveyFiles.length) { alert("Please select one or more survey XYZ files."); return; }
    if (surveyFiles.length > 1 && typeof JSZip === "undefined") {
        alert("ZIP library did not load. Check your internet connection and try again."); return;
    }

    processButton.disabled = true;
    processButton.textContent = "Processing...";
    progressContainer.style.display = "block";
    progress.value = 0;
    progressText.textContent = "0%";
    resetVdatumOutput();

    try {
        setStatus("Reading the VDATUM MLLW file...");
        const vdatumText = await vdatumFile.text();
        vdatumPoints = parseXYZ(vdatumText);
        if (!vdatumPoints.length) throw new Error("No valid XYZ points were found in the VDATUM file.");
        setStatus("VDATUM points loaded: " + vdatumPoints.length.toLocaleString() + "\nBuilding closest-point search tree...");
        await new Promise(resolve => setTimeout(resolve, 20));
        kdTree = buildKDTree(vdatumPoints);

        const zip = surveyFiles.length > 1 ? new JSZip() : null;
        let singleOutputText = "";
        let totalValid = 0;
        let totalUnchanged = 0;

        for (let fileIndex = 0; fileIndex < surveyFiles.length; fileIndex++) {
            const surveyFile = surveyFiles[fileIndex];
            setStatus("Processing file " + (fileIndex + 1) + " of " + surveyFiles.length + ":\n" + surveyFile.name);
            const surveyLines = (await surveyFile.text()).split(/\r?\n/);
            const outputLines = [];
            let validPoints = 0;
            let unchangedLines = 0;

            for (let i = 0; i < surveyLines.length; i++) {
                const originalLine = surveyLines[i];
                const line = originalLine.trim();
                if (!line) { outputLines.push(originalLine); unchangedLines++; continue; }
                const parts = splitXYZColumns(line);
                if (parts.length < 3) { outputLines.push(originalLine); unchangedLines++; continue; }
                const x = Number(parts[0]), y = Number(parts[1]), z = Number(parts[2]);
                if (!Number.isFinite(x) || !Number.isFinite(y) || !Number.isFinite(z)) {
                    outputLines.push(originalLine); unchangedLines++; continue;
                }
                const nearest = nearestPoint(kdTree, {x:x, y:y});
                if (!nearest || !nearest.point) throw new Error("Could not find a nearest VDATUM point for " + surveyFile.name + ".");
                const newZ = z + nearest.point.z;
                outputLines.push(x.toFixed(2) + " " + y.toFixed(2) + " " + roundHalfUp(newZ, roundOn ? 1 : 2));
                validPoints++;
                if (i % 5000 === 0) {
                    const overall = ((fileIndex + (i / Math.max(1, surveyLines.length))) / surveyFiles.length) * 100;
                    progress.value = overall;
                    progressText.textContent = Math.round(overall) + "%";
                    await new Promise(resolve => setTimeout(resolve, 0));
                }
            }
            const baseName = surveyFile.name.replace(/\.[^/.]+$/, "");
            const outName = baseName + "_VDATUM_ADJUSTED.xyz";
            const outputText = outputLines.join("\n");
            if (zip) zip.file(outName, outputText);
            else {
                singleOutputText = outputText;
                outputFileName = outName;
            }
            totalValid += validPoints;
            totalUnchanged += unchangedLines;
        }

        if (zip) {
            setStatus("Creating ZIP archive...");
            outputBlob = await zip.generateAsync({type:"blob"});
            outputFileName = "VDATUM_ADJUSTED_FILES.zip";
        } else {
            outputBlob = new Blob([singleOutputText], {type:"text/plain;charset=utf-8"});
        }

        progress.value = 100;
        progressText.textContent = "100%";
        document.getElementById("vdatumDownloadSection").style.display = "block";
        document.getElementById("vdatumOutputFileName").textContent = "Output ready: " + outputFileName + " (" + surveyFiles.length + " survey file(s))";
        if (surveyFiles.length === 1) {
            downloadButton.style.display = "inline-block";
            saveAsButton.style.display = "inline-block";
        } else {
            zipDownloadButton.style.display = "inline-block";
        }
        setStatus("PROCESSING COMPLETE\n\nVDATUM points: " + vdatumPoints.length.toLocaleString() +
            "\nSurvey files processed: " + surveyFiles.length +
            "\nValid survey points processed: " + totalValid.toLocaleString() +
            "\nUnchanged/non-XYZ lines: " + totalUnchanged.toLocaleString() +
            "\n\nCalculation: New Z = Survey Z + nearest VDATUM Z" +
            (surveyFiles.length === 1 ? "\n\nUse Download or Save As to save the adjusted XYZ file." : "\n\nUse Download ZIP to save all adjusted XYZ files."));
    } catch (error) {
        console.error(error);
        setStatus("ERROR\n\n" + (error.message || String(error)));
        alert("An error occurred:\n\n" + (error.message || String(error)));
    } finally {
        processButton.disabled = false;
        processButton.textContent = "Process";
    }
});

function downloadVdatumOutput() {
    if (!outputBlob) { alert("Please process the XYZ file first."); return; }
    const url = URL.createObjectURL(outputBlob);
    const link = document.createElement("a");
    link.href = url;
    link.download = outputFileName;
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
    setTimeout(() => URL.revokeObjectURL(url), 1000);
}

downloadButton.addEventListener("click", downloadVdatumOutput);
zipDownloadButton.addEventListener("click", downloadVdatumOutput);
saveAsButton.addEventListener("click", async function () {
    if (!outputBlob) { alert("Please process the XYZ file first."); return; }
    if (window.showSaveFilePicker) {
        try {
            const handle = await window.showSaveFilePicker({
                suggestedName: outputFileName,
                types: [{ description: "XYZ text file", accept: {"text/plain": [".xyz"]} }]
            });
            const writable = await handle.createWritable();
            await writable.write(outputBlob);
            await writable.close();
        } catch (error) {
            if (error.name !== "AbortError") alert("Could not save the file: " + (error.message || String(error)));
        }
    } else {
        downloadVdatumOutput();
    }
});

document.getElementById("vdatumRefreshButton").addEventListener("click", function () {
    document.getElementById("vdatumFile").value = "";
    vdatumSurveyInput.value = "";
    document.getElementById("vdatumName").textContent = "No VDATUM file selected";
    vdatumSurveyName.textContent = "No survey files selected";
    document.getElementById("vdatumRound").checked = false;
    vdatumPoints = [];
    kdTree = null;
    outputBlob = null;
    outputFileName = "";
    hideOutputButtons();
    document.getElementById("vdatumOutputFileName").textContent = "";
    document.getElementById("vdatumProgressContainer").style.display = "none";
    document.getElementById("vdatumProgressBar").value = 0;
    document.getElementById("vdatumProgressText").textContent = "0%";
    document.getElementById("vdatumProcessButton").disabled = false;
    document.getElementById("vdatumProcessButton").textContent = "Process";
    setStatus("Select both files to begin.");
});


/* ================= Z ADJUST TOOL ================= */
let zOutputText = "";
let zOriginalFileName = "";
let zOutputFiles = [];
let zMode = "multi";
const zAdjustFileInput = document.getElementById("zAdjustFile");
const zAdjustFileNames = document.getElementById("zAdjustFileNames");
const zDownloadBtn = document.getElementById("zDownloadBtn");
const zDownloadZipBtn = document.getElementById("zDownloadZipBtn");
function resetZAdjustOutput() {
  zOutputFiles = []; zOutputText = "";
  zDownloadBtn.style.display = "none"; zDownloadZipBtn.style.display = "none";
  document.getElementById("zStatus").innerHTML = "";
  document.getElementById("zResult").textContent = "";
}
function selectZAdjustFiles(files) {
  zMode = files.length === 1 ? "single" : "multi"; resetZAdjustOutput();
  zAdjustFileNames.textContent = files.length ? files.length + " file(s) selected: " + files.map(f => f.name).join(", ") : "No files selected";
}
zAdjustFileInput.addEventListener("change", function () { selectZAdjustFiles(Array.from(this.files || [])); });
function processZAdjustText(text, zAdjustment, invertZAdjust, zRoundOn) {
  const lines = text.split(/\r?\n/), processedLines = []; let validPoints = 0, unchangedLines = 0;
  for (const line of lines) {
    if (line.trim() === "") { processedLines.push(line); continue; }
    const parts = splitXYZColumns(line);
    if (parts.length >= 3) {
      const x = Number(parts[0]), y = Number(parts[1]), z = Number(parts[2]);
      if (Number.isFinite(x) && Number.isFinite(y) && Number.isFinite(z)) {
        let newZ = z + zAdjustment; if (invertZAdjust) newZ = -newZ;
        processedLines.push(x.toFixed(zRoundOn ? 2 : 3) + " " + y.toFixed(zRoundOn ? 2 : 3) + " " + roundHalfUp(newZ, zRoundOn ? 1 : 3)); validPoints++;
      } else { processedLines.push(line); unchangedLines++; }
    } else { processedLines.push(line); unchangedLines++; }
  }
  return { text: processedLines.join("\n"), validPoints, unchangedLines, preview: processedLines.slice(0, 10).join("\n") };
}
document.getElementById("zProcessBtn").addEventListener("click", async function () {
  const files = Array.from(zAdjustFileInput.files || []);
  zMode = files.length === 1 ? "single" : "multi";
  if (!files.length) { alert("Please select a file using Choose Files."); return; }
  const zAdjustment = Number(document.getElementById("zAdjustment").value);
  if (!Number.isFinite(zAdjustment)) { alert("Please enter a valid Z adjustment value."); return; }
  const invert = document.getElementById("invertZAdjust").checked, round = document.getElementById("zRound").checked;
  resetZAdjustOutput(); zOriginalFileName = files[0].name;
  document.getElementById("zStatus").innerHTML = "<div class='info'>Processing " + files.length + " file(s)...</div>";
  try {
    let totalPoints = 0, totalUnchanged = 0;
    for (const file of files) {
      const res = processZAdjustText(await file.text(), zAdjustment, invert, round);
      zOutputFiles.push({name:file.name.replace(/\.[^/.]+$/, "") + "_Z_ADJUSTED.xyz", text:res.text});
      totalPoints += res.validPoints; totalUnchanged += res.unchangedLines;
    }
    zOutputText = zOutputFiles[0].text;
    document.getElementById("zStatus").innerHTML = "<div class='success'><strong>Processing complete.</strong><br>Files processed: " + zOutputFiles.length + "<br>Points processed: " + totalPoints.toLocaleString() + "<br>Lines unchanged: " + totalUnchanged.toLocaleString() + "<br>Z adjustment: " + zAdjustment.toFixed(2) + "<br>Invert Z: " + (invert ? "YES" : "NO") + "<br>Output: " + (round ? "X Y 2 decimals, Z 1 decimal" : "X Y Z 3 decimals") + "</div>";
    document.getElementById("zResult").textContent = "Preview — " + zOutputFiles[0].name + "\n" + processZAdjustText(await files[0].text(), zAdjustment, invert, round).preview;
    if (zMode === "single") zDownloadBtn.style.display = "inline-block"; else zDownloadZipBtn.style.display = "inline-block";
  } catch (err) { console.error(err); document.getElementById("zStatus").innerHTML = "<div class='error'>Could not process files: " + String(err.message || err) + "</div>"; }
});
zDownloadBtn.addEventListener("click", function () {
  if (!zOutputFiles.length) { alert("Please process the file first."); return; }
  const blob = new Blob([zOutputText], {type:"text/plain;charset=utf-8"}), url = URL.createObjectURL(blob), a = document.createElement("a");
  a.href = url; a.download = zOutputFiles[0].name; document.body.appendChild(a); a.click(); a.remove(); setTimeout(() => URL.revokeObjectURL(url), 1500);
});
zDownloadZipBtn.addEventListener("click", async function () {
  if (!zOutputFiles.length) { alert("Please process files first."); return; }
  if (typeof JSZip === "undefined") { alert("ZIP support could not load. Please check your internet connection and reload this page."); return; }
  const zip = new JSZip(); zOutputFiles.forEach(file => zip.file(file.name, file.text));
  const blob = await zip.generateAsync({type:"blob"}), url = URL.createObjectURL(blob), a = document.createElement("a");
  a.href = url; a.download = "Z_ADJUSTED_FILES.zip"; document.body.appendChild(a); a.click(); a.remove(); setTimeout(() => URL.revokeObjectURL(url), 1500);
});


/* ============================================================
   GLOBAL CLEAR ALL
============================================================ */

document
.getElementById("clearAllBtn")
.addEventListener("click", function() {

    /* MTX */
    if (document.getElementById("mtxFile"))
        document.getElementById("mtxFile").value = "";

    if (document.getElementById("mtxZ"))
        document.getElementById("mtxZ").value = "0";

    if (document.getElementById("mtxStatus"))
        document.getElementById("mtxStatus").innerHTML = "";

    if (document.getElementById("mtxResult"))
        document.getElementById("mtxResult").textContent = "";

    if (document.getElementById("mtxDownloadBtn"))
        document.getElementById("mtxDownloadBtn").style.display = "none";

    if (typeof mtxOutputText !== "undefined") mtxOutputText = "";
    if (typeof mtxOriginalFileName !== "undefined") mtxOriginalFileName = "";

    /* CHN */
    if (document.getElementById("chnFile"))
        document.getElementById("chnFile").value = "";

    if (document.getElementById("chnStatus"))
        document.getElementById("chnStatus").innerHTML = "";

    if (document.getElementById("chnResult"))
        document.getElementById("chnResult").textContent = "";

    if (document.getElementById("chnDownloadBtn"))
        document.getElementById("chnDownloadBtn").style.display = "none";

    if (typeof chnOutputText !== "undefined") chnOutputText = "";
    if (typeof chnOriginalFileName !== "undefined") chnOriginalFileName = "";

    /* VDATUM */
    if (document.getElementById("vdatumFile"))
        document.getElementById("vdatumFile").value = "";

    if (document.getElementById("surveyFile"))
        document.getElementById("surveyFile").value = "";

    if (document.getElementById("vdatumName"))
        document.getElementById("vdatumName").textContent =
            "No VDATUM file selected";

    if (document.getElementById("surveyName"))
        document.getElementById("surveyName").textContent =
            "No survey files selected";

    if (typeof vdatumPoints !== "undefined") vdatumPoints = [];
    if (typeof kdTree !== "undefined") kdTree = null;
    if (typeof vdatumOutputBlob !== "undefined") vdatumOutputBlob = null;
    if (typeof vdatumOutputFileName !== "undefined") vdatumOutputFileName = "";

    if (document.getElementById("vdatumDownloadSection"))
        document.getElementById("vdatumDownloadSection").style.display = "none";

    if (document.getElementById("vdatumOutputFileName"))
        document.getElementById("vdatumOutputFileName").textContent = "";

    if (document.getElementById("vdatumProgressContainer"))
        document.getElementById("vdatumProgressContainer").style.display = "none";

    if (document.getElementById("vdatumProgressBar"))
        document.getElementById("vdatumProgressBar").value = 0;

    if (document.getElementById("vdatumProgressText"))
        document.getElementById("vdatumProgressText").textContent = "0%";

    if (document.getElementById("vdatumStatus"))
        document.getElementById("vdatumStatus").textContent =
            "Select both files to begin.";

    /* Z ADJUST / INVERT */
    if (document.getElementById("zAdjustFile"))
        document.getElementById("zAdjustFile").value = "";

    if (document.getElementById("zAdjustment"))
        document.getElementById("zAdjustment").value = "0";

    if (document.getElementById("invertZAdjust"))
        document.getElementById("invertZAdjust").checked = false;

    if (document.getElementById("zStatus"))
        document.getElementById("zStatus").innerHTML = "";

    if (document.getElementById("zResult"))
        document.getElementById("zResult").textContent = "";

    if (document.getElementById("zDownloadBtn"))
        document.getElementById("zDownloadBtn").style.display = "none";

    if (typeof zOutputText !== "undefined") zOutputText = "";
    if (typeof zOriginalFileName !== "undefined") zOriginalFileName = "";
    if (typeof zOutputFiles !== "undefined") zOutputFiles = [];
});

</script>


<script>

/* ============================================================
   COORDINATE CONVERTER TAB (NJ 2900 / NY East 3101 / NY Long Island 3104)
   Wrapped in its own scope so it cannot clash with the other tools.
============================================================ */

(function () {

/* ---------- Projection math (GRS80, US survey foot) ---------- */
const A_ = 6378137.0, F_ = 1 / 298.257222101, E2 = 2 * F_ - F_ * F_, E = Math.sqrt(E2);
const FT = 1200 / 3937; // metres per US survey foot
const rad = d => d * Math.PI / 180;
const {sin, cos, tan, atan, atan2, asin, sinh, cosh, tanh, log, sqrt, PI} = Math;
const atanh = Math.atanh;

/* Transverse Mercator (used by NJ 2900 and NY East 3101) */
function makeTM(p) {
  const n = F_ / (2 - F_);
  const AK = A_ / (1 + n) * (1 + n ** 2 / 4 + n ** 4 / 64);
  const AL = [n / 2 - 2 * n ** 2 / 3 + 5 * n ** 3 / 16, 13 * n ** 2 / 48 - 3 * n ** 3 / 5, 61 * n ** 3 / 240];
  const BE = [n / 2 - 2 * n ** 2 / 3 + 37 * n ** 3 / 96, n ** 2 / 48 + n ** 3 / 15, 17 * n ** 3 / 480];
  const conf = lat => atan(sinh(atanh(sin(lat)) - E * atanh(E * sin(lat))));
  const arc = lat => { const x = conf(lat); return AK * (x + AL.reduce((s, a, j) => s + a * sin(2 * (j + 1) * x), 0)); };
  const M0 = p.k0 * arc(p.lat0);
  return {
    toLL(Em, Nm) {
      const xi = (Nm - p.fn + M0) / (p.k0 * AK), eta = (Em - p.fe) / (p.k0 * AK);
      let xi_ = xi, eta_ = eta;
      for (let j = 0; j < 3; j++) {
        xi_ -= BE[j] * sin(2 * (j + 1) * xi) * cosh(2 * (j + 1) * eta);
        eta_ -= BE[j] * cos(2 * (j + 1) * xi) * sinh(2 * (j + 1) * eta);
      }
      const chi = asin(sin(xi_) / cosh(eta_));
      let lat = chi;
      for (let i = 0; i < 10; i++) lat = asin(tanh(atanh(sin(chi)) + E * atanh(E * sin(lat))));
      return [lat, p.lon0 + atan2(sinh(eta_), cos(xi_))];
    },
    fromLL(lat, lon) {
      const c = conf(lat), dl = lon - p.lon0;
      const xi_ = atan2(tan(c), cos(dl)), eta_ = atanh(sin(dl) * cos(c));
      let xi = xi_, eta = eta_;
      for (let j = 0; j < 3; j++) {
        xi += AL[j] * sin(2 * (j + 1) * xi_) * cosh(2 * (j + 1) * eta_);
        eta += AL[j] * cos(2 * (j + 1) * xi_) * sinh(2 * (j + 1) * eta_);
      }
      return [p.fe + p.k0 * AK * eta, p.fn + p.k0 * AK * xi - M0];
    }
  };
}

/* Lambert Conformal Conic, 2 standard parallels (NY Long Island 3104) */
function makeLCC(p) {
  const mm = q => cos(q) / sqrt(1 - E2 * sin(q) ** 2);
  const tt = q => tan(PI / 4 - q / 2) / (((1 - E * sin(q)) / (1 + E * sin(q))) ** (E / 2));
  const n = (log(mm(p.p1)) - log(mm(p.p2))) / (log(tt(p.p1)) - log(tt(p.p2)));
  const F = mm(p.p1) / (n * tt(p.p1) ** n), R0 = A_ * F * tt(p.p0) ** n;
  return {
    fromLL(lat, lon) {
      const r = A_ * F * tt(lat) ** n, th = n * (lon - p.lon0);
      return [p.fe + r * sin(th), R0 - r * cos(th)];
    },
    toLL(Em, Nm) {
      const x = Em - p.fe, y = R0 - Nm;
      const r = sqrt(x * x + y * y), th = atan2(x, y);
      const t = (r / (A_ * F)) ** (1 / n);
      let lat = PI / 2 - 2 * atan(t);
      for (let i = 0; i < 10; i++) lat = PI / 2 - 2 * atan(t * ((1 - E * sin(lat)) / (1 + E * sin(lat))) ** (E / 2));
      return [lat, th / n + p.lon0];
    }
  };
}

const ZONES = {
  NJ:   {label: "NJ FIPS 2900 (EPSG:3424)",              tag: "NJ_FIPS2900",
         ...makeTM({lat0: rad(38 + 50 / 60), lon0: rad(-74.5), k0: 0.9999, fe: 150000, fn: 0})},
  NYE:  {label: "NY East FIPS 3101 (EPSG:2260)",         tag: "NYE_FIPS3101",
         ...makeTM({lat0: rad(38 + 50 / 60), lon0: rad(-74.5), k0: 0.9999, fe: 150000, fn: 0})},
  NYLI: {label: "NY Long Island FIPS 3104 (EPSG:2263)",  tag: "NYLI_FIPS3104",
         ...makeLCC({p1: rad(41 + 2 / 60), p2: rad(40 + 40 / 60), p0: rad(40 + 10 / 60), lon0: rad(-74), fe: 300000})}
};

/* coordinates in US survey feet in and out */
function convertXY(from, to, x, y) {
  const [la, lo] = ZONES[from].toLL(x * FT, y * FT);
  const [e, n] = ZONES[to].fromLL(la, lo);
  return [e / FT, n / FT];
}


function cvRoundHalfUp(v, d) {
  const f = Math.pow(10, d);
  return (Math.sign(v) * Math.round(Math.abs(v) * f + 1e-9) / f).toFixed(d);
}
const isNum = t => /^[+-]?(\d+\.?\d*|\.\d+)$/.test(t || "");
/* returns index of the X column (0 = X Y [Z], 1 = ID X Y [Z]) or -1 if the line is not coordinates */
function detectIdx(p) {
  if (isNum(p[0]) && isNum(p[1])) {
    return (p.length >= 4 && /^\d+$/.test(p[0]) && isNum(p[2]) && isNum(p[3])) ? 1 : 0;
  }
  return (isNum(p[1]) && isNum(p[2])) ? 1 : -1;
}

function cvConvertText(text, dir, round) {
  const [from, to] = dir.split(">");
  const lines = text.split(/\r?\n/);
  const split = line => splitXYZColumns(line);
  let idx = -1;
  for (const l of lines) { if (!l.trim()) continue; const d = detectIdx(split(l)); if (d !== -1) { idx = d; break; } }
  let ok = 0; const bad = []; const rows = []; const out = [];
  lines.forEach((line, i) => {
    if (!line.trim()) { out.push(line); return; }
    const parts = split(line);
    const x = parseFloat(parts[idx]), y = parseFloat(parts[idx + 1]);
    if (idx < 0 || !isFinite(x) || !isFinite(y)) { bad.push(i + 1); out.push(line); return; }
    const [nx, ny] = convertXY(from, to, x, y);
    let z = parts[idx + 2];
    if (round && z !== undefined && isNum(z)) z = cvRoundHalfUp(parseFloat(z), 1);
    if (rows.length < 10) rows.push({id: idx ? parts[0] : "", x, y, z: z === undefined ? "" : z, nx, ny});
    parts[idx] = nx.toFixed(2); parts[idx + 1] = ny.toFixed(2);
    if (z !== undefined) parts[idx + 2] = z;
    ok++;
    out.push(parts.join(" "));
  });
  return {text: out.join("\n"), ok, bad, rows, hasId: idx === 1};
}

if (typeof document !== "undefined") {
  const $ = id => document.getElementById(id);
  const esc = t => String(t).replace(/[&<>]/g, c => ({"&":"&amp;", "<":"&lt;", ">":"&gt;"}[c]));
  let cvFiles = [], cvMode = "multi", cvZipBlob = null, cvSingleBlob = null, cvSingleName = "";
  function resetOutput() { cvZipBlob = null; cvSingleBlob = null; $("cvDownloadBtn").style.display="none"; $("cvDownloadZipBtn").style.display="none"; $("cvPreview").innerHTML=""; $("cvStatus").innerHTML=""; }
  function setCvFiles(files) {
    cvFiles=files; cvMode=files.length === 1 ? "single" : "multi"; resetOutput();
    $("cvConvertBtn").disabled=!cvFiles.length; $("cvConvertBtn").textContent=cvMode === "single" ? "Convert File" : "Convert All";
    $("cvFileNames").textContent=cvFiles.length ? cvFiles.length+" file(s) selected: "+cvFiles.map(f=>f.name).join(", ") : "No files selected";
    $("cvStatus").innerHTML=cvFiles.length ? '<div class="info">Ready to convert '+cvFiles.length+' file(s).</div>' : "";
  }
  $("cvFile").addEventListener("change",e=>setCvFiles(Array.from(e.target.files||[])));
  function note(){const d=$("cvDir").value;$("cvNote").style.display=(d==="NJ>NYE"||d==="NYE>NJ")?"block":"none";}
  $("cvDir").addEventListener("change",()=>{resetOutput();note();}); $("cvRound").addEventListener("change",resetOutput); note();
  $("cvConvertBtn").addEventListener("click",async()=>{
    if(!cvFiles.length)return;
    const btn=$("cvConvertBtn");
    if(cvMode==="multi" && typeof JSZip==="undefined"){$("cvStatus").innerHTML='<div class="error">ZIP support could not load. Check your internet connection and reload this page.</div>';return;}
    btn.disabled=true;btn.textContent="Converting...";resetOutput();
    let totalPoints=0,failures=[],firstPreview=null;const dir=$("cvDir").value,to=dir.split(">")[1],tag=ZONES[to].tag;const zip=cvMode==="multi"?new JSZip():null;
    try{
      for(let i=0;i<cvFiles.length;i++){
        const file=cvFiles[i];$("cvStatus").innerHTML='<div class="info">Converting '+(i+1)+' of '+cvFiles.length+': '+esc(file.name)+'</div>';
        try{const source=await file.text(),res=cvConvertText(source,dir,$("cvRound").checked);if(!res.ok)throw new Error("No valid coordinate rows found.");const output=res.text.replace(/\n*$/, "\n"),base=file.name.replace(/\.[^/.]+$/, ""),outName=base+"_"+tag+".xyz";
          if(cvMode==="single"){cvSingleBlob=new Blob([output],{type:"text/plain;charset=utf-8"});cvSingleName=outName;$("cvDownloadBtn").dataset.outputName=outName;}else zip.file(outName,output);
          totalPoints+=res.ok;if(!firstPreview)firstPreview={res,fileName:file.name};
        }catch(e){failures.push(file.name+": "+(e.message||e));}await new Promise(resolve=>setTimeout(resolve,0));
      }
      const converted=cvMode==="single"?(cvSingleBlob?1:0):Object.keys(zip.files).length;if(!converted)throw new Error("No files could be converted. "+failures.join(" | "));
      if(cvMode==="single")$("cvDownloadBtn").style.display="inline-block";else{cvZipBlob=await zip.generateAsync({type:"blob"});$("cvDownloadZipBtn").style.display="inline-block";}
      let msg="Converted "+converted+" of "+cvFiles.length+" file(s) to "+ZONES[to].label+". Total points converted: "+totalPoints.toLocaleString()+".";if(failures.length)msg+=" Files not converted: "+failures.join(" | ");msg+=cvMode==="single"?" Click Download or Save As to save the converted file.":" Download ZIP to save the converted files.";$("cvStatus").innerHTML='<div class="success">'+esc(msg)+'</div>';
      if(firstPreview){const res=firstPreview.res;let h="<h3>Preview: "+esc(firstPreview.fileName)+" — first "+res.rows.length+" converted points</h3><table><tr>"+(res.hasId?"<th>ID</th>":"")+"<th>Input X</th><th>Input Y</th><th>Z</th><th>Output X</th><th>Output Y</th></tr>";res.rows.forEach(r=>{h+="<tr>"+(res.hasId?"<td>"+esc(r.id)+"</td>":"")+"<td>"+r.x.toFixed(2)+"</td><td>"+r.y.toFixed(2)+"</td><td>"+esc(r.z)+"</td><td>"+r.nx.toFixed(2)+"</td><td>"+r.ny.toFixed(2)+"</td></tr>";});$("cvPreview").innerHTML=h+"</table>";}
    }catch(e){$("cvStatus").innerHTML='<div class="error">'+esc(e.message||e)+'</div>';}finally{btn.disabled=!cvFiles.length;btn.textContent=cvMode==="single"?"Convert File":"Convert All";}
  });
  $("cvDownloadBtn").addEventListener("click",()=>{if(!cvSingleBlob)return;const url=URL.createObjectURL(cvSingleBlob),a=document.createElement("a");a.href=url;a.download=cvSingleName;document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),1500);});
  $("cvDownloadZipBtn").addEventListener("click",()=>{if(!cvZipBlob)return;const tag=ZONES[$("cvDir").value.split(">")[1]].tag,url=URL.createObjectURL(cvZipBlob),a=document.createElement("a");a.href=url;a.download="Converted_Grid_"+tag+".zip";document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),1500);});
  /* Clear All button */
  const clr = $("clearAllBtn");
  if (clr) clr.addEventListener("click", () => {
    $("cvFile").value = "";
    cvFiles = []; cvMode = "multi";
    $("cvFileNames").textContent = "No files selected";
    $("cvConvertBtn").disabled = true;
    $("cvConvertBtn").textContent = "Convert All";
    $("cvDir").selectedIndex = 0;
    $("cvRound").checked = false;
    resetOutput();
    note();
  });
}

/* ============================================================
   CONVERT HYPACK RAW / HSX NAVIGATION COORDINATES
   Converts POS X/Y and RAW FIX X/Y records, then updates the
   projection metadata to match the destination zone.
============================================================ */
(function(){
  const zoneMeta = {
    NJ: {pro:'PRO TM -74.500000 0.999900 38.833333 0.000000 0.000000 492125.0000 0.0000', central:'-74.5000000000', epsg:'3424', fe:'492125', north:'0.0000000000', projection:'TM', ref:'38.8333333333', scale:'0.9999000000', south:'0.0000000000', zoneId:'0', zoneName:'NJ-2900 NEW JERSEY'},
    NYE:{pro:'PRO TM -74.500000 0.999900 38.833333 0.000000 0.000000 492125.0000 0.0000', central:'-74.5000000000', epsg:'2260', fe:'492125', north:'0.0000000000', projection:'TM', ref:'38.8333333333', scale:'0.9999000000', south:'0.0000000000', zoneId:'1210', zoneName:'NY-3101 NEW YORK EAST'},
    NYLI:{pro:'PRO LCC -74.000000 1.000000 40.166667 41.033333 40.666667 984250.0000 0.0000', central:'-74.0000000000', epsg:'2263', fe:'984250', north:'41.0333333333', projection:'LCC', ref:'40.1666666667', scale:'1.0000000000', south:'40.6666666667', zoneId:'1220', zoneName:'NY-3104 NEW YORK LONG ISLAND'}
  };
  function updateRawMetadata(lines, dest){
    const m=zoneMeta[dest];
    return lines.map(line=>{
      if(/^PRO\s/.test(line)) return m.pro;
      if(!/^INI\s/.test(line)) return line;
      const k=line.match(/^INI\s+([^=]+)=/); if(!k) return line;
      const key=k[1].trim();
      const values={CentralMeridian:m.central,EPSG:m.epsg,FalseEasting:m.fe,FalseNorthing:'0',NorthParallel:m.north,Projection:m.projection,RefLatitude:m.ref,ScaleFactor:m.scale,SouthParallel:m.south,UnitsName:'US Survey Foot',ZoneId:m.zoneId,ZoneName:m.zoneName};
      return Object.prototype.hasOwnProperty.call(values,key) ? 'INI '+key+'='+values[key] : line;
    });
  }
  function convertHypackText(text, dir, kind, round){
    const [from,to]=dir.split('>');
    const lines=text.split(/\r?\n/); let converted=0, posCount=0, fixCount=0;
    for(let i=0;i<lines.length;i++){
      const line=lines[i];
      if(!line) continue;
      const match=line.match(/^(POS|FIX)\s+/);
      if(!match) continue;
      const type=match[1];
      const parts=line.trim().split(/\s+/);
      let xi=-1, yi=-1;
      if(type==='POS' && parts.length>=5){xi=3; yi=4; posCount++;}
      else if(type==='FIX' && kind==='raw' && parts.length>=6){xi=4; yi=5; fixCount++;}
      if(xi<0 || !isNum(parts[xi]) || !isNum(parts[yi])) continue;
      const x=Number(parts[xi]), y=Number(parts[yi]);
      const [nx,ny]=convertXY(from,to,x,y);
      parts[xi]=round?cvRoundHalfUp(nx,2):nx.toFixed(3);
      parts[yi]=round?cvRoundHalfUp(ny,2):ny.toFixed(3);
      lines[i]=parts.join(' '); converted++;
    }
    const updated=updateRawMetadata(lines,to);
    if(!converted) throw new Error('No supported POS navigation coordinates were found in this file.');
    return {text:updated.join('\r\n'),converted,posCount,fixCount};
  }
  function wire(kind){
    const cap=kind.toUpperCase(),fileEl=document.getElementById(kind+'File'),dirEl=document.getElementById(kind+'Dir'),roundEl=document.getElementById(kind+'Round'),convertBtn=document.getElementById(kind+'ConvertBtn'),downloadBtn=document.getElementById(kind+'DownloadBtn'),zipBtn=document.getElementById(kind+'DownloadZipBtn'),status=document.getElementById(kind+'Status'),namesEl=document.getElementById(kind+'FileNames');
    let selectedFiles=[],mode='multi',zipBlob=null,singleBlob=null,singleName='';
    function reset(){zipBlob=null;singleBlob=null;downloadBtn.style.display='none';zipBtn.style.display='none';status.innerHTML='';}
    function choose(files){mode=files.length===1?'single':'multi';selectedFiles=files;reset();convertBtn.disabled=!files.length;convertBtn.textContent=mode==='single'?'Convert File':'Convert All '+cap;namesEl.textContent=files.length?files.length+' file(s) selected: '+files.map(f=>f.name).join(', '):'No files selected';if(files.length)status.innerHTML='<div class="info">Ready to convert '+files.length+' '+cap+' file(s).</div>';}
    fileEl.addEventListener('change',()=>choose(Array.from(fileEl.files||[])));
    convertBtn.addEventListener('click',async()=>{
      if(!selectedFiles.length)return;if(mode==='multi' && typeof JSZip==='undefined'){status.innerHTML='<div class="error">ZIP support could not load. Check your internet connection and reload this page.</div>';return;}convertBtn.disabled=true;convertBtn.textContent='Converting...';reset();const zip=mode==='multi'?new JSZip():null;let totalConverted=0,totalPos=0,totalFix=0,failed=[];
      try{const [from,to]=dirEl.value.split('>');for(let i=0;i<selectedFiles.length;i++){const file=selectedFiles[i];status.innerHTML='<div class="info">Converting '+(i+1)+' of '+selectedFiles.length+': '+file.name+'</div>';try{const res=convertHypackText(await file.text(),dirEl.value,kind,roundEl.checked),ext=kind==='raw'?'.RAW':'.HSX',tag=ZONES[to].tag,outName=file.name.replace(/\.[^/.]+$/,'')+'_'+tag+ext;if(mode==='single'){singleBlob=new Blob([res.text],{type:'text/plain;charset=utf-8'});singleName=outName;downloadBtn.dataset.outputName=outName;}else zip.file(outName,res.text);totalConverted+=res.converted;totalPos+=res.posCount;totalFix+=res.fixCount;}catch(e){failed.push(file.name+': '+(e.message||e));}await new Promise(resolve=>setTimeout(resolve,0));}
        const converted=mode==='single'?(singleBlob?1:0):Object.keys(zip.files).length;if(!converted)throw new Error('No files could be converted. '+failed.join(' | '));if(mode==='single')downloadBtn.style.display='inline-block';else{zipBlob=await zip.generateAsync({type:'blob'});zipBtn.style.display='inline-block';}
        let msg='Converted '+converted+' of '+selectedFiles.length+' '+cap+' file(s). Total navigation records converted: '+totalConverted.toLocaleString()+'.';if(kind==='raw')msg+=' POS records: '+totalPos.toLocaleString()+'; FIX records: '+totalFix.toLocaleString()+'.';if(failed.length)msg+=' Failed files: '+failed.join(' | ');msg+=mode==='single'?' Click Download or Save As to save the converted file.':' Download ZIP to save all converted files together.';status.innerHTML='<div class="success">'+msg+'</div>';
      }catch(e){status.innerHTML='<div class="error">'+String(e.message||e).replace(/[&<>]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;'}[c]))+'</div>';}finally{convertBtn.disabled=!selectedFiles.length;convertBtn.textContent=mode==='single'?'Convert File':'Convert All '+cap;}
    });
    downloadBtn.addEventListener('click',()=>{if(!singleBlob)return;const url=URL.createObjectURL(singleBlob),a=document.createElement('a');a.href=url;a.download=singleName;document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),1500);});
    zipBtn.addEventListener('click',()=>{if(!zipBlob)return;const tag=ZONES[dirEl.value.split('>')[1]].tag,url=URL.createObjectURL(zipBlob),a=document.createElement('a');a.href=url;a.download='Converted_'+cap+'_'+tag+'.zip';document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),1500);});
    dirEl.addEventListener('change',reset);roundEl.addEventListener('change',reset);
    const clearAll=document.getElementById('clearAllBtn');if(clearAll)clearAll.addEventListener('click',()=>{fileEl.value='';dirEl.selectedIndex=0;roundEl.checked=false;choose([]);convertBtn.textContent='Convert All '+cap;});
  }
  wire('raw'); wire('hsx');
})();

window.GridCore = {convertXY, ZONES, cvConvertText};
})();

</script>
<script>
/* ============================================================
   CONVERT IMAGE TAB: re-georeference a TIFF + TFW between
   NJ 2900 / NY East 3101 / NY Long Island 3104.
   Uses the projection code from the Convert Grid tab (window.GridCore).
============================================================ */

(function () {

const GC = window.GridCore;

/* ---------- TIFF reading ---------- */

function parseIFD(buf) {
  const dv = new DataView(buf);
  if (buf.byteLength < 8) throw new Error("This is not a TIFF file.");
  const bo = dv.getUint16(0);
  const le = bo === 0x4949 ? true : bo === 0x4D4D ? false : null;
  if (le === null) throw new Error("This is not a TIFF file.");
  const magic = dv.getUint16(2, le);
  if (magic === 43) throw new Error("BigTIFF is not supported.");
  if (magic !== 42) throw new Error("This is not a TIFF file.");
  const off = dv.getUint32(4, le);
  const n = dv.getUint16(off, le);
  const sizes = {1: 1, 2: 1, 3: 2, 4: 4, 5: 8, 6: 1, 7: 1, 8: 2, 9: 4, 10: 8, 11: 4, 12: 8, 16: 8};
  const tags = {};
  for (let i = 0; i < n; i++) {
    const e = off + 2 + i * 12;
    const tag = dv.getUint16(e, le), type = dv.getUint16(e + 2, le), count = dv.getUint32(e + 4, le);
    const sz = (sizes[type] || 1) * count;
    const vo = sz <= 4 ? e + 8 : dv.getUint32(e + 8, le);
    const vals = new Array(count);
    for (let k = 0; k < count; k++) {
      switch (type) {
        case 3: vals[k] = dv.getUint16(vo + k * 2, le); break;
        case 4: vals[k] = dv.getUint32(vo + k * 4, le); break;
        case 8: vals[k] = dv.getInt16(vo + k * 2, le); break;
        case 9: vals[k] = dv.getInt32(vo + k * 4, le); break;
        case 5: vals[k] = dv.getUint32(vo + k * 8, le) / (dv.getUint32(vo + k * 8 + 4, le) || 1); break;
        case 12: vals[k] = dv.getFloat64(vo + k * 8, le); break;
        case 16: vals[k] = dv.getUint32(vo + k * 8, le) + dv.getUint32(vo + k * 8 + 4, le) * 4294967296; break;
        default: vals[k] = dv.getUint8(vo + k);
      }
    }
    tags[tag] = vals;
  }
  return {le, tags};
}

function imageSize(buf) {
  const {tags} = parseIFD(buf);
  if (!tags[256] || !tags[257]) throw new Error("Could not read the image size from the TIFF.");
  return {width: tags[256][0], height: tags[257][0]};
}

function lzwDecode(src, expected) {
  const out = new Uint8Array(expected);
  const prefix = new Int32Array(4096), suffix = new Uint8Array(4096), stack = new Uint8Array(4097);
  let op = 0, next = 258, bits = 9, bitBuf = 0, bitCnt = 0, sp = 0, prev = -1;
  function emit(code) {
    let n = 0, c = code;
    while (c >= 258) { stack[n++] = suffix[c]; c = prefix[c]; }
    stack[n++] = c;
    const first = c;
    for (let i = n - 1; i >= 0; i--) { if (op < expected) out[op++] = stack[i]; }
    return first;
  }
  while (op < expected) {
    while (bitCnt < bits && sp < src.length) { bitBuf = ((bitBuf << 8) | src[sp++]) & 0xFFFFFF; bitCnt += 8; }
    if (bitCnt < bits) break;
    const code = (bitBuf >> (bitCnt - bits)) & ((1 << bits) - 1);
    bitCnt -= bits;
    if (code === 257) break;
    if (code === 256) { next = 258; bits = 9; prev = -1; continue; }
    if (prev === -1) {
      if (op < expected) out[op++] = code;
      prev = code;
      continue;
    }
    let first;
    if (code < next) {
      first = emit(code);
    } else {
      let c = prev;
      while (c >= 258) c = prefix[c];
      first = c;
      emit(prev);
      if (op < expected) out[op++] = first;
    }
    if (next < 4096) {
      prefix[next] = prev; suffix[next] = first; next++;
      if (next === 511) bits = 10; else if (next === 1023) bits = 11; else if (next === 2047) bits = 12;
    }
    prev = code;
  }
  return out;
}

function packBitsDecode(src, expected) {
  const out = new Uint8Array(expected);
  let ip = 0, op = 0;
  while (op < expected && ip < src.length) {
    const n = (src[ip++] << 24) >> 24;
    if (n >= 0) {
      for (let i = 0; i <= n && op < expected; i++) out[op++] = src[ip++];
    } else if (n !== -128) {
      const v = src[ip++];
      for (let i = 0; i < 1 - n && op < expected; i++) out[op++] = v;
    }
  }
  return out;
}

async function inflate(src) {
  if (typeof DecompressionStream === "undefined") throw new Error("This browser cannot read Deflate-compressed TIFF files.");
  const stream = new Blob([src]).stream().pipeThrough(new DecompressionStream("deflate"));
  return new Uint8Array(await new Response(stream).arrayBuffer());
}

async function decodeTiff(buf) {
  const {tags} = parseIFD(buf);
  const t = (k, d) => (tags[k] ? tags[k] : d);
  const W = t(256)[0], H = t(257)[0];
  const bits = t(258, [1]), spp = t(277, [1])[0], comp = t(259, [1])[0];
  const photo = t(262, [1])[0], planar = t(284, [1])[0], pred = t(317, [1])[0];
  if (bits.some(b => b !== 8)) throw new Error("Only 8-bit TIFF images are supported for the north-up option.");
  if (planar !== 1) throw new Error("Planar TIFF layout is not supported for the north-up option.");
  if (comp === 7 || comp === 6) throw new Error("JPEG-compressed TIFF is not supported for the north-up option.");
  if (![1, 5, 8, 32946, 32773].includes(comp)) throw new Error("This TIFF compression is not supported for the north-up option.");
  const bytes = new Uint8Array(buf);
  const raw = new Uint8Array(W * H * spp);

  async function chunk(off, len, expected) {
    const src = bytes.subarray(off, off + len);
    if (comp === 1) return src;
    if (comp === 5) return lzwDecode(src, expected);
    if (comp === 32773) return packBitsDecode(src, expected);
    return inflate(src);
  }
  function unpredict(d, rows, w) {
    if (pred !== 2) return;
    for (let r = 0; r < rows; r++) {
      const base = r * w * spp;
      for (let i = spp; i < w * spp; i++) d[base + i] = (d[base + i] + d[base + i - spp]) & 255;
    }
  }

  if (tags[322]) {
    const tw = tags[322][0], th = tags[323][0], offs = tags[324], cnts = tags[325];
    const across = Math.ceil(W / tw);
    for (let i = 0; i < offs.length; i++) {
      const d = await chunk(offs[i], cnts[i], tw * th * spp);
      const tmp = d.length >= tw * th * spp ? d : (() => { const z = new Uint8Array(tw * th * spp); z.set(d); return z; })();
      const copy = comp === 1 ? Uint8Array.from(tmp) : tmp;
      unpredict(copy, th, tw);
      const tx = (i % across) * tw, ty = Math.floor(i / across) * th;
      const cw = Math.min(tw, W - tx), chh = Math.min(th, H - ty);
      for (let r = 0; r < chh; r++) {
        raw.set(copy.subarray(r * tw * spp, r * tw * spp + cw * spp), ((ty + r) * W + tx) * spp);
      }
    }
  } else {
    const rps = Math.min(t(278, [H])[0], H), offs = tags[273], cnts = tags[279];
    for (let s = 0; s < offs.length; s++) {
      const rows = Math.min(rps, H - s * rps);
      if (rows <= 0) break;
      const need = rows * W * spp;
      const len = cnts ? cnts[s] : need;
      let d = await chunk(offs[s], len, need);
      if (comp === 1) d = Uint8Array.from(d.subarray(0, need));
      unpredict(d, rows, W);
      raw.set(d.subarray(0, need), s * rps * W * spp);
    }
  }

  /* to RGB or RGBA */
  const n = W * H;
  if (photo === 2 && spp >= 3) {
    const ch = spp >= 4 ? 4 : 3;
    if (spp === ch) return {width: W, height: H, ch, data: raw};
    const data = new Uint8Array(n * ch);
    for (let i = 0; i < n; i++) for (let k = 0; k < ch; k++) data[i * ch + k] = raw[i * spp + k];
    return {width: W, height: H, ch, data};
  }
  if ((photo === 0 || photo === 1) && spp >= 1) {
    const ch = spp >= 2 ? 4 : 3;
    const data = new Uint8Array(n * ch);
    for (let i = 0; i < n; i++) {
      const g = photo === 0 ? 255 - raw[i * spp] : raw[i * spp];
      data[i * ch] = data[i * ch + 1] = data[i * ch + 2] = g;
      if (ch === 4) data[i * ch + 3] = raw[i * spp + 1];
    }
    return {width: W, height: H, ch, data};
  }
  if (photo === 3 && tags[320]) {
    const cm = tags[320], cnt = cm.length / 3;
    const data = new Uint8Array(n * 3);
    for (let i = 0; i < n; i++) {
      const v = raw[i * spp];
      data[i * 3] = cm[v] >> 8; data[i * 3 + 1] = cm[cnt + v] >> 8; data[i * 3 + 2] = cm[2 * cnt + v] >> 8;
    }
    return {width: W, height: H, ch: 3, data};
  }
  throw new Error("This TIFF color type is not supported for the north-up option.");
}

/* ---------- TIFF writing (uncompressed 8-bit RGB / RGBA) ---------- */

function encodeTiff(data, W, H, ch, geo) {
  const rps = Math.max(1, Math.floor(65536 / (W * ch)));
  const nStrips = Math.ceil(H / rps);
  const dataLen = W * H * ch;

  /* Optional embedded GeoTIFF information.  The raster itself remains
     uncompressed 8-bit RGB/RGBA, just like the normal TIFF writer. */
  const hasGeo = !!geo;
  const nTags = (ch === 4 ? 14 : 13) + (hasGeo ? 2 : 0);
  let pos = 8 + dataLen;
  if (pos % 2) pos++;
  const bitsOff = pos; pos += ch * 2;
  const xresOff = pos; pos += 8;
  const yresOff = pos; pos += 8;
  const soOff = pos; pos += nStrips > 1 ? nStrips * 4 : 0;
  const scOff = pos; pos += nStrips > 1 ? nStrips * 4 : 0;

  let mtOff = 0, keyOff = 0;
  if (hasGeo) {
    if (pos % 8) pos += 8 - (pos % 8);
    mtOff = pos; pos += 16 * 8;
    if (pos % 2) pos++;
    keyOff = pos; pos += 20 * 2; // GeoKeyDirectory: 4 header + 4 keys x 4 shorts
  }

  const ifdOff = pos;
  const total = ifdOff + 2 + nTags * 12 + 4;
  const buf = new ArrayBuffer(total);
  const dv = new DataView(buf);
  new Uint8Array(buf, 8, dataLen).set(data);
  dv.setUint8(0, 0x49); dv.setUint8(1, 0x49); dv.setUint16(2, 42, true); dv.setUint32(4, ifdOff, true);
  for (let i = 0; i < ch; i++) dv.setUint16(bitsOff + i * 2, 8, true);
  dv.setUint32(xresOff, 72, true); dv.setUint32(xresOff + 4, 1, true);
  dv.setUint32(yresOff, 72, true); dv.setUint32(yresOff + 4, 1, true);

  const counts = [];
  for (let st = 0; st < nStrips; st++) {
    const rows = Math.min(rps, H - st * rps);
    counts.push(rows * W * ch);
    if (nStrips > 1) {
      dv.setUint32(soOff + st * 4, 8 + st * rps * W * ch, true);
      dv.setUint32(scOff + st * 4, rows * W * ch, true);
    }
  }

  if (hasGeo) {
    const m = geo.matrix;
    for (let i = 0; i < 16; i++) dv.setFloat64(mtOff + i * 8, Number(m[i]), true);

    const epsg = Number(geo.epsg);
    const keys = [
      1024, 0, 1, 1,       // GTModelTypeGeoKey = Projected
      1025, 0, 1, 1,       // GTRasterTypeGeoKey = PixelIsArea
      2048, 0, 1, 4269,    // GeographicTypeGeoKey = NAD83
      3072, 0, 1, epsg     // ProjectedCSTypeGeoKey
    ];
    dv.setUint16(keyOff, 1, true);      // GeoTIFF version
    dv.setUint16(keyOff + 2, 1, true);  // revision major
    dv.setUint16(keyOff + 4, 0, true);  // revision minor
    dv.setUint16(keyOff + 6, 4, true);  // number of keys
    for (let i = 0; i < keys.length; i++) dv.setUint16(keyOff + 8 + i * 2, keys[i], true);
  }

  let e = ifdOff;
  dv.setUint16(e, nTags, true); e += 2;
  function entry(tag, type, count, value) {
    dv.setUint16(e, tag, true); dv.setUint16(e + 2, type, true); dv.setUint32(e + 4, count, true);
    if (type === 3 && count === 1) dv.setUint16(e + 8, value, true); else dv.setUint32(e + 8, value, true);
    e += 12;
  }
  entry(256, 4, 1, W);
  entry(257, 4, 1, H);
  entry(258, 3, ch, bitsOff);
  entry(259, 3, 1, 1);
  entry(262, 3, 1, 2);
  entry(273, 4, nStrips, nStrips > 1 ? soOff : 8);
  entry(277, 3, 1, ch);
  entry(278, 4, 1, rps);
  entry(279, 4, nStrips, nStrips > 1 ? scOff : counts[0]);
  entry(282, 5, 1, xresOff);
  entry(283, 5, 1, yresOff);
  entry(284, 3, 1, 1);
  entry(296, 3, 1, 2);
  if (ch === 4) entry(338, 3, 1, 2);
  if (hasGeo) {
    entry(34264, 12, 16, mtOff); // ModelTransformationTag
    entry(34735, 3, 20, keyOff); // GeoKeyDirectoryTag
  }
  dv.setUint32(e, 0, true);
  return buf;
}
/* ---------- Georeferencing math ---------- */

function parseTfw(text) {
  const v = text.split(/\s+/).filter(Boolean).slice(0, 6).map(Number);
  if (v.length < 6 || v.some(x => !isFinite(x))) throw new Error("The TFW file must contain 6 numbers.");
  return v; /* A D B E C F */
}

/* Read embedded GeoTIFF CRS and convert its pixel-corner georeferencing to TFW pixel-center form. */
function embeddedGeoTfw(image) {
  const fd = image.getFileDirectory ? image.getFileDirectory() : {};
  const rawKeys = image.getGeoKeys ? image.getGeoKeys() : null;
  const keys = rawKeys || {};
  const epsg = Number(keys.ProjectedCSTypeGeoKey || keys.ProjectedCRSGeoKey || 0);
  const zones = {2260:"NYE",6538:"NYE",2263:"NYLI",6539:"NYLI",3424:"NJ"};
  const zone = zones[epsg] || null;

  const mt = fd.ModelTransformation;
  if (mt && mt.length >= 16) {
    const a=Number(mt[0]), b=Number(mt[1]), d=Number(mt[4]), e=Number(mt[5]);
    const c=Number(mt[3]), f=Number(mt[7]);
    if ([a,b,c,d,e,f].every(Number.isFinite))
      return {tfw:[a,d,b,e,c+.5*a+.5*b,f+.5*d+.5*e],zone,epsg,source:"Embedded GeoTIFF ModelTransformation"};
  }

  const scale=fd.ModelPixelScale, tie=fd.ModelTiepoint;
  if (scale && tie && scale.length>=2 && tie.length>=6) {
    const sx=Number(scale[0]), sy=Math.abs(Number(scale[1])), tx=Number(tie[3]), ty=Number(tie[4]);
    if ([sx,sy,tx,ty].every(Number.isFinite))
      return {tfw:[sx,0,0,-sy,tx+sx/2,ty-sy/2],zone,epsg,source:"Embedded GeoTIFF ModelPixelScale/ModelTiepoint"};
  }
  return null;
}

/* Fit X = a*u + b*v + c, Y = d*u + e*v + f over the whole image (u,v = continuous pixel coords). */
function fitAffine(S, W, H, from, to) {
  const N = 15, cu = W / 2, cv = H / 2;
  const rows = [], X = [], Y = [];
  for (let i = 0; i < N; i++) for (let j = 0; j < N; j++) {
    const u = W * j / (N - 1), v = H * i / (N - 1);
    const col = u - 0.5, row = v - 0.5;
    const x = S[0] * col + S[2] * row + S[4], y = S[1] * col + S[3] * row + S[5];
    const p = GC.convertXY(from, to, x, y);
    rows.push([u - cu, v - cv, 1]); X.push(p[0]); Y.push(p[1]);
  }
  function solve(T) {
    const M = [[0, 0, 0], [0, 0, 0], [0, 0, 0]], r = [0, 0, 0];
    for (let k = 0; k < rows.length; k++) for (let a = 0; a < 3; a++) {
      r[a] += rows[k][a] * T[k];
      for (let b = 0; b < 3; b++) M[a][b] += rows[k][a] * rows[k][b];
    }
    for (let c = 0; c < 3; c++) {
      let piv = c;
      for (let q = c + 1; q < 3; q++) if (Math.abs(M[q][c]) > Math.abs(M[piv][c])) piv = q;
      [M[c], M[piv]] = [M[piv], M[c]]; [r[c], r[piv]] = [r[piv], r[c]];
      for (let q = c + 1; q < 3; q++) {
        const f = M[q][c] / M[c][c];
        for (let b = c; b < 3; b++) M[q][b] -= f * M[c][b];
        r[q] -= f * r[c];
      }
    }
    const s = [0, 0, 0];
    for (let c = 2; c >= 0; c--) {
      let acc = r[c];
      for (let b = c + 1; b < 3; b++) acc -= M[c][b] * s[b];
      s[c] = acc / M[c][c];
    }
    return s;
  }
  const sx = solve(X), sy = solve(Y);
  const a = sx[0], b = sx[1], c = sx[2] - a * cu - b * cv;
  const d = sy[0], e = sy[1], f = sy[2] - d * cu - e * cv;
  let maxErr = 0;
  for (let k = 0; k < rows.length; k++) {
    const u = rows[k][0] + cu, v = rows[k][1] + cv;
    maxErr = Math.max(maxErr, Math.hypot(a * u + b * v + c - X[k], d * u + e * v + f - Y[k]));
  }
  return {T: [a, b, c, d, e, f], maxErr};
}

const fmt = v => v.toFixed(12);
function tfwText(v) { return v.map(fmt).join("\r\n") + "\r\n"; }

/* ---------- Resampling (bicubic) to a north-up grid ---------- */

async function warp(img, T, outW, outH, X0, Ytop, ps, onProgress) {
  const W = img.width, H = img.height, ch = img.ch, src = img.data;
  const [a, b, c, d, e, f] = T;
  const det = a * e - b * d;
  const i00 = e / det, i01 = -b / det, i10 = -d / det, i11 = a / det;
  const out = new Uint8Array(outW * outH * ch);
  const A = -0.5;
  const cub = x => { x = Math.abs(x); return x <= 1 ? ((A + 2) * x - (A + 3)) * x * x + 1 : (x < 2 ? A * (((x - 5) * x + 8) * x - 4) : 0); };
  const wx = new Float64Array(4), wy = new Float64Array(4), xi = new Int32Array(4), yo = new Int32Array(4);
  const fill = [255, 255, 255, 0];
  let o = 0, lastYield = 0;
  for (let y = 0; y < outH; y++) {
    const Y = Ytop - (y + 0.5) * ps;
    for (let x = 0; x < outW; x++) {
      const dx = X0 + (x + 0.5) * ps - c, dy = Y - f;
      const u = i00 * dx + i01 * dy, v = i10 * dx + i11 * dy;
      if (u < 0 || v < 0 || u >= W || v >= H) {
        for (let k = 0; k < ch; k++) out[o++] = fill[k];
        continue;
      }
      const fu = u - 0.5, fv = v - 0.5;
      const x0 = Math.floor(fu), y0 = Math.floor(fv), tx = fu - x0, ty = fv - y0;
      for (let k = 0; k < 4; k++) {
        wx[k] = cub(tx - (k - 1)); wy[k] = cub(ty - (k - 1));
        const xx = x0 + k - 1, yy = y0 + k - 1;
        xi[k] = (xx < 0 ? 0 : xx >= W ? W - 1 : xx) * ch;
        yo[k] = (yy < 0 ? 0 : yy >= H ? H - 1 : yy) * W * ch;
      }
      for (let k = 0; k < ch; k++) {
        let acc = 0;
        for (let j = 0; j < 4; j++) {
          const base = yo[j] + k;
          acc += wy[j] * (wx[0] * src[base + xi[0]] + wx[1] * src[base + xi[1]] + wx[2] * src[base + xi[2]] + wx[3] * src[base + xi[3]]);
        }
        out[o++] = acc < 0 ? 0 : acc > 255 ? 255 : (acc + 0.5) | 0;
      }
    }
    if (onProgress && y - lastYield >= 40) {
      lastYield = y;
      onProgress(y / outH);
      await new Promise(r => setTimeout(r));
    }
  }
  return out;
}

/* ---------- Main conversion (no DOM) ---------- */

async function convertImage(imgBuf, tfwStr, dir, mode, onProgress) {
  const sameCoordinates = dir === "SAME";
  const [from, to] = sameCoordinates ? [null, null] : dir.split(">");
  const {width: W, height: H} = imageSize(imgBuf);
  let S = null, sourceInfo = "";
  const geoTiff = await GeoTIFF.fromArrayBuffer(imgBuf);
  const geoImage = await geoTiff.getImage();
  const embedded = embeddedGeoTfw(geoImage);
  if (embedded) {
    if (!sameCoordinates && embedded.zone && embedded.zone !== from) {
      throw new Error("The TIFF is embedded as " + embedded.zone + " (EPSG:" + embedded.epsg + "), but the selected conversion starts from " + from + ".");
    }
    S = embedded.tfw;
    sourceInfo = embedded.source + (embedded.epsg ? " (EPSG:" + embedded.epsg + ")" : "");
  }
  if (!S && tfwStr) {
    S = parseTfw(tfwStr);
    sourceInfo = "External TFW";
  }
  if (!S) throw new Error("No embedded GeoTIFF georeferencing or TFW was found.");
  if (sameCoordinates && (!embedded || !embedded.epsg)) {
    throw new Error("No Selection keeps the original coordinates, but the TIFF must contain an identifiable embedded GeoTIFF CRS. A TFW file alone does not identify its coordinate system.");
  }
  const fit = sameCoordinates
    ? {T: [S[0], S[2], S[4] - 0.5*S[0] - 0.5*S[2], S[1], S[3], S[5] - 0.5*S[1] - 0.5*S[3]], maxErr: 0}
    : fitAffine(S, W, H, from, to);
  const [a, b, c, d, e, f] = fit.T;
  const rot = Math.atan2(d, a) * 180 / Math.PI;
  const scale = Math.hypot(a, d);
  const info = {width: W, height: H, maxErr: fit.maxErr, rotation: rot, pixelSize: scale, sourceInfo};
  if (mode === "geotiff") {
    const img = await decodeTiff(imgBuf);
    const vals = [
      a,
      d,
      b,
      e,
      a * 0.5 + b * 0.5 + c,
      d * 0.5 + e * 0.5 + f
    ];
    const epsg = sameCoordinates ? embedded.epsg : (to === "NJ" ? 3424 : (to === "NYLI" ? 2263 : 2260));
    const tif = encodeTiff(img.data, img.width, img.height, img.ch, {
      epsg,
      matrix: [
        a, b, 0, vals[4],
        d, e, 0, vals[5],
        0, 0, 1, 0,
        0, 0, 0, 1
      ]
    });
    return {...info, tfw: tfwText(vals), tfwValues: vals, tif, outW: img.width, outH: img.height, geoEpsg: epsg};
  }
  if (mode === "rot") {
    /*
       IMPORTANT FOR GLOBAL MAPPER:
       Never return the original TIFF here.  A Global Mapper TIFF can contain
       embedded GeoTIFF georeferencing for the OLD coordinate system.  If the
       original bytes are downloaded, that embedded NYLI georeferencing can
       override/conflict with the new TFW.

       Decode the pixels and write a completely NEW plain TIFF.  The new TIFF
       therefore contains no old GeoTIFF georeferencing tags, and the matching
       TFW supplies the new NJ 2900 position.
    */
    const img = await decodeTiff(imgBuf);
    const vals = [
      a,
      d,
      b,
      e,
      a * 0.5 + b * 0.5 + c,
      d * 0.5 + e * 0.5 + f
    ];
    const tif = encodeTiff(img.data, img.width, img.height, img.ch);
    return {...info, tfw: tfwText(vals), tfwValues: vals, tif, outW: img.width, outH: img.height};
  }
  /* north-up */
  const img = await decodeTiff(imgBuf);
  const sig3 = Number(Math.sqrt(Math.abs(a * e - b * d)).toPrecision(3));
  const ps = sig3 > 0 ? sig3 : 1;
  const corners = [[0, 0], [W, 0], [0, H], [W, H]].map(p => [a * p[0] + b * p[1] + c, d * p[0] + e * p[1] + f]);
  const xs = corners.map(p => p[0]), ys = corners.map(p => p[1]);
  const X0 = Math.floor(Math.min(...xs) / ps) * ps, Ytop = Math.ceil(Math.max(...ys) / ps) * ps;
  const outW = Math.ceil((Math.max(...xs) - X0) / ps - 1e-9), outH = Math.ceil((Ytop - Math.min(...ys)) / ps - 1e-9);
  if (outW * outH * img.ch > 800e6) throw new Error("The output image would be too large for the browser.");
  const px = await warp(img, fit.T, outW, outH, X0, Ytop, ps, onProgress);
  const tif = encodeTiff(px, outW, outH, img.ch);
  const vals = [ps, 0, 0, -ps, X0 + ps / 2, Ytop - ps / 2];
  return {...info, tfw: tfwText(vals), tfwValues: vals, tif, outW, outH, ps};
}

window.ImgCore = {parseIFD, imageSize, decodeTiff, encodeTiff, fitAffine, convertImage, lzwDecode, packBitsDecode};

/* ---------- UI ---------- */

if (typeof document !== "undefined" && document.getElementById("ciConvertBtn")) {
  const $ = id => document.getElementById(id);
  let imgFile = null, tfwFile = null, outTfw = null, outTif = null, outGeo = null, outBase = "";

  function resetOutput() {
    outTfw = outTif = outGeo = null;
    $("ciDlTfw").style.display = "none"; $("ciDlTif").style.display = "none"; $("ciDlGeo").style.display = "none";
    $("ciStatus").innerHTML = ""; $("ciResult").textContent = ""; $("ciProgress").style.display = "none";
  }
  function ready() { $("ciConvertBtn").disabled = !imgFile; }

  $("ciImg").addEventListener("change", e => { imgFile = e.target.files[0] || null; resetOutput(); ready(); });
  $("ciTfw").addEventListener("change", e => { tfwFile = e.target.files[0] || null; resetOutput(); ready(); });
  $("ciDir").addEventListener("change", resetOutput);
  $("ciMode").addEventListener("change", resetOutput);

  function outName(name, from, to) {
    const base = name.replace(/\.[^.]+$/, "");
    const re = new RegExp("(^|[^A-Za-z0-9])" + from + "([^A-Za-z0-9]|$)", "i");
    return re.test(base) ? base.replace(re, (m, p1, p2) => p1 + to + p2) : base + "_" + to;
  }

  $("ciConvertBtn").addEventListener("click", async () => {
    resetOutput();
    const dir = $("ciDir").value, mode = $("ciMode").value;
    const [from, to] = dir === "SAME" ? ["SAME", "SAME"] : dir.split(">");
    $("ciConvertBtn").disabled = true;
    const bar = $("ciProgress");
    try {
      if (mode === "north") { bar.value = 0; bar.style.display = "block"; }
      $("ciStatus").innerHTML = '<div class="info">Working...</div>';
      await new Promise(r => setTimeout(r));
      const imgBuf = await imgFile.arrayBuffer();
      const tfwStr = tfwFile ? await tfwFile.text() : null;
      const res = await convertImage(imgBuf, tfwStr, dir, mode, p => { bar.value = Math.round(p * 100); });
      outBase = (dir === "SAME" ? imgFile.name.replace(/\.[^.]+$/, "") + "_SameCoordinates" : outName(imgFile.name, from, to)) + (mode === "north" ? "_northup" : (mode === "geotiff" ? "_GeoTiff" : ""));
      outTfw = new Blob([res.tfw], {type: "text/plain"});
      /* res.tif is ALWAYS a newly encoded TIFF.  Do not fall back to the
         original bytes because Global Mapper TIFFs may contain old embedded
         GeoTIFF georeferencing. */
      outTif = new Blob([res.tif], {type: "image/tiff"});
      outGeo = mode === "geotiff" ? outTif : null;
      $("ciDlTfw").style.display = mode === "geotiff" ? "none" : "inline-block";
      $("ciDlTif").style.display = mode === "geotiff" ? "none" : "inline-block";
      $("ciDlGeo").style.display = mode === "geotiff" ? "inline-block" : "none";
      $("ciStatus").innerHTML = '<div class="success">Done. ' + res.width + ' x ' + res.height + ' px' +
        (mode === "north" ? ' resampled to ' + res.outW + ' x ' + res.outH + ' px (' + res.ps + ' ft pixels)' :
         mode === "geotiff" ? ' NEW GeoTIFF with embedded EPSG:' + res.geoEpsg + ' georeferencing (no TFW required)' :
         ' NEW TIFF written without the original embedded georeferencing') +
        '. Fit error ' + res.maxErr.toFixed(3) + ' ft.</div>';
      $("ciResult").textContent = res.tfw.replace(/\r\n/g, "\n").trim();
    } catch (err) {
      resetOutput();
      $("ciStatus").innerHTML = '<div class="error">' + String(err.message || err).replace(/[&<>]/g, c => ({"&": "&amp;", "<": "&lt;", ">": "&gt;"}[c])) + '</div>';
    }
    bar.style.display = "none";
    ready();
  });

  function save(blob, name) {
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    a.href = url; a.download = name;
    document.body.appendChild(a); a.click(); document.body.removeChild(a);
    setTimeout(() => URL.revokeObjectURL(url), 2000);
  }
  $("ciDlTfw").addEventListener("click", () => outTfw && save(outTfw, outBase + ".tfw"));
  $("ciDlTif").addEventListener("click", () => outTif && save(outTif, outBase + ".tif"));
  $("ciDlGeo").addEventListener("click", () => outGeo && save(outGeo, outBase + ".tif"));

  const clr = $("clearAllBtn");
  if (clr) clr.addEventListener("click", () => {
    $("ciImg").value = ""; $("ciTfw").value = ""; imgFile = tfwFile = null;
    $("ciDir").selectedIndex = 0; $("ciMode").selectedIndex = 0;
    resetOutput(); ready();
  });
}

})();

</script>

<script>
/* ============================================================
   CONVERT IMAGE TAB: Water / Land Clip (self-contained)
============================================================ */
(function(){
"use strict";
// ===================== TIFF reading =====================
const TYPE_SIZE={1:1,2:1,3:2,4:4,5:8,6:1,7:1,8:2,9:4,10:8,11:4,12:8,16:8,17:8,18:8};
function readTiffIFD(buf){
  const dv=new DataView(buf),bo=dv.getUint16(0);
  if(bo!==0x4949&&bo!==0x4D4D)throw Error('Not a TIFF file.');
  const le=bo===0x4949,u16=o=>dv.getUint16(o,le),u32=o=>dv.getUint32(o,le);
  const magic=u16(2);
  let big=false,ifd;
  if(magic===42)ifd=u32(4);
  else if(magic===43){big=true;ifd=Number(dv.getBigUint64(8,le))}
  else throw Error('Not a TIFF file.');
  const n=big?Number(dv.getBigUint64(ifd,le)):u16(ifd);
  const tags={};
  for(let i=0;i<n;i++){
    const e=big?ifd+8+i*20:ifd+2+i*12;
    const tag=u16(e),type=u16(e+2),count=big?Number(dv.getBigUint64(e+4,le)):u32(e+4);
    const sz=(TYPE_SIZE[type]||1)*count;
    let off=big?(sz<=8?e+12:Number(dv.getBigUint64(e+12,le))):(sz<=4?e+8:u32(e+8));
    const vals=[];
    for(let k=0;k<count;k++){const o=off+k*(TYPE_SIZE[type]||1);
      switch(type){case 1:case 7:case 2:vals.push(dv.getUint8(o));break;case 6:vals.push(dv.getInt8(o));break;
        case 3:vals.push(u16(o));break;case 8:vals.push(dv.getInt16(o,le));break;case 4:vals.push(u32(o));break;
        case 9:vals.push(dv.getInt32(o,le));break;case 5:vals.push(u32(o)/u32(o+4));break;case 10:vals.push(dv.getInt32(o,le)/dv.getInt32(o+4,le));break;
        case 11:vals.push(dv.getFloat32(o,le));break;case 12:vals.push(dv.getFloat64(o,le));break;
        case 16:case 18:vals.push(Number(dv.getBigUint64(o,le)));break;case 17:vals.push(Number(dv.getBigInt64(o,le)));break;default:vals.push(0)}}
    tags[tag]={type,vals:type===2?String.fromCharCode(...vals.filter(c=>c!==0)):vals};
  }
  return{tags,le};
}
function lzwDecode(src,expected){
  const out=new Uint8Array(expected);let op=0;
  const pfx=new Int32Array(4096),suf=new Uint8Array(4096),len=new Uint16Array(4096),first=new Uint8Array(4096);
  for(let i=0;i<256;i++){pfx[i]=-1;suf[i]=i;len[i]=1;first[i]=i}
  let width=9,next=258,old=-1,bitPos=0;const nbits=src.length*8;
  const write=code=>{const l=len[code];let p=op+l-1;if(p>=expected){ // truncate safely
      const tmp=[];let c=code;while(c>=0){tmp.push(suf[c]);c=pfx[c]}tmp.reverse();for(const b of tmp){if(op<expected)out[op++]=b}return}
    let c=code;while(c>=0){out[p--]=suf[c];c=pfx[c]}op+=l};
  while(bitPos+width<=nbits){
    let code=0;for(let i=0;i<width;i++){const b=bitPos+i;code=(code<<1)|((src[b>>3]>>(7-(b&7)))&1)}bitPos+=width;
    if(code===257)break;
    if(code===256){width=9;next=258;old=-1;continue}
    if(old===-1){write(code);old=code;continue}
    if(code<next){write(code);if(next<4096){pfx[next]=old;suf[next]=first[code];len[next]=len[old]+1;first[next]=first[old];next++}}
    else{if(next<4096){pfx[next]=old;suf[next]=first[old];len[next]=len[old]+1;first[next]=first[old];next++}write(next-1)}
    old=code;
    if(next+1>=(1<<width)&&width<12)width++;
    if(op>=expected)break;
  }
  return out;
}
function packbitsDecode(src,expected){const out=new Uint8Array(expected);let i=0,o=0;
  while(i<src.length&&o<expected){const n=(src[i]<<24)>>24;i++;
    if(n>=0){for(let k=0;k<=n&&o<expected;k++)out[o++]=src[i++]}
    else if(n!==-128){const b=src[i++];for(let k=0;k<1-n&&o<expected;k++)out[o++]=b}}
  return out}
async function inflate(src){const s=new Blob([src]).stream().pipeThrough(new DecompressionStream('deflate'));return new Uint8Array(await new Response(s).arrayBuffer())}
async function deflate(src){const s=new Blob([src]).stream().pipeThrough(new CompressionStream('deflate'));return new Uint8Array(await new Response(s).arrayBuffer())}
async function decodeJpegChunk(tables,data){
  let bytes=data;
  if(tables&&tables.length>4){bytes=new Uint8Array(tables.length-2+data.length-2);bytes.set(tables.subarray(0,tables.length-2),0);bytes.set(data.subarray(2),tables.length-2)}
  const bmp=await createImageBitmap(new Blob([bytes],{type:'image/jpeg'}));
  const cv=new OffscreenCanvas(bmp.width,bmp.height),g=cv.getContext('2d');g.drawImage(bmp,0,0);
  const id=g.getImageData(0,0,bmp.width,bmp.height);bmp.close();return{rgba:id.data,w:id.width,h:id.height};
}
// Returns {width,height,rgb:Uint8Array(w*h*3), valid:Uint8Array|null, tags}
async function decodeTiff(buf,progress){
  const{tags}=readTiffIFD(buf);const T=t=>tags[t]&&tags[t].vals;
  const W=T(256)[0],H=T(257)[0];
  const bps=T(258)||[1],spp=(T(277)||[1])[0],comp=(T(259)||[1])[0],photo=(T(262)||[2])[0],planar=(T(284)||[1])[0],pred=(T(317)||[1])[0];
  const fmt=(T(339)||[1])[0];
  if(bps[0]!==8&&!(photo===3&&(bps[0]===8||bps[0]===4)))throw Error('Only 8-bit images are supported (this file has '+bps[0]+'-bit samples).');
  if(fmt!==1&&fmt!==undefined)throw Error('Only unsigned 8-bit images are supported.');
  if(comp===6)throw Error('Old-style JPEG TIFF is not supported. Re-save the image with LZW, Deflate, JPEG or no compression.');
  if(![1,5,7,8,32946,32773].includes(comp))throw Error('Unsupported TIFF compression code '+comp+'.');
  const tiled=!!tags[322];
  const cw=tiled?T(322)[0]:W,ch=tiled?T(323)[0]:(T(278)||[H])[0]>H?H:(T(278)||[H])[0];
  const offs=tiled?T(324):T(273),cnts=tiled?T(325):T(279);
  const across=Math.ceil(W/cw),down=Math.ceil(H/ch),perPlane=across*down;
  const planes=planar===2?spp:1,cspp=planar===2?1:spp;
  const rgb=new Uint8Array(W*H*3);let valid=null;
  const extra=T(338)||[];const hasAlpha=spp>=4&&photo===2||(spp===2&&(photo===1||photo===0));
  if(hasAlpha)valid=new Uint8Array(W*H);
  const cmap=T(320);
  const tablesTag=T(347);const tables=tablesTag?new Uint8Array(tablesTag):null;
  const src=new Uint8Array(buf);
  for(let pl=0;pl<planes;pl++)for(let ci=0;ci<perPlane;ci++){
    const idx=pl*perPlane+ci,cx=(ci%across)*cw,cy=Math.floor(ci/across)*ch;
    const rows=tiled?ch:Math.min(ch,H-cy),cols=tiled?cw:W;
    const expected=rows*cols*cspp;
    const raw=src.subarray(offs[idx],offs[idx]+cnts[idx]);
    let d;let jpeg=null;
    if(cnts[idx]===0){d=new Uint8Array(expected)}
    else if(comp===1)d=raw;
    else if(comp===5)d=lzwDecode(raw,expected);
    else if(comp===8||comp===32946)d=await inflate(raw);
    else if(comp===32773)d=packbitsDecode(raw,expected);
    else if(comp===7)jpeg=await decodeJpegChunk(tables,raw);
    if(jpeg){ // browser returns RGB(A) already converted
      for(let r=0;r<rows;r++){const y=cy+r;if(y>=H)break;for(let c=0;c<cols;c++){const x=cx+c;if(x>=W)continue;
        const s=(r*jpeg.w+c)*4,o=(y*W+x)*3;
        if(photo===1||photo===0){const v=photo===0?255-jpeg.rgba[s]:jpeg.rgba[s];rgb[o]=rgb[o+1]=rgb[o+2]=v}
        else{rgb[o]=jpeg.rgba[s];rgb[o+1]=jpeg.rgba[s+1];rgb[o+2]=jpeg.rgba[s+2]}}}
    }else{
      if(pred===2){for(let r=0;r<rows;r++){const b=r*cols*cspp;for(let i=cspp;i<cols*cspp;i++)d[b+i]=(d[b+i]+d[b+i-cspp])&255}}
      if(planar===1&&photo===2&&cspp>=3){ // fast path: chunky RGB(A)
        const cmax=Math.min(cols,W-cx);
        for(let r=0;r<rows;r++){const y=cy+r;if(y>=H)break;let s=r*cols*cspp,o=(y*W+cx)*3,p=y*W+cx;
          if(valid){for(let c=0;c<cmax;c++,s+=cspp,o+=3,p++){rgb[o]=d[s];rgb[o+1]=d[s+1];rgb[o+2]=d[s+2];valid[p]=d[s+3]>127?1:0}}
          else if(cspp===3)rgb.set(d.subarray(s,s+cmax*3),o);
          else{for(let c=0;c<cmax;c++,s+=cspp,o+=3){rgb[o]=d[s];rgb[o+1]=d[s+1];rgb[o+2]=d[s+2]}}}
      }else
      for(let r=0;r<rows;r++){const y=cy+r;if(y>=H)break;for(let c=0;c<cols;c++){const x=cx+c;if(x>=W)continue;
        const s=(r*cols+c)*cspp,o=(y*W+x)*3,p=y*W+x;
        if(planar===2){if(pl<3)rgb[o+pl]=d[s];else if(pl===3&&valid)valid[p]=d[s]>127?1:0;if(spp===1){rgb[o+1]=rgb[o+2]=rgb[o]}}
        else if(photo===2||photo===6){rgb[o]=d[s];rgb[o+1]=d[s+1];rgb[o+2]=d[s+2];if(valid)valid[p]=d[s+3]>127?1:0}
        else if(photo===3){const v=d[s],n=cmap.length/3;rgb[o]=cmap[v]>>8;rgb[o+1]=cmap[n+v]>>8;rgb[o+2]=cmap[2*n+v]>>8}
        else{let v=d[s];if(photo===0)v=255-v;rgb[o]=rgb[o+1]=rgb[o+2]=v;if(valid)valid[p]=d[s+1]>127?1:0}}}
    }
    if(progress&&ci%64===0)await progress((pl*perPlane+ci)/(planes*perPlane));
  }
  if(photo===6&&comp!==7)throw Error('YCbCr TIFF without JPEG compression is not supported.');
  if(planar===2&&spp===3){}
  return{width:W,height:H,rgb,valid,tags};
}

// ===================== Georeferencing =====================
function parseTfw(text){const v=text.trim().split(/\s+/).map(Number);if(v.length<6||v.slice(0,6).some(x=>!Number.isFinite(x)))throw Error('The TFW file must contain 6 numbers.');return v.slice(0,6)}
// TFW = [A, D, B, E, C, F]; X = A*col + B*row + C (pixel centres)
function geoFromTags(tags){
  const T=t=>tags[t]&&tags[t].vals;
  let pixelIsPoint=false;const gk=T(34735);
  if(gk){for(let i=4;i+3<gk.length;i+=4)if(gk[i]===1025&&gk[i+1]===0)pixelIsPoint=gk[i+3]===2}
  const sh=pixelIsPoint?0:0.5;
  const mt=T(34264);
  if(mt&&mt.length>=16){const[a,b,,c,d,e,,f]=mt;return[a,d,b,e,c+a*sh+b*sh,f+d*sh+e*sh]}
  const sc=T(33550),tp=T(33922);
  if(sc&&tp&&tp.length>=6){const[I,J,,X,Y]=tp,sx=sc[0],sy=sc[1];const c=X-I*sx,f=Y+J*sy;return[sx,0,0,-sy,c+sx*sh,f-sy*sh]}
  return null;
}

// ===================== Water detection =====================
function boxBlur(src,w,h,r){ // separable running-sum box filter, edge clamped
  const tmp=new Float32Array(w*h),out=new Float32Array(w*h),n=2*r+1;
  for(let y=0;y<h;y++){const o=y*w;let s=0;for(let k=-r;k<=r;k++)s+=src[o+Math.min(w-1,Math.max(0,k))];
    for(let x=0;x<w;x++){tmp[o+x]=s/n;s+=src[o+Math.min(w-1,x+r+1)]-src[o+Math.max(0,x-r)]}}
  for(let x=0;x<w;x++){let s=0;for(let k=-r;k<=r;k++)s+=tmp[Math.min(h-1,Math.max(0,k))*w+x];
    for(let y=0;y<h;y++){out[y*w+x]=s/n;s+=tmp[Math.min(h-1,y+r+1)*w+x]-tmp[Math.max(0,y-r)*w+x]}}
  return out;
}
function minmax1D(src,w,h,r,isMin,horizontal){const out=new Uint8Array(w*h);
  if(horizontal){for(let y=0;y<h;y++){const o=y*w;for(let x=0;x<w;x++){let m=src[o+x];const a=Math.max(0,x-r),b=Math.min(w-1,x+r);for(let k=a;k<=b;k++){const v=src[o+k];if(isMin?v<m:v>m)m=v}out[o+x]=m}}}
  else{for(let y=0;y<h;y++){const a=Math.max(0,y-r),b=Math.min(h-1,y+r);for(let x=0;x<w;x++){let m=src[y*w+x];for(let k=a;k<=b;k++){const v=src[k*w+x];if(isMin?v<m:v>m)m=v}out[y*w+x]=m}}}
  return out}
function grayOpen(ch,w,h,r){let a=minmax1D(ch,w,h,r,true,true);a=minmax1D(a,w,h,r,true,false);a=minmax1D(a,w,h,r,false,true);return minmax1D(a,w,h,r,false,false)}
// Build the reduced working image and per-pixel features (done once per file)
function buildFeatures(img,factor){
  const{width:W,height:H,rgb,valid}=img,f=factor,w=Math.floor(W/f),h=Math.floor(H/f),N=w*h;
  const R=new Uint8Array(N),G=new Uint8Array(N),B=new Uint8Array(N),nod=new Uint8Array(N);
  for(let y=0;y<h;y++)for(let x=0;x<w;x++){let r=0,g=0,b=0,cnt=0,bad=0;
    for(let j=0;j<f;j++){const row=(y*f+j)*W;for(let i=0;i<f;i++){const p=row+x*f+i,o=p*3;const isNo=valid?!valid[p]:(rgb[o]===0&&rgb[o+1]===0&&rgb[o+2]===0);if(isNo){bad++;continue}r+=rgb[o];g+=rgb[o+1];b+=rgb[o+2];cnt++}}
    const q=y*w+x;if(cnt){R[q]=r/cnt+.5;G[q]=g/cnt+.5;B[q]=b/cnt+.5}if(bad*2>f*f)nod[q]=1}
  // remove sun glints / whitecaps: grayscale opening (removes small bright specks)
  const rad=2;const oR=grayOpen(R,w,h,rad),oG=grayOpen(G,w,h,rad),oB=grayOpen(B,w,h,rad);
  const br=new Float32Array(N);for(let i=0;i<N;i++)br[i]=(oR[i]+oG[i]+oB[i])/3;
  const m=boxBlur(br,w,h,5),sq=new Float32Array(N);for(let i=0;i<N;i++)sq[i]=br[i]*br[i];
  const m2=boxBlur(sq,w,h,5),sd=new Float32Array(N);for(let i=0;i<N;i++)sd[i]=Math.sqrt(Math.max(0,m2[i]-m[i]*m[i]));
  const sR=boxBlur(Float32Array.from(oR),w,h,2),sG=boxBlur(Float32Array.from(oG),w,h,2),sB=boxBlur(Float32Array.from(oB),w,h,2);
  return{w,h,f,R:sR,G:sG,B:sB,sd,nod,preview:{R,G,B}};
}
// Automatic water colour: most common colour among very smooth pixels
function autoWaterColor(F){
  const{R,G,B,sd,nod,w,h}=F,N=w*h,hist=new Uint32Array(32768);
  for(let i=0;i<N;i++){if(nod[i]||sd[i]>3.5)continue;const br=(R[i]+G[i]+B[i])/3;if(br<20||br>200)continue;hist[((R[i]>>3)<<10)|((G[i]>>3)<<5)|(B[i]>>3)]++}
  let best=0;for(let k=1;k<32768;k++)if(hist[k]>hist[best])best=k;
  if(!hist[best])throw Error('Could not find a smooth water surface automatically. Click on the water in the preview to pick it.');
  const br_=best>>10,bg=(best>>5)&31,bb=best&31;
  return sampleColor(F,i=>{if(nod[i]||sd[i]>3.5)return false;const r=R[i]>>3,g=G[i]>>3,b=B[i]>>3;return Math.abs(r-br_)<=1&&Math.abs(g-bg)<=1&&Math.abs(b-bb)<=1});
}
function sampleColor(F,pred){const{R,G,B,w,h}=F;let n=0,s=[0,0,0],s2=[0,0,0];
  for(let i=0;i<w*h;i++)if(pred(i)){n++;s[0]+=R[i];s[1]+=G[i];s[2]+=B[i];s2[0]+=R[i]*R[i];s2[1]+=G[i]*G[i];s2[2]+=B[i]*B[i]}
  if(!n)throw Error('No water sample found.');
  const mu=s.map(v=>v/n),sig=s2.map((v,k)=>Math.sqrt(Math.max(0,v/n-mu[k]*mu[k])));return{mu,sig,n}}
function pickColorAt(F,px,py,rad=6){const{w,h}=F;const x0=Math.round(px),y0=Math.round(py);
  return sampleColor(F,i=>{const x=i%w,y=(i/w)|0;return Math.abs(x-x0)<=rad&&Math.abs(y-y0)<=rad&&!F.nod[i]})}
function labelComponents(mask,w,h,value,conn8){ // returns {lab:Int32Array, sizes:[], touches:[]}
  const lab=new Int32Array(w*h).fill(-1),sizes=[],touches=[],stack=new Int32Array(w*h);
  for(let s=0;s<w*h;s++){if(mask[s]!==value||lab[s]!==-1)continue;
    const id=sizes.length;let sp=0,size=0,touch=false;stack[sp++]=s;lab[s]=id;
    while(sp){const p=stack[--sp];size++;const x=p%w,y=(p-x)/w;if(x===0||y===0||x===w-1||y===h-1)touch=true;
      for(let dy=-1;dy<=1;dy++)for(let dx=-1;dx<=1;dx++){if(!dx&&!dy)continue;if(!conn8&&dx&&dy)continue;const nx=x+dx,ny=y+dy;if(nx<0||ny<0||nx>=w||ny>=h)continue;const q=ny*w+nx;if(mask[q]===value&&lab[q]===-1){lab[q]=id;stack[sp++]=q}}}
    sizes.push(size);touches.push(touch)}
  return{lab,sizes,touches}}
function binMorph(mask,w,h,erode){const a=new Uint8Array(w*h);
  for(let y=0;y<h;y++)for(let x=0;x<w;x++){let v=erode?1:0;for(let dy=-1;dy<=1&&(erode?v:!v);dy++)for(let dx=-1;dx<=1;dx++){const nx=Math.min(w-1,Math.max(0,x+dx)),ny=Math.min(h-1,Math.max(0,y+dy));const m=mask[ny*w+nx];if(erode&&!m){v=0;break}if(!erode&&m){v=1;break}}a[y*w+x]=v}
  return a}
// opts: {color:{mu,sig}, tolerance (multiplier, 1 = default), smooth (sd limit), minWaterPx, fillPx}
function classify(F,opts){
  const{R,G,B,sd,nod,w,h}=F,N=w*h,{mu,sig}=opts.color;
  const spread=Math.sqrt((sig[0]**2+sig[1]**2+sig[2]**2)/3);
  const tol=Math.min(40,Math.max(opts.minTol||18,3.5*spread))*opts.tolerance,tol2=tol*tol;
  const LW=opts.lumaWeight??1;
  const mb=(mu[0]+mu[1]+mu[2])/3,mc=[mu[0]-mb,mu[1]-mb,mu[2]-mb];
  const sdMax=(opts.smooth||6)*Math.max(1,opts.tolerance);
  let m=new Uint8Array(N);
  for(let i=0;i<N;i++){if(nod[i])continue;const b=(R[i]+G[i]+B[i])/3,dl=(b-mb)*LW,dr=R[i]-b-mc[0],dg=G[i]-b-mc[1],db=B[i]-b-mc[2];
    // brightness differences (shade, shallow water) count half as much as colour differences
    if(dl*dl+(dr*dr+dg*dg+db*db)*(opts.chromaWeight??3)<=tol2&&sd[i]<=sdMax)m[i]=1}
  m=binMorph(binMorph(m,w,h,true),w,h,false);                     // opening: remove specks
  let C=labelComponents(m,w,h,1,true);
  for(let i=0;i<N;i++)if(m[i]&&C.sizes[C.lab[i]]<opts.minWaterPx)m[i]=0; // drop small false patches
  C=labelComponents(m,w,h,0,false);                                // gaps inside water
  for(let i=0;i<N;i++)if(!m[i]&&!nod[i]&&!C.touches[C.lab[i]]&&C.sizes[C.lab[i]]<opts.fillPx)m[i]=1;
  for(let i=0;i<N;i++)if(nod[i])m[i]=0;
  return{mask:m,tol};
}
// Smooth working mask -> value in [0,1] for bilinear upsampling
// ===== improved water detection (v2) =====
function nearestClass(cls,r,g,b){ // returns min weighted squared distance to any class
  let best=1e12,bi=-1;
  for(let k=0;k<cls.length;k++){const c=cls[k],br=(r+g+b)/3,dl=(br-c.mb)*c.LW,dr=r-br-c.mc[0],dg=g-br-c.mc[1],db=b-br-c.mc[2];
    const d=(dl*dl+(dr*dr+dg*dg+db*db)*c.CW)/(c.tol*c.tol);if(d<best){best=d;bi=k}}
  return best; // <=1 means inside that class tolerance
}
function colourClasses(F,opts,first){
  const{R,G,B,sd,nod,w,h}=F,N=w*h,sdMax=opts.texture;
  const pts=[];const step=Math.max(1,Math.floor(N/40000));
  for(let i=0;i<N;i+=step){if(nod[i]||sd[i]>sdMax)continue;const br=(R[i]+G[i]+B[i])/3;if(br<8||br>215)continue;
    if(opts.hue&&B[i]-R[i]<opts.hueMin)continue;pts.push([R[i],G[i],B[i]])}
  const K=Math.max(1,opts.classes|0);
  const mk=(mu,sig)=>{const mb=(mu[0]+mu[1]+mu[2])/3,spread=Math.sqrt((sig[0]**2+sig[1]**2+sig[2]**2)/3);
    return{mu,sig,mb,mc:[mu[0]-mb,mu[1]-mb,mu[2]-mb],LW:opts.lumaWeight,CW:3,tol:Math.min(40,Math.max(opts.minTol||18,3.5*spread))*opts.tolerance}};
  const cls=[mk(first.mu,first.sig)];
  if(K>1&&pts.length>50){
    // k-means seeded with the primary colour, then farthest-point seeds
    let cen=[first.mu.slice()];
    while(cen.length<K+1){let bi=-1,bd=-1;for(let p=0;p<pts.length;p+=7){let d=1e12;for(const c of cen){const dd=(pts[p][0]-c[0])**2+(pts[p][1]-c[1])**2+(pts[p][2]-c[2])**2;if(dd<d)d=dd}if(d>bd){bd=d;bi=p}}cen.push(pts[bi].slice())}
    for(let it=0;it<8;it++){const S=cen.map(()=>[0,0,0,0]);
      for(const p of pts){let bk=0,bd=1e12;for(let k=0;k<cen.length;k++){const d=(p[0]-cen[k][0])**2+(p[1]-cen[k][1])**2+(p[2]-cen[k][2])**2;if(d<bd){bd=d;bk=k}}S[bk][0]+=p[0];S[bk][1]+=p[1];S[bk][2]+=p[2];S[bk][3]++}
      cen=cen.map((c,k)=>S[k][3]?[S[k][0]/S[k][3],S[k][1]/S[k][3],S[k][2]/S[k][3]]:c)}
    const S=cen.map(()=>({n:0,s:[0,0,0],s2:[0,0,0]}));
    for(const p of pts){let bk=0,bd=1e12;for(let k=0;k<cen.length;k++){const d=(p[0]-cen[k][0])**2+(p[1]-cen[k][1])**2+(p[2]-cen[k][2])**2;if(d<bd){bd=d;bk=k}}const q=S[bk];q.n++;for(let c=0;c<3;c++){q.s[c]+=p[c];q.s2[c]+=p[c]*p[c]}}
    for(let k=1;k<cen.length;k++){const q=S[k];if(q.n<pts.length*0.04)continue;const mu=q.s.map(v=>v/q.n),sig=q.s2.map((v,c)=>Math.sqrt(Math.max(0,v/q.n-mu[c]*mu[c])));
      // only keep if hue similar to the primary water colour (blue-ish relative to red)
      if(opts.hue&&mu[2]-mu[0]<opts.hueMin)continue;cls.push(mk(mu,sig))}
  }
  return cls;
}
function classify2(F,opts){
  const{R,G,B,sd,nod,w,h}=F,N=w*h;
  const cls=colourClasses(F,opts,opts.color);
  const sdMax=opts.texture*Math.max(1,opts.tolerance);
  const hueOK=i=>!opts.hue||B[i]-R[i]>=opts.hueMin;
  let m=new Uint8Array(N);
  for(let i=0;i<N;i++){if(nod[i]||sd[i]>sdMax||!hueOK(i))continue;if(nearestClass(cls,R[i],G[i],B[i])<=1)m[i]=1}
  // grow into shaded / darker water that is connected to sure water
  if(opts.grow>0){
    const stepTol=3+4*opts.grow,capMul=1+0.9*opts.grow,sdG=sdMax*(1+0.35*opts.grow);
    const q=new Int32Array(N);let qh=0,qt=0;for(let i=0;i<N;i++)if(m[i])q[qt++]=i;
    while(qh<qt){const p=q[qh++],x=p%w,y=(p-x)/w;
      for(let k=0;k<4;k++){const nx=x+(k===0?1:k===1?-1:0),ny=y+(k===2?1:k===3?-1:0);if(nx<0||ny<0||nx>=w||ny>=h)continue;const j=ny*w+nx;
        if(m[j]||nod[j]||sd[j]>sdG||!hueOK(j))continue;
        const dr=R[j]-R[p],dg=G[j]-G[p],db=B[j]-B[p];if(dr*dr+dg*dg+db*db>stepTol*stepTol*3)continue;
        if(nearestClass(cls,R[j],G[j],B[j])>capMul*capMul)continue;
        m[j]=1;q[qt++]=j}}
  }
  for(let r=0;r<(opts.open|0);r++){m=binMorph(m,w,h,true)}
  for(let r=0;r<(opts.open|0);r++){m=binMorph(m,w,h,false)}
  let C=labelComponents(m,w,h,1,true);
  for(let i=0;i<N;i++)if(m[i]&&C.sizes[C.lab[i]]<opts.minWaterPx)m[i]=0;
  C=labelComponents(m,w,h,0,false);
  for(let i=0;i<N;i++)if(!m[i]&&!nod[i]&&!C.touches[C.lab[i]]&&C.sizes[C.lab[i]]<opts.fillPx)m[i]=1;
  let kept=0;
  if(opts.inland==='main'){ // keep separate ponds / lakes: remove only water connected to the main water body
    C=labelComponents(m,w,h,1,true);const nc=C.sizes.length,tn=new Uint8Array(nc);let big=-1,bs=0;
    for(let k=0;k<nc;k++)if(C.sizes[k]>bs){bs=C.sizes[k];big=k}
    for(let i=0;i<N;i++){if(!m[i])continue;const x=i%w,y=(i-x)/w;
      if((x>0&&nod[i-1])||(x<w-1&&nod[i+1])||(y>0&&nod[i-w])||(y<h-1&&nod[i+w]))tn[C.lab[i]]=1}
    const keep=new Uint8Array(nc);for(let k=0;k<nc;k++){keep[k]=(C.touches[k]||tn[k]||k===big)?0:1;if(keep[k])kept++}
    for(let i=0;i<N;i++)if(m[i]&&keep[C.lab[i]])m[i]=0;
  }
  const sh=opts.shore|0;for(let r=0;r<Math.abs(sh);r++)m=binMorph(m,w,h,sh<0);
  for(let i=0;i<N;i++)if(nod[i])m[i]=0;
  return{mask:m,tol:cls[0].tol,classes:cls.length,pondsKept:kept};
}

function smoothMask(mask,w,h,r){const f=new Float32Array(w*h);for(let i=0;i<w*h;i++)f[i]=mask[i];const rr=r===undefined?1:r;return rr<=0?f:boxBlur(f,w,h,rr)}

// ===================== TIFF writing =====================
function lzwEncode(data){
  const out=[];let acc=0,nacc=0;
  const put=(code,nb)=>{acc=(acc<<nb)|code;nacc+=nb;while(nacc>=8){nacc-=8;out.push((acc>>nacc)&255)}acc&=(1<<nacc)-1};
  const HS=9973,hkey=new Int32Array(HS),hval=new Int16Array(HS);let epoch=1;const hep=new Int32Array(HS);
  let nbits=9,maxcode=511,free=258;
  if(!data.length){put(256,9);put(257,9);if(nacc)out.push((acc<<(8-nacc))&255);return Uint8Array.from(out)}
  put(256,nbits);let ent=data[0];
  for(let i=1;i<data.length;i++){const c=data[i],key=(ent<<8)|c;let hpos=key%HS,found=-1;
    while(hep[hpos]===epoch){if(hkey[hpos]===key){found=hval[hpos];break}hpos=(hpos+1)%HS}
    if(found>=0){ent=found;continue}
    put(ent,nbits);ent=c;hep[hpos]=epoch;hkey[hpos]=key;hval[hpos]=free++;
    if(free===4094){put(256,nbits);nbits=9;maxcode=511;free=258;epoch++}
    else if(free>maxcode){nbits++;maxcode=(1<<nbits)-1}}
  put(ent,nbits);free++;
  if(free===4094){put(256,nbits);nbits=9}else if(free>maxcode)nbits++;
  put(257,nbits);if(nacc)out.push((acc<<(8-nacc))&255);
  return Uint8Array.from(out);
}
const GEO_TAGS=[33550,33922,34264,34735,34736,34737];
// rowSource(y0,rows) -> Uint8Array rows*W*spp ; compression: 'lzw'|'deflate'|'none'
async function writeTiff(W,H,spp,rowSource,opts,progress){
  const rps=Math.max(1,Math.min(H,Math.floor(65536/(W*spp))||1)),nStrips=Math.ceil(H/rps);
  const comp=opts.compression,strips=[];
  for(let s=0;s<nStrips;s++){const y0=s*rps,rows=Math.min(rps,H-y0);let d=rowSource(y0,rows);
    if(comp!=='none'){ // horizontal predictor
      d=Uint8Array.from(d);for(let r=0;r<rows;r++){const b=r*W*spp;for(let i=W*spp-1;i>=spp;i--)d[b+i]=(d[b+i]-d[b+i-spp])&255}}
    strips.push(comp==='lzw'?lzwEncode(d):comp==='deflate'?await deflate(d):d);
    if(progress&&s%16===0)await progress(s/nStrips)}
  const entries=[[256,4,[W]],[257,4,[H]],[258,3,new Array(spp).fill(8)],[259,3,[comp==='lzw'?5:comp==='deflate'?8:1]],[262,3,[2]],
    [273,4,null],[277,3,[spp]],[278,4,[rps]],[279,4,strips.map(s=>s.length)],[284,3,[1]],[305,2,'XYZ water clip tool']];
  if(comp!=='none')entries.push([317,3,[2]]);
  if(spp===4)entries.push([338,3,[2]]);
  if(opts.nodata!=null)entries.push([42113,2,String(opts.nodata)]);
  for(const[t,v]of Object.entries(opts.geo||{}))entries.push([+t,v.type,v.vals]);
  entries.sort((a,b)=>a[0]-b[0]);
  let pos=8;const stripOff=[];for(const s of strips){stripOff.push(pos);pos+=s.length;if(pos&1)pos++}
  entries.find(e=>e[0]===273)[2]=stripOff;
  const ifdPos=pos,ifdSize=2+entries.length*12+4;let extraPos=ifdPos+ifdSize;
  const extra=[],ifd=new DataView(new ArrayBuffer(ifdSize));ifd.setUint16(0,entries.length,true);
  const sz={2:1,3:2,4:4,12:8};
  entries.forEach(([tag,type,vals],i)=>{
    let bytes;if(type===2){const s=vals+'\0';bytes=new Uint8Array([...s].map(c=>c.charCodeAt(0)&255))}
    else{bytes=new Uint8Array(vals.length*sz[type]);const dv=new DataView(bytes.buffer);vals.forEach((v,k)=>{if(type===3)dv.setUint16(k*2,v,true);else if(type===4)dv.setUint32(k*4,v,true);else dv.setFloat64(k*8,v,true)})}
    const e=2+i*12;ifd.setUint16(e,tag,true);ifd.setUint16(e+2,type,true);ifd.setUint32(e+4,type===2?bytes.length:vals.length,true);
    if(bytes.length<=4){for(let k=0;k<bytes.length;k++)ifd.setUint8(e+8+k,bytes[k])}
    else{ifd.setUint32(e+8,extraPos,true);extra.push(bytes);extraPos+=bytes.length;if(extraPos&1){extra.push(new Uint8Array(1));extraPos++}}});
  ifd.setUint32(ifdSize-4,0,true);
  const head=new DataView(new ArrayBuffer(8));head.setUint16(0,0x4949);head.setUint16(2,42,true);head.setUint32(4,ifdPos,true);
  const parts=[head.buffer];for(const s of strips){parts.push(s);if(s.length&1)parts.push(new Uint8Array(1))}
  parts.push(ifd.buffer,...extra);
  if(extraPos>4294967295)throw Error('Output exceeds 4 GB (classic TIFF limit).');
  return parts;
}
// Row generator for the output image. keep: 'land' | 'water'; alpha: true -> RGBA, false -> RGB with nodata 0
function makeRowSource(img,F,maskF,keep,alpha){
  const{width:W,rgb,valid}=img,{w,h,f}=F,spp=alpha?4:3;
  return(y0,rows)=>{const out=new Uint8Array(rows*W*spp);
    for(let r=0;r<rows;r++){const y=y0+r;let v=(y+0.5)/f-0.5;v=Math.min(h-1,Math.max(0,v));const j0=Math.floor(v),j1=Math.min(h-1,j0+1),fy=v-j0;
      for(let x=0;x<W;x++){let u=(x+0.5)/f-0.5;u=Math.min(w-1,Math.max(0,u));const i0=Math.floor(u),i1=Math.min(w-1,i0+1),fx=u-i0;
        const m=(maskF[j0*w+i0]*(1-fx)+maskF[j0*w+i1]*fx)*(1-fy)+(maskF[j1*w+i0]*(1-fx)+maskF[j1*w+i1]*fx)*fy;
        const p=y*W+x,s=p*3,o=(r*W+x)*spp,isWater=m>=0.5;
        let keepPx=keep==='water'?isWater:!isWater;
        if(valid&&!valid[p])keepPx=false;
        if(keepPx){let R=rgb[s],G=rgb[s+1],B=rgb[s+2];if(!alpha&&R===0&&G===0&&B===0)R=G=B=1;out[o]=R;out[o+1]=G;out[o+2]=B;if(alpha)out[o+3]=255}
      }}
    return out}}

// ===================== Water / Land Clip page =====================
const $=id=>document.getElementById(id);
let IMG=null,F=null,GEO=null,COLOR=null,RES=null,EDITS=[],tfwFromFile=null,srcName='image',busy=false,TOOL='remove',K=1;
const tick=()=>new Promise(r=>setTimeout(r,15));
const esc=s=>String(s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const say=(t,kind)=>{$('wcStatus').innerHTML='<div class="'+(kind||'info')+'" style="white-space:pre-wrap">'+esc(t)+'</div>'};
const prog=p=>{const e=$('wcProgress');if(p==null){e.style.display='none';return}e.style.display='block';e.value=Math.round(p*100)};
const fmt=v=>v.toLocaleString(undefined,{maximumFractionDigits:2});
function pixelArea(){const ps=GEO?Math.hypot(GEO[0],GEO[1]):1;return(ps*F.f)**2}
function setBusy(b){busy=b;
  $('wcDetect').disabled=b||!$('wcTif').files[0];
  $('wcUndo').disabled=$('wcClearEd').disabled=b||!EDITS.length;
  $('wcDlTif').style.display=RES?'inline-block':'none';$('wcDlTif').disabled=b;
  $('wcDlTfw').style.display=RES&&GEO?'inline-block':'none';$('wcDlTfw').disabled=b;
  const stem=outStem();$('wcDlTif').dataset.outputName=stem+'.tif';$('wcDlTfw').dataset.outputName=stem+'.tfw'}
function resetAll(){IMG=F=RES=COLOR=null;EDITS=[];$('wcTools').style.display='none';prog(null);setBusy(false)}
$('wcTif').addEventListener('change',()=>{resetAll();say($('wcTif').files[0]?'Click "Detect water".':'Choose a TIFF file to begin.')});
$('wcTfw').addEventListener('change',async()=>{tfwFromFile=null;const f=$('wcTfw').files[0];if(f){try{tfwFromFile=parseTfw(await f.text());if(IMG){GEO=tfwFromFile;if(RES)run()}}catch(e){say('TFW: '+e.message,'error')}}});
const WC_PRESETS={
 auto:{wcTol:1.15,wcGrow:2.5,wcTex:6,wcLuma:1,wcClasses:3,wcHue:true,wcOpen:1,wcShore:0,wcEdge:1,wcMinW:20000,wcFill:500},
 strict:{wcTol:1,wcGrow:0,wcTex:6,wcLuma:1,wcClasses:1,wcHue:false,wcOpen:1,wcShore:0,wcEdge:1,wcMinW:20000,wcFill:500},
 shaded:{wcTol:1.3,wcGrow:3.2,wcTex:7,wcLuma:0.7,wcClasses:3,wcHue:true,wcOpen:1,wcShore:1,wcEdge:1,wcMinW:20000,wcFill:1000},
 smooth:{wcTol:1.15,wcGrow:2.5,wcTex:6,wcLuma:1,wcClasses:3,wcHue:true,wcOpen:2,wcShore:0,wcEdge:3,wcMinW:50000,wcFill:3000},
 fine:{wcTol:1,wcGrow:1.5,wcTex:5,wcLuma:1,wcClasses:3,wcHue:true,wcOpen:0,wcShore:0,wcEdge:0,wcMinW:2000,wcFill:100},
 aggressive:{wcTol:1.4,wcGrow:3.5,wcTex:8,wcLuma:0.6,wcClasses:4,wcHue:true,wcOpen:2,wcShore:1,wcEdge:1,wcMinW:20000,wcFill:2000}};
const WC_SLIDERS=['wcTol','wcGrow','wcTex','wcLuma','wcOpen','wcShore','wcEdge'];
function wcLabels(){for(const id of WC_SLIDERS){const el=$(id+'V');if(el){const v=+$(id).value;el.textContent=id==='wcTol'||id==='wcLuma'?v.toFixed(2):(Number.isInteger(v)?v:v.toFixed(1))}}}
function wcApplyPreset(name){const p=WC_PRESETS[name];if(!p)return;for(const k in p){const el=$(k);if(el.type==='checkbox')el.checked=p[k];else el.value=p[k]}wcLabels()}
function wcShowCustom(){$('wcCustomBox').style.display=$('wcPreset').value==='custom'?'block':'none'}
$('wcPreset').addEventListener('change',()=>{wcApplyPreset($('wcPreset').value);wcShowCustom();if(RES&&!busy)run()});
for(const id of WC_SLIDERS)$(id).addEventListener('input',()=>{wcLabels();$('wcPreset').value='custom'});
for(const id of['wcTol','wcGrow','wcTex','wcLuma','wcClasses','wcHue','wcOpen','wcShore','wcEdge','wcMinW','wcFill','wcInland'])$(id).addEventListener('change',()=>{if(id==='wcClasses'||id==='wcHue'||id==='wcMinW'||id==='wcFill')$('wcPreset').value='custom';if(RES&&!busy)run()});
wcLabels();
for(const id of['wcKeep','wcView','wcZoom'])$(id).addEventListener('change',()=>{if(RES)draw();setBusy(busy)});
document.querySelectorAll('#ciClipPane .wc-tool').forEach(b=>b.addEventListener('click',()=>{TOOL=b.dataset.tool;document.querySelectorAll('#ciClipPane .wc-tool').forEach(x=>x.classList.toggle('active',x===b))}));

$('wcDetect').addEventListener('click',async()=>{
  const f=$('wcTif').files[0];if(!f)return;setBusy(true);
  try{
    if(!IMG){
      srcName=f.name.replace(/\.[^.]+$/,'');
      say('Reading '+f.name+' ('+fmt(f.size/1048576)+' MB) …');prog(0);await tick();
      let buf=await f.arrayBuffer();
      IMG=await decodeTiff(buf,async p=>{say('Decoding image … '+Math.round(p*100)+'%');prog(p*0.7);await tick()});buf=null;
      GEO=tfwFromFile||geoFromTags(IMG.tags);
      say('Analysing '+fmt(IMG.width)+' × '+fmt(IMG.height)+' pixels …');prog(0.75);await tick();
      F=buildFeatures(IMG,Math.max(1,Math.ceil(Math.sqrt(IMG.width*IMG.height/13e6))));
      COLOR=autoWaterColor(F);
    }
    await run();
  }catch(e){console.error(e);say('Error: '+(e.message||e),'error');IMG=F=RES=null}
  prog(null);setBusy(false);
});

async function run(){
  const pa=pixelArea();
  RES=classify2(F,{color:COLOR,tolerance:+$('wcTol').value,texture:+$('wcTex').value,lumaWeight:+$('wcLuma').value,grow:+$('wcGrow').value,classes:+$('wcClasses').value,hue:$('wcHue').checked,hueMin:8,inland:$('wcInland').value,open:+$('wcOpen').value,shore:+$('wcShore').value,minWaterPx:(+$('wcMinW').value||0)/pa,fillPx:(+$('wcFill').value||0)/pa});
  const msgs=applyEdits();
  RES.maskF=smoothMask(RES.mask,F.w,F.h,+$('wcEdge').value);
  let n=0;for(const v of RES.mask)n+=v;let valid=0;for(const v of F.nod)if(!v)valid++;
  const units=GEO?'sq ft':'sq px',wa=n*pa,la=(valid-n)*pa;
  $('wcChip').style.background='rgb('+COLOR.mu.map(Math.round)+')';
  say('Image: '+fmt(IMG.width)+' × '+fmt(IMG.height)+' px'+(GEO?', pixel size '+fmt(Math.hypot(GEO[0],GEO[1]))+' (georeferencing '+(tfwFromFile?'from TFW file':'from GeoTIFF tags')+')':' — no georeferencing found (choose a TFW to get map units and a TFW download)')+
    '\nWater: '+fmt(wa)+' '+units+(GEO?' ('+fmt(wa/43560)+' acres)':'')+
    '\nLand:  '+fmt(la)+' '+units+(GEO?' ('+fmt(la/43560)+' acres)':'')+
    (RES.pondsKept?'\nSeparate inland water bodies kept: '+RES.pondsKept:'')+(EDITS.length?'\nCorrections applied: '+EDITS.length:'')+(msgs.length?'\n'+msgs.join('\n'):'')+
    '\n\nCheck the preview and click on it to correct, then download.','success');
  $('wcTools').style.display='block';draw();setBusy(false);
}
function applyEdits(){const{w,h}=F,m=RES.mask,N=w*h,msgs=[];const stack=new Int32Array(N);
  for(const e of EDITS){
    const x0=Math.min(w-1,Math.floor(e.x)),y0=Math.min(h-1,Math.floor(e.y));
    if(e.type==='remove'){let s=-1;const RR=Math.max(6,Math.ceil(2*K));for(let r=0;r<=RR&&s<0;r++)for(let dy=-r;dy<=r&&s<0;dy++)for(let dx=-r;dx<=r;dx++){const x=x0+dx,y=y0+dy;if(x>=0&&y>=0&&x<w&&y<h&&m[y*w+x]){s=y*w+x;break}}
      if(s<0)continue;let sp=0;stack[sp++]=s;m[s]=0;
      while(sp){const p=stack[--sp],x=p%w,y=(p-x)/w;for(let dy=-1;dy<=1;dy++)for(let dx=-1;dx<=1;dx++){const nx=x+dx,ny=y+dy;if(nx<0||ny<0||nx>=w||ny>=h)continue;const q=ny*w+nx;if(m[q]){m[q]=0;stack[sp++]=q}}}}
    else{const R=Math.max(4,Math.ceil(2*K)),tried=new Set();let done=false,big=false;
      for(let r=0;r<=R&&!done;r++)for(let dy=-r;dy<=r&&!done;dy++)for(let dx=-r;dx<=r&&!done;dx++){
        if(Math.max(Math.abs(dx),Math.abs(dy))!==r)continue;const x=x0+dx,y=y0+dy;if(x<0||y<0||x>=w||y>=h)continue;const s=y*w+x;
        if(m[s]||F.nod[s]||tried.has(s))continue;
        const seen=new Uint8Array(N);let sp=0,cnt=0,list=[],tooBig=false;stack[sp++]=s;seen[s]=1;
        while(sp){const p=stack[--sp];list.push(p);if(++cnt>N*0.03){tooBig=true;break}const px=p%w,py=(p-px)/w;
          for(const[ex,ey]of[[1,0],[-1,0],[0,1],[0,-1]]){const nx=px+ex,ny=py+ey;if(nx<0||ny<0||nx>=w||ny>=h)continue;const q=ny*w+nx;if(!m[q]&&!seen[q]&&!F.nod[q]){seen[q]=1;stack[sp++]=q}}}
        if(tooBig){big=true;for(const p of list)tried.add(p);continue}
        for(const p of list)m[p]=1;done=true}
      if(!done&&big)msgs.push('One "add water" click was ignored: that area connects to a large land area. Zoom in and click inside the gap itself.')}}
  return msgs}

// ---------- preview ----------
const cv=$('wcCv');
function draw(){
  if(!RES)return;
  const{w,h}=F,z=+$('wcZoom').value,boxW=Math.max(300,$('wcWrap').clientWidth-4);
  K=Math.max(1,Math.ceil(Math.max(w/boxW,h/Math.max(450,window.innerHeight*0.74))))/z;K=Math.max(K,1/4);
  const cw=Math.floor(w/K),ch=Math.floor(h/K);cv.width=cw;cv.height=ch;
  const g=cv.getContext('2d'),id=g.createImageData(cw,ch),D=id.data,{R,G,B}=F.preview,m=RES.mask,mode=$('wcView').value,keepLand=$('wcKeep').value==='land';
  for(let y=0;y<ch;y++){const sy=Math.min(h-1,Math.floor(y*K));for(let x=0;x<cw;x++){const sx=Math.min(w-1,Math.floor(x*K)),s=sy*w+sx,o=(y*cw+x)*4;
    let r=R[s],gg=G[s],b=B[s];const water=m[s]===1;
    if(mode==='overlay'){if(water){r=r*0.45;gg=gg*0.45+50;b=b*0.45+140}}
    else{const keep=F.nod[s]?false:(keepLand?!water:water);if(!keep){const c=((x>>3)+(y>>3))&1?235:250;r=gg=b=c}}
    D[o]=r;D[o+1]=gg;D[o+2]=b;D[o+3]=255}}
  g.putImageData(id,0,0);cv.style.width=cw+'px';
  for(const e of EDITS){g.beginPath();g.arc(e.x/K,e.y/K,5,0,7);g.fillStyle=e.type==='remove'?'#e63946':'#2a9d8f';g.fill();g.strokeStyle='#fff';g.stroke()}
}
cv.addEventListener('click',async e=>{
  if(busy||!RES)return;const rc=cv.getBoundingClientRect();const x=(e.clientX-rc.left)*(cv.width/rc.width)*K,y=(e.clientY-rc.top)*(cv.height/rc.height)*K;
  setBusy(true);say('Updating …');await tick();
  try{if(TOOL==='pick')COLOR=pickColorAt(F,x,y,6);else EDITS.push({type:TOOL,x,y});await run()}catch(err){say('Error: '+err.message,'error')}
  setBusy(false);
});
$('wcUndo').onclick=async()=>{EDITS.pop();setBusy(true);await tick();await run()};
$('wcClearEd').onclick=async()=>{EDITS=[];setBusy(true);await tick();await run()};
window.addEventListener('resize',()=>{if(RES&&$('ciClipPane').classList.contains('active'))draw()});

// ---------- downloads ----------
function download(name,parts,type){const blob=new Blob(parts,{type}),url=URL.createObjectURL(blob),a=document.createElement('a');a.href=url;a.download=name;document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),60000)}
function outStem(){return srcName+'_'+$('wcKeep').value+'_only'}
$('wcDlTif').addEventListener('click',async()=>{
  if(!RES||busy)return;setBusy(true);
  try{
    const alpha=$('wcBg').value==='alpha',keep=$('wcKeep').value;
    const geo={};for(const k of GEO_TAGS)if(IMG.tags[k])geo[k]={type:IMG.tags[k].type,vals:IMG.tags[k].vals};
    if(tfwFromFile||(!geo[34264]&&!geo[33922]&&GEO)){delete geo[33550];delete geo[33922];const[A,D,Bx,E,C,Fy]=GEO;geo[34264]={type:12,vals:[A,Bx,0,C-A/2-Bx/2,D,E,0,Fy-D/2-E/2,0,0,0,0,0,0,0,1]}}
    for(const k in geo){const t=geo[k].type;if(t!==2&&t!==3&&t!==12)geo[k].type=(t===4?4:12)}
    prog(0);
    const parts=await writeTiff(IMG.width,IMG.height,alpha?4:3,makeRowSource(IMG,F,RES.maskF,keep,alpha),{compression:$('wcComp').value,geo,nodata:alpha?null:0},
      async p=>{say('Writing TIFF … '+Math.round(p*100)+'%');prog(p);await tick()});
    download(outStem()+'.tif',parts,'image/tiff');
    say('TIFF saved: '+outStem()+'.tif'+(GEO?'\nAlso download the TFW so programs without GeoTIFF support place it correctly.':''),'success');
  }catch(e){console.error(e);say('Error writing TIFF: '+e.message,'error')}
  prog(null);setBusy(false);
});
$('wcDlTfw').addEventListener('click',()=>{if(!GEO)return;download(outStem()+'.tfw',[GEO.map(v=>String(v)).join('\r\n')+'\r\n'],'text/plain')});
const clr=$('clearAllBtn');if(clr)clr.addEventListener('click',()=>{$('wcTif').value='';$('wcTfw').value='';tfwFromFile=null;GEO=null;resetAll();$('wcPreset').value='auto';wcApplyPreset('auto');wcShowCustom();$('wcInland').value='main';say('Choose a TIFF file to begin.')});
setBusy(false);

})();
</script>

<script>
/* ============================================================
   EXTRACT XYZ TAB: XYZ -> Border .brd/.dxf (self-contained)
============================================================ */
(function(){
"use strict";
// ---------- Delaunay triangulation (sweep-hull, after Delaunator by Mapbox, ISC licence) ----------
const DL_EPS=Math.pow(2,-52);
function Delaunay(coords){
  const n=coords.length>>1;
  const maxT=Math.max(2*n-5,0);
  const triangles=new Uint32Array(maxT*3), halfedges=new Int32Array(maxT*3);
  const hashSize=Math.ceil(Math.sqrt(n));
  const hullPrev=new Uint32Array(n), hullNext=new Uint32Array(n), hullTri=new Uint32Array(n), hullHash=new Int32Array(hashSize).fill(-1);
  const ids=new Uint32Array(n), dists=new Float64Array(n);
  const STACK=new Uint32Array(512);
  let trianglesLen=0, hullStart=0, cxC=0, cyC=0;
  const X=i=>coords[2*i], Y=i=>coords[2*i+1];
  function link(a,b){halfedges[a]=b;if(b!==-1)halfedges[b]=a}
  function addTri(i0,i1,i2,a,b,c){const t=trianglesLen;triangles[t]=i0;triangles[t+1]=i1;triangles[t+2]=i2;link(t,a);link(t+1,b);link(t+2,c);trianglesLen+=3;return t}
  function hashKey(x,y){return Math.floor(pseudoAngle(x-cxC,y-cyC)*hashSize)%hashSize}
  function legalize(a){
    let i=0,ar=0;
    while(true){
      const b=halfedges[a];const a0=a-a%3;ar=a0+(a+2)%3;
      if(b===-1){if(i===0)break;a=STACK[--i];continue}
      const b0=b-b%3,al=a0+(a+1)%3,bl=b0+(b+2)%3;
      const p0=triangles[ar],pr=triangles[a],pl=triangles[al],p1=triangles[bl];
      if(inCircle(X(p0),Y(p0),X(pr),Y(pr),X(pl),Y(pl),X(p1),Y(p1))){
        triangles[a]=p1;triangles[b]=p0;
        const hbl=halfedges[bl];
        if(hbl===-1){let e=hullStart;do{if(hullTri[e]===bl){hullTri[e]=a;break}e=hullPrev[e]}while(e!==hullStart)}
        link(a,hbl);link(b,halfedges[ar]);link(ar,bl);
        const br=b0+(b+1)%3;
        if(i<STACK.length)STACK[i++]=br;
      }else{if(i===0)break;a=STACK[--i]}
    }
    return ar;
  }
  let minX=Infinity,minY=Infinity,maxX=-Infinity,maxY=-Infinity;
  for(let i=0;i<n;i++){const x=X(i),y=Y(i);if(x<minX)minX=x;if(y<minY)minY=y;if(x>maxX)maxX=x;if(y>maxY)maxY=y;ids[i]=i}
  const cx=(minX+maxX)/2,cy=(minY+maxY)/2;
  let i0=0,i1=0,i2=0;
  for(let i=0,md=Infinity;i<n;i++){const d=sqd(cx,cy,X(i),Y(i));if(d<md){i0=i;md=d}}
  const i0x=X(i0),i0y=Y(i0);
  for(let i=0,md=Infinity;i<n;i++){if(i===i0)continue;const d=sqd(i0x,i0y,X(i),Y(i));if(d<md&&d>0){i1=i;md=d}}
  let i1x=X(i1),i1y=Y(i1),minR=Infinity;
  for(let i=0;i<n;i++){if(i===i0||i===i1)continue;const r=circumradius(i0x,i0y,i1x,i1y,X(i),Y(i));if(r<minR){i2=i;minR=r}}
  let i2x=X(i2),i2y=Y(i2);
  if(minR===Infinity)throw Error('All points lie on a single line; a boundary area cannot be formed.');
  if(orient(i0x,i0y,i1x,i1y,i2x,i2y)){const i=i1,x=i1x,y=i1y;i1=i2;i1x=i2x;i1y=i2y;i2=i;i2x=x;i2y=y}
  const c=circumcenter(i0x,i0y,i1x,i1y,i2x,i2y);cxC=c.x;cyC=c.y;
  for(let i=0;i<n;i++)dists[i]=sqd(X(i),Y(i),c.x,c.y);
  quicksort(ids,dists,0,n-1);
  hullStart=i0;let hullSize=3;
  hullNext[i0]=hullPrev[i2]=i1;hullNext[i1]=hullPrev[i0]=i2;hullNext[i2]=hullPrev[i1]=i0;
  hullTri[i0]=0;hullTri[i1]=1;hullTri[i2]=2;
  hullHash[hashKey(i0x,i0y)]=i0;hullHash[hashKey(i1x,i1y)]=i1;hullHash[hashKey(i2x,i2y)]=i2;
  addTri(i0,i1,i2,-1,-1,-1);
  for(let k=0,xp=0,yp=0;k<n;k++){
    const i=ids[k],x=X(i),y=Y(i);
    if(k>0&&Math.abs(x-xp)<=DL_EPS&&Math.abs(y-yp)<=DL_EPS)continue;
    xp=x;yp=y;
    if(i===i0||i===i1||i===i2)continue;
    let start=0;
    for(let j=0,key=hashKey(x,y);j<hashSize;j++){start=hullHash[(key+j)%hashSize];if(start!==-1&&start!==hullNext[start])break}
    start=hullPrev[start];
    let e=start,q;
    while(q=hullNext[e],!orient(x,y,X(e),Y(e),X(q),Y(q))){e=q;if(e===start){e=-1;break}}
    if(e===-1)continue;
    let t=addTri(e,i,hullNext[e],-1,-1,hullTri[e]);
    hullTri[i]=legalize(t+2);hullTri[e]=t;hullSize++;
    let nn=hullNext[e];
    while(q=hullNext[nn],orient(x,y,X(nn),Y(nn),X(q),Y(q))){t=addTri(nn,i,q,hullTri[i],-1,hullTri[nn]);hullTri[i]=legalize(t+2);hullNext[nn]=nn;hullSize--;nn=q}
    if(e===start){while(q=hullPrev[e],orient(x,y,X(q),Y(q),X(e),Y(e))){t=addTri(q,i,e,-1,hullTri[e],hullTri[q]);legalize(t+2);hullTri[q]=t;hullNext[e]=e;hullSize--;e=q}}
    hullStart=hullPrev[i]=e;hullNext[e]=hullPrev[nn]=i;hullNext[i]=nn;
    hullHash[hashKey(x,y)]=i;hullHash[hashKey(X(e),Y(e))]=e;
  }
  return {triangles:triangles.subarray(0,trianglesLen),halfedges:halfedges.subarray(0,trianglesLen)};
}
function pseudoAngle(dx,dy){const p=dx/(Math.abs(dx)+Math.abs(dy));return(dy>0?3-p:1+p)/4}
function sqd(ax,ay,bx,by){const dx=ax-bx,dy=ay-by;return dx*dx+dy*dy}
function orient(px,py,qx,qy,rx,ry){return(qy-py)*(rx-qx)-(qx-px)*(ry-qy)<0}
function inCircle(ax,ay,bx,by,cx,cy,px,py){const dx=ax-px,dy=ay-py,ex=bx-px,ey=by-py,fx=cx-px,fy=cy-py;const ap=dx*dx+dy*dy,bp=ex*ex+ey*ey,cp=fx*fx+fy*fy;return dx*(ey*cp-bp*fy)-dy*(ex*cp-bp*fx)+ap*(ex*fy-ey*fx)<0}
function circumradius(ax,ay,bx,by,cx,cy){const dx=bx-ax,dy=by-ay,ex=cx-ax,ey=cy-ay,bl=dx*dx+dy*dy,cl=ex*ex+ey*ey,d=0.5/(dx*ey-dy*ex),x=(ey*bl-dy*cl)*d,y=(dx*cl-ex*bl)*d;return x*x+y*y}
function circumcenter(ax,ay,bx,by,cx,cy){const dx=bx-ax,dy=by-ay,ex=cx-ax,ey=cy-ay,bl=dx*dx+dy*dy,cl=ex*ex+ey*ey,d=0.5/(dx*ey-dy*ex);return{x:ax+(ey*bl-dy*cl)*d,y:ay+(dx*cl-ex*bl)*d}}
function quicksort(ids,dists,left,right){
  if(right-left<=20){for(let i=left+1;i<=right;i++){const temp=ids[i],td=dists[temp];let j=i-1;while(j>=left&&dists[ids[j]]>td)ids[j+1]=ids[j--];ids[j+1]=temp}}
  else{const median=(left+right)>>1;let i=left+1,j=right;swap(ids,median,i);
    if(dists[ids[left]]>dists[ids[right]])swap(ids,left,right);
    if(dists[ids[i]]>dists[ids[right]])swap(ids,i,right);
    if(dists[ids[left]]>dists[ids[i]])swap(ids,left,i);
    const temp=ids[i],td=dists[temp];
    while(true){do i++;while(dists[ids[i]]<td);do j--;while(dists[ids[j]]>td);if(j<i)break;swap(ids,i,j)}
    ids[left+1]=ids[j];ids[j]=temp;
    if(right-i+1>=j-left){quicksort(ids,dists,i,right);quicksort(ids,dists,left,j-1)}
    else{quicksort(ids,dists,left,j-1);quicksort(ids,dists,i,right)}}
}
function swap(a,i,j){const t=a[i];a[i]=a[j];a[j]=t}

// ---------- Concave outer boundary (chi-shape: peel long outer triangle edges) ----------
// coords: Float64Array [x0,y0,x1,y1,...] already shifted near the origin.
// Starts from the Delaunay triangulation (whose outline is the convex hull) and repeatedly removes the
// outer triangle behind the longest boundary edge while that edge is longer than maxLen.
// A triangle is only removed if its inner vertex is not already on the boundary, so the outline
// always stays ONE simple polygon: it never crosses itself and never pinches through a narrow neck.
function spacingStats(coords,del){
  const n=coords.length>>1,nn=new Float64Array(n).fill(Infinity),{triangles:T}=del;
  for(let e=0;e<T.length;e++){const a=T[e],b=T[e%3===2?e-2:e+1];const d=Math.sqrt(sqd(coords[2*a],coords[2*a+1],coords[2*b],coords[2*b+1]));if(d<nn[a])nn[a]=d;if(d<nn[b])nn[b]=d}
  const v=[];for(let i=0;i<n;i++)if(nn[i]<Infinity)v.push(nn[i]);
  v.sort((a,b)=>a-b);
  // trimmed mean (drop top 2%) so a few isolated stray points don't inflate the spacing
  const keep=v.slice(0,Math.max(1,Math.floor(v.length*0.98)));
  const mean=keep.reduce((s,x)=>s+x,0)/keep.length;
  return{meanNN:mean,medianNN:v[v.length>>1]};
}
function concaveBoundary(coords,del,maxLen){
  const{triangles:T,halfedges:H}=del,m=T.length,n=coords.length>>1;
  const nxt=e=>e%3===2?e-2:e+1;
  const half=Int32Array.from(H);              // working copy; -1 = boundary edge
  const alive=new Uint8Array(m/3).fill(1);
  const onB=new Uint8Array(n);
  const len=e=>{const a=T[e],b=T[nxt(e)];return Math.sqrt(sqd(coords[2*a],coords[2*a+1],coords[2*b],coords[2*b+1]))};
  // max-heap of boundary edges
  const hp=[],hk=[];
  const push=(e,k)=>{hp.push(e);hk.push(k);let i=hp.length-1;while(i>0){const p=(i-1)>>1;if(hk[p]>=hk[i])break;[hp[p],hp[i]]=[hp[i],hp[p]];[hk[p],hk[i]]=[hk[i],hk[p]];i=p}};
  const pop=()=>{const e=hp[0],k=hk[0],le=hp.pop(),lk=hk.pop();if(hp.length){hp[0]=le;hk[0]=lk;let i=0;for(;;){const l=2*i+1,r=l+1;let b=i;if(l<hp.length&&hk[l]>hk[b])b=l;if(r<hp.length&&hk[r]>hk[b])b=r;if(b===i)break;[hp[b],hp[i]]=[hp[i],hp[b]];[hk[b],hk[i]]=[hk[i],hk[b]];i=b}}return[e,k]};
  for(let e=0;e<m;e++)if(half[e]===-1){onB[T[e]]=1;const k=len(e);if(k>maxLen)push(e,k)}
  let removed=0;
  while(hp.length){
    const[e]=pop();const t=(e/3)|0;
    if(!alive[t]||half[e]!==-1)continue;
    const e1=nxt(e),e2=nxt(e1),v=T[e2];      // v = inner vertex opposite the boundary edge
    if(onB[v])continue;                       // would pinch the polygon at v -> keep this edge
    alive[t]=0;removed++;onB[v]=1;
    for(const f of[e1,e2]){const tw=half[f];half[f]=-2;if(tw>=0){half[tw]=-1;const k=len(tw);if(k>maxLen)push(tw,k)}}
  }
  // walk the remaining outer boundary
  const out=new Int32Array(n).fill(-1);let count=0,first=-1;
  for(let e=0;e<m;e++)if(alive[(e/3)|0]&&half[e]===-1){out[T[e]]=T[nxt(e)];count++;if(first<0)first=T[e]}
  const ring=[];let v=first;
  for(let i=0;i<=count;i++){ring.push(v);v=out[v];if(v===first)break}
  if(ring.length!==count)throw Error('Internal error tracing the boundary ('+ring.length+' of '+count+' edges).');
  return{ring,removed};
}

// ---------- Extract XYZ -> Border page logic ----------
const $=id=>document.getElementById(id);
const typeSel=$('extractType'),stdPanel=$('extractStdPanel'),panel=$('bdPanel');
let state=null,result=null,view=null;
const esc=s=>String(s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const say=(t,kind)=>{$('bdStatus').innerHTML=t?'<div class="'+(kind||'info')+'">'+esc(t)+'</div>':''};
const fmt=v=>v.toLocaleString(undefined,{maximumFractionDigits:2});
const tick=()=>new Promise(r=>setTimeout(r,20));
function syncPanel(){const on=typeSel.value==='border';panel.style.display=on?'block':'none';stdPanel.style.display=on?'none':'block';if(on&&result){view=null;draw()}}
typeSel.addEventListener('change',syncPanel);
function parseXYZ(txt){
  const seen=new Set(),xs=[],ys=[];
  const lines=txt.replace(/^﻿/,'').split(/\r?\n/);
  for(let k=0;k<lines.length;k++){const s=lines[k].trim();if(!s||s[0]==='#'||s[0]===';')continue;
    const a=s.split(/[\s,;]+/);if(a.length<2)continue;const x=+a[0],y=+a[1];if(!Number.isFinite(x)||!Number.isFinite(y))continue;
    const key=a[0]+'|'+a[1];if(seen.has(key))continue;seen.add(key);xs.push(x);ys.push(y)}
  return{xs,ys};
}
function prepare(xs,ys){
  const n=xs.length;let ox=Infinity,oy=Infinity;
  for(let i=0;i<n;i++){if(xs[i]<ox)ox=xs[i];if(ys[i]<oy)oy=ys[i]}
  const coords=new Float64Array(2*n);for(let i=0;i<n;i++){coords[2*i]=xs[i]-ox;coords[2*i+1]=ys[i]-oy}
  const del=Delaunay(coords);
  const T=del.triangles,H=del.halfedges,nn=new Float64Array(n).fill(Infinity);let edges=new Float64Array(T.length),ne=0;
  for(let e=0;e<T.length;e++){const a=T[e],b=T[e%3===2?e-2:e+1];const d=Math.hypot(coords[2*a]-coords[2*b],coords[2*a+1]-coords[2*b+1]);
    if(d<nn[a])nn[a]=d;if(d<nn[b])nn[b]=d;if(H[e]<e)edges[ne++]=d}
  edges=edges.subarray(0,ne).sort();
  let sm=0,c=0;for(const v of nn)if(v<Infinity){sm+=v;c++}const meanNN=sm/c;
  const p99=edges[Math.min(edges.length-1,Math.floor(edges.length*0.99))];
  return{coords,del,ox,oy,stats:{meanNN,auto:Math.max(1.15*p99,1.5*meanNN)}};
}
function makeBoundary(L){
  const{coords,del,ox,oy}=state;const{ring}=concaveBoundary(coords,del,L);
  let pts=ring.map(i=>({x:coords[2*i]+ox,y:coords[2*i+1]+oy}));
  let A=0;for(let i=0;i<pts.length;i++){const a=pts[i],b=pts[(i+1)%pts.length];A+=a.x*b.y-b.x*a.y}
  if(A>0)pts.reverse();
  let s=0;for(let i=1;i<pts.length;i++)if(pts[i].y<pts[s].y||(pts[i].y===pts[s].y&&pts[i].x<pts[s].x))s=i;
  return{pts:pts.slice(s).concat(pts.slice(0,s)),area:Math.abs(A/2)};
}
function dxf(points){let s='0\nSECTION\n2\nHEADER\n9\n$ACADVER\n1\nAC1009\n0\nENDSEC\n0\nSECTION\n2\nENTITIES\n0\nPOLYLINE\n8\nBOUNDARY\n66\n1\n10\n0.0\n20\n0.0\n30\n0.0\n70\n1\n';for(const p of points)s+='0\nVERTEX\n8\nBOUNDARY\n10\n'+p.x.toFixed(4)+'\n20\n'+p.y.toFixed(4)+'\n30\n0.0\n';return s+'0\nSEQEND\n8\nBOUNDARY\n0\nENDSEC\n0\nEOF\n'}
function brd(points){const p=points.slice();p.push(p[0]);return p.map(q=>q.x.toFixed(2)+' '+q.y.toFixed(2)).join('\r\n')+'\r\n'}
function download(name,content,type){const blob=new Blob([content],{type}),url=URL.createObjectURL(blob),a=document.createElement('a');a.href=url;a.download=name;document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),1500)}
function showDl(on){for(const id of['bdDlBrd','bdDlDxf'])$(id).style.display=on?'inline-block':'none';
  if(result){$('bdDlBrd').dataset.outputName=result.stem+'_border.brd';$('bdDlDxf').dataset.outputName=result.stem+'_border.dxf'}}
function reset(msg){state=null;result=null;showDl(false);$('bdUseAuto').disabled=true;$('bdWrap').style.display='none';$('bdResult').textContent='';say(msg||'')}

$('bdFile').addEventListener('change',()=>{const f=$('bdFile').files[0];$('bdFileName').textContent=f?f.name:'No file selected';$('bdProcessBtn').disabled=!f;reset()});
$('bdUseAuto').addEventListener('click',()=>{if(state)$('bdMax').value=state.stats.auto.toFixed(1)});
$('bdClearBtn').addEventListener('click',()=>{$('bdFile').value='';$('bdMax').value='';$('bdFileName').textContent='No file selected';$('bdProcessBtn').disabled=true;reset()});
const clr=$('clearAllBtn');if(clr)clr.addEventListener('click',()=>{$('bdClearBtn').click();syncPanel()});

$('bdProcessBtn').addEventListener('click',async()=>{
  const f=$('bdFile').files[0];if(!f)return;
  const raw=$('bdMax').value.trim(),manual=raw===''?null:Number(raw);
  if(manual!==null&&(!Number.isFinite(manual)||manual<=0)){say('Enter a positive maximum segment length in feet, or leave it blank for automatic.','error');return}
  const btn=$('bdProcessBtn');btn.disabled=true;
  try{
    if(!state||state.file!==f){
      say('Reading '+f.name+' …');await tick();
      const{xs,ys}=parseXYZ(await f.text());
      if(xs.length<3)throw Error('Could not find at least 3 valid XY points. Expected X Y [Z] values separated by spaces, commas or tabs.');
      say('Triangulating '+fmt(xs.length)+' points …');await tick();
      state=Object.assign(prepare(xs,ys),{xs,ys,file:f});$('bdUseAuto').disabled=false;
    }
    const L=manual??state.stats.auto;say('Tracing border …');await tick();
    const{pts,area}=makeBoundary(L);
    let longest=0,over=0;for(let i=0;i<pts.length;i++){const d=Math.hypot(pts[i].x-pts[(i+1)%pts.length].x,pts[i].y-pts[(i+1)%pts.length].y);if(d>longest)longest=d;if(d>L*1.000001)over++}
    result={pts,L,stem:f.name.replace(/\.[^.]+$/,'')};
    $('bdResult').textContent='Unique XY points:          '+fmt(state.xs.length)+'\nAverage point spacing:     '+fmt(state.stats.meanNN)+' ft\nAutomatic max segment:     '+fmt(state.stats.auto)+' ft\nMax segment used:          '+fmt(L)+' ft'+(manual===null?' (automatic)':' (manual)')+
      '\nBorder vertices:           '+fmt(pts.length)+' (all real survey points)\nLongest border segment:    '+fmt(longest)+' ft\nEnclosed area:             '+fmt(area)+' sq ft ('+fmt(area/43560)+' acres)';
    say('Border created.'+(over?' '+over+' segment(s) are longer than the limit; they were kept because going inward there would cross the border or cut through a narrow neck.':'')+' Download the BRD or DXF.','success');
    $('bdWrap').style.display='block';view=null;draw();showDl(true);
  }catch(e){console.error(e);say('Could not create border: '+e.message,'error');showDl(false)}
  finally{btn.disabled=!$('bdFile').files[0]}
});
$('bdDlBrd').addEventListener('click',()=>{if(result)download(result.stem+'_border.brd',brd(result.pts),'text/plain')});
$('bdDlDxf').addEventListener('click',()=>{if(result)download(result.stem+'_border.dxf',dxf(result.pts),'application/dxf')});

// ---------- preview ----------
const cv=$('bdCv');
function fitView(){const W=cv.clientWidth,H=cv.clientHeight;let x0=Infinity,y0=Infinity,x1=-Infinity,y1=-Infinity;for(const p of result.pts){if(p.x<x0)x0=p.x;if(p.x>x1)x1=p.x;if(p.y<y0)y0=p.y;if(p.y>y1)y1=p.y}
  return{s:0.92*Math.min(W/((x1-x0)||1),H/((y1-y0)||1)),cx:(x0+x1)/2,cy:(y0+y1)/2}}
function draw(){
  if(!result||!cv.clientWidth)return;const dpr=window.devicePixelRatio||1,W=cv.clientWidth,H=cv.clientHeight;
  cv.width=W*dpr;cv.height=H*dpr;const g=cv.getContext('2d');g.setTransform(dpr,0,0,dpr,0,0);g.clearRect(0,0,W,H);
  if(!view)view=fitView();const{s,cx,cy}=view,tx=x=>W/2+(x-cx)*s,ty=y=>H/2-(y-cy)*s;
  const{xs,ys}=state,n=xs.length,step=Math.max(1,Math.floor(n/250000));
  g.fillStyle='#9aa4ae';const r=s*state.stats.meanNN>6?2:1.2;
  for(let i=0;i<n;i+=step){const X=tx(xs[i]),Y=ty(ys[i]);if(X<-2||Y<-2||X>W+2||Y>H+2)continue;g.fillRect(X-r/2,Y-r/2,r,r)}
  const P=result.pts;g.strokeStyle='#d62828';g.lineWidth=1.6;g.lineJoin='round';g.beginPath();
  for(let i=0;i<=P.length;i++){const p=P[i%P.length];i?g.lineTo(tx(p.x),ty(p.y)):g.moveTo(tx(p.x),ty(p.y))}g.stroke();
  if(P.length<3000||s*state.stats.meanNN>4){g.fillStyle='#d62828';for(const p of P){const X=tx(p.x),Y=ty(p.y);if(X>-3&&Y>-3&&X<W+3&&Y<H+3)g.fillRect(X-1.5,Y-1.5,3,3)}}
}
cv.addEventListener('wheel',e=>{if(!view)return;e.preventDefault();const rc=cv.getBoundingClientRect(),W=cv.clientWidth,H=cv.clientHeight,mx=e.clientX-rc.left,my=e.clientY-rc.top;
  const wx=view.cx+(mx-W/2)/view.s,wy=view.cy-(my-H/2)/view.s;view.s*=Math.exp(-e.deltaY*0.0015);view.cx=wx-(mx-W/2)/view.s;view.cy=wy+(my-H/2)/view.s;draw()},{passive:false});
let drag=null;
cv.addEventListener('pointerdown',e=>{if(!view)return;drag={x:e.clientX,y:e.clientY,cx:view.cx,cy:view.cy};cv.setPointerCapture(e.pointerId);cv.style.cursor='grabbing'});
cv.addEventListener('pointermove',e=>{if(!drag)return;view.cx=drag.cx-(e.clientX-drag.x)/view.s;view.cy=drag.cy+(e.clientY-drag.y)/view.s;draw()});
cv.addEventListener('pointerup',()=>{drag=null;cv.style.cursor='grab'});
cv.addEventListener('dblclick',()=>{view=null;draw()});
window.addEventListener('resize',()=>{if(panel.style.display!=='none')draw()});
document.querySelectorAll('.tab-button').forEach(b=>b.addEventListener('click',()=>setTimeout(()=>{if(panel.offsetParent)draw()},0)));
syncPanel();

})();
</script>

<script>
/* ============================================================
   CREATE CONTOURS TAB (self-contained TIN contour generator)
============================================================ */
(function(){
"use strict";
// ---------- Delaunay triangulation (sweep-hull, after Delaunator by Mapbox, ISC licence) ----------
const DL_EPS=Math.pow(2,-52);
function Delaunay(coords){
  const n=coords.length>>1;
  const maxT=Math.max(2*n-5,0);
  const triangles=new Uint32Array(maxT*3), halfedges=new Int32Array(maxT*3);
  const hashSize=Math.ceil(Math.sqrt(n));
  const hullPrev=new Uint32Array(n), hullNext=new Uint32Array(n), hullTri=new Uint32Array(n), hullHash=new Int32Array(hashSize).fill(-1);
  const ids=new Uint32Array(n), dists=new Float64Array(n);
  const STACK=new Uint32Array(512);
  let trianglesLen=0, hullStart=0, cxC=0, cyC=0;
  const X=i=>coords[2*i], Y=i=>coords[2*i+1];
  function link(a,b){halfedges[a]=b;if(b!==-1)halfedges[b]=a}
  function addTri(i0,i1,i2,a,b,c){const t=trianglesLen;triangles[t]=i0;triangles[t+1]=i1;triangles[t+2]=i2;link(t,a);link(t+1,b);link(t+2,c);trianglesLen+=3;return t}
  function hashKey(x,y){return Math.floor(pseudoAngle(x-cxC,y-cyC)*hashSize)%hashSize}
  function legalize(a){
    let i=0,ar=0;
    while(true){
      const b=halfedges[a];const a0=a-a%3;ar=a0+(a+2)%3;
      if(b===-1){if(i===0)break;a=STACK[--i];continue}
      const b0=b-b%3,al=a0+(a+1)%3,bl=b0+(b+2)%3;
      const p0=triangles[ar],pr=triangles[a],pl=triangles[al],p1=triangles[bl];
      if(inCircle(X(p0),Y(p0),X(pr),Y(pr),X(pl),Y(pl),X(p1),Y(p1))){
        triangles[a]=p1;triangles[b]=p0;
        const hbl=halfedges[bl];
        if(hbl===-1){let e=hullStart;do{if(hullTri[e]===bl){hullTri[e]=a;break}e=hullPrev[e]}while(e!==hullStart)}
        link(a,hbl);link(b,halfedges[ar]);link(ar,bl);
        const br=b0+(b+1)%3;
        if(i<STACK.length)STACK[i++]=br;
      }else{if(i===0)break;a=STACK[--i]}
    }
    return ar;
  }
  let minX=Infinity,minY=Infinity,maxX=-Infinity,maxY=-Infinity;
  for(let i=0;i<n;i++){const x=X(i),y=Y(i);if(x<minX)minX=x;if(y<minY)minY=y;if(x>maxX)maxX=x;if(y>maxY)maxY=y;ids[i]=i}
  const cx=(minX+maxX)/2,cy=(minY+maxY)/2;
  let i0=0,i1=0,i2=0;
  for(let i=0,md=Infinity;i<n;i++){const d=sqd(cx,cy,X(i),Y(i));if(d<md){i0=i;md=d}}
  const i0x=X(i0),i0y=Y(i0);
  for(let i=0,md=Infinity;i<n;i++){if(i===i0)continue;const d=sqd(i0x,i0y,X(i),Y(i));if(d<md&&d>0){i1=i;md=d}}
  let i1x=X(i1),i1y=Y(i1),minR=Infinity;
  for(let i=0;i<n;i++){if(i===i0||i===i1)continue;const r=circumradius(i0x,i0y,i1x,i1y,X(i),Y(i));if(r<minR){i2=i;minR=r}}
  let i2x=X(i2),i2y=Y(i2);
  if(minR===Infinity)throw Error('All points lie on a single line; a boundary area cannot be formed.');
  if(orient(i0x,i0y,i1x,i1y,i2x,i2y)){const i=i1,x=i1x,y=i1y;i1=i2;i1x=i2x;i1y=i2y;i2=i;i2x=x;i2y=y}
  const c=circumcenter(i0x,i0y,i1x,i1y,i2x,i2y);cxC=c.x;cyC=c.y;
  for(let i=0;i<n;i++)dists[i]=sqd(X(i),Y(i),c.x,c.y);
  quicksort(ids,dists,0,n-1);
  hullStart=i0;let hullSize=3;
  hullNext[i0]=hullPrev[i2]=i1;hullNext[i1]=hullPrev[i0]=i2;hullNext[i2]=hullPrev[i1]=i0;
  hullTri[i0]=0;hullTri[i1]=1;hullTri[i2]=2;
  hullHash[hashKey(i0x,i0y)]=i0;hullHash[hashKey(i1x,i1y)]=i1;hullHash[hashKey(i2x,i2y)]=i2;
  addTri(i0,i1,i2,-1,-1,-1);
  for(let k=0,xp=0,yp=0;k<n;k++){
    const i=ids[k],x=X(i),y=Y(i);
    if(k>0&&Math.abs(x-xp)<=DL_EPS&&Math.abs(y-yp)<=DL_EPS)continue;
    xp=x;yp=y;
    if(i===i0||i===i1||i===i2)continue;
    let start=0;
    for(let j=0,key=hashKey(x,y);j<hashSize;j++){start=hullHash[(key+j)%hashSize];if(start!==-1&&start!==hullNext[start])break}
    start=hullPrev[start];
    let e=start,q;
    while(q=hullNext[e],!orient(x,y,X(e),Y(e),X(q),Y(q))){e=q;if(e===start){e=-1;break}}
    if(e===-1)continue;
    let t=addTri(e,i,hullNext[e],-1,-1,hullTri[e]);
    hullTri[i]=legalize(t+2);hullTri[e]=t;hullSize++;
    let nn=hullNext[e];
    while(q=hullNext[nn],orient(x,y,X(nn),Y(nn),X(q),Y(q))){t=addTri(nn,i,q,hullTri[i],-1,hullTri[nn]);hullTri[i]=legalize(t+2);hullNext[nn]=nn;hullSize--;nn=q}
    if(e===start){while(q=hullPrev[e],orient(x,y,X(q),Y(q),X(e),Y(e))){t=addTri(q,i,e,-1,hullTri[e],hullTri[q]);legalize(t+2);hullTri[q]=t;hullNext[e]=e;hullSize--;e=q}}
    hullStart=hullPrev[i]=e;hullNext[e]=hullPrev[nn]=i;hullNext[i]=nn;
    hullHash[hashKey(x,y)]=i;hullHash[hashKey(X(e),Y(e))]=e;
  }
  return {triangles:triangles.subarray(0,trianglesLen),halfedges:halfedges.subarray(0,trianglesLen)};
}
function pseudoAngle(dx,dy){const p=dx/(Math.abs(dx)+Math.abs(dy));return(dy>0?3-p:1+p)/4}
function sqd(ax,ay,bx,by){const dx=ax-bx,dy=ay-by;return dx*dx+dy*dy}
function orient(px,py,qx,qy,rx,ry){return(qy-py)*(rx-qx)-(qx-px)*(ry-qy)<0}
function inCircle(ax,ay,bx,by,cx,cy,px,py){const dx=ax-px,dy=ay-py,ex=bx-px,ey=by-py,fx=cx-px,fy=cy-py;const ap=dx*dx+dy*dy,bp=ex*ex+ey*ey,cp=fx*fx+fy*fy;return dx*(ey*cp-bp*fy)-dy*(ex*cp-bp*fx)+ap*(ex*fy-ey*fx)<0}
function circumradius(ax,ay,bx,by,cx,cy){const dx=bx-ax,dy=by-ay,ex=cx-ax,ey=cy-ay,bl=dx*dx+dy*dy,cl=ex*ex+ey*ey,d=0.5/(dx*ey-dy*ex),x=(ey*bl-dy*cl)*d,y=(dx*cl-ex*bl)*d;return x*x+y*y}
function circumcenter(ax,ay,bx,by,cx,cy){const dx=bx-ax,dy=by-ay,ex=cx-ax,ey=cy-ay,bl=dx*dx+dy*dy,cl=ex*ex+ey*ey,d=0.5/(dx*ey-dy*ex);return{x:ax+(ey*bl-dy*cl)*d,y:ay+(dx*cl-ex*bl)*d}}
function quicksort(ids,dists,left,right){
  if(right-left<=20){for(let i=left+1;i<=right;i++){const temp=ids[i],td=dists[temp];let j=i-1;while(j>=left&&dists[ids[j]]>td)ids[j+1]=ids[j--];ids[j+1]=temp}}
  else{const median=(left+right)>>1;let i=left+1,j=right;swap(ids,median,i);
    if(dists[ids[left]]>dists[ids[right]])swap(ids,left,right);
    if(dists[ids[i]]>dists[ids[right]])swap(ids,i,right);
    if(dists[ids[left]]>dists[ids[i]])swap(ids,left,i);
    const temp=ids[i],td=dists[temp];
    while(true){do i++;while(dists[ids[i]]<td);do j--;while(dists[ids[j]]>td);if(j<i)break;swap(ids,i,j)}
    ids[left+1]=ids[j];ids[j]=temp;
    if(right-i+1>=j-left){quicksort(ids,dists,i,right);quicksort(ids,dists,left,j-1)}
    else{quicksort(ids,dists,left,j-1);quicksort(ids,dists,i,right)}}
}
function swap(a,i,j){const t=a[i];a[i]=a[j];a[j]=t}

// ---------- Concave outer boundary (chi-shape: peel long outer triangle edges) ----------
// coords: Float64Array [x0,y0,x1,y1,...] already shifted near the origin.
// Starts from the Delaunay triangulation (whose outline is the convex hull) and repeatedly removes the
// outer triangle behind the longest boundary edge while that edge is longer than maxLen.
// A triangle is only removed if its inner vertex is not already on the boundary, so the outline
// always stays ONE simple polygon: it never crosses itself and never pinches through a narrow neck.
function spacingStats(coords,del){
  const n=coords.length>>1,nn=new Float64Array(n).fill(Infinity),{triangles:T}=del;
  for(let e=0;e<T.length;e++){const a=T[e],b=T[e%3===2?e-2:e+1];const d=Math.sqrt(sqd(coords[2*a],coords[2*a+1],coords[2*b],coords[2*b+1]));if(d<nn[a])nn[a]=d;if(d<nn[b])nn[b]=d}
  const v=[];for(let i=0;i<n;i++)if(nn[i]<Infinity)v.push(nn[i]);
  v.sort((a,b)=>a-b);
  // trimmed mean (drop top 2%) so a few isolated stray points don't inflate the spacing
  const keep=v.slice(0,Math.max(1,Math.floor(v.length*0.98)));
  const mean=keep.reduce((s,x)=>s+x,0)/keep.length;
  return{meanNN:mean,medianNN:v[v.length>>1]};
}
function concaveBoundary(coords,del,maxLen){
  const{triangles:T,halfedges:H}=del,m=T.length,n=coords.length>>1;
  const nxt=e=>e%3===2?e-2:e+1;
  const half=Int32Array.from(H);              // working copy; -1 = boundary edge
  const alive=new Uint8Array(m/3).fill(1);
  const onB=new Uint8Array(n);
  const len=e=>{const a=T[e],b=T[nxt(e)];return Math.sqrt(sqd(coords[2*a],coords[2*a+1],coords[2*b],coords[2*b+1]))};
  // max-heap of boundary edges
  const hp=[],hk=[];
  const push=(e,k)=>{hp.push(e);hk.push(k);let i=hp.length-1;while(i>0){const p=(i-1)>>1;if(hk[p]>=hk[i])break;[hp[p],hp[i]]=[hp[i],hp[p]];[hk[p],hk[i]]=[hk[i],hk[p]];i=p}};
  const pop=()=>{const e=hp[0],k=hk[0],le=hp.pop(),lk=hk.pop();if(hp.length){hp[0]=le;hk[0]=lk;let i=0;for(;;){const l=2*i+1,r=l+1;let b=i;if(l<hp.length&&hk[l]>hk[b])b=l;if(r<hp.length&&hk[r]>hk[b])b=r;if(b===i)break;[hp[b],hp[i]]=[hp[i],hp[b]];[hk[b],hk[i]]=[hk[i],hk[b]];i=b}}return[e,k]};
  for(let e=0;e<m;e++)if(half[e]===-1){onB[T[e]]=1;const k=len(e);if(k>maxLen)push(e,k)}
  let removed=0;
  while(hp.length){
    const[e]=pop();const t=(e/3)|0;
    if(!alive[t]||half[e]!==-1)continue;
    const e1=nxt(e),e2=nxt(e1),v=T[e2];      // v = inner vertex opposite the boundary edge
    if(onB[v])continue;                       // would pinch the polygon at v -> keep this edge
    alive[t]=0;removed++;onB[v]=1;
    for(const f of[e1,e2]){const tw=half[f];half[f]=-2;if(tw>=0){half[tw]=-1;const k=len(tw);if(k>maxLen)push(tw,k)}}
  }
  // walk the remaining outer boundary
  const out=new Int32Array(n).fill(-1);let count=0,first=-1;
  for(let e=0;e<m;e++)if(alive[(e/3)|0]&&half[e]===-1){out[T[e]]=T[nxt(e)];count++;if(first<0)first=T[e]}
  const ring=[];let v=first;
  for(let i=0;i<=count;i++){ring.push(v);v=out[v];if(v===first)break}
  if(ring.length!==count)throw Error('Internal error tracing the boundary ('+ring.length+' of '+count+' edges).');
  return{ring,removed,alive};
}
// ===================== TIN model + smooth contouring =====================
// Points: Float64Array xs, ys (shifted to origin), zs.
function dedupePoints(X,Y,Z){
  const map=new Map(),xs=[],ys=[],zs=[],cnt=[];
  for(let i=0;i<X.length;i++){const k=X[i]+'|'+Y[i];const j=map.get(k);
    if(j===undefined){map.set(k,xs.length);xs.push(X[i]);ys.push(Y[i]);zs.push(Z[i]);cnt.push(1)}
    else{zs[j]+=Z[i];cnt[j]++}}
  let dups=0;for(let j=0;j<zs.length;j++)if(cnt[j]>1){zs[j]/=cnt[j];dups+=cnt[j]-1}
  return{xs,ys,zs,dups};
}
function edgeStats(coords,del){
  const T=del.triangles,H=del.halfedges,n=coords.length>>1,nn=new Float64Array(n).fill(Infinity);let edges=new Float64Array(T.length),ne=0;
  for(let e=0;e<T.length;e++){const a=T[e],b=T[e%3===2?e-2:e+1];const d=Math.hypot(coords[2*a]-coords[2*b],coords[2*a+1]-coords[2*b+1]);
    if(d<nn[a])nn[a]=d;if(d<nn[b])nn[b]=d;if(H[e]<e)edges[ne++]=d}
  edges=edges.subarray(0,ne).sort();let s=0,c=0;for(const v of nn)if(v<Infinity){s+=v;c++}
  const p99=edges[Math.min(edges.length-1,Math.floor(edges.length*0.99))];
  return{meanNN:s/c,autoMaxEdge:Math.max(1.15*p99,1.5*s/c)};
}
// Which triangles form the TIN. mode 'all' = drop any triangle with a side > maxEdge (HYPACK style);
// 'outer' = only peel long triangles from the outside (no interior holes).
function tinTriangles(coords,del,maxEdge,mode){
  const T=del.triangles,nt=T.length/3,alive=new Uint8Array(nt).fill(1);
  if(!(maxEdge>0))return alive;
  if(mode==='outer')return concaveBoundary(coords,del,maxEdge).alive;
  const L=(a,b)=>Math.hypot(coords[2*a]-coords[2*b],coords[2*a+1]-coords[2*b+1]);
  for(let t=0;t<nt;t++){const a=T[3*t],b=T[3*t+1],c=T[3*t+2];if(L(a,b)>maxEdge||L(b,c)>maxEdge||L(c,a)>maxEdge)alive[t]=0}
  return alive;
}
// Area-weighted vertex gradients from the surrounding TIN triangles
function vertexGradients(coords,zs,T,alive){
  const n=zs.length,gx=new Float64Array(n),gy=new Float64Array(n),wt=new Float64Array(n);
  for(let t=0;t<alive.length;t++){if(!alive[t])continue;const a=T[3*t],b=T[3*t+1],c=T[3*t+2];
    const x1=coords[2*a],y1=coords[2*a+1],x2=coords[2*b],y2=coords[2*b+1],x3=coords[2*c],y3=coords[2*c+1];
    const d=(x2-x1)*(y3-y1)-(x3-x1)*(y2-y1);if(Math.abs(d)<1e-12)continue;
    const dz2=zs[b]-zs[a],dz3=zs[c]-zs[a];
    const px=(dz2*(y3-y1)-dz3*(y2-y1))/d,py=((x2-x1)*dz3-(x3-x1)*dz2)/d,w=Math.abs(d);
    for(const v of[a,b,c]){gx[v]+=px*w;gy[v]+=py*w;wt[v]+=w}}
  for(let i=0;i<n;i++)if(wt[i]>0){gx[i]/=wt[i];gy[i]/=wt[i]}
  return{gx,gy};
}
// Extract contour segments from the TIN. level n = subdivision (1 = plain linear TIN).
// Surface: cubic Bezier triangle per TIN triangle (edge controls from vertex slopes, clamped so
// every edge stays monotone between its end values -> no invented bumps or false contours).
function contourTIN(coords,zs,del,alive,levels,n,tension,onProgress){
  const T=del.triangles,H=del.halfedges,N=zs.length,nt=alive.length;
  const G=n>1?vertexGradients(coords,zs,T,alive):null;
  const nl=levels.length;
  const segs=levels.map(()=>({keys:[],pts:[]}));          // keys: [k1,k2,...], pts: [x1,y1,x2,y2,...]
  const nv=(n+1)*(n+2)/2,ni=(n-1)*(n-2)/2,edgeBase=N,intBase=N+3*nt*Math.max(0,n-1);
  const sx=new Float64Array(nv),sy=new Float64Array(nv),sz=new Float64Array(nv),sid=new Float64Array(nv);
  const idx=(i,j)=>{/* row j has n+1-j entries */return j*(n+1)-(j*(j-1))/2+i};
  const clamp=(v,a,b)=>v<Math.min(a,b)?Math.min(a,b):v>Math.max(a,b)?Math.max(a,b):v;
  const ctrl=(a,b)=>{ // control value near a on edge a->b
    const dx=coords[2*b]-coords[2*a],dy=coords[2*b+1]-coords[2*a+1];return clamp(zs[a]+tension*(G.gx[a]*dx+G.gy[a]*dy)/3,zs[a],zs[b])};
  const lvlRange=(lo,hi)=>{let a=0,b=nl;while(a<b){const m=(a+b)>>1;if(levels[m]<lo-1e-9)a=m+1;else b=m}const i0=a;
    a=0;b=nl;while(a<b){const m=(a+b)>>1;if(levels[m]<=hi+1e-9)a=m+1;else b=m}return[i0,a-1]};
  for(let t=0;t<nt;t++){
    if(!alive[t])continue;
    const v=[T[3*t],T[3*t+1],T[3*t+2]],z=[zs[v[0]],zs[v[1]],zs[v[2]]];
    let lo=Math.min(z[0],z[1],z[2]),hi=Math.max(z[0],z[1],z[2]);
    const [l0,l1]=lvlRange(lo,hi);if(l0>l1)continue;           // controls are clamped inside [lo,hi]
    const X=[coords[2*v[0]],coords[2*v[1]],coords[2*v[2]]],Y=[coords[2*v[0]+1],coords[2*v[1]+1],coords[2*v[2]+1]];
    // edge ids: edge k joins local vertex k and k+1 (halfedge 3t+k)
    const eid=[0,1,2].map(k=>{const e=3*t+k,h=H[e];return h>=0&&h<e?h:e});
    let b210,b120,b201,b102,b021,b012,b111;
    if(n>1){b210=ctrl(v[0],v[1]);b120=ctrl(v[1],v[0]);b021=ctrl(v[1],v[2]);b012=ctrl(v[2],v[1]);b102=ctrl(v[2],v[0]);b201=ctrl(v[0],v[2]);
      const E=(b210+b120+b021+b012+b102+b201)/6,V=(z[0]+z[1]+z[2])/3;b111=clamp(E+(E-V)/2,lo,hi);}
    // fill sub-vertices
    for(let j=0;j<=n;j++)for(let i=0;i+j<=n;i++){
      const k=idx(i,j),u=(n-i-j)/n,vv=i/n,w=j/n;
      sx[k]=u*X[0]+vv*X[1]+w*X[2];sy[k]=u*Y[0]+vv*Y[1]+w*Y[2];
      let id,zz;
      if(i===0&&j===0){id=v[0];zz=z[0]}else if(i===n){id=v[1];zz=z[1]}else if(j===n){id=v[2];zz=z[2]}
      else{
        let ea=-1,eb,steps;   // edge sub-vertex: canonical evaluation from the lower vertex id
        if(j===0){ea=0;eb=1;steps=i}else if(i+j===n){ea=1;eb=2;steps=j}else if(i===0){ea=2;eb=0;steps=n-j}
        if(ea>=0){
          const a=v[ea],b=v[eb],eIdx=ea,lowFirst=a<b,p=lowFirst?a:b,q=lowFirst?b:a,s=lowFirst?steps:n-steps;
          id=edgeBase+eid[eIdx]*(n-1)+(s-1);
          const tt=s/n,c1=ctrl(p,q),c2=ctrl(q,p),m=1-tt;
          zz=m*m*m*zs[p]+3*m*m*tt*c1+3*m*tt*tt*c2+tt*tt*tt*zs[q];
        }else{
          id=intBase+t*nv+k;   // unique per triangle
          zz=u*u*u*z[0]+vv*vv*vv*z[1]+w*w*w*z[2]+3*u*u*vv*b210+3*u*vv*vv*b120+3*u*u*w*b201+3*u*w*w*b102+3*vv*vv*w*b021+3*vv*w*w*b012+6*u*vv*w*b111;
        }
      }
      sid[k]=id;sz[k]=zz;
    }
    // contour each sub-triangle
    const tri=(a,b,c)=>{
      const za=sz[a],zb=sz[b],zc=sz[c];const[m0,m1]=lvlRange(Math.min(za,zb,zc),Math.max(za,zb,zc));
      for(let li=m0;li<=m1;li++){const Lv=levels[li];const A=za>=Lv,B=zb>=Lv,C=zc>=Lv;if(A===B&&B===C)continue;
        const S=segs[li];let first=true;
        for(const[p,q,zp,zq,P,Q]of[[a,b,za,zb,A,B],[b,c,zb,zc,B,C],[c,a,zc,za,C,A]]){if(P===Q)continue;
          const r=(Lv-zp)/(zq-zp),ip=sid[p],iq=sid[q];
          S.keys.push(ip<iq?ip+','+iq:iq+','+ip);S.pts.push(sx[p]+r*(sx[q]-sx[p]),sy[p]+r*(sy[q]-sy[p]))}}};
    for(let j=0;j<n;j++)for(let i=0;i+j<n;i++){tri(idx(i,j),idx(i+1,j),idx(i,j+1));if(i+j<n-1)tri(idx(i+1,j),idx(i+1,j+1),idx(i,j+1))}
    if(onProgress&&(t&65535)===0)onProgress(t/nt);
  }
  return segs;
}
// Join segments that share crossing keys into polylines
function stitch(S){
  const ns=S.keys.length/2,map=new Map();
  for(let k=0;k<S.keys.length;k++){const key=S.keys[k],l=map.get(key);if(l===undefined)map.set(key,k);else map.set(key,[l,k].flat())}
  const used=new Uint8Array(ns),lines=[];
  const other=(k)=>{const v=map.get(S.keys[k]);if(typeof v==='number')return -1;for(const o of v)if(o!==k)return o;return -1};
  const pt=k=>({x:S.pts[2*k],y:S.pts[2*k+1]});
  for(let s0=0;s0<ns;s0++){if(used[s0])continue;used[s0]=1;
    // extend forward from end 2*s0+1, backward from end 2*s0
    const fwd=[pt(2*s0),pt(2*s0+1)];let e=2*s0+1,closed=false;
    while(true){const o=other(e);if(o<0)break;const s=o>>1;if(used[s]){if(s===s0)closed=true;break}used[s]=1;const far=o^1;fwd.push(pt(far));e=far}
    if(!closed){const back=[];e=2*s0;
      while(true){const o=other(e);if(o<0)break;const s=o>>1;if(used[s])break;used[s]=1;const far=o^1;back.push(pt(far));e=far}
      lines.push({pts:back.reverse().concat(fwd),closed:false})}
    else{fwd.pop();lines.push({pts:fwd,closed:true})}
  }
  return lines;
}
function chaikin(p,closed,passes){
  for(let k=0;k<passes;k++){if(p.length<3)return p;const r=[];const n=p.length;
    if(!closed)r.push(p[0]);
    const lim=closed?n:n-1;
    for(let i=0;i<lim;i++){const a=p[i],b=p[(i+1)%n];r.push({x:.75*a.x+.25*b.x,y:.75*a.y+.25*b.y},{x:.25*a.x+.75*b.x,y:.25*a.y+.75*b.y})}
    if(!closed)r.push(p[n-1]);p=r}
  return p}
function douglasPeucker(p,tol,closed){
  if(tol<=0||p.length<3)return p;
  if(closed){ // split loop at the farthest point from p[0]
    let far=0,fd=-1;for(let i=1;i<p.length;i++){const d=(p[i].x-p[0].x)**2+(p[i].y-p[0].y)**2;if(d>fd){fd=d;far=i}}
    const a=douglasPeucker(p.slice(0,far+1),tol,false),b=douglasPeucker(p.slice(far).concat([p[0]]),tol,false);
    return a.concat(b.slice(1,-1))}
  const keep=new Uint8Array(p.length);keep[0]=keep[p.length-1]=1;const st=[[0,p.length-1]],t2=tol*tol;
  while(st.length){const[s,e]=st.pop();const ax=p[s].x,ay=p[s].y,dx=p[e].x-ax,dy=p[e].y-ay,L=dx*dx+dy*dy;let md=-1,mi=-1;
    for(let i=s+1;i<e;i++){let d;if(L===0)d=(p[i].x-ax)**2+(p[i].y-ay)**2;else{const c=(p[i].x-ax)*dy-(p[i].y-ay)*dx;d=c*c/L}if(d>md){md=d;mi=i}}
    if(md>t2){keep[mi]=1;st.push([s,mi],[mi,e])}}
  return p.filter((_,i)=>keep[i])}
function polyLength(p,closed){let s=0;for(let i=1;i<p.length;i++)s+=Math.hypot(p[i].x-p[i-1].x,p[i].y-p[i-1].y);if(closed&&p.length>1)s+=Math.hypot(p[0].x-p[p.length-1].x,p[0].y-p[p.length-1].y);return s}
// Outline of the TIN (all boundary edges of the kept triangles, chained into rings)
function tinOutline(del,alive){
  const T=del.triangles,H=del.halfedges,nx=e=>e%3===2?e-2:e+1,next=new Map();
  for(let e=0;e<T.length;e++){const t=(e/3)|0;if(!alive[t])continue;const h=H[e];if(h>=0&&alive[(h/3)|0])continue;
    const a=T[e];if(!next.has(a))next.set(a,[]);next.get(a).push(T[nx(e)])}
  const rings=[];
  for(const[s]of next){while(next.get(s)&&next.get(s).length){const ring=[s];let v=next.get(s).pop();
      while(v!==s){ring.push(v);const l=next.get(v);if(!l||!l.length)break;v=l.pop()}
      rings.push(ring)}}
  return rings}
// Noise filter: Gaussian-weighted average of Z within radius R (isotropic, uses a grid index).
function smoothZ(coords,zs,R){
  if(!(R>0))return zs;
  const n=zs.length,cs=R;let minx=Infinity,miny=Infinity,maxx=-Infinity,maxy=-Infinity;
  for(let i=0;i<n;i++){const x=coords[2*i],y=coords[2*i+1];if(x<minx)minx=x;if(y<miny)miny=y;if(x>maxx)maxx=x;if(y>maxy)maxy=y}
  const gw=Math.floor((maxx-minx)/cs)+1,gh=Math.floor((maxy-miny)/cs)+1;
  if(gw*gh>5e7)throw Error('Noise filter radius is too small for this area.');
  const head=new Int32Array(gw*gh).fill(-1),nxt=new Int32Array(n);
  for(let i=0;i<n;i++){const c=Math.floor((coords[2*i+1]-miny)/cs)*gw+Math.floor((coords[2*i]-minx)/cs);nxt[i]=head[c];head[c]=i}
  const out=new Float64Array(n),s2=2*(R/2)**2,R2=R*R;
  for(let i=0;i<n;i++){const x=coords[2*i],y=coords[2*i+1],cx=Math.floor((x-minx)/cs),cy=Math.floor((y-miny)/cs);let sw=0,sz=0;
    for(let gy=Math.max(0,cy-1);gy<=Math.min(gh-1,cy+1);gy++)for(let gx=Math.max(0,cx-1);gx<=Math.min(gw-1,cx+1);gx++){
      for(let j=head[gy*gw+gx];j>=0;j=nxt[j]){const dx=coords[2*j]-x,dy=coords[2*j+1]-y,d2=dx*dx+dy*dy;if(d2>R2)continue;const w=Math.exp(-d2/s2);sw+=w;sz+=w*zs[j]}}
    out[i]=sz/sw}
  return out}

// ===================== App =====================
const $=id=>document.getElementById('ct_'+id);
const status=(t,cls)=>{const e=$('status');e.textContent=t;e.className='ct-status'+(cls?' '+cls:'')};
const num=id=>Number($(id).value);
const pause=()=>new Promise(r=>setTimeout(r,10));
const fmt=(v,d=3)=>Number(v).toLocaleString(undefined,{maximumFractionDigits:d});
const bar=p=>$('bar').style.width=Math.round(p)+'%';
let S=null;          // loaded data and TIN
let RESULT=null;     // {contours, rings, alive, levels, step}
let fileName='contours';

const PRESETS={none:{subdiv:1,noise:0,passes:0,tol:0},light:{subdiv:2,noise:1.5,passes:1,tol:0.02},medium:{subdiv:4,noise:2.5,passes:2,tol:0.05},strong:{subdiv:6,noise:4,passes:3,tol:0.1}};
function applyPreset(){const p=PRESETS[$('preset').value];if(!p)return;
  $('subdiv').value=p.subdiv;$('passes').value=p.passes;$('tol').value=p.tol;
  if(S)$('noise').value=p.noise?+(p.noise*S.stats.meanNN).toFixed(2):0;else{$('noise').value='';$('noise').placeholder=p.noise?'Auto ('+p.noise+'× spacing)':'0'}}
$('preset').onchange=applyPreset;
for(const id of['subdiv','noise','passes','tol'])$(id).addEventListener('input',()=>{$('preset').value='custom'});
applyPreset();

function parseXYZ(txt){
  const X=[],Y=[],Z=[];
  const lines=txt.split(/\r?\n/);
  for(let k=0;k<lines.length;k++){const s=lines[k].trim();if(!s||s[0]==='#'||s[0]===';')continue;
    const a=s.split(/[,\s;]+/);if(a.length<3)continue;const x=+a[0],y=+a[1],z=+a[2];
    if(Number.isFinite(x)&&Number.isFinite(y)&&Number.isFinite(z)){X.push(x);Y.push(y);Z.push(z)}}
  return{X,Y,Z};
}
$('file').addEventListener('change',async e=>{
  const f=e.target.files[0];if(!f)return;
  S=null;RESULT=null;$('download').disabled=true;$('download').style.display='none';$('generate').disabled=true;draw();
  try{
    status('Reading '+f.name+' …');await pause();
    const{X,Y,Z}=parseXYZ(await f.text());
    if(X.length<3)throw Error('At least 3 valid X Y Z points are required.');
    fileName=f.name.replace(/\.[^.]+$/,'');$('outName').value=fileName+'_contours';
    let ox=Infinity,oy=Infinity;for(let i=0;i<X.length;i++){if(X[i]<ox)ox=X[i];if(Y[i]<oy)oy=Y[i]}
    for(let i=0;i<X.length;i++){X[i]-=ox;Y[i]-=oy}
    const D=dedupePoints(X,Y,Z);const n=D.xs.length;
    const coords=new Float64Array(2*n);for(let i=0;i<n;i++){coords[2*i]=D.xs[i];coords[2*i+1]=D.ys[i]}
    status('Triangulating '+n.toLocaleString()+' points …');await pause();
    const del=Delaunay(coords);const stats=edgeStats(coords,del);
    let zmin=Infinity,zmax=-Infinity;for(const z of D.zs){if(z<zmin)zmin=z;if(z>zmax)zmax=z}
    S={ox,oy,coords,zs:Float64Array.from(D.zs),del,stats,zmin,zmax,n,raw:X.length,dups:D.dups,cache:{}};
    applyPreset();
    $('maxEdge').placeholder='Auto ('+fmt(stats.autoMaxEdge,1)+')';
    const range=zmax-zmin,nice=[0.1,0.2,0.25,0.5,1,2,5,10,20,25,50,100];
    $('summary').textContent='File: '+f.name+'\nPoints: '+X.length.toLocaleString()+(D.dups?' ('+D.dups.toLocaleString()+' duplicate XY averaged)':'')+
      '\nZ range: '+fmt(zmin)+' to '+fmt(zmax)+'\nAverage point spacing: '+fmt(stats.meanNN,2)+' ft';
    status('Loaded '+n.toLocaleString()+' points. Z range '+fmt(zmin)+' to '+fmt(zmax)+(range/num('step')>400?'\nTip: '+fmt(range/num('step'),0)+' contour levels at the current interval — consider a larger interval.':'')+'\nClick "Generate contours".','good');
    $('generate').disabled=false;view=null;draw();
  }catch(err){console.error(err);status('Could not read file: '+err.message,'bad')}
});

$('generate').onclick=async()=>{
  if(!S)return;$('generate').disabled=true;$('download').disabled=true;bar(3);
  try{
    const step=num('step');if(!(step>0))throw Error('Contour interval must be greater than zero.');
    const rawMax=$('maxEdge').value.trim(),maxEdge=rawMax===''?S.stats.autoMaxEdge:Number(rawMax),trim=$('trim').value;
    if(!(maxEdge>=0))throw Error('Enter a valid max triangle side, or leave it blank for automatic.');
    status('Building TIN …');await pause();
    const tk=trim+'|'+maxEdge;
    if(S.cache.tinKey!==tk){S.cache.alive=trim==='none'?new Uint8Array(S.del.triangles.length/3).fill(1):tinTriangles(S.coords,S.del,maxEdge,trim);S.cache.tinKey=tk;S.cache.zKey=null}
    const alive=S.cache.alive;let nAlive=0;for(const a of alive)nAlive+=a;
    if(!nAlive)throw Error('No triangles left. Increase the max triangle side.');
    let noiseR=$('noise').value.trim()===''?0:num('noise');if(!(noiseR>=0))noiseR=0;
    if(noiseR>0&&S.cache.zKey!==noiseR){status('Noise filter (radius '+fmt(noiseR,2)+' ft) …');await pause();S.cache.zs=smoothZ(S.coords,S.zs,noiseR);S.cache.zKey=noiseR}
    const zs=noiseR>0?S.cache.zs:S.zs;
    // elevation range of the vertices used by the TIN
    let zmin=Infinity,zmax=-Infinity;const T=S.del.triangles;
    for(let t=0;t<alive.length;t++)if(alive[t])for(let k=0;k<3;k++){const z=zs[T[3*t+k]];if(z<zmin)zmin=z;if(z>zmax)zmax=z}
    // Custom values (if any) replace the regular interval
    const customRaw=($('customLevels').value||'').split(/[\s,;]+/).filter(Boolean),customVals=customRaw.map(Number);
    if(customVals.some(v=>!Number.isFinite(v)))throw Error('Custom values must be numbers separated by spaces, e.g. 3 7 9 3.5');
    const useCustom=customVals.length>0;let levels=[],flipped=false,outside=0;
    if(useCustom){
      const inRange=v=>v>=zmin-1e-9&&v<=zmax+1e-9;
      let vals=customVals;
      if(!vals.some(inRange)&&vals.map(v=>-v).some(inRange)){vals=vals.map(v=>-v);flipped=true}   // typed with the other sign
      levels=[...new Set(vals.filter(inRange).map(v=>+v.toFixed(8)))].sort((a,b)=>a-b);
      outside=new Set(vals.map(v=>+v.toFixed(8))).size-levels.length;
      if(!levels.length)throw Error('None of the custom values fall inside the Z range ('+fmt(zmin)+' to '+fmt(zmax)+').');
    }else{
      for(let i=Math.ceil(zmin/step-1e-9);i*step<=zmax+1e-9;i++){levels.push(+(i*step).toFixed(8));if(levels.length>5000)throw Error('More than 5000 contour levels. Use a larger contour interval.')}
      if(!levels.length)throw Error('No contour level falls inside the Z range ('+fmt(zmin)+' to '+fmt(zmax)+').');
    }
    const n=+$('subdiv').value,passes=+$('passes').value,tol=Math.max(0,num('tol')||0),minLoop=Math.max(0,num('minLoop')||0);
    status('Contouring '+levels.length+' levels on '+nAlive.toLocaleString()+' triangles …');bar(10);await pause();
    const segs=contourTIN(S.coords,zs,S.del,alive,levels,n,1);
    bar(70);status('Joining and smoothing lines …');await pause();
    const majorEvery=Math.max(0,Math.round(num('major')||0)),contours=[];let removed=0;
    for(let li=0;li<levels.length;li++){
      const z=levels[li],isMajor=majorEvery>0&&Math.abs(Math.round(z/step)%majorEvery)===0;
      for(const l of stitch(segs[li])){
        let p=l.pts;if(passes)p=chaikin(p,l.closed,passes);if(tol>0)p=douglasPeucker(p,tol,l.closed);
        if(p.length<2||(l.closed&&p.length<3))continue;
        if(l.closed&&minLoop>0&&polyLength(p,true)<minLoop){removed++;continue}
        contours.push({z,closed:l.closed,major:isMajor,pts:p})}
      segs[li]=null;
    }
    bar(90);
    const rings=tinOutline(S.del,alive);
    RESULT={contours,rings,alive,levels,step,zs};
    const verts=contours.reduce((a,c)=>a+c.pts.length,0),closed=contours.filter(c=>c.closed).length;
    $('summary').textContent='Points: '+S.raw.toLocaleString()+'\nTIN triangles: '+nAlive.toLocaleString()+' (max side '+fmt(maxEdge,2)+' ft, '+(trim==='all'?'trimmed everywhere':trim==='outer'?'trimmed at outer edge':'not trimmed')+')'+
      '\nContour levels: '+levels.length+' ('+(useCustom?'custom values: '+levels.join(' ')+(flipped?' (sign matched to data)':'')+(outside?'; '+outside+' outside the Z range skipped':''):step+' ft interval, '+fmt(levels[0])+' to '+fmt(levels[levels.length-1]))+')'+
      '\nContour lines: '+contours.length.toLocaleString()+' ('+closed.toLocaleString()+' closed)'+(removed?'\nSmall closed contours removed: '+removed:'')+
      '\nVertices: '+verts.toLocaleString()+
      '\nSmoothing: TIN level '+$('subdiv').selectedOptions[0].text.split(' ')[0]+', noise radius '+fmt(noiseR,2)+' ft, '+passes+' line passes, simplify '+tol+' ft';
    bar(100);status('Done. Download the DXF.','good');
    $('download').disabled=false;$('download').style.display='inline-block';syncName();draw();
  }catch(err){console.error(err);status('Generation failed: '+err.message,'bad');bar(0)}
  finally{$('generate').disabled=false}
};

// Preview removed
let view=null;function draw(){}

// ---------- DXF (AutoCAD R12 ASCII) ----------
const dist=(a,b)=>Math.hypot(a.x-b.x,a.y-b.y);
function plen(p){let s=0;for(let i=1;i<p.length;i++)s+=dist(p[i-1],p[i]);return s}
function interpAt(p,d){let run=0;for(let i=1;i<p.length;i++){const l=dist(p[i-1],p[i]);if(run+l>=d){const t=(d-run)/(l||1),a=p[i-1],b=p[i];return{p:{x:a.x+(b.x-a.x)*t,y:a.y+(b.y-a.y)*t},angle:Math.atan2(b.y-a.y,b.x-a.x)*180/Math.PI}}run+=l}return{p:p[p.length-1],angle:0}}
function slicePath(p,lo,hi){const out=[interpAt(p,lo).p];let run=0;for(let i=1;i<p.length;i++){run+=dist(p[i-1],p[i]);if(run>lo&&run<hi)out.push(p[i])}out.push(interpAt(p,hi).p);return out}
// ---------- HYPACK colour file (.hcf) ----------
// Line 1 = number of colours, lines 2-4 = min, max, step, then "Z COLORREF" rows
// (Windows COLORREF = 0x00BBGGRR). A Z value takes the colour of the last row whose Z is <= it.
let HCF=null,hcfName='';
function parseHCF(txt){
  const L=txt.split(/\r?\n/).map(t=>t.trim()),n=parseInt(L[0],10);
  if(!(n>0))throw Error('This is not a HYPACK colour file (first line must be the number of colours).');
  const out=[];
  for(let i=4;i<L.length&&out.length<n;i++){const a=L[i].split(/\s+/);if(a.length<2)continue;const z=+a[0],c=+a[1];
    if(!Number.isFinite(z)||!Number.isFinite(c))continue;out.push({z,r:c&255,g:(c>>>8)&255,b:(c>>>16)&255})}
  if(!out.length)throw Error('No Z / colour rows found in the colour file.');
  out.sort((a,b)=>a.z-b.z);
  return{list:out,allPositive:out.every(e=>e.z>=0)};
}
function hcfColor(z){
  const{list,allPositive}=HCF;if(allPositive&&z<0)z=-z;   // depth colour files use positive depths
  let lo=0,hi=list.length-1,k=0;
  if(z<list[0].z)return list[0];
  while(lo<=hi){const m=(lo+hi)>>1;if(list[m].z<=z+1e-9){k=m;lo=m+1}else hi=m-1}
  return list[k];
}
// AutoCAD Color Index palette (R12 DXF layers use ACI colours)
const ACI=(()=>{const p=[[0,0,0],[255,0,0],[255,255,0],[0,255,0],[0,255,255],[0,0,255],[255,0,255],[255,255,255],[128,128,128],[192,192,192]];
  for(let i=10;i<250;i++){const h=(Math.floor(i/10)-1)*15,s=i%10,v=[1,.65,.5,.3,.15][s>>1];
    const c=n=>{const k=(n+h/60)%6;return 1-Math.max(0,Math.min(k,4-k,1))};
    let rgb=[c(5),c(3),c(1)];if(s&1)rgb=rgb.map(x=>.5+.5*x);p.push(rgb.map(x=>Math.round(x*v*255)))}
  [51,91,132,173,214,255].forEach(g=>p.push([g,g,g]));return p})();
function nearestACI(r,g,b){let best=7,bd=Infinity;
  for(let i=1;i<256;i++){const q=ACI[i],dr=q[0]-r,dg=q[1]-g,db=q[2]-b,d=2*dr*dr+4*dg*dg+3*db*db;if(d<bd){bd=d;best=i}}return best}
function hcfUI(){const bar=$('hcfBar'),info=$('hcfInfo');
  if(!HCF){bar.style.display='none';info.textContent='Optional. Gives each contour layer the colour for its Z value. Without it: minor white/black, major red.';info.style.color='';return}
  const l=HCF.list,z0=l[0].z,z1=l[l.length-1].z,span=(z1-z0)||1;
  bar.style.background='linear-gradient(to right,'+l.map(e=>'rgb('+e.r+','+e.g+','+e.b+') '+((e.z-z0)/span*100).toFixed(2)+'%').join(',')+')';
  bar.style.display='block';info.style.color='';
  info.textContent=hcfName+': '+l.length+' colours, Z '+fmt(z0,2)+' to '+fmt(z1,2)+'. Layer colours use the nearest CAD colour.';
}
$('hcf').addEventListener('change',async e=>{const f=e.target.files[0];HCF=null;hcfName='';
  if(f){try{HCF=parseHCF(await f.text());hcfName=f.name}catch(err){hcfUI();$('hcfInfo').textContent='Colour file: '+err.message;$('hcfInfo').style.color='var(--bad)';$('hcf').value='';return}}
  hcfUI()});
function customLabelValues(){return($('labelValues').value||'').split(/[\s,;]+/).filter(Boolean).map(Number).filter(Number.isFinite)}
function syncLabelMode(){const m=$('labelMode').value,none=m==='none';
  $('labelValues').disabled=m!=='custom';
  for(const id of['labelSpacing','labelHeight','decimals','labelGap','labelsOnLine'])$(id).disabled=none}
$('labelMode').addEventListener('change',syncLabelMode);
$('labelValues').addEventListener('input',()=>{const v=$('labelValues').value.trim();if(v&&!customLabelValues().length)$('labelValues').style.borderColor='var(--bad)';else $('labelValues').style.borderColor=''});
syncLabelMode();
function makeDXF(){
  const prec=num('coordDecimals')||3,zmul=Number($('zSign').value)||1,ox=S.ox,oy=S.oy;
  const N=v=>{const t=Number(v).toFixed(prec);return/^-0\.?0*$/.test(t)?t.slice(1):t};
  const is3d=$('exportType').value==='3d';
  const spacing=Math.max(1,num('labelSpacing')),gap=Math.max(0,num('labelGap')),dec=+$('decimals').value;
  const onLine=$('labelsOnLine').checked,h=num('labelHeight')>0?num('labelHeight'):2;
  const Lb='TIN_BOUNDARY';
  // Which contours get labels: all / major only / custom list (blank = all) / none. Unlabelled lines are not broken.
  const lm=$('labelMode').value,custom=customLabelValues();
  const wantLabel=(c,z)=>lm==='none'?false:lm==='major'?c.major:(lm==='custom'&&custom.length)?custom.some(v=>Math.abs(v-z)<1e-6||Math.abs(v-c.z)<1e-6):true;
  // One layer per elevation (contour + its labels). All entities are BYLAYER, so colour and
  // line type are set per layer and can be changed in the CAD layer manager after opening.
  const layers=new Map();     // name -> [ACI colour, linetype, sortKey]
  // R12 layer names may only use A-Z 0-9 $ - _ : write the decimal point as '_' (10.5 -> 10_5, 0 -> 0_0)
  const zLayer=z=>{let v=Number(z.toFixed(4)).toString();if(v==='-0')v='0';if(/e/i.test(v))v=z.toFixed(4);if(v==='0')v='0.0';return v.replace(/\./g,'_').replace(/[^A-Za-z0-9$_-]/g,'_').slice(0,31)};
  const ents=[];let minX=Infinity,minY=Infinity,minZ=Infinity,maxX=-Infinity,maxY=-Infinity,maxZ=-Infinity;
  const ext=(x,y,z)=>{if(x<minX)minX=x;if(x>maxX)maxX=x;if(y<minY)minY=y;if(y>maxY)maxY=y;if(z<minZ)minZ=z;if(z>maxZ)maxZ=z};
  const E=(c,v)=>ents.push(c+'\r\n'+v+'\r\n');
  function polyline(pts,z,layer,closed,force2d){if(pts.length<2)return;const d3=is3d&&!force2d;
    E(0,'POLYLINE');E(8,layer);E(66,1);E(10,N(0));E(20,N(0));E(30,N(0));E(70,(d3?8:0)+(closed?1:0));
    for(const p of pts){const X=p.x+ox,Y=p.y+oy,Z=d3?z:0;ext(X,Y,Z);E(0,'VERTEX');E(8,layer);E(10,N(X));E(20,N(Y));E(30,N(Z));if(d3)E(70,32)}
    E(0,'SEQEND');E(8,layer)}
  if($('contours').checked)for(const c of RESULT.contours){
    const z=c.z*zmul,L=zLayer(z);
    if(!layers.has(L)){let col=c.major?1:7;if(HCF){const h=hcfColor(c.z);col=nearestACI(h.r,h.g,h.b)}layers.set(L,[col,'CONTINUOUS',z])}
    const path=c.closed?c.pts.concat([c.pts[0]]):c.pts,total=plen(path),pos=[];
    if(wantLabel(c,z)){const nlab=Math.max(c.closed||total>spacing*0.6?1:0,Math.floor(total/spacing+0.5));for(let i=0;i<nlab;i++)pos.push(total*(i+0.5)/nlab)}
    const cuts=onLine?pos.filter(d=>total>gap*1.5).map(d=>[Math.max(0,d-gap/2),Math.min(total,d+gap/2)]):[];
    if(!cuts.length)polyline(c.pts,z,L,c.closed);
    else{let cur=0;for(const[a,b]of cuts){if(a>cur+1e-6)polyline(slicePath(path,cur,a),z,L,false);cur=Math.max(cur,b)}if(cur<total-1e-6)polyline(slicePath(path,cur,total),z,L,false)}
    for(const d of(onLine||!cuts.length?pos:[])){const a=interpAt(path,d);let ang=onLine?a.angle:0;if(ang>90)ang-=180;if(ang<-90)ang+=180;
      let val=z.toFixed(dec);if(/^-0\.?0*$/.test(val))val=val.slice(1);
      const X=a.p.x+ox,Y=a.p.y+oy,Z=is3d?z:0;ext(X,Y,Z);
      E(0,'TEXT');E(8,L);E(10,N(X));E(20,N(Y));E(30,N(Z));E(40,h);E(1,val);E(50,ang.toFixed(3));E(72,1);E(73,2);E(11,N(X));E(21,N(Y));E(31,N(Z))}
  }
  if($('boundary').checked){layers.set(Lb,[8,'CONTINUOUS',1e9]);for(const r of RESULT.rings)polyline(r.map(v=>({x:S.coords[2*v],y:S.coords[2*v+1]})),0,Lb,true,true)}
  if(!isFinite(minX)){minX=minY=minZ=maxX=maxY=maxZ=0}
  const out=[],P=(c,v)=>out.push(c+'\r\n'+v+'\r\n');
  P(0,'SECTION');P(2,'HEADER');P(9,'$ACADVER');P(1,'AC1009');P(9,'$INSBASE');P(10,'0.0');P(20,'0.0');P(30,'0.0');
  P(9,'$EXTMIN');P(10,N(minX));P(20,N(minY));P(30,N(minZ));P(9,'$EXTMAX');P(10,N(maxX));P(20,N(maxY));P(30,N(maxZ));P(9,'$LTSCALE');P(40,1);P(0,'ENDSEC');
  P(0,'SECTION');P(2,'TABLES');P(0,'TABLE');P(2,'LTYPE');P(70,5);
  const lt=(name,desc,len,els)=>{P(0,'LTYPE');P(2,name);P(70,0);P(3,desc);P(72,65);P(73,els.length);P(40,len);els.forEach(e=>P(49,e))};
  lt('CONTINUOUS','Solid line',0,[]);lt('DASHED','Dashed __ __ __',0.6,[0.4,-0.2]);lt('DOTTED','Dotted . . . .',0.2,[0,-0.2]);lt('CENTER','Center ____ _ ____',2,[1.25,-0.25,0.25,-0.25]);lt('HIDDEN','Hidden __ __ __',0.375,[0.25,-0.125]);
  P(0,'ENDTAB');
  const names=[['0',[7,'CONTINUOUS',-1e9]]].concat([...layers.entries()].filter(e=>e[0]!=='0').sort((a,b)=>a[1][2]-b[1][2]));
  P(0,'TABLE');P(2,'LAYER');P(70,names.length);for(const[nm,[c,l]]of names){P(0,'LAYER');P(2,nm);P(70,0);P(62,c);P(6,l)}P(0,'ENDTAB');P(0,'ENDSEC');
  P(0,'SECTION');P(2,'ENTITIES');
  return{parts:out.concat(ents,['0\r\nENDSEC\r\n0\r\nEOF\r\n']),layers:names.length-1,entities:ents.length};
}
$('download').onclick=()=>{
  if(!RESULT)return;
  try{const{parts,layers}=makeDXF();const txt=parts.join('');if(/NaN|Infinity|undefined/.test(txt))throw Error('The DXF contained an invalid number.');
    const name=(($('outName').value||fileName+'_contours').trim().replace(/\.dxf$/i,'').replace(/[\\/:*?"<>|]+/g,'_'))||'contours';
    const blob=new Blob([txt],{type:'application/dxf'}),url=URL.createObjectURL(blob),a=document.createElement('a');a.href=url;a.download=name+'.dxf';document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),5000);
    status('DXF saved: '+name+'.dxf ('+(blob.size/1048576).toFixed(2)+' MB, '+layers+' layers'+(HCF?', colours from '+hcfName:'')+').','good')}
  catch(err){console.error(err);status('Could not write DXF: '+err.message,'bad')}
};
function syncName(){const n=(($('outName').value||fileName+'_contours').trim().replace(/\.dxf$/i,'').replace(/[\\/:*?"<>|]+/g,'_'))||'contours';$('download').dataset.outputName=n+'.dxf'}
$('outName').addEventListener('input',syncName);
const DEFAULTS=[...document.querySelectorAll('#contourTab input:not([type=file]),#contourTab select')].map(e=>[e,e.type==='checkbox'?e.checked:e.value]);
$('reset').onclick=()=>{for(const[e,v]of DEFAULTS){if(e.type==='checkbox')e.checked=v;else e.value=v}syncLabelMode();
  if(S){$('outName').value=fileName+'_contours'}applyPreset();syncName();status(S?'Options reset. Click "Generate contours" to apply them.':'Choose an XYZ file to begin.')};
const clr=document.getElementById('clearAllBtn');
if(clr)clr.addEventListener('click',()=>{$('file').value='';$('hcf').value='';HCF=null;hcfName='';hcfUI();S=null;RESULT=null;$('generate').disabled=true;$('download').style.display='none';$('summary').textContent='No file loaded.';bar(0);$('reset').onclick();view=null;draw()});
document.querySelectorAll('.tab-button').forEach(b=>b.addEventListener('click',()=>setTimeout(()=>{if(document.getElementById('contourTab').classList.contains('active')){if(!view&&S)view=null;draw()}},0)));
draw();

})();
</script>

<script>
/* Removes any stray text accidentally pasted above or between the page elements */
(function () {
  Array.from(document.body.childNodes).forEach(function (n) {
    if (n.nodeType === 3 && n.nodeValue.trim()) n.parentNode.removeChild(n);
  });
})();
</script>


<script>
/* Save As buttons for every output/download control.
   Keep the selected file handle active long enough to catch both synchronous
   and asynchronous output generation, then write the exact generated Blob. */
(function () {
  if (window.__hydroCadSaveAsInstalled) return;
  window.__hydroCadSaveAsInstalled = true;

  const blobByUrl = new Map();
  const originalCreateObjectURL = URL.createObjectURL.bind(URL);
  URL.createObjectURL = function (object) {
    const url = originalCreateObjectURL(object);
    if (object instanceof Blob) blobByUrl.set(url, object);
    return url;
  };

  let pendingSave = null;
  function showMessage(message) {
    let box = document.getElementById('hydroCadSaveAsMessage');
    if (!box) {
      box = document.createElement('div');
      box.id = 'hydroCadSaveAsMessage';
      box.style.cssText = 'position:fixed;right:18px;bottom:18px;z-index:99999;max-width:420px;padding:12px 16px;background:#17324d;color:#fff;border-radius:8px;box-shadow:0 4px 18px #0003;font:14px/1.45 Arial,sans-serif';
      document.body.appendChild(box);
    }
    box.textContent = message;
    box.style.display = 'block';
    clearTimeout(box._hideTimer);
    box._hideTimer = setTimeout(() => { box.style.display = 'none'; }, 9000);
  }

  document.addEventListener('click', function (event) {
    const link = event.target && event.target.closest ? event.target.closest('a[download]') : null;
    if (!link || !pendingSave) return;
    let blob = blobByUrl.get(link.href);
    if (!blob && link.href && link.href.startsWith('data:')) {
      try {
        const parts = link.href.split(',');
        const meta = parts[0];
        const mime = (meta.match(/^data:([^;]+)/) || [,'application/octet-stream'])[1];
        const bytes = meta.includes(';base64') ? atob(parts[1]) : decodeURIComponent(parts[1]);
        const arr = new Uint8Array(bytes.length);
        for (let i=0; i<bytes.length; i++) arr[i] = bytes.charCodeAt(i);
        blob = new Blob([arr], {type:mime});
      } catch (_) {}
    }
    if (!blob) return;

    event.preventDefault();
    event.stopImmediatePropagation();
    const job = pendingSave;
    pendingSave = null;
    clearTimeout(job.timeout);
    (async function () {
      try {
        const writable = await job.handle.createWritable();
        await writable.write(blob);
        await writable.close();
        showMessage('Saved successfully: ' + (job.name || 'output file'));
      } catch (err) {
        console.error('Save As failed:', err);
        showMessage('Could not save the file. ' + (err && err.message ? err.message : 'Please try again.'));
      }
    })();
  }, true);

  function suggestedName(target) {
    const id = target.id || '';
    try {
      if (target.dataset.outputName) return target.dataset.outputName;
      if (id === 'vdatumDownloadButton' && typeof outputFileName !== 'undefined' && outputFileName) return outputFileName;
      if (id === 'zDownloadBtn' && typeof zOriginalFileName !== 'undefined' && zOriginalFileName) return zOriginalFileName.replace(/\.[^/.]+$/, '') + '_Z_ADJUSTED.xyz';
      if (id === 'extractDownloadBtn' && typeof extractOriginalFileName !== 'undefined' && extractOriginalFileName) {
        const type = document.getElementById('extractType').value;
        const base = extractOriginalFileName.replace(/\.[^/.]+$/, '');
        const suffix = type === 'mtx' ? '_four_corners.xyz' : type === 'contourDxf' ? '_contour_points.xyz' : type === 'soundingDxf' ? '_sounding_points.xyz' : '_nodes.xyz';
        return base + suffix;
      }
      if (id === 'combineDownloadBtn') return document.getElementById('combineRemoveOverlap').checked ? 'combined_XYZ_overlap_removed.xyz' : 'combined_XYZ.xyz';
      if (id === 'cvDownloadBtn') return (typeof cvSingleName !== 'undefined' && cvSingleName) ? cvSingleName : 'Converted_Grid.xyz';
      if (id === 'rawDownloadBtn') return 'Converted_RAW.RAW';
      if (id === 'hsxDownloadBtn') return 'Converted_HSX.HSX';
      if (id === 'ciDlTfw') return ((document.getElementById('ciImg').files[0] || {}).name || 'Converted_Image').replace(/\.[^/.]+$/, '') + '.tfw';
      if (id === 'ciDlTif' || id === 'ciDlGeo') return ((document.getElementById('ciImg').files[0] || {}).name || 'Converted_Image').replace(/\.[^/.]+$/, '') + '.tif';
    } catch (_) {}
    const label = (target.textContent || 'output').trim().toLowerCase();
    const ext = /zip/i.test(label) ? '.zip' : /tfw/i.test(label) ? '.tfw' : /tif|geotiff/i.test(label) ? '.tif' : '.xyz';
    return 'Hydro_CAD_Output' + ext;
  }

  function addSaveAs(target) {
    if (!target || target.dataset.saveAsAdded === '1') return;
    target.dataset.saveAsAdded = '1';
    const button = document.createElement('button');
    button.type = 'button';
    button.className = 'saveAsBtn';
    button.textContent = 'Save As';
    button.style.cssText = 'background:#0a6b43;color:#fff;margin-left:6px';
    button.setAttribute('aria-label', 'Save output to a chosen location');
    target.insertAdjacentElement('afterend', button);

    const syncVisibility = function () {
      const isZipButton = /zip/i.test(target.textContent || '') || /zip/i.test(target.id || '');
      if (target.id === 'vdatumDownloadButton') {
        button.style.display = target.dataset.mode !== 'single' || getComputedStyle(target).display === 'none' ? 'none' : 'inline-block';
        return;
      }
      if (isZipButton) { button.style.display = 'none'; return; }
      button.style.display = getComputedStyle(target).display === 'none' ? 'none' : 'inline-block';
    };
    syncVisibility();
    new MutationObserver(syncVisibility).observe(target, { attributes: true, attributeFilter: ['style', 'class', 'data-mode'] });

    button.addEventListener('click', async function () {
      /* File System Access save pickers are blocked inside cross-origin iframes
         (for example, an embedded preview). In that case, fall back to the
         normal browser download so the Save As button still produces the file. */
      const fallbackToBrowserDownload = function (reason) {
        showMessage((reason ? reason + ' ' : '') + 'This page is embedded, so the location picker is blocked. Starting a normal download instead. To choose a folder, enable “Ask where to save each file” in your browser download settings.');
        try { target.click(); }
        catch (err) { showMessage('Could not start the download. Please use the Download button.'); }
      };

      if (window.self !== window.top) {
        fallbackToBrowserDownload('');
        return;
      }
      if (typeof window.showSaveFilePicker !== 'function') {
        fallbackToBrowserDownload('The Save As location picker is not available in this browser context.');
        return;
      }
      if (pendingSave) {
        showMessage('A Save As operation is already waiting for its output. Please wait a moment.');
        return;
      }
      const name = suggestedName(target);
      let handle;
      try {
        handle = await window.showSaveFilePicker({ suggestedName: name });
      } catch (err) {
        if (err && err.name === 'AbortError') return;
        const detail = err && err.message ? err.message : 'Please try again.';
        if (err && (err.name === 'SecurityError' || /cross origin|sub frames|iframe/i.test(detail))) {
          fallbackToBrowserDownload('The browser blocked the save dialog because this page is embedded.');
        } else {
          showMessage('Could not open the Save As dialog. ' + detail);
        }
        return;
      }

      const job = {handle, name, timeout:null};
      pendingSave = job;
      job.timeout = setTimeout(function () {
        if (pendingSave === job) {
          pendingSave = null;
          showMessage('No output file was captured. Run Process/Convert first, then click Save As beside the output button.');
        }
      }, 30000);
      try {
        target.click();
      } catch (err) {
        if (pendingSave === job) pendingSave = null;
        clearTimeout(job.timeout);
        showMessage('Could not generate the output. ' + (err && err.message ? err.message : 'Please run Process/Convert again.'));
      }
    });
  }

  function installButtons() {
    const targets = Array.from(document.querySelectorAll('button.downloadBtn:not(#vdatumDownloadButton):not(#vdatumSaveAsButton)'));
    targets.forEach(addSaveAs);
  }
  if (document.readyState === 'loading') document.addEventListener('DOMContentLoaded', installButtons);
  else installButtons();
})();
</script>

<script>
/* Other image types (JPG, PNG, BMP, GIF, WebP) -> TIFF inside the browser, for Convert Image and Water / Land Clip */
(function(){
"use strict";
const IDS=['ciImg','wcTif'];
function writeRgbTiff(rgba,w,h){
  const rps=Math.max(1,Math.floor(65536/(w*3))),ns=Math.ceil(h/rps);
  const nEnt=11;let pos=8+2+nEnt*12+4;
  const bpsOff=pos;pos+=6;
  let soff=0,cnt=0;if(ns>1){soff=pos;pos+=ns*4;cnt=pos;pos+=ns*4;}
  const starts=[],sizes=[];let p=pos+(pos&1);
  for(let s=0;s<ns;s++){const rows=Math.min(rps,h-s*rps);starts.push(p);sizes.push(rows*w*3);p+=rows*w*3;}
  const buf=new Uint8Array(p),dv=new DataView(buf.buffer);
  buf[0]=0x49;buf[1]=0x49;dv.setUint16(2,42,true);dv.setUint32(4,8,true);
  dv.setUint16(bpsOff,8,true);dv.setUint16(bpsOff+2,8,true);dv.setUint16(bpsOff+4,8,true);
  if(ns>1)for(let s=0;s<ns;s++){dv.setUint32(soff+s*4,starts[s],true);dv.setUint32(cnt+s*4,sizes[s],true);}
  const ent=[[256,4,1,w],[257,4,1,h],[258,3,3,bpsOff],[259,3,1,1],[262,3,1,2],[273,4,ns,ns>1?soff:starts[0]],[277,3,1,3],[278,4,1,rps],[279,4,ns,ns>1?cnt:sizes[0]],[284,3,1,1],[296,3,1,1]];
  dv.setUint16(8,ent.length,true);let q=10;
  ent.forEach(([id,ty,c,v])=>{dv.setUint16(q,id,true);dv.setUint16(q+2,ty,true);dv.setUint32(q+4,c,true);if(ty===3&&c===1)dv.setUint16(q+8,v,true);else dv.setUint32(q+8,v,true);q+=12;});
  dv.setUint32(q,0,true);
  for(let s=0;s<ns;s++){let o=starts[s];const r0=s*rps,r1=Math.min(h,r0+rps);for(let y=r0;y<r1;y++){let i=y*w*4;for(let x=0;x<w;x++){const a=rgba[i+3];
    if(a===255){buf[o++]=rgba[i];buf[o++]=rgba[i+1];buf[o++]=rgba[i+2];}else{const k=a/255;buf[o++]=Math.round(rgba[i]*k+255*(1-k));buf[o++]=Math.round(rgba[i+1]*k+255*(1-k));buf[o++]=Math.round(rgba[i+2]*k+255*(1-k));}i+=4;}}}
  return buf;
}
function showErr(id,msg){const box=document.getElementById(id==='ciImg'?'ciStatus':'wcStatus');if(box)box.innerHTML='<div class="error">'+msg.replace(/[&<>]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;'}[c]))+'</div>';}
document.addEventListener('change',async function(e){
  const t=e.target;if(!t||IDS.indexOf(t.id)<0||t._ggShim)return;
  const f=t.files&&t.files[0];if(!f)return;
  if(/\.tiff?$/i.test(f.name))return;           // TIFF: handled by the existing code
  e.stopImmediatePropagation();
  const box=document.getElementById(t.id==='ciImg'?'ciStatus':'wcStatus');
  if(box)box.innerHTML='<div class="info">Converting '+f.name.replace(/[&<>]/g,'')+' to TIFF…</div>';
  try{
    const bm=await createImageBitmap(f);
    const c=document.createElement('canvas');c.width=bm.width;c.height=bm.height;
    const g=c.getContext('2d',{willReadFrequently:true});g.drawImage(bm,0,0);
    if(bm.close)bm.close();
    if(c.width*c.height>150e6)throw new Error('Image is too large ('+c.width+' × '+c.height+').');
    const d=g.getImageData(0,0,c.width,c.height).data;
    const tif=writeRgbTiff(d,c.width,c.height);
    const nf=new File([tif],f.name.replace(/\.[^.]+$/,'')+'.tif',{type:'image/tiff'});
    const dt=new DataTransfer();dt.items.add(nf);t.files=dt.files;
    t._ggShim=true;t.dispatchEvent(new Event('change',{bubbles:true}));t._ggShim=false;
    if(box)box.innerHTML='<div class="info">'+f.name.replace(/[&<>]/g,'')+' converted to TIFF ('+c.width+' × '+c.height+' px). '+(t.id==='ciImg'?'Choose its world file (JGW / PGW / WLD), then click Convert.':'Add its world file (JGW / PGW / WLD) if you want real-world area, then click Detect water.')+'</div>';
  }catch(err){
    t.value='';
    showErr(t.id,'Could not read this image ('+(err&&err.message?err.message:err)+'). Use TIFF, JPG, PNG, BMP, GIF or WebP. JPEG 2000 (.jp2) cannot be opened in most browsers.');
  }
},true);
})();
</script>
<script>
(function(){
"use strict";
const $=id=>document.getElementById(id);
const FT=1200/3937,A=6378137,F=1/298.257222101,E2=2*F-F*F,E=Math.sqrt(E2),rad=d=>d*Math.PI/180;
const ZONES={
 nyli:{name:'NAD83 / New York Long Island (ftUS)',epsg:2263,type:'lcc',lat1:41+2/60,lat2:40+40/60,lat0:40+10/60,lon0:-74,fe:300000,fn:0,prj:'NAD_1983_StatePlane_New_York_Long_Island_FIPS_3104_Feet',fe_ft:984250},
 nye:{name:'NAD83 / New York East (ftUS)',epsg:2260,type:'tm',lat0:38+50/60,lon0:-74.5,k0:.9999,fe:150000,fn:0,prj:'NAD_1983_StatePlane_New_York_East_FIPS_3101_Feet',fe_ft:492125},
 nj:{name:'NAD83 / New Jersey (ftUS)',epsg:3424,type:'tm',lat0:38+50/60,lon0:-74.5,k0:.9999,fe:150000,fn:0,prj:'NAD_1983_StatePlane_New_Jersey_FIPS_2900_Feet',fe_ft:492125}};
function mfn(p){return Math.cos(p)/Math.sqrt(1-E2*Math.sin(p)**2);}
function tfn(p){const s=Math.sin(p);return Math.tan(Math.PI/4-p/2)/Math.pow((1-E*s)/(1+E*s),E/2);}
function meridian(p){return A*((1-E2/4-3*E2*E2/64-5*E2**3/256)*p-(3*E2/8+3*E2*E2/32+45*E2**3/1024)*Math.sin(2*p)+(15*E2*E2/256+45*E2**3/1024)*Math.sin(4*p)-(35*E2**3/3072)*Math.sin(6*p));}
function zobj(z){return typeof z==='string'?ZONES[z]:z}
function utmZone(zn,hem){return{type:'tm',lat0:0,lon0:zn*6-183,k0:0.9996,fe:500000,fn:hem==='S'?1e7:0}}
function fwd(z,latd,lond){const Z=zobj(z),lat=rad(latd),lon=rad(lond);
 if(Z.type==='lcc'){const l1=rad(Z.lat1),l2=rad(Z.lat2),l0=rad(Z.lat0);
  const n=(Math.log(mfn(l1))-Math.log(mfn(l2)))/(Math.log(tfn(l1))-Math.log(tfn(l2)));
  const Fc=mfn(l1)/(n*Math.pow(tfn(l1),n)),r0=A*Fc*Math.pow(tfn(l0),n),r=A*Fc*Math.pow(tfn(lat),n),th=n*(lon-rad(Z.lon0));
  return[Z.fe+r*Math.sin(th),Z.fn+r0-r*Math.cos(th)];}
 const ep2=E2/(1-E2),N=A/Math.sqrt(1-E2*Math.sin(lat)**2),T=Math.tan(lat)**2,C=ep2*Math.cos(lat)**2,Aa=(lon-rad(Z.lon0))*Math.cos(lat);
 const M=meridian(lat),M0=meridian(rad(Z.lat0));
 const x=Z.fe+Z.k0*N*(Aa+(1-T+C)*Aa**3/6+(5-18*T+T*T+72*C-58*ep2)*Aa**5/120);
 const y=Z.fn+Z.k0*(M-M0+N*Math.tan(lat)*(Aa*Aa/2+(5-T+9*C+4*C*C)*Aa**4/24+(61-58*T+T*T+600*C-330*ep2)*Aa**6/720));
 return[x,y];}
function inv(z,x,y){const Z=zobj(z);
 if(Z.type==='lcc'){const l1=rad(Z.lat1),l2=rad(Z.lat2),l0=rad(Z.lat0);
  const n=(Math.log(mfn(l1))-Math.log(mfn(l2)))/(Math.log(tfn(l1))-Math.log(tfn(l2)));
  const Fc=mfn(l1)/(n*Math.pow(tfn(l1),n)),r0=A*Fc*Math.pow(tfn(l0),n);
  const dx=x-Z.fe,dy=r0-(y-Z.fn),rho=Math.sign(n)*Math.hypot(dx,dy),t=Math.pow(rho/(A*Fc),1/n),th=Math.atan2(dx*Math.sign(n),dy*Math.sign(n));
  let phi=Math.PI/2-2*Math.atan(t);for(let i=0;i<12;i++){const s=Math.sin(phi);phi=Math.PI/2-2*Math.atan(t*Math.pow((1-E*s)/(1+E*s),E/2))}
  return[phi*180/Math.PI,(th/n+rad(Z.lon0))*180/Math.PI];}
 const ep2=E2/(1-E2),e1=(1-Math.sqrt(1-E2))/(1+Math.sqrt(1-E2)),M0=meridian(rad(Z.lat0)),M=M0+(y-Z.fn)/Z.k0,
  mu=M/(A*(1-E2/4-3*E2*E2/64-5*E2**3/256)),
  p1=mu+(3*e1/2-27*e1**3/32)*Math.sin(2*mu)+(21*e1*e1/16-55*e1**4/32)*Math.sin(4*mu)+(151*e1**3/96)*Math.sin(6*mu)+(1097*e1**4/512)*Math.sin(8*mu),
  C1=ep2*Math.cos(p1)**2,T1=Math.tan(p1)**2,N1=A/Math.sqrt(1-E2*Math.sin(p1)**2),R1=A*(1-E2)/Math.pow(1-E2*Math.sin(p1)**2,1.5),D=(x-Z.fe)/(N1*Z.k0);
 const lat=p1-(N1*Math.tan(p1)/R1)*(D*D/2-(5+3*T1+10*C1-4*C1*C1-9*ep2)*D**4/24+(61+90*T1+298*C1+45*T1*T1-252*ep2-3*C1*C1)*D**6/720);
 const lon=rad(Z.lon0)+(D-(1+2*T1+C1)*D**3/6+(5-2*C1+28*T1-3*C1*C1+8*ep2+24*T1*T1)*D**5/120)/Math.cos(p1);
 return[lat*180/Math.PI,lon*180/Math.PI];}
function prjText(z){const Z=ZONES[z],g='GEOGCS["GCS_North_American_1983",DATUM["D_North_American_1983",SPHEROID["GRS_1980",6378137.0,298.257222101]],PRIMEM["Greenwich",0.0],UNIT["Degree",0.0174532925199433]]';
 if(Z.type==='lcc')return'PROJCS["'+Z.prj+'",'+g+',PROJECTION["Lambert_Conformal_Conic"],PARAMETER["False_Easting",'+Z.fe_ft.toFixed(1)+'],PARAMETER["False_Northing",0.0],PARAMETER["Central_Meridian",'+Z.lon0+'],PARAMETER["Standard_Parallel_1",'+Z.lat1.toFixed(14)+'],PARAMETER["Standard_Parallel_2",'+Z.lat2.toFixed(14)+'],PARAMETER["Latitude_Of_Origin",'+Z.lat0.toFixed(14)+'],UNIT["Foot_US",0.3048006096012192]]';
 return'PROJCS["'+Z.prj+'",'+g+',PROJECTION["Transverse_Mercator"],PARAMETER["False_Easting",'+Z.fe_ft.toFixed(1)+'],PARAMETER["False_Northing",0.0],PARAMETER["Central_Meridian",'+Z.lon0+'],PARAMETER["Scale_Factor",'+Z.k0+'],PARAMETER["Latitude_Of_Origin",'+Z.lat0.toFixed(14)+'],UNIT["Foot_US",0.3048006096012192]]';}

let imgData=null,imgW=0,imgH=0,result=null,pkCanvas=null;
const MAXP=20,PKCOL=['#e53935','#1e88e5','#43a047','#fb8c00','#8e24aa','#00acc1','#6d4c41','#d81b60'];
let NAMES=[],NP=0,ACT=0,PU=[],PV=[];
const esc=t=>String(t).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const letter=i=>i<26?String.fromCharCode(65+i):'P'+(i+1);
function say(t,err){const m=$('gsMsg');m.textContent=t;m.style.color=err?'#b00020':'';m.style.fontWeight=err?'600':'';}
// ---- minimal TIFF decoder (8-bit gray/RGB/RGBA; none, LZW, PackBits, Deflate; strips or tiles; predictor 2) ----
function lzwDecode(src,expected){const out=new Uint8Array(expected);let op=0,bitBuf=0,bits=0,sp=0,codeLen=9;
 let table=[],tl=258;const init=()=>{table=new Array(4096);for(let i=0;i<256;i++)table[i]=[i];codeLen=9;tl=258;};
 init();let prev=null;
 const read=()=>{while(bits<codeLen){if(sp>=src.length)return 257;bitBuf=(bitBuf<<8)|src[sp++];bits+=8;}
  const c=(bitBuf>>(bits-codeLen))&((1<<codeLen)-1);bits-=codeLen;bitBuf&=(1<<bits)-1;return c;};
 for(;;){const c=read();if(c===257)break;
  if(c===256){init();prev=null;continue;}
  let e;
  if(prev===null){e=table[c];if(!e)break;}
  else{if(c<tl&&table[c])e=table[c];else e=prev.concat(prev[0]);
   if(tl<4096){table[tl++]=prev.concat(e[0]);}}
  for(let i=0;i<e.length&&op<expected;i++)out[op++]=e[i];
  prev=e;
  if(tl>=4095&&codeLen<12)codeLen=12;else if(tl>=2047)codeLen=Math.max(codeLen,12);else if(tl>=1023)codeLen=Math.max(codeLen,11);else if(tl>=511)codeLen=Math.max(codeLen,10);
  if(op>=expected)break;}
 return out;}
function packBits(src,expected){const out=new Uint8Array(expected);let i=0,o=0;while(i<src.length&&o<expected){let n=src[i++];if(n>127)n-=256;
 if(n>=0){for(let k=0;k<=n&&o<expected;k++)out[o++]=src[i++];}else if(n!==-128){const v=src[i++];for(let k=0;k<1-n&&o<expected;k++)out[o++]=v;}}return out;}
async function inflate(src,expected){const ds=new DecompressionStream('deflate');const w=ds.writable.getWriter();w.write(src);w.close();
 const buf=new Uint8Array(await new Response(ds.readable).arrayBuffer());if(buf.length>=expected)return buf.subarray(0,expected);const o=new Uint8Array(expected);o.set(buf);return o;}
async function decodeTiff(ab){const dv=new DataView(ab),le=dv.getUint16(0)===0x4949;const g16=o=>dv.getUint16(o,le),g32=o=>dv.getUint32(o,le);
 if(g16(2)!==42)throw new Error('Unsupported TIFF (BigTIFF).');
 const ifd=g32(4),n=g16(ifd),T={};const tsz={1:1,2:1,3:2,4:4,5:8,6:1,7:1,8:2,9:4,10:8,11:4,12:8,16:8};
 for(let i=0;i<n;i++){const o=ifd+2+i*12,id=g16(o),ty=g16(o+2),cnt=g32(o+4),sz=tsz[ty]*cnt,vo=sz>4?g32(o+8):o+8,vals=[];
  if(ty===3||ty===4||ty===1||ty===8||ty===9){for(let k=0;k<cnt;k++)vals.push(ty===3?g16(vo+k*2):ty===1?dv.getUint8(vo+k):g32(vo+k*4));}T[id]=vals;}
 const W=T[256][0],H=T[257][0],spp=(T[277]||[1])[0],comp=(T[259]||[1])[0],pred=(T[317]||[1])[0],pm=(T[262]||[2])[0];
 const bps=(T[258]||[8]);if(bps[0]!==8)throw new Error('Only 8-bit TIFF images are supported here. Save a JPG or 8-bit TIFF.');
 if((T[284]||[1])[0]!==1)throw new Error('Planar TIFF not supported.');
 if(!(spp===1||spp===3||spp===4))throw new Error('Unsupported TIFF colour layout.');
 const tiled=!!T[322],tw=tiled?T[322][0]:W,th=tiled?T[323][0]:((T[278]||[H])[0]),offs=tiled?T[324]:T[273],cnts=tiled?T[325]:T[279];
 const across=Math.ceil(W/tw);const out=new ImageData(W,H),od=out.data;
 for(let ti=0;ti<offs.length;ti++){const rows=tiled?th:Math.min(th,H-Math.floor(ti)*th);const need=tw*rows*spp;
  const raw=new Uint8Array(ab,offs[ti],Math.min(cnts[ti],ab.byteLength-offs[ti]));let d;
  if(comp===1)d=raw;else if(comp===5)d=lzwDecode(raw,need);else if(comp===32773)d=packBits(raw,need);else if(comp===8||comp===32946)d=await inflate(raw,need);
  else throw new Error('TIFF compression '+comp+' is not supported here. Save a JPG, PNG or LZW/uncompressed TIFF.');
  if(pred===2){for(let r=0;r<rows;r++){for(let x=1;x<tw;x++)for(let k=0;k<spp;k++)d[(r*tw+x)*spp+k]=(d[(r*tw+x)*spp+k]+d[(r*tw+x-1)*spp+k])&255;}}
  const x0=tiled?(ti%across)*tw:0,y0=tiled?Math.floor(ti/across)*th:ti*th;
  for(let r=0;r<rows;r++){const y=y0+r;if(y>=H)break;for(let x=0;x<tw;x++){const X=x0+x;if(X>=W)break;const si=(r*tw+x)*spp,di=(y*W+X)*4;
   if(spp===1){let v=d[si];if(pm===0)v=255-v;od[di]=od[di+1]=od[di+2]=v;od[di+3]=255;}else{od[di]=d[si];od[di+1]=d[si+1];od[di+2]=d[si+2];od[di+3]=255;}}}}
 return out;}
async function loadImage(f){
 const ab=await f.arrayBuffer(),h=new Uint8Array(ab,0,4);
 if((h[0]===0x49&&h[1]===0x49&&h[2]===42)||(h[0]===0x4D&&h[1]===0x4D&&h[3]===42)){
  try{return await decodeTiff(ab);}catch(e){throw new Error('TIFF: '+e.message);}}
 const blob=new Blob([ab],{type:/png$/i.test(f.name)?'image/png':'image/jpeg'});
 try{const bm=await createImageBitmap(blob);const c=document.createElement('canvas');c.width=bm.width;c.height=bm.height;const g=c.getContext('2d');g.drawImage(bm,0,0);return g.getImageData(0,0,c.width,c.height);}
 catch(e1){
  return await new Promise((res,rej)=>{const u=URL.createObjectURL(blob),im=new Image();
   im.onload=()=>{try{const c=document.createElement('canvas');c.width=im.naturalWidth;c.height=im.naturalHeight;const g=c.getContext('2d');g.drawImage(im,0,0);const d=g.getImageData(0,0,c.width,c.height);URL.revokeObjectURL(u);res(d);}catch(e){rej(e);}};
   im.onerror=()=>rej(new Error('Could not read "'+f.name+'" ('+(f.size/1048576).toFixed(1)+' MB, starts with bytes '+Array.from(h).map(x=>x.toString(16).padStart(2,'0')).join(' ')+'). Use a JPG, PNG or TIFF saved from Google Earth.'));im.src=u;});}}

function build(n){n=Math.max(3,Math.min(MAXP,n));
 const old=[];for(let i=0;i<NP;i++)old.push(['a','b'].map(k=>$('gs_'+k+i).value));const oldN=NP;NP=n;
 for(let i=0;i<n;i++){if(PU[i]===undefined){PU[i]=null;PV[i]=null}if(!NAMES[i])NAMES[i]=letter(i)}PU.length=PV.length=NAMES.length=n;
 const ll=$('gs_ctype').value==='ll';
 let h='<div class="gs-grid">'+['Point','Pixel X','Pixel Y','',ll?'Latitude':'Easting (X)',ll?'Longitude':'Northing (Y)','Error (ft)'].map(x=>'<div>'+x+'</div>').join('');
 for(let i=0;i<n;i++)h+='<div id="gs_nm'+i+'" style="font-weight:700;color:'+PKCOL[i%PKCOL.length]+';overflow:hidden;text-overflow:ellipsis;white-space:nowrap" title="'+esc(NAMES[i])+'">'+esc(NAMES[i])+'</div><input id="gs_u'+i+'" type="number" step="any"><input id="gs_v'+i+'" type="number" step="any"><button class="s" id="gs_pk'+i+'">Pick</button><input id="gs_a'+i+'" type="text" placeholder="'+(ll?'40.737623':'')+'"><input id="gs_b'+i+'" type="text" placeholder="'+(ll?'-73.954665':'')+'"><div id="gs_e'+i+'"></div>';
 $('gs_rows').innerHTML=h+'</div>';
 for(let i=0;i<Math.min(oldN,n);i++){$('gs_a'+i).value=old[i][0];$('gs_b'+i).value=old[i][1]}
 for(let i=0;i<n;i++){if(PU[i]!==null)$('gs_u'+i).value=PU[i];if(PV[i]!==null)$('gs_v'+i).value=PV[i];
  $('gs_pk'+i).onclick=()=>{ACT=i;now();draw()};
  for(const k of['u','v'])$('gs_'+k+i).oninput=()=>{const v=parseFloat($('gs_'+k+i).value);(k==='u'?PU:PV)[i]=isFinite(v)?v:null;draw()};}
 now();draw();}
function now(){$('gs_now').textContent=ACT<NP?NAMES[ACT]+' – click its tip on the picture':'all marked';
 for(let i=0;i<NP;i++){const e=$('gs_nm'+i);if(e)e.className=i===ACT?'gs-act':''}}
function draw(){const cv=$('gs_pk');if(!imgData){cv.width=cv.height=10;return}
 const z=+$('gs_zoom').value,dispW=Math.round(Math.max(300,$('gs_wrap').clientWidth-2)*z),cw=Math.min(imgW,dispW),sc=cw/imgW;
 cv.width=cw;cv.height=Math.round(imgH*sc);cv.style.width=dispW+'px';cv.style.height='auto';
 const g=cv.getContext('2d');if(!pkCanvas){pkCanvas=document.createElement('canvas');pkCanvas.width=imgW;pkCanvas.height=imgH;pkCanvas.getContext('2d').putImageData(imgData,0,0)}
 g.drawImage(pkCanvas,0,0,cv.width,cv.height);
 for(let i=0;i<NP;i++){if(PU[i]===null||PV[i]===null)continue;const x=PU[i]*sc,y=PV[i]*sc,c=PKCOL[i%PKCOL.length];
  g.lineWidth=3;g.strokeStyle='#fff';g.beginPath();g.moveTo(x-12,y);g.lineTo(x+12,y);g.moveTo(x,y-12);g.lineTo(x,y+12);g.stroke();
  g.lineWidth=1.5;g.strokeStyle=c;g.beginPath();g.moveTo(x-12,y);g.lineTo(x+12,y);g.moveTo(x,y-12);g.lineTo(x,y+12);g.stroke();
  g.font='bold 15px Arial';g.lineWidth=3;g.strokeStyle='#fff';g.strokeText(NAMES[i],x+9,y-9);g.fillStyle=c;g.fillText(NAMES[i],x+9,y-9);}}
$('gs_zoom').onchange=draw;window.addEventListener('resize',()=>{if(imgData)draw()});
$('gs_pk').addEventListener('click',e=>{if(!imgData||ACT>=NP)return;const r=e.target.getBoundingClientRect(),i=ACT;
 PU[i]=+((e.clientX-r.left)/r.width*imgW).toFixed(2);PV[i]=+((e.clientY-r.top)/r.height*imgH).toFixed(2);$('gs_u'+i).value=PU[i];$('gs_v'+i).value=PV[i];
 ACT=i+1;while(ACT<NP&&PU[ACT]!==null)ACT++;now();draw();});
$('gs_ctype').onchange=()=>build(NP);
$('gs_add').onclick=()=>{if(NP>=MAXP)return;build(NP+1);ACT=NP-1;now();};
$('gs_del').onclick=()=>{if(NP>3)build(NP-1)};
$('gs_img').onchange=async e=>{const f=e.target.files[0];imgData=null;pkCanvas=null;if(!f)return;
 try{say('Reading picture…');imgData=await loadImage(f);imgW=imgData.width;imgH=imgData.height;say('Picture '+imgW+' × '+imgH+' loaded.');draw();if(KMLN)await findPins(true)}catch(err){say(err.message,1)}};
function solveLS(rows,rhs,n){ // normal equations, Gaussian elimination
 const M=Array.from({length:n},()=>new Array(n+1).fill(0));
 rows.forEach((r,k)=>{for(let i=0;i<n;i++){for(let j=0;j<n;j++)M[i][j]+=r[i]*r[j];M[i][n]+=r[i]*rhs[k]}});
 for(let c=0;c<n;c++){let p=c;for(let r=c+1;r<n;r++)if(Math.abs(M[r][c])>Math.abs(M[p][c]))p=r;if(Math.abs(M[p][c])<1e-9)throw new Error('The control points are too close together or in a straight line. Spread them out.');
  [M[c],M[p]]=[M[p],M[c]];for(let r=0;r<n;r++){if(r===c)continue;const f=M[r][c]/M[c][c];for(let j=c;j<=n;j++)M[r][j]-=f*M[c][j]}}
 return M.map((r,i)=>r[n]/r[i]);}
function gaussSq(M,b){const n=b.length,A2=M.map((r,i)=>r.concat([b[i]]));
 for(let c=0;c<n;c++){let p=c;for(let r=c+1;r<n;r++)if(Math.abs(A2[r][c])>Math.abs(A2[p][c]))p=r;if(Math.abs(A2[p][c])<1e-12)throw new Error('The control points are too close together or in a straight line. Spread them out.');
  [A2[c],A2[p]]=[A2[p],A2[c]];for(let r=0;r<n;r++){if(r===c)continue;const f=A2[r][c]/A2[c][c];if(f)for(let j=c;j<=n;j++)A2[r][j]-=f*A2[c][j]}}
 return A2.map((r,i)=>r[n]/r[i]);}
// ---- models: pixel (u,v) <-> ground (x,y) in US ft. Each returns {f:(u,v)=>[x,y], g:(x,y)=>[u,v], lin:[a,b,c,d,e,f]|null}
const SN=1000,mean=a=>a.reduce((p,q)=>p+q,0)/a.length;
function normPts(U,V,X,Y){const cu=mean(U),cv=mean(V),cx=mean(X),cy=mean(Y);return{cu,cv,cx,cy,u:U.map(t=>(t-cu)/SN),v:V.map(t=>(t-cv)/SN),x:X.map(t=>(t-cx)/SN),y:Y.map(t=>(t-cy)/SN)}}
function linModel(a,b,c,d,e,f){const det=a*e-b*d;if(!isFinite(det)||Math.abs(det)<1e-12)throw new Error('The points do not define a valid scale. Check that pixel positions and coordinates belong to the same placemarks.');
 return{lin:[a,b,c,d,e,f],f:(u,v)=>[a*u+b*v+c,d*u+e*v+f],g:(x,y)=>[(e*(x-c)-b*(y-f))/det,(-d*(x-c)+a*(y-f))/det]}}
function fitLinear(kind,U,V,X,Y){const N=normPts(U,V,X,Y);let a,b,d,e;
 if(kind==='sim'){const rows=[],rhs=[];for(let i=0;i<U.length;i++){rows.push([N.u[i],N.v[i]]);rhs.push(N.x[i]);rows.push([-N.v[i],N.u[i]]);rhs.push(N.y[i])}
  const[p,q]=solveLS(rows,rhs,2);a=p;b=q;d=q;e=-p;}
 else if(kind==='aff'){const R=N.u.map((t,i)=>[t,N.v[i]]);[a,b]=solveLS(R,N.x,2);[d,e]=solveLS(R,N.y,2);}
 else{[a]=solveLS(N.u.map(t=>[t]),N.x,1);[e]=solveLS(N.v.map(t=>[t]),N.y,1);b=0;d=0;}
 return linModel(a,b,N.cx-a*N.cu-b*N.cv,d,e,N.cy-d*N.cu-e*N.cv);}
function inv3(m){const[a,b,c,d,e,f,g,h,i]=m.flat();const A=e*i-f*h,B=-(d*i-f*g),C=d*h-e*g,det=a*A+b*B+c*C;if(Math.abs(det)<1e-14)throw new Error('The points do not define a valid perspective.');
 return[[A/det,-(b*i-c*h)/det,(b*f-c*e)/det],[B/det,(a*i-c*g)/det,-(a*f-c*d)/det],[C/det,-(a*h-b*g)/det,(a*e-b*d)/det]]}
function fitProj(U,V,X,Y){const N=normPts(U,V,X,Y),rows=[],rhs=[];
 for(let i=0;i<U.length;i++){const u=N.u[i],v=N.v[i],x=N.x[i],y=N.y[i];rows.push([u,v,1,0,0,0,-u*x,-v*x]);rhs.push(x);rows.push([0,0,0,u,v,1,-u*y,-v*y]);rhs.push(y)}
 const h=solveLS(rows,rhs,8),H=[[h[0],h[1],h[2]],[h[3],h[4],h[5]],[h[6],h[7],1]],Hi=inv3(H);
 return{lin:null,f:(U1,V1)=>{const u=(U1-N.cu)/SN,v=(V1-N.cv)/SN,w=H[2][0]*u+H[2][1]*v+1;return[N.cx+SN*(H[0][0]*u+H[0][1]*v+H[0][2])/w,N.cy+SN*(H[1][0]*u+H[1][1]*v+H[1][2])/w]},
  g:(X1,Y1)=>{const x=(X1-N.cx)/SN,y=(Y1-N.cy)/SN,w=Hi[2][0]*x+Hi[2][1]*y+Hi[2][2];return[N.cu+SN*(Hi[0][0]*x+Hi[0][1]*y+Hi[0][2])/w,N.cv+SN*(Hi[1][0]*x+Hi[1][1]*y+Hi[1][2])/w]}}}
function tpsFit(px,py,vals){ // thin-plate spline through nodes (px,py) with 2 value sets; coordinates already normalised
 const n=px.length,phi=r2=>r2>0?0.5*r2*Math.log(r2):0,K=[],P=[];
 for(let i=0;i<n+3;i++)K.push(new Array(n+3).fill(0));
 for(let i=0;i<n;i++){for(let j=0;j<n;j++)K[i][j]=phi((px[i]-px[j])**2+(py[i]-py[j])**2);K[i][i]+=1e-9;K[i][n]=1;K[i][n+1]=px[i];K[i][n+2]=py[i];K[n][i]=1;K[n+1][i]=px[i];K[n+2][i]=py[i]}
 const sol=vals.map(v=>gaussSq(K,v.concat([0,0,0])));
 return(x,y)=>sol.map(w=>{let s=w[n]+w[n+1]*x+w[n+2]*y;for(let i=0;i<n;i++)s+=w[i]*phi((x-px[i])**2+(y-py[i])**2);return s})}
function fitRub(U,V,X,Y){const base=fitProj(U,V,X,Y),N=normPts(U,V,X,Y),n=U.length;
 const rx=[],ry=[],ru=[],rv=[];
 for(let i=0;i<n;i++){const f=base.f(U[i],V[i]),g=base.g(X[i],Y[i]);rx.push((X[i]-f[0])/SN);ry.push((Y[i]-f[1])/SN);ru.push((U[i]-g[0])/SN);rv.push((V[i]-g[1])/SN)}
 const t1=tpsFit(N.u,N.v,[rx,ry]),t2=tpsFit(N.x,N.y,[ru,rv]);
 return{lin:null,f:(u,v)=>{const b=base.f(u,v),d=t1((u-N.cu)/SN,(v-N.cv)/SN);return[b[0]+SN*d[0],b[1]+SN*d[1]]},
  g:(x,y)=>{const b=base.g(x,y),d=t2((x-N.cx)/SN,(y-N.cy)/SN);return[b[0]+SN*d[0],b[1]+SN*d[1]]}}}
const MINPTS={sim:3,aff:3,ss:3,proj:4,rub:5},KNAME={sim:'rotate + scale + shift',aff:'full affine',ss:'scale + shift',proj:'perspective (homography)',rub:'perspective + rubber-sheet'};
function fitKind(kind,U,V,X,Y){return kind==='proj'?fitProj(U,V,X,Y):kind==='rub'?fitRub(U,V,X,Y):fitLinear(kind,U,V,X,Y)}
function looErr(kind,U,V,X,Y){ // leave-one-out ground error (ft) for each point
 const n=U.length,out=[];for(let i=0;i<n;i++){const ix=[...Array(n).keys()].filter(k=>k!==i);
  try{const m=fitKind(kind,ix.map(k=>U[k]),ix.map(k=>V[k]),ix.map(k=>X[k]),ix.map(k=>Y[k])),p=m.f(U[i],V[i]);out.push(Math.hypot(p[0]-X[i],p[1]-Y[i]))}catch(e){out.push(Infinity)}}
 return out;}
const rmsOf=a=>Math.sqrt(a.reduce((p,q)=>p+q*q,0)/a.length);

function parseAngle(s){s=String(s||'').trim().toUpperCase();if(!s)return NaN;const neg=/[SW]/.test(s)||/^\s*-/.test(s);
 const nums=s.replace(/,/g,' ').match(/\d+(\.\d+)?/g);if(!nums)return NaN;let v=0,div=1;for(const n of nums.slice(0,3)){v+=parseFloat(n)/div;div*=60}return neg?-v:v;}
function latLon(i){const t=$('gs_ctype').value,a=$('gs_a'+i).value,b=$('gs_b'+i).value,nm=NAMES[i];
 if(t==='ll'){const lat=parseAngle(a),lon=parseAngle(b);if(!isFinite(lat)||!isFinite(lon))throw new Error('Enter latitude and longitude for point '+nm+'.');
  if(Math.abs(lat)>90||Math.abs(lon)>180)throw new Error('Point '+nm+': latitude / longitude look swapped or wrong.');return[lat,lon];}
 const x=parseFloat(String(a).replace(/,/g,'')),y=parseFloat(String(b).replace(/,/g,''));if(!isFinite(x)||!isFinite(y))throw new Error('Enter easting and northing for point '+nm+'.');return inv(t,x*FT,y*FT);}
// ---- pins ----
function detectPins(data,W,H,maxN){
  const N=W*H,white=new Uint8Array(N);
  for(let i=0;i<N;i++){const o=i*4;if(data[o]>=232&&data[o+1]>=232&&data[o+2]>=232)white[i]=1}
  const lab=new Int32Array(N),stack=new Int32Array(N),cands=[];let id=0;
  for(let s=0;s<N;s++){if(!white[s]||lab[s])continue;id++;let sp=0,n=0,x0=1e9,x1=-1,y0=1e9,y1=-1;stack[sp++]=s;lab[s]=id;const px=[];
    while(sp){const p=stack[--sp],x=p%W,y=(p-x)/W;n++;px.push(p);if(x<x0)x0=x;if(x>x1)x1=x;if(y<y0)y0=y;if(y>y1)y1=y;
      if(n>3000){break}
      for(let dy=-1;dy<=1;dy++)for(let dx=-1;dx<=1;dx++){if(!dx&&!dy)continue;const nx=x+dx,ny=y+dy;if(nx<0||ny<0||nx>=W||ny>=H)continue;const q=ny*W+nx;if(white[q]&&!lab[q]){lab[q]=id;stack[sp++]=q}}}
    if(n>3000)continue;const w=x1-x0+1,h=y1-y0+1;
    if(n<25||w<4||h<7||w>34||h>48)continue;const asp=h/w,fill=n/(w*h);
    if(asp<1.15||asp>3.2||fill<0.38||fill>0.9)continue;
    // teardrop: top part wider than bottom part
    const rowW=new Int32Array(h);for(const p of px){rowW[((p/W)|0)-y0]++}
    const top=(rowW[0]+rowW[1]+rowW[2]+rowW[Math.floor(h*0.3)])/4,bot=(rowW[h-1]+rowW[h-2]+rowW[h-3])/3;
    const taper=top/Math.max(1,bot);if(taper<1.6)continue;
    // dark outline: pixels touching the blob should mostly be dark (the pin has a black border)
    let touch=0,dark=0;const seen=new Set();
    for(const p of px){const x=p%W,y=(p-x)/W;for(let dy=-2;dy<=2;dy++)for(let dx=-2;dx<=2;dx++){const nx=x+dx,ny=y+dy;if(nx<0||ny<0||nx>=W||ny>=H)continue;const q=ny*W+nx;if(white[q]||seen.has(q))continue;seen.add(q);touch++;const o=q*4;if((data[o]+data[o+1]+data[o+2])/3<120)dark++}}
    const dk=touch?dark/touch:0;if(dk<0.55)continue;
    // isolation: ring around bbox should not be mostly white
    let ring=0,rc=0;for(let x=x0-3;x<=x1+3;x++)for(const y of[y0-3,y1+3]){if(x<0||y<0||x>=W||y>=H)continue;rc++;if(white[y*W+x])ring++}
    for(let y=y0-3;y<=y1+3;y++)for(const x of[x0-3,x1+3]){if(x<0||y<0||x>=W||y>=H)continue;rc++;if(white[y*W+x])ring++}
    if(rc&&ring/rc>0.25)continue;
    // tip = centre of the lowest rows
    let sx=0,sc=0;for(const p of px){const y=(p/W)|0;if(y>=y1-1){sx+=p%W;sc++}}
    const cx=Math.round(sx/sc);let ty=y1+1;
    for(let k=1;k<=8;k++){const y=y1+k;if(y>=H)break;let dk2=false;for(let dx=-1;dx<=1;dx++){const x=cx+dx;if(x<0||x>=W)continue;const o=(y*W+x)*4;if((data[o]+data[o+1]+data[o+2])/3<95)dk2=true}if(dk2)ty=y+1;else break}
    const score=dk*4+Math.min(taper,4)+(fill>0.5&&fill<0.75?1:0)+(asp>1.4&&asp<2.4?1:0)-ring/Math.max(1,rc);
    cands.push({u:sx/sc+0.5,v:ty,w,h,n,dk,score});}
  cands.sort((a,b)=>b.score-a.score);return cands.slice(0,maxN||6);
}


async function unzipKml(ab){const dv=new DataView(ab),u8=new Uint8Array(ab);let e=u8.length-22;while(e>=0&&dv.getUint32(e,true)!==0x06054b50)e--;
 if(e<0)throw new Error('This KMZ file could not be opened.');const cnt=dv.getUint16(e+10,true);let p=dv.getUint32(e+16,true),best=null;
 for(let i=0;i<cnt;i++){if(dv.getUint32(p,true)!==0x02014b50)break;const method=dv.getUint16(p+10,true),csize=dv.getUint32(p+20,true),nl=dv.getUint16(p+28,true),el=dv.getUint16(p+30,true),cl=dv.getUint16(p+32,true),lho=dv.getUint32(p+42,true);
  const name=new TextDecoder().decode(u8.subarray(p+46,p+46+nl));if(/\.kml$/i.test(name)&&(!best||/doc\.kml$/i.test(name)))best={method,csize,lho};p+=46+nl+el+cl;}
 if(!best)throw new Error('No .kml found inside the KMZ.');const nl=dv.getUint16(best.lho+26,true),el=dv.getUint16(best.lho+28,true),ds=best.lho+30+nl+el,data=u8.subarray(ds,ds+best.csize);
 if(best.method===0)return new TextDecoder().decode(data);
 const st=new DecompressionStream('deflate-raw'),w=st.writable.getWriter();w.write(data);w.close();return new TextDecoder().decode(await new Response(st.readable).arrayBuffer());}
async function readPlacemarks(f){const text=/\.kmz$/i.test(f.name)?await unzipKml(await f.arrayBuffer()):await f.text();
 const doc=new DOMParser().parseFromString(text,'text/xml'),out=[];
 for(const pm of Array.from(doc.getElementsByTagName('Placemark'))){const nm=pm.getElementsByTagName('name')[0],co=pm.getElementsByTagName('coordinates')[0];if(!co)continue;
  const t=co.textContent.trim().split(/\s+/)[0].split(',').map(Number);if(t.length<2||!isFinite(t[0])||!isFinite(t[1]))continue;out.push({name:nm?nm.textContent.trim():'',lon:t[0],lat:t[1]});}
 return out;}

function permsOf(n,k){const out=[];const rec=(cur)=>{if(cur.length===k){out.push(cur.slice());return}for(let i=0;i<n;i++){if(cur.includes(i))continue;cur.push(i);rec(cur);cur.pop()}};rec([]);return out;}
function simRms(P,XY){const rows=[],rhs=[];for(let i=0;i<3;i++){rows.push([P[i][0],P[i][1],1,0]);rhs.push(XY[i][0]);rows.push([-P[i][1],P[i][0],0,1]);rhs.push(XY[i][1])}
 try{const[p,q,cx,cy]=solveLS(rows,rhs,4);let ss=0;for(let i=0;i<3;i++){const x=p*P[i][0]+q*P[i][1]+cx,y=q*P[i][0]-p*P[i][1]+cy;ss+=(x-XY[i][0])**2+(y-XY[i][1])**2}const sc=Math.hypot(p,q);if(!(sc>0.05&&sc<200)||p<=0)return 1e12;return Math.sqrt(ss/3)}catch(e){return 1e12}}

let KMLN=0;
$('gs_kml').onchange=async e=>{const f=e.target.files[0];KMLN=0;if(!f)return;
 try{let pts=await readPlacemarks(f);if(pts.length<3)throw new Error('Only '+pts.length+' placemark(s) found; at least 3 are needed. Put all placemarks in one folder, right-click the folder → Save Place As.');
  pts=pts.slice(0,MAXP).map((p,i)=>({...p,name:p.name||letter(i)}));pts.sort((p,q)=>p.name.localeCompare(q.name,undefined,{numeric:true}));
  NAMES=pts.map(p=>p.name);NP=0;PU=[];PV=[];$('gs_ctype').value='ll';build(pts.length);
  pts.forEach((p,i)=>{$('gs_a'+i).value=p.lat.toFixed(8);$('gs_b'+i).value=p.lon.toFixed(8)});KMLN=pts.length;
  say('Read '+pts.length+' placemarks: '+NAMES.join(', ')+'.');if(imgData)await findPins(true);
 }catch(err){say('Placemarks: '+(err.message||err),1)}};
function setPix(i,u,v){PU[i]=u===null?null:+u.toFixed(1);PV[i]=v===null?null:+v.toFixed(1);$('gs_u'+i).value=PU[i]===null?'':PU[i];$('gs_v'+i).value=PV[i]===null?'':PV[i]}
function greedy(pred,cands,tol){const pairs=[];pred.forEach((p,i)=>{if(!p)return;cands.forEach((c,k)=>pairs.push([Math.hypot(c.u-p[0],c.v-p[1]),i,k]))});pairs.sort((a,b)=>a[0]-b[0]);
 const rowOf=new Array(pred.length).fill(-1),used=new Set();for(const[d,i,k]of pairs){if(d>tol)break;if(rowOf[i]>=0||used.has(k))continue;rowOf[i]=k;used.add(k)}return rowOf}
async function findPins(quiet){
 if(!imgData){say('Choose the picture first.',1);return}
 say('Looking for the white pins…');await new Promise(r=>setTimeout(r,20));
 const cands=detectPins(imgData.data,imgW,imgH,60),z=$('gs_zone').value,rows=[],XY=[];
 for(let i=0;i<NP;i++){try{const ll=latLon(i),q=fwd(z,ll[0],ll[1]);rows.push(i);XY.push([q[0]/FT,q[1]/FT])}catch(e){}}
 if(cands.length<3){say('Found only '+cands.length+' pin(s) in the picture – click the points on the picture instead (zoom in for accuracy).',quiet?0:1);return}
 let how='';
 if(rows.length>=3){
  // 1) best-spread triple of coordinates, find the 3 pins that fit it as a similarity
  let bt=null,ba=-1;const m=rows.length;for(let a=0;a<m;a++)for(let b=a+1;b<m;b++)for(let c=b+1;c<m;c++){const ar=Math.abs((XY[b][0]-XY[a][0])*(XY[c][1]-XY[a][1])-(XY[c][0]-XY[a][0])*(XY[b][1]-XY[a][1]));if(ar>ba){ba=ar;bt=[a,b,c]}}
  const M=Math.min(cands.length,25);let best=null,bc=1e18;for(const p of permsOf(M,3)){const c=simRms(p.map(k=>[cands[k].u,cands[k].v]),bt.map(j=>XY[j]));if(c<bc){bc=c;best=p}}
  if(!best||bc>1e11){say('The pins in the picture do not match these coordinates. Check the coordinate type and output system.',1);return}
  let U=best.map(k=>cands[k].u),V=best.map(k=>cands[k].v),X=bt.map(j=>XY[j][0]),Y=bt.map(j=>XY[j][1]);
  let model=fitKind('sim',U,V,X,Y),rowOf=[],tol=Math.max(30,0.07*Math.hypot(imgW,imgH));
  for(let it=0;it<4;it++){ // predict all, pair, refit with everything paired, tighten
   const pred=new Array(NP).fill(null);rows.forEach((r,j)=>{const g=model.g(XY[j][0],XY[j][1]);pred[r]=g});
   rowOf=greedy(pred,cands,tol);
   const ix=rows.map((r,j)=>rowOf[r]>=0?j:-1).filter(j=>j>=0);if(ix.length<3)break;
   const k=ix.length>=6?'rub':ix.length>=5?'proj':ix.length>=4?'aff':'sim';
   try{model=fitKind(k==='rub'?'proj':k,ix.map(j=>cands[rowOf[rows[j]]].u),ix.map(j=>cands[rowOf[rows[j]]].v),ix.map(j=>XY[j][0]),ix.map(j=>XY[j][1]))}catch(e){break}
   tol=Math.max(12,tol*0.6);}
  let found=0;for(let i=0;i<NP;i++){if(rowOf[i]>=0){const c=cands[rowOf[i]];setPix(i,c.u,c.v);found++}else setPix(i,null,null)}
  how=found+' of '+rows.length+' points paired with a pin in the picture.'+(found<rows.length?' Click the missing ones on the picture (Pick).':'');
 }else{const k=Math.min(cands.length,NP);const top=cands.slice(0,k).sort((a,b)=>a.u-b.u);for(let i=0;i<NP;i++){if(i<k)setPix(i,top[i].u,top[i].v);else setPix(i,null,null)}
  how='Pins sorted left to right – enter the coordinates (or load the placemarks file) and click Find pins again to pair them properly.'}
 ACT=NP;for(let i=0;i<NP;i++)if(PU[i]===null){ACT=i;break}now();draw();say(how+' Check the markers on the picture, then click Georeference.');}
$('gs_find').onclick=()=>findPins(false).catch(e=>say('Error: '+(e.message||e),1));
// ---- georeference ----
$('gs_go').onclick=async()=>{try{if(!imgData){say('Choose the picture first.',1);return}run()}catch(e){say('Error: '+(e.message||e),1);console.error(e)}};
function run(){
 const z=$('gs_zone').value,W=imgW,H=imgH,U=[],V=[],X=[],Y=[],idx=[];
 for(let i=0;i<NP;i++){const vals=['u','v','a','b'].map(k=>$('gs_'+k+i).value.trim());$('gs_e'+i).textContent='';if(vals.every(t=>!t))continue;
  const u=parseFloat(vals[0]),v=parseFloat(vals[1]);if(!isFinite(u)||!isFinite(v))throw new Error('Mark point '+NAMES[i]+' on the picture (or clear its row).');
  const ll=latLon(i),q=fwd(z,ll[0],ll[1]);U.push(u);V.push(v);X.push(q[0]/FT);Y.push(q[1]/FT);idx.push(i)}
 const n=U.length;if(n<3)throw new Error('At least 3 points are needed (you have '+n+').');
 const auto=$('gs_fit').value==='auto',cand=['sim'];if(auto){if(n>=4)cand.push('aff');if(n>=5)cand.push('proj');if(n>=6)cand.push('rub')}
 let kind=null,bs=Infinity;const rep=[];
 for(const k of cand){const r=rmsOf(looErr(k,U,V,X,Y).map(e=>isFinite(e)?e:1e9));rep.push(KNAME[k]+' '+(r<1e8?r.toFixed(1):'n/a'));if(kind===null||r<bs*0.9){kind=k;bs=r}}
 const model=fitKind(kind,U,V,X,Y),res=U.map((u,i)=>{const p=model.f(u,V[i]);return Math.hypot(p[0]-X[i],p[1]-Y[i])});
 const loo=n>=MINPTS[kind]+1?looErr(kind,U,V,X,Y):null,show=loo||res,srt=show.slice().sort((p,q)=>p-q),med=srt[Math.floor(srt.length/2)];
 idx.forEach((ri,k)=>{const el=$('gs_e'+ri),val=show[k],bad=isFinite(val)&&val>Math.max(3*med,4);el.textContent=isFinite(val)?val.toFixed(1):'—';el.style.color=bad?'#c62828':'inherit';el.style.fontWeight=bad?'700':'400'});
 const worst=show.indexOf(Math.max(...show)),ctr=model.f(W/2,H/2),pa=model.f(W/2+1,H/2),pb=model.f(W/2,H/2+1);
 const ja=pa[0]-ctr[0],jd=pa[1]-ctr[1],jb=pb[0]-ctr[0],je=pb[1]-ctr[1],lin=model.lin;
 const northUp=lin&&lin[0]>0&&lin[4]<0&&Math.abs(lin[1])<=3e-4*Math.abs(lin[0])&&Math.abs(lin[3])<=3e-4*Math.abs(lin[0]);
 let outW,outH,ulx,uly,ps,pix;
 if(northUp){outW=W;outH=H;ulx=lin[2];uly=lin[5];ps=lin[0];pix=imgData.data}
 else{ps=Math.max(0.05,+Math.sqrt(Math.abs(ja*je-jb*jd)).toFixed(3));const bp=[];
  for(let t=0;t<=40;t++){const q=t/40;bp.push(model.f(W*q,0),model.f(W*q,H),model.f(0,H*q),model.f(W,H*q))}
  if(bp.some(p=>!isFinite(p[0])||!isFinite(p[1])))throw new Error('The fit gives an impossible picture shape. Check that each point is paired with the right placemark.');
  const x0=Math.floor(Math.min(...bp.map(p=>p[0]))/ps)*ps,x1=Math.ceil(Math.max(...bp.map(p=>p[0]))/ps)*ps,y0=Math.floor(Math.min(...bp.map(p=>p[1]))/ps)*ps,y1=Math.ceil(Math.max(...bp.map(p=>p[1]))/ps)*ps;
  outW=Math.round((x1-x0)/ps);outH=Math.round((y1-y0)/ps);if(outW*outH>60e6)throw new Error('Output too large – check that each point is paired with the right placemark.');
  ulx=x0;uly=y1;pix=new Uint8ClampedArray(outW*outH*4);const src=imgData.data;
  for(let r=0;r<outH;r++){const gy=uly-ps*(r+.5);for(let q=0;q<outW;q++){const gx=ulx+ps*(q+.5),o=(r*outW+q)*4,uv=model.g(gx,gy),u=uv[0],v=uv[1];let ok=false;
   if(u>=0&&u<=W-1&&v>=0&&v<=H-1){const xa=Math.floor(u),ya=Math.floor(v),xb=Math.min(W-1,xa+1),yb=Math.min(H-1,ya+1),fx=u-xa,fy=v-ya;
    for(let k=0;k<3;k++){const p1=src[(ya*W+xa)*4+k]*(1-fx)+src[(ya*W+xb)*4+k]*fx,p2=src[(yb*W+xa)*4+k]*(1-fx)+src[(yb*W+xb)*4+k]*fx;pix[o+k]=p1*(1-fy)+p2*fy}ok=true}
   if(!ok){pix[o]=pix[o+1]=pix[o+2]=255}pix[o+3]=255}}}
 result={z,outW,outH,ulx,uly,psf:ps,psx:ps,psy:ps,pix};
 const cv=$('gs_cv'),g=cv.getContext('2d');g.fillStyle='#dde7ef';g.fillRect(0,0,cv.width,cv.height);const t=document.createElement('canvas');t.width=outW;t.height=outH;t.getContext('2d').putImageData(new ImageData(new Uint8ClampedArray(pix.buffer?pix:pix),outW,outH),0,0);
 const s=Math.min(cv.width/outW,cv.height/outH);g.drawImage(t,0,0,outW*s,outH*s);
 const err=rmsOf(show.map(e=>isFinite(e)?e:0));
 $('gs_info').innerHTML='<b>'+n+' points</b>, method: <b>'+KNAME[kind]+'</b> ('+(auto?'chosen automatically':'rotate, scale and shift only')+(cand.length>1?' – typical error per method in ft: '+rep.join(', '):'')+').<br>'+(loo?'Typical error at a point (that point left out): ':'Fit error: ')+'<b>'+err.toFixed(1)+' ft = '+(err*FT).toFixed(1)+' m</b>. Worst point: <b>'+esc(NAMES[idx[worst]])+'</b> ('+show[worst].toFixed(1)+' ft)'+(show[worst]>Math.max(3*med,4)?' – check its position on the picture and its coordinates (red in the table).':'.')+(n<5?'<br><span style="color:#a15a00">With fewer than 5 points the picture can only be moved, rotated and scaled. Add more points around the area you need.</span>':'')+'<br>'+ZONES[z].name+' · pixel '+ps.toFixed(3)+' ft · '+outW+' × '+outH+' px';
 $('gs_d1').disabled=$('gs_d2').disabled=false;say('Done. Download below.');}
// ---- TIFF writer (uncompressed RGB, optional GeoTIFF tags) ----
function makeTiff(r,geo){const {outW:w,outH:h,pix}=r;const rps=Math.max(1,Math.floor(65536/(w*3))),ns=Math.ceil(h/rps);
 const tags=[];const T=(id,type,count,val)=>tags.push({id,type,count,val});
 // layout: header 8, IFD, extra data, strips
 const nT=11+(geo?3:0);let ifdSize=2+nT*12+4,pos=8+ifdSize;
 const extra=[];const addExtra=(bytes)=>{const o=pos;extra.push([o,bytes]);pos+=bytes.length+(bytes.length&1);return o;};
 const u16=a=>{const b=new Uint8Array(a.length*2),v=new DataView(b.buffer);a.forEach((x,i)=>v.setUint16(i*2,x,true));return b;};
 const u32=a=>{const b=new Uint8Array(a.length*4),v=new DataView(b.buffer);a.forEach((x,i)=>v.setUint32(i*4,x,true));return b;};
 const f64=a=>{const b=new Uint8Array(a.length*8),v=new DataView(b.buffer);a.forEach((x,i)=>v.setFloat64(i*8,x,true));return b;};
 const bpsOff=addExtra(u16([8,8,8]));
 const stripBytes=[];for(let s=0;s<ns;s++){const rows=Math.min(rps,h-s*rps);stripBytes.push(rows*w*3);}
 let soff,cnt;
 if(ns>1){soff=addExtra(new Uint8Array(ns*4));cnt=addExtra(u32(stripBytes));}
 let geoPS,geoTP,geoKD;
 if(geo){geoPS=addExtra(f64([r.psx,r.psy,0]));geoTP=addExtra(f64([0,0,0,r.ulx,r.uly,0]));geoKD=addExtra(u16([1,1,0,4, 1024,0,1,1, 1025,0,1,1, 3072,0,1,ZONES[r.z].epsg, 3076,0,1,9003]));}
 const dataStart=pos+(pos&1);const starts=[];let p=dataStart;for(let s=0;s<ns;s++){starts.push(p);p+=stripBytes[s];}
 const buf=new Uint8Array(p),dv=new DataView(buf.buffer);
 buf[0]=0x49;buf[1]=0x49;dv.setUint16(2,42,true);dv.setUint32(4,8,true);
 extra.forEach(([o,b])=>buf.set(b,o));
 if(ns>1){const sv=new DataView(buf.buffer,soff,ns*4);starts.forEach((s,i)=>sv.setUint32(i*4,s,true));}
 let ent=[[256,4,1,w],[257,4,1,h],[258,3,3,bpsOff],[259,3,1,1],[262,3,1,2],[273,4,ns,ns>1?soff:starts[0]],[277,3,1,3],[278,4,1,rps],[279,4,ns,ns>1?cnt:stripBytes[0]],[284,3,1,1],[296,3,1,1]];
 if(geo)ent.push([33550,12,3,geoPS],[33922,12,6,geoTP],[34735,3,20,geoKD]);
 ent.sort((a,b)=>a[0]-b[0]);
 dv.setUint16(8,ent.length,true);let q=10;
 ent.forEach(([id,type,count,val])=>{dv.setUint16(q,id,true);dv.setUint16(q+2,type,true);dv.setUint32(q+4,count,true);
  if(type===3&&count===1)dv.setUint16(q+8,val,true);else dv.setUint32(q+8,val,true);q+=12;});
 dv.setUint32(q,0,true);
 for(let s=0;s<ns;s++){let o=starts[s];const r0=s*rps,r1=Math.min(h,r0+rps);for(let y=r0;y<r1;y++){let i=y*w*4;for(let x=0;x<w;x++){buf[o++]=pix[i];buf[o++]=pix[i+1];buf[o++]=pix[i+2];i+=4;}}}
 return buf;}
function save(name,data,type){const u=URL.createObjectURL(new Blob([data],{type:type||'application/octet-stream'}));const a=document.createElement('a');a.href=u;a.download=name;document.body.appendChild(a);a.click();setTimeout(()=>{a.remove();URL.revokeObjectURL(u);},800);}

const baseName=()=>{const f=$('gs_img').files[0];return(f?f.name.replace(/\.[^.]+$/,''):'image')+'_'+result.z.toUpperCase()};
$('gs_d1').onclick=()=>{if(result)save(baseName()+'_GeoTIFF.tif',makeTiff(result,true),'image/tiff')};
$('gs_d2').onclick=()=>{if(!result)return;const b=baseName()+'_TFW';save(b+'.tif',makeTiff(result,false),'image/tiff');
 setTimeout(()=>save(b+'.tfw',[result.psx.toFixed(10),'0.0000000000','0.0000000000',(-result.psy).toFixed(10),(result.ulx+result.psx/2).toFixed(4),(result.uly-result.psy/2).toFixed(4)].join('\r\n')+'\r\n','text/plain'),400);
 setTimeout(()=>save(b+'.prj',prjText(result.z),'text/plain'),800)};
$('gs_clear').onclick=()=>{imgData=null;pkCanvas=null;result=null;KMLN=0;$('gs_img').value='';$('gs_kml').value='';NAMES=[];PU=[];PV=[];NP=0;ACT=0;build(3);$('gs_info').innerHTML='';$('gs_d1').disabled=$('gs_d2').disabled=true;say('');draw();const c=$('gs_cv');c.getContext('2d').clearRect(0,0,c.width,c.height)};
build(3);


})();
</script>
</body>
</html>
