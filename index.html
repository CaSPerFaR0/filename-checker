<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>File Duplicate Checker</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Instrument+Serif:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0e0e11;
    --surface: #17171c;
    --surface2: #1f1f27;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(255,255,255,0.12);
    --text: #f0efe8;
    --muted: #6b6a75;
    --accent: #c8f060;
    --accent2: #7b6ef6;
    --red: #ff5f5f;
    --blue: #60b4f0;
    --green: #60e89a;
    --mono: 'DM Mono', monospace;
    --sans: 'DM Sans', sans-serif;
    --serif: 'Instrument Serif', serif;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    padding: 0;
    overflow-x: hidden;
  }

  /* bg grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .glow {
    position: fixed;
    width: 600px; height: 600px;
    border-radius: 50%;
    filter: blur(120px);
    pointer-events: none;
    z-index: 0;
  }
  .glow-1 { background: rgba(200,240,96,0.06); top: -200px; right: -100px; }
  .glow-2 { background: rgba(123,110,246,0.07); bottom: -200px; left: -100px; }

  .container {
    position: relative;
    z-index: 1;
    max-width: 920px;
    margin: 0 auto;
    padding: 48px 24px 80px;
  }

  header {
    margin-bottom: 48px;
  }

  .eyebrow {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.15em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .eyebrow::before {
    content: '';
    display: inline-block;
    width: 20px; height: 1px;
    background: var(--accent);
  }

  h1 {
    font-family: var(--serif);
    font-size: clamp(32px, 5vw, 52px);
    font-weight: 400;
    line-height: 1.1;
    letter-spacing: -0.02em;
    color: var(--text);
  }
  h1 em {
    font-style: italic;
    color: var(--accent);
  }

  .subtitle {
    margin-top: 12px;
    font-size: 14px;
    color: var(--muted);
    font-weight: 300;
    letter-spacing: 0.01em;
  }

  /* panels */
  .panels {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  @media (max-width: 640px) { .panels { grid-template-columns: 1fr; } }

  .panel {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    transition: border-color 0.2s;
  }
  .panel:hover { border-color: var(--border2); }

  .panel-head {
    padding: 14px 18px;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 12px;
    font-weight: 500;
    color: var(--muted);
    background: var(--surface2);
  }

  .pill {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 20px;
    font-family: var(--mono);
    font-weight: 500;
    margin-left: auto;
  }
  .pill-main { background: rgba(200,240,96,0.12); color: var(--accent); }
  .pill-compare { background: rgba(123,110,246,0.12); color: var(--accent2); }

  .count-badge {
    margin-left: auto;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    background: rgba(255,255,255,0.05);
    padding: 2px 8px;
    border-radius: 20px;
    border: 1px solid var(--border);
  }

  /* drop zone */
  .drop-zone {
    position: relative;
    margin: 16px;
    border: 1px dashed rgba(255,255,255,0.12);
    border-radius: 12px;
    padding: 28px 20px;
    text-align: center;
    cursor: pointer;
    transition: all 0.2s;
    background: rgba(255,255,255,0.02);
  }
  .drop-zone:hover {
    border-color: var(--accent);
    background: rgba(200,240,96,0.04);
  }
  .drop-zone input {
    position: absolute;
    inset: 0;
    opacity: 0;
    cursor: pointer;
  }

  .dz-icon {
    width: 40px; height: 40px;
    margin: 0 auto 10px;
    background: rgba(200,240,96,0.08);
    border: 1px solid rgba(200,240,96,0.2);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .dz-icon svg { width: 20px; height: 20px; stroke: var(--accent); fill: none; stroke-width: 1.5; }

  .dz-title {
    font-size: 13px;
    font-weight: 500;
    color: var(--text);
    margin-bottom: 4px;
  }
  .dz-sub {
    font-size: 11px;
    color: var(--muted);
  }

  .folder-preview {
    max-height: 140px;
    overflow-y: auto;
    scrollbar-width: thin;
    scrollbar-color: var(--border2) transparent;
  }

  .file-item {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 5px 18px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    border-bottom: 1px solid var(--border);
    transition: background 0.1s;
  }
  .file-item:hover { background: rgba(255,255,255,0.02); }
  .file-item:last-child { border-bottom: none; }
  .file-item svg { width: 12px; height: 12px; stroke: var(--muted); fill: none; stroke-width: 1.5; flex-shrink: 0; }

  textarea {
    width: 100%;
    height: 234px;
    background: transparent;
    border: none;
    outline: none;
    resize: none;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text);
    padding: 16px 18px;
    line-height: 1.7;
    display: block;
    scrollbar-width: thin;
    scrollbar-color: var(--border2) transparent;
  }
  textarea::placeholder { color: var(--muted); }

  /* action bar */
  .action-bar {
    display: flex;
    gap: 10px;
    margin-bottom: 32px;
  }

  .btn {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 11px 20px;
    border-radius: 10px;
    font-size: 13px;
    font-weight: 500;
    font-family: var(--sans);
    cursor: pointer;
    border: 1px solid transparent;
    transition: all 0.15s;
  }
  .btn svg { width: 15px; height: 15px; fill: none; stroke-width: 2; stroke: currentColor; flex-shrink: 0; }

  .btn-primary {
    flex: 1;
    background: var(--accent);
    color: #0e0e11;
    border-color: var(--accent);
    justify-content: center;
    font-size: 14px;
  }
  .btn-primary:hover { background: #d4f570; transform: translateY(-1px); }
  .btn-primary:active { transform: translateY(0); }

  .btn-ghost {
    background: var(--surface);
    color: var(--muted);
    border-color: var(--border);
  }
  .btn-ghost:hover { background: var(--surface2); color: var(--text); border-color: var(--border2); }

  /* stats */
  .stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 24px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
    transition: border-color 0.2s;
  }
  .stat-card:hover { border-color: var(--border2); }

  .stat-num {
    font-family: var(--serif);
    font-size: 36px;
    line-height: 1;
    margin-bottom: 6px;
    color: var(--text);
  }
  .stat-num.red { color: var(--red); }
  .stat-num.blue { color: var(--blue); }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    font-weight: 400;
    letter-spacing: 0.03em;
  }

  /* tabs */
  .tabs {
    display: flex;
    gap: 4px;
    margin-bottom: 14px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 4px;
    width: fit-content;
  }

  .tab {
    padding: 6px 16px;
    border-radius: 7px;
    font-size: 12px;
    font-weight: 500;
    cursor: pointer;
    border: none;
    background: transparent;
    color: var(--muted);
    font-family: var(--sans);
    transition: all 0.15s;
  }
  .tab:hover { color: var(--text); }
  .tab.active {
    background: var(--surface2);
    color: var(--text);
    border: 1px solid var(--border2);
  }

  /* search */
  .search-wrap {
    position: relative;
    margin-bottom: 14px;
  }
  .search-wrap svg {
    position: absolute;
    left: 14px; top: 50%;
    transform: translateY(-50%);
    width: 14px; height: 14px;
    stroke: var(--muted);
    fill: none; stroke-width: 2;
    pointer-events: none;
  }
  #search-input {
    width: 100%;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    color: var(--text);
    font-family: var(--mono);
    font-size: 12px;
    padding: 9px 14px 9px 36px;
    outline: none;
    transition: border-color 0.15s;
  }
  #search-input:focus { border-color: var(--border2); }
  #search-input::placeholder { color: var(--muted); }

  /* result list */
  .result-panel {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
  }

  .result-head {
    padding: 12px 18px;
    border-bottom: 1px solid var(--border);
    font-size: 11px;
    font-weight: 500;
    color: var(--muted);
    background: var(--surface2);
    display: flex;
    align-items: center;
    gap: 8px;
    font-family: var(--mono);
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }

  .result-list {
    max-height: 380px;
    overflow-y: auto;
    scrollbar-width: thin;
    scrollbar-color: var(--border2) transparent;
  }

  .result-row {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 8px 18px;
    border-bottom: 1px solid var(--border);
    transition: background 0.1s;
  }
  .result-row:hover { background: rgba(255,255,255,0.02); }
  .result-row:last-child { border-bottom: none; }
  .result-row svg { width: 13px; height: 13px; stroke: var(--muted); fill: none; stroke-width: 1.5; flex-shrink: 0; }

  .rname {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text);
    flex: 1;
    word-break: break-all;
  }

  .tag {
    font-size: 10px;
    padding: 2px 9px;
    border-radius: 20px;
    font-family: var(--mono);
    font-weight: 500;
    white-space: nowrap;
  }
  .tag-dup { background: rgba(255,95,95,0.12); color: var(--red); border: 1px solid rgba(255,95,95,0.2); }
  .tag-new { background: rgba(96,180,240,0.1); color: var(--blue); border: 1px solid rgba(96,180,240,0.2); }
  .tag-ok  { background: rgba(96,232,154,0.08); color: var(--green); border: 1px solid rgba(96,232,154,0.15); }

  .empty {
    padding: 48px 20px;
    text-align: center;
    font-size: 13px;
    color: var(--muted);
  }

  #results { display: none; }

  .divider {
    height: 1px;
    background: var(--border);
    margin: 0 18px;
  }

  /* scroll bar webkit */
  ::-webkit-scrollbar { width: 4px; height: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 4px; }
</style>
</head>
<body>

<div class="glow glow-1"></div>
<div class="glow glow-2"></div>

<div class="container">

  <header>
    <div class="eyebrow">Utility Tool</div>
    <h1>File <em>Duplicate</em><br>Checker</h1>
    <p class="subtitle">เปรียบเทียบชื่อไฟล์ใน folder กับรายชื่อที่ copy มา</p>
  </header>

  <div class="panels">

    <!-- Panel: Folder (หลัก) -->
    <div class="panel">
      <div class="panel-head">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 7a2 2 0 012-2h4l2 2h8a2 2 0 012 2v9a2 2 0 01-2 2H5a2 2 0 01-2-2z"/></svg>
        Folder ต้นฉบับ
        <span class="pill pill-main">หลัก</span>
        <span class="count-badge" id="folder-count">0 files</span>
      </div>

      <div class="drop-zone" id="drop-zone">
        <input type="file" id="folder-input" multiple webkitdirectory>
        <div class="dz-icon">
          <svg viewBox="0 0 24 24"><path d="M3 7a2 2 0 012-2h4l2 2h8a2 2 0 012 2v9a2 2 0 01-2 2H5a2 2 0 01-2-2z"/></svg>
        </div>
        <p class="dz-title" id="dz-title">คลิกเพื่อเลือก Folder</p>
        <p class="dz-sub" id="dz-sub">ระบบจะอ่านชื่อไฟล์ทั้งหมดใน folder</p>
      </div>

      <div class="folder-preview" id="folder-preview"></div>
    </div>

    <!-- Panel: Paste (เทียบกับ) -->
    <div class="panel">
      <div class="panel-head">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="9" y="2" width="13" height="13" rx="2"/><path d="M5 15H4a2 2 0 01-2-2V4a2 2 0 012-2h9a2 2 0 012 2v1"/></svg>
        รายชื่อที่ copy มา
        <span class="pill pill-compare">เทียบกับ</span>
        <span class="count-badge" id="paste-count">0 files</span>
      </div>
      <textarea id="paste-input" placeholder="วางรายชื่อไฟล์ที่นี่&#10;&#10;HIM_0001.JPG&#10;HIM_0002.JPG&#10;HIM_0003.JPG&#10;..." oninput="updatePasteCount()"></textarea>
    </div>

  </div>

  <div class="action-bar">
    <button class="btn btn-primary" onclick="compare()">
      <svg viewBox="0 0 24 24"><path d="M8 7h12M8 12h12M8 17h12M3 7h.01M3 12h.01M3 17h.01"/></svg>
      เปรียบเทียบ
    </button>
    <button class="btn btn-ghost" onclick="clearAll()">
      <svg viewBox="0 0 24 24"><path d="M3 6h18M8 6V4h8v2M19 6l-1 14H6L5 6"/></svg>
      ล้าง
    </button>
    <button class="btn btn-ghost" id="export-btn" style="display:none" onclick="exportCSV()">
      <svg viewBox="0 0 24 24"><path d="M12 15V3m0 12l-4-4m4 4l4-4M2 17l.621 2.485A2 2 0 004.561 21h14.878a2 2 0 001.94-1.515L22 17"/></svg>
      Export CSV
    </button>
  </div>

  <div id="results">
    <div class="stats">
      <div class="stat-card">
        <div class="stat-num" id="s-total">0</div>
        <div class="stat-label">ไฟล์ใน folder ทั้งหมด</div>
      </div>
      <div class="stat-card">
        <div class="stat-num red" id="s-dup">—</div>
        <div class="stat-label">ซ้ำกับรายชื่อที่ copy มา</div>
      </div>
      <div class="stat-card">
        <div class="stat-num blue" id="s-notfound">—</div>
        <div class="stat-label">ไม่มีในรายชื่อที่ copy มา</div>
      </div>
    </div>

    <div style="display:flex; align-items:center; justify-content:space-between; flex-wrap:wrap; gap:10px; margin-bottom:14px;">
      <div class="tabs">
        <button class="tab active" onclick="switchTab('all',this)">ทั้งหมด</button>
        <button class="tab" onclick="switchTab('dup',this)">ซ้ำ</button>
        <button class="tab" onclick="switchTab('notfound',this)">ไม่มีในรายชื่อ</button>
      </div>
    </div>

    <div class="search-wrap">
      <svg viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><path d="M21 21l-4.35-4.35"/></svg>
      <input id="search-input" placeholder="ค้นหาชื่อไฟล์..." oninput="renderResult()">
    </div>

    <div class="result-panel">
      <div class="result-head">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2"/></svg>
        <span id="result-label">ผลการเปรียบเทียบทั้งหมด</span>
      </div>
      <div class="result-list" id="result-list"></div>
    </div>
  </div>

</div>

<script>
let folderFiles = [];
let pasteSet = new Set();
let resultData = [];
let currentTab = 'all';

document.getElementById('folder-input').addEventListener('change', function(e) {
  const files = Array.from(e.target.files);
  if (!files.length) return;
  folderFiles = files.map(f => f.name);
  const folderName = (files[0].webkitRelativePath || files[0].name).split('/')[0];

  document.getElementById('folder-count').textContent = files.length + ' files';
  document.getElementById('dz-title').textContent = folderName;
  document.getElementById('dz-sub').textContent = files.length + ' ไฟล์';

  const preview = folderFiles.slice(0, 200).map(n => `
    <div class="file-item">
      <svg viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14,2 14,8 20,8"/></svg>
      ${n}
    </div>`).join('');
  const more = folderFiles.length > 200
    ? `<div class="file-item" style="color:var(--muted);font-style:italic;">... และอีก ${folderFiles.length - 200} ไฟล์</div>`
    : '';
  document.getElementById('folder-preview').innerHTML = preview + more;
});

function updatePasteCount() {
  const lines = document.getElementById('paste-input').value.split(/[\n,]+/).map(s => s.trim()).filter(Boolean);
  document.getElementById('paste-count').textContent = lines.length + ' files';
}

function compare() {
  if (!folderFiles.length) { alert('กรุณาเลือก Folder ก่อน'); return; }
  const raw = document.getElementById('paste-input').value;
  const pasteLines = raw.split(/[\n,]+/).map(s => s.trim()).filter(Boolean);
  pasteSet = new Set(pasteLines.map(s => s.toLowerCase()));

  resultData = folderFiles.map(name => ({
    name,
    inPaste: pasteLines.length > 0 ? pasteSet.has(name.toLowerCase()) : null
  }));

  const dupCount = resultData.filter(r => r.inPaste === true).length;
  const notFoundCount = resultData.filter(r => r.inPaste === false).length;

  document.getElementById('s-total').textContent = resultData.length;
  document.getElementById('s-dup').textContent = pasteLines.length > 0 ? dupCount : '—';
  document.getElementById('s-notfound').textContent = pasteLines.length > 0 ? notFoundCount : '—';

  document.getElementById('results').style.display = 'block';
  document.getElementById('export-btn').style.display = '';

  currentTab = 'all';
  document.querySelectorAll('.tab').forEach((t, i) => t.classList.toggle('active', i === 0));
  document.getElementById('result-label').textContent = 'ผลการเปรียบเทียบทั้งหมด';
  document.getElementById('search-input').value = '';
  renderResult();

  document.getElementById('results').scrollIntoView({ behavior: 'smooth', block: 'start' });
}

function switchTab(tab, el) {
  currentTab = tab;
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  el.classList.add('active');
  const labels = { all: 'ผลการเปรียบเทียบทั้งหมด', dup: 'ซ้ำกับรายชื่อที่ copy มา', notfound: 'ไม่มีในรายชื่อที่ copy มา' };
  document.getElementById('result-label').textContent = labels[tab];
  renderResult();
}

function renderResult() {
  const search = document.getElementById('search-input').value.toLowerCase();
  let items = [...resultData];

  if (currentTab === 'dup') items = items.filter(r => r.inPaste === true);
  else if (currentTab === 'notfound') items = items.filter(r => r.inPaste === false);
  if (search) items = items.filter(r => r.name.toLowerCase().includes(search));

  if (!items.length) {
    document.getElementById('result-list').innerHTML = '<div class="empty">ไม่พบรายการ</div>';
    return;
  }

  document.getElementById('result-list').innerHTML = items.map(r => {
    let tag = '';
    if (r.inPaste === true)
      tag = `<span class="tag tag-dup">ซ้ำ</span>`;
    else if (r.inPaste === false)
      tag = `<span class="tag tag-new">ไม่มีในรายชื่อ</span>`;
    else
      tag = `<span class="tag tag-ok">ยังไม่ได้วางรายชื่อ</span>`;

    return `<div class="result-row">
      <svg viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14,2 14,8 20,8"/></svg>
      <span class="rname">${r.name}</span>
      ${tag}
    </div>`;
  }).join('');
}

function clearAll() {
  folderFiles = []; pasteSet = new Set(); resultData = [];
  document.getElementById('folder-input').value = '';
  document.getElementById('paste-input').value = '';
  document.getElementById('folder-count').textContent = '0 files';
  document.getElementById('paste-count').textContent = '0 files';
  document.getElementById('folder-preview').innerHTML = '';
  document.getElementById('dz-title').textContent = 'คลิกเพื่อเลือก Folder';
  document.getElementById('dz-sub').textContent = 'ระบบจะอ่านชื่อไฟล์ทั้งหมดใน folder';
  document.getElementById('results').style.display = 'none';
  document.getElementById('export-btn').style.display = 'none';
}

function exportCSV() {
  let csv = '\uFEFFชื่อไฟล์ใน Folder,สถานะ\n';
  for (const r of resultData) {
    const s = r.inPaste === true ? 'ซ้ำกับรายชื่อที่ copy มา' : r.inPaste === false ? 'ไม่มีในรายชื่อที่ copy มา' : 'ยังไม่ได้วางรายชื่อ';
    csv += `${r.name},${s}\n`;
  }
  const a = document.createElement('a');
  a.href = URL.createObjectURL(new Blob([csv], { type: 'text/csv;charset=utf-8' }));
  a.download = 'compare_result.csv';
  a.click();
}
</script>
</body>
</html>
