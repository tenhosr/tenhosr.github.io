<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Developer Mandays Timeline Generator</title>

  <!-- XLSX -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js" defer></script>

  <style>
    :root{
      --bg1:#667eea; --bg2:#764ba2;
      --card:#ffffff; --muted:#718096; --text:#1a202c;
      --border:#e2e8f0; --border2:#cbd5e0;
      --primary:#667eea; --primary2:#5568d3;
      --success:#48bb78; --success2:#38a169;
      --danger:#f56565; --danger2:#e53e3e;
      --soft:#f7fafc; --soft2:#f0f4ff;
      --focus: 0 0 0 3px rgba(102,126,234,.25);
      --shadow: 0 20px 60px rgba(0,0,0,.3);
      --shadow2: 0 8px 24px rgba(0,0,0,.12);
      --radius: 16px;
    }

    * { box-sizing: border-box; }
    html, body { height: 100%; }
    body {
      margin: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background: linear-gradient(135deg, var(--bg1) 0%, var(--bg2) 100%);
      padding: 40px 20px;
      color: var(--text);
    }

    .container {
      max-width: 1400px;
      margin: 0 auto;
      background: var(--card);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 36px;
    }

    header {
      display: flex;
      align-items: start;
      justify-content: space-between;
      gap: 16px;
      margin-bottom: 18px;
    }

    h1 {
      margin: 0;
      font-size: 32px;
      display: flex;
      align-items: center;
      gap: 12px;
      line-height: 1.15;
    }

    .subtitle {
      margin: 10px 0 0 0;
      color: var(--muted);
      font-size: 16px;
    }

    .pill {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 12px;
      background: var(--soft);
      border: 1px solid var(--border);
      border-radius: 999px;
      color: #4a5568;
      font-size: 13px;
      white-space: nowrap;
    }

    .grid {
      display: grid;
      gap: 18px;
    }

    .layout-selector,
    .config-section {
      background: var(--soft);
      border-radius: 12px;
      padding: 22px;
      border: 2px solid var(--border);
    }

    .section-title {
      font-size: 18px;
      font-weight: 700;
      color: #2d3748;
      display: flex;
      align-items: center;
      gap: 10px;
      margin: 0 0 14px 0;
    }

    .layout-options {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 14px;
      margin-top: 12px;
    }

    .layout-card {
      background: var(--card);
      border: 2px solid var(--border);
      border-radius: 12px;
      padding: 18px;
      cursor: pointer;
      transition: transform .15s, box-shadow .15s, border-color .15s, background .15s;
      user-select: none;
      outline: none;
    }

    .layout-card:hover {
      border-color: var(--primary);
      transform: translateY(-2px);
      box-shadow: 0 6px 16px rgba(102, 126, 234, .28);
    }

    .layout-card.selected {
      border-color: var(--primary);
      background: var(--soft2);
    }

    .layout-card:focus-visible {
      box-shadow: var(--shadow2), var(--focus);
    }

    .layout-title {
      font-weight: 700;
      font-size: 16px;
      margin-bottom: 6px;
      color: #2d3748;
      display: flex;
      align-items: center;
      gap: 8px;
      flex-wrap: wrap;
    }

    .layout-description {
      font-size: 14px;
      color: var(--muted);
      line-height: 1.55;
    }

    .layout-example {
      margin-top: 10px;
      padding: 10px 12px;
      background: var(--soft);
      border: 1px solid var(--border);
      border-radius: 8px;
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
      font-size: 12px;
      color: #4a5568;
      overflow-x: auto;
      white-space: pre;
    }

    .badge {
      display: inline-block;
      padding: 3px 8px;
      border-radius: 999px;
      font-size: 12px;
      font-weight: 800;
      border: 1px solid rgba(0,0,0,.06);
    }
    .badge-recommended { background: var(--success); color: #fff; }

    .input-group {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 14px;
      margin-bottom: 12px;
    }

    .input-wrapper {
      display: flex;
      flex-direction: column;
      gap: 6px;
      min-width: 0;
    }

    label { font-size: 13px; font-weight: 700; color: #4a5568; }

    input[type="text"], input[type="number"], input[type="month"] {
      padding: 10px 12px;
      border: 2px solid var(--border2);
      border-radius: 10px;
      font-size: 14px;
      transition: border-color .15s, box-shadow .15s;
      background: #fff;
      width: 100%;
    }

    input:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: var(--focus);
    }

    .list-item {
      display: grid;
      grid-template-columns: 2fr 1fr auto;
      gap: 12px;
      align-items: end;
      background: #fff;
      padding: 14px;
      border-radius: 10px;
      border: 1px solid var(--border);
      margin-bottom: 12px;
    }

    .list-item.project {
      grid-template-columns: 1fr auto;
    }

    @media (max-width: 720px) {
      .list-item { grid-template-columns: 1fr; }
      header { flex-direction: column; align-items: start; }
    }

    button {
      padding: 12px 16px;
      border: none;
      border-radius: 10px;
      font-size: 14px;
      font-weight: 800;
      cursor: pointer;
      transition: transform .15s, box-shadow .15s, background .15s;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      white-space: nowrap;
    }

    button:focus-visible { outline: none; box-shadow: var(--focus); }

    .btn-primary { background: var(--primary); color: #fff; }
    .btn-primary:hover { background: var(--primary2); transform: translateY(-1px); box-shadow: 0 6px 16px rgba(102,126,234,.35); }

    .btn-success { background: var(--success); color: #fff; font-size: 15px; padding: 13px 18px; }
    .btn-success:hover { background: var(--success2); transform: translateY(-1px); box-shadow: 0 6px 16px rgba(72,187,120,.35); }

    .btn-danger { background: var(--danger); color: #fff; padding: 10px 12px; }
    .btn-danger:hover { background: var(--danger2); }

    .btn-secondary { background: #e2e8f0; color: #4a5568; }
    .btn-secondary:hover { background: #cbd5e0; }

    .button-group {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      justify-content: center;
      margin-top: 10px;
    }

    .icon { width: 20px; height: 20px; flex: 0 0 auto; }

    .preview-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(86px, 1fr));
      gap: 8px;
      margin-top: 10px;
    }

    .preview-item {
      background: #fff;
      padding: 8px 10px;
      border-radius: 8px;
      font-size: 13px;
      color: #2d3748;
      border: 1px solid var(--border);
      text-align: center;
    }

    .info-box {
      background: #ebf8ff;
      border: 2px solid #90cdf4;
      border-radius: 12px;
      padding: 18px;
      margin-top: 22px;
    }

    .info-box h3 { margin: 0 0 10px 0; color: #2c5282; font-size: 16px; }
    .info-box ul { margin: 0; padding-left: 18px; color: #2d3748; font-size: 14px; line-height: 1.8; }
    .info-box li { margin-bottom: 6px; }

    .success-message, .error-message {
      border-radius: 10px;
      padding: 14px 16px;
      margin-top: 14px;
      display: none;
      align-items: center;
      gap: 10px;
      font-weight: 700;
    }

    .success-message { background: #c6f6d5; border: 2px solid var(--success); color: #22543d; }
    .error-message { background: #fed7d7; border: 2px solid var(--danger); color: #742a2a; }

    .show { display: flex; }

    .hint {
      margin-top: 10px;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.5;
    }

    .top-actions {
      display: flex;
      gap: 10px;
      align-items: center;
      flex-wrap: wrap;
      justify-content: flex-end;
    }
  </style>
</head>

<body>
  <div class="container">
    <header>
      <div>
        <h1>
          <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
          </svg>
          Developer Mandays Timeline Generator
        </h1>
        <p class="subtitle">Generate Excel timelines for allocations across months, developers, and projects.</p>
      </div>

      <div class="top-actions">
        <span class="pill" id="countsPill">3 devs · 3 projects · 12 months</span>
        <button class="btn-secondary" id="resetBtn" type="button" title="Reset to defaults">
          <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M4 4v6h6M20 20v-6h-6M5 19a9 9 0 0114-6.708M19 5a9 9 0 00-14 6.708" />
          </svg>
          Reset
        </button>
      </div>
    </header>

    <div class="layout-selector" aria-labelledby="layoutTitle">
      <div class="section-title" id="layoutTitle">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M4 5a1 1 0 011-1h14a1 1 0 011 1v2a1 1 0 01-1 1H5a1 1 0 01-1-1V5zM4 13a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H5a1 1 0 01-1-1v-6zM16 13a1 1 0 011-1h2a1 1 0 011 1v6a1 1 0 01-1 1h-2a1 1 0 01-1-1v-6z" />
        </svg>
        Choose your timeline layout
      </div>

      <div class="layout-options" id="layoutOptions" role="listbox" aria-label="Timeline layout">
        <div class="layout-card selected" role="option" aria-selected="true" tabindex="0" data-layout="developer-timeline">
          <div class="layout-title">Developer Timeline <span class="badge badge-recommended">Recommended</span></div>
          <div class="layout-description">Each row is a developer, columns are months. Shows all projects per developer.</div>
          <div class="layout-example">Dev1 | Jan-P1 | Jan-P2 | Feb-P1 | Feb-P2 | ...</div>
        </div>

        <div class="layout-card" role="option" aria-selected="false" tabindex="0" data-layout="project-timeline">
          <div class="layout-title">Project Timeline</div>
          <div class="layout-description">Each row is a project, columns are months. Shows all developers per project.</div>
          <div class="layout-example">Proj1 | Jan-Dev1 | Jan-Dev2 | Feb-Dev1 | ...</div>
        </div>

        <div class="layout-card" role="option" aria-selected="false" tabindex="0" data-layout="matrix">
          <div class="layout-title">Monthly Matrix View</div>
          <div class="layout-description">Rows are developers, columns are projects, with separate sheets per month.</div>
          <div class="layout-example">[Jan] Dev1 | P1 | P2 | P3&#10;[Feb] Dev1 | P1 | P2 | P3</div>
        </div>

        <div class="layout-card" role="option" aria-selected="false" tabindex="0" data-layout="heatmap">
          <div class="layout-title">Utilization Heatmap</div>
          <div class="layout-description">Rows are developers, columns are months. Shows utilization percentages.</div>
          <div class="layout-example">Dev1 | 85% | 90% | 75% | 100% | ...</div>
        </div>

        <div class="layout-card" role="option" aria-selected="false" tabindex="0" data-layout="pivot">
          <div class="layout-title">Project Capacity View</div>
          <div class="layout-description">Total FTE per project per month (handy for capacity planning).</div>
          <div class="layout-example">Project1 | Jan:2.5 | Feb:3.0 | Mar:2.8 | ...</div>
        </div>

        <div class="layout-card" role="option" aria-selected="false" tabindex="0" data-layout="gantt">
          <div class="layout-title">Gantt-Style Timeline</div>
          <div class="layout-description">Developer–project rows with month allocations for quick scanning.</div>
          <div class="layout-example">Dev1-Proj1 | 5 | 8 | 10 | 12 | ...</div>
        </div>
      </div>

      <p class="hint">
        Tip: use arrow keys / Enter on the layout cards (keyboard-friendly now).
      </p>
    </div>

    <div class="config-section" aria-labelledby="devTitle">
      <div class="section-title" id="devTitle">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
        </svg>
        Developers
      </div>

      <div id="developersList" aria-live="polite"></div>

      <button class="btn-secondary" id="addDeveloperBtn" type="button">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
        </svg>
        Add developer
      </button>
    </div>

    <div class="config-section" aria-labelledby="projTitle">
      <div class="section-title" id="projTitle">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
        </svg>
        Projects
      </div>

      <div id="projectsList" aria-live="polite"></div>

      <button class="btn-secondary" id="addProjectBtn" type="button">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
        </svg>
        Add project
      </button>
    </div>

    <div class="config-section" aria-labelledby="periodTitle">
      <div class="section-title" id="periodTitle">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
        </svg>
        Timeline period
      </div>

      <div class="input-group">
        <div class="input-wrapper">
          <label for="startMonth">Start month</label>
          <input type="month" id="startMonth" value="2025-01" />
        </div>
        <div class="input-wrapper">
          <label for="endMonth">End month</label>
          <input type="month" id="endMonth" value="2025-12" />
        </div>
      </div>

      <div class="preview-grid" id="monthsPreview" aria-label="Months preview"></div>
      <div class="error-message" id="errorMessage" role="alert" aria-live="assertive"></div>
    </div>

    <div class="button-group">
      <button class="btn-success" id="generateBtn" type="button">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
        </svg>
        Generate Excel timeline
      </button>

      <button class="btn-primary" id="generateSampleBtn" type="button">
        <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
        </svg>
        Generate with sample data
      </button>
    </div>

    <div class="success-message" id="successMessage" role="status" aria-live="polite">
      <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
          d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
      </svg>
      <span>Excel timeline generated successfully!</span>
    </div>

    <div class="info-box">
      <h3>📊 Timeline features</h3>
      <ul>
        <li><strong>Developer Timeline:</strong> track individual capacity across the year</li>
        <li><strong>Project Timeline:</strong> resource planning per project</li>
        <li><strong>Monthly Matrix:</strong> month-by-month 3D view</li>
        <li><strong>Utilization Heatmap:</strong> quick utilization scan</li>
        <li><strong>Project Capacity View:</strong> total FTE per project per month</li>
        <li><strong>Gantt-Style:</strong> simple, readable timeline layout</li>
      </ul>
    </div>
  </div>

  <script>
    "use strict";

    // ---------- State ----------
    const state = {
      selectedLayout: "developer-timeline",
      developers: [
        { name: "Developer 1", availableMandays: 20 },
        { name: "Developer 2", availableMandays: 20 },
        { name: "Developer 3", availableMandays: 20 },
      ],
      projects: [
        { name: "Project Alpha" },
        { name: "Project Beta" },
        { name: "Project Gamma" },
      ],
    };

    // ---------- Helpers ----------
    const $ = (id) => document.getElementById(id);

    function showError(msg) {
      const el = $("errorMessage");
      el.textContent = msg;
      el.classList.add("show");
      setTimeout(() => el.classList.remove("show"), 4500);
    }

    function showSuccess() {
      const el = $("successMessage");
      el.classList.add("show");
      setTimeout(() => el.classList.remove("show"), 2800);
    }

    function safeFilePart(s) {
      return String(s || "")
        .trim()
        .replace(/[\\/:*?"<>|]+/g, "-")
        .replace(/\s+/g, "_")
        .slice(0, 80) || "Timeline";
    }

    function clamp(n, min, max) {
      const x = Number(n);
      if (!Number.isFinite(x)) return min;
      return Math.min(max, Math.max(min, x));
    }

    function toMonthLabel(ym) {
      // ym = "YYYY-MM"
      const [y, m] = ym.split("-").map(Number);
      const d = new Date(y, m - 1, 1);
      return d.toLocaleString(undefined, { month: "short", year: "numeric" });
    }

    function getMonthsRange(start, end) {
      if (!start || !end) return [];
      const startDate = new Date(start + "-01T00:00:00");
      const endDate = new Date(end + "-01T00:00:00");

      if (Number.isNaN(startDate.getTime()) || Number.isNaN(endDate.getTime())) return [];
      if (startDate > endDate) return [];

      const months = [];
      const current = new Date(startDate);
      while (current <= endDate) {
        const y = current.getFullYear();
        const m = String(current.getMonth() + 1).padStart(2, "0");
        months.push(`${y}-${m}`);
        current.setMonth(current.getMonth() + 1);
      }
      return months;
    }

    function updateCountsPill() {
      const months = getMonthsRange($("startMonth").value, $("endMonth").value);
      $("countsPill").textContent = `${state.developers.length} devs · ${state.projects.length} projects · ${months.length} months`;
    }

    function validateInputs() {
      const start = $("startMonth").value;
      const end = $("endMonth").value;
      const months = getMonthsRange(start, end);

      if (!start || !end) return { ok: false, months: [], message: "Please select a start and end month." };
      if (months.length === 0) return { ok: false, months: [], message: "Start month must be before (or equal to) end month." };

      const badDev = state.developers.find((d) => !String(d.name).trim());
      if (badDev) return { ok: false, months, message: "Every developer needs a name." };

      const badProj = state.projects.find((p) => !String(p.name).trim());
      if (badProj) return { ok: false, months, message: "Every project needs a name." };

      return { ok: true, months, message: "" };
    }

    // ---------- Layout Selection (no inline onclick, keyboard-friendly) ----------
    function setSelectedLayout(layout) {
      state.selectedLayout = layout;

      document.querySelectorAll(".layout-card").forEach((card) => {
        const isSelected = card.dataset.layout === layout;
        card.classList.toggle("selected", isSelected);
        card.setAttribute("aria-selected", String(isSelected));
      });
    }

    function wireLayoutCards() {
      const cards = Array.from(document.querySelectorAll(".layout-card"));

      cards.forEach((card, idx) => {
        card.addEventListener("click", () => setSelectedLayout(card.dataset.layout));
        card.addEventListener("keydown", (e) => {
          const key = e.key;
          if (key === "Enter" || key === " ") {
            e.preventDefault();
            setSelectedLayout(card.dataset.layout);
          }
          if (key === "ArrowRight" || key === "ArrowDown") {
            e.preventDefault();
            const next = cards[(idx + 1) % cards.length];
            next.focus();
          }
          if (key === "ArrowLeft" || key === "ArrowUp") {
            e.preventDefault();
            const prev = cards[(idx - 1 + cards.length) % cards.length];
            prev.focus();
          }
        });
      });
    }

    // ---------- Renderers ----------
    function renderDevelopers() {
      const container = $("developersList");

      container.innerHTML = state.developers
        .map((dev, idx) => {
          const removeBtn =
            state.developers.length > 1
              ? `<button class="btn-danger" type="button" data-action="remove-dev" data-idx="${idx}">Remove</button>`
              : "";

          return `
            <div class="list-item">
              <div class="input-wrapper" style="flex:2;">
                <label for="dev-name-${idx}">Name</label>
                <input id="dev-name-${idx}" type="text" value="${escapeHtml(dev.name)}" data-action="dev-name" data-idx="${idx}">
              </div>
              <div class="input-wrapper" style="flex:1;">
                <label for="dev-md-${idx}">Available mandays / month</label>
                <input id="dev-md-${idx}" type="number" min="0" value="${Number(dev.availableMandays) || 0}" data-action="dev-md" data-idx="${idx}">
              </div>
              ${removeBtn}
            </div>
          `;
        })
        .join("");

      updateCountsPill();
    }

    function renderProjects() {
      const container = $("projectsList");

      container.innerHTML = state.projects
        .map((proj, idx) => {
          const removeBtn =
            state.projects.length > 1
              ? `<button class="btn-danger" type="button" data-action="remove-proj" data-idx="${idx}">Remove</button>`
              : "";

          return `
            <div class="list-item project">
              <div class="input-wrapper">
                <label for="proj-name-${idx}">Project name</label>
                <input id="proj-name-${idx}" type="text" value="${escapeHtml(proj.name)}" data-action="proj-name" data-idx="${idx}">
              </div>
              ${removeBtn}
            </div>
          `;
        })
        .join("");

      updateCountsPill();
    }

    function updateMonthsPreview() {
      const { ok, months, message } = validateInputs();
      const container = $("monthsPreview");
      container.innerHTML = months.map((m) => `<div class="preview-item">${escapeHtml(toMonthLabel(m))}</div>`).join("");

      if (!ok) showError(message);
      updateCountsPill();
    }

    // Basic HTML escaping for safe rendering of user inputs in templates.
    function escapeHtml(str) {
      return String(str ?? "")
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");
    }

    // ---------- CRUD ----------
    function addDeveloper() {
      state.developers.push({ name: `Developer ${state.developers.length + 1}`, availableMandays: 20 });
      renderDevelopers();
    }
    function removeDeveloper(idx) {
      state.developers.splice(idx, 1);
      renderDevelopers();
    }
    function addProject() {
      const nextLetter = String.fromCharCode(65 + state.projects.length);
      state.projects.push({ name: `Project ${nextLetter}` });
      renderProjects();
    }
    function removeProject(idx) {
      state.projects.splice(idx, 1);
      renderProjects();
    }

    function resetDefaults() {
      state.selectedLayout = "developer-timeline";
      state.developers = [
        { name: "Developer 1", availableMandays: 20 },
        { name: "Developer 2", availableMandays: 20 },
        { name: "Developer 3", availableMandays: 20 },
      ];
      state.projects = [
        { name: "Project Alpha" },
        { name: "Project Beta" },
        { name: "Project Gamma" },
      ];
      $("startMonth").value = "2025-01";
      $("endMonth").value = "2025-12";
      setSelectedLayout(state.selectedLayout);
      renderDevelopers();
      renderProjects();
      updateMonthsPreview();
    }

    // ---------- Sample Data ----------
    function sampleMandays() {
      return Math.floor(Math.random() * 8) + 2; // 2..9
    }

    // ---------- Excel generation helpers ----------
    function aoaSheetWithColumns(data, colWidths) {
      const ws = XLSX.utils.aoa_to_sheet(data);
      ws["!cols"] = colWidths.map((wch) => ({ wch }));
      // Improve readability: wrap headers
      if (ws["!ref"]) {
        const range = XLSX.utils.decode_range(ws["!ref"]);
        for (let C = range.s.c; C <= range.e.c; C++) {
          const addr = XLSX.utils.encode_cell({ r: 0, c: C });
          if (ws[addr]) {
            ws[addr].s = ws[addr].s || {};
            ws[addr].s.alignment = { wrapText: true, vertical: "center" };
            ws[addr].s.font = { bold: true };
          }
        }
      }
      return ws;
    }

    // Note: SheetJS community build has limited styling support in some contexts,
    // but column widths + header wrapping often still help.
    function generateExcel(withSample) {
      const v = validateInputs();
      if (!v.ok) {
        showError(v.message);
        return;
      }

      if (!window.XLSX) {
        showError("XLSX library not loaded yet. Try again in a moment.");
        return;
      }

      const months = v.months;
      const wb = XLSX.utils.book_new();

      switch (state.selectedLayout) {
        case "developer-timeline":
          generateDeveloperTimeline(wb, months, withSample);
          break;
        case "project-timeline":
          generateProjectTimeline(wb, months, withSample);
          break;
        case "matrix":
          generateMatrixView(wb, months, withSample);
          break;
        case "heatmap":
          generateHeatmap(wb, months, withSample);
          break;
        case "pivot":
          generatePivotView(wb, months, withSample);
          break;
        case "gantt":
          generateGanttView(wb, months, withSample);
          break;
        default:
          showError("Unknown layout selected.");
          return;
      }

      const fileName = `${safeFilePart("Developer_Timeline")}_${safeFilePart(state.selectedLayout)}${withSample ? "_Sample" : ""}.xlsx`;
      XLSX.writeFile(wb, fileName);
      showSuccess();
    }

    // ---------- Sheet generators ----------
    function generateDeveloperTimeline(wb, months, withSample) {
      const header = ["Developer", "Available/Mo"];
      months.forEach((month) => {
        state.projects.forEach((proj) => header.push(`${toMonthLabel(month)}\n${proj.name}`));
        header.push(`${toMonthLabel(month)}\nTotal`);
        header.push(`${toMonthLabel(month)}\nUtil%`);
      });

      const rows = state.developers.map((dev) => {
        const row = [dev.name, Number(dev.availableMandays) || 0];

        months.forEach(() => {
          const values = state.projects.map(() => (withSample ? sampleMandays() : ""));
          row.push(...values);

          if (withSample) {
            const total = values.reduce((a, b) => a + (Number(b) || 0), 0);
            const avail = Number(dev.availableMandays) || 0;
            const util = avail > 0 ? (total / avail) * 100 : 0;
            row.push(total);
            row.push(Number(util.toFixed(1)));
          } else {
            row.push("", "");
          }
        });

        return row;
      });

      const data = [header, ...rows];
      const colWidths = [18, 14, ...Array(header.length - 2).fill(12)];
      const ws = aoaSheetWithColumns(data, colWidths);
      XLSX.utils.book_append_sheet(wb, ws, "Developer Timeline");
    }

    function generateProjectTimeline(wb, months, withSample) {
      const header = ["Project"];
      months.forEach((month) => {
        state.developers.forEach((dev) => header.push(`${toMonthLabel(month)}\n${dev.name}`));
        header.push(`${toMonthLabel(month)}\nTotal`);
      });

      const rows = state.projects.map((proj) => {
        const row = [proj.name];

        months.forEach(() => {
          const values = state.developers.map(() => (withSample ? sampleMandays() : ""));
          row.push(...values);

          if (withSample) {
            const total = values.reduce((a, b) => a + (Number(b) || 0), 0);
            row.push(total);
          } else {
            row.push("");
          }
        });

        return row;
      });

      const data = [header, ...rows];
      const colWidths = [22, ...Array(header.length - 1).fill(12)];
      const ws = aoaSheetWithColumns(data, colWidths);
      XLSX.utils.book_append_sheet(wb, ws, "Project Timeline");
    }

    function generateMatrixView(wb, months, withSample) {
      months.forEach((month) => {
        const header = ["Developer", ...state.projects.map((p) => p.name), "Total", "Remaining", "Util%"];

        const rows = state.developers.map((dev) => {
          const avail = Number(dev.availableMandays) || 0;

          const vals = state.projects.map(() => (withSample ? sampleMandays() : ""));
          const row = [dev.name, ...vals];

          if (withSample) {
            const total = vals.reduce((a, b) => a + (Number(b) || 0), 0);
            const remaining = avail - total;
            const util = avail > 0 ? (total / avail) * 100 : 0;
            row.push(total, remaining, Number(util.toFixed(1)));
          } else {
            row.push("", "", "");
          }

          return row;
        });

        const data = [header, ...rows];
        const colWidths = [18, ...Array(header.length - 1).fill(14)];
        const ws = aoaSheetWithColumns(data, colWidths);

        // Sheet names max 31 chars
        const sheetName = safeFilePart(toMonthLabel(month)).slice(0, 31);
        XLSX.utils.book_append_sheet(wb, ws, sheetName);
      });
    }

    function generateHeatmap(wb, months, withSample) {
      const header = ["Developer", "Avg Mandays", ...months.map(toMonthLabel), "Year Avg"];

      const rows = state.developers.map((dev) => {
        const row = [dev.name, Number(dev.availableMandays) || 0];

        const utils = months.map(() => (withSample ? (Math.random() * 40 + 60) : ""));
        row.push(...utils.map((x) => (x === "" ? "" : Number(x.toFixed(1)))));

        if (withSample) {
          const avg = utils.reduce((a, b) => a + (Number(b) || 0), 0) / utils.length;
          row.push(Number(avg.toFixed(1)));
        } else {
          row.push("");
        }

        return row;
      });

      const data = [header, ...rows];
      const colWidths = [18, 14, ...Array(header.length - 2).fill(12)];
      const ws = aoaSheetWithColumns(data, colWidths);
      XLSX.utils.book_append_sheet(wb, ws, "Utilization");
    }

    function generatePivotView(wb, months, withSample) {
      const header = ["Project", ...months.map(toMonthLabel), "Avg FTE"];

      const rows = state.projects.map((proj) => {
        const row = [proj.name];
        const ftes = months.map(() => (withSample ? (Math.random() * 2 + 0.5) : ""));
        row.push(...ftes.map((x) => (x === "" ? "" : Number(x.toFixed(2)))));

        if (withSample) {
          const avg = ftes.reduce((a, b) => a + (Number(b) || 0), 0) / ftes.length;
          row.push(Number(avg.toFixed(2)));
        } else {
          row.push("");
        }
        return row;
      });

      const data = [header, ...rows];
      const colWidths = [24, ...Array(header.length - 1).fill(12)];
      const ws = aoaSheetWithColumns(data, colWidths);
      XLSX.utils.book_append_sheet(wb, ws, "Project Capacity");
    }

    function generateGanttView(wb, months, withSample) {
      const header = ["Developer", "Project", ...months.map(toMonthLabel), "Total Mandays"];
      const rows = [];

      state.developers.forEach((dev) => {
        state.projects.forEach((proj) => {
          const vals = months.map(() => (withSample ? (Math.random() > 0.3 ? sampleMandays() : 0) : ""));
          const row = [dev.name, proj.name, ...vals];

          if (withSample) {
            const total = vals.reduce((a, b) => a + (Number(b) || 0), 0);
            row.push(total);
          } else {
            row.push("");
          }

          rows.push(row);
        });
      });

      const data = [header, ...rows];
      const colWidths = [18, 22, ...Array(header.length - 3).fill(10), 14];
      const ws = aoaSheetWithColumns(data, colWidths);
      XLSX.utils.book_append_sheet(wb, ws, "Gantt");
    }

    // ---------- Event delegation ----------
    function wireEvents() {
      // Inputs affecting months preview
      $("startMonth").addEventListener("change", updateMonthsPreview);
      $("endMonth").addEventListener("change", updateMonthsPreview);

      // Developers list events
      $("developersList").addEventListener("input", (e) => {
        const t = e.target;
        if (!(t instanceof HTMLInputElement)) return;
        const idx = Number(t.dataset.idx);
        const action = t.dataset.action;

        if (action === "dev-name") state.developers[idx].name = t.value;
        if (action === "dev-md") state.developers[idx].availableMandays = clamp(t.value, 0, 9999);
        updateCountsPill();
      });

      $("developersList").addEventListener("click", (e) => {
        const btn = e.target.closest("button");
        if (!btn) return;
        if (btn.dataset.action === "remove-dev") removeDeveloper(Number(btn.dataset.idx));
      });

      // Projects list events
      $("projectsList").addEventListener("input", (e) => {
        const t = e.target;
        if (!(t instanceof HTMLInputElement)) return;
        const idx = Number(t.dataset.idx);
        const action = t.dataset.action;

        if (action === "proj-name") state.projects[idx].name = t.value;
        updateCountsPill();
      });

      $("projectsList").addEventListener("click", (e) => {
        const btn = e.target.closest("button");
        if (!btn) return;
        if (btn.dataset.action === "remove-proj") removeProject(Number(btn.dataset.idx));
      });

      // Add buttons
      $("addDeveloperBtn").addEventListener("click", addDeveloper);
      $("addProjectBtn").addEventListener("click", addProject);

      // Generate buttons
      $("generateBtn").addEventListener("click", () => generateExcel(false));
      $("generateSampleBtn").addEventListener("click", () => generateExcel(true));

      // Reset
      $("resetBtn").addEventListener("click", resetDefaults);
    }

    // ---------- Init ----------
    document.addEventListener("DOMContentLoaded", () => {
      wireLayoutCards();
      wireEvents();
      setSelectedLayout(state.selectedLayout);
      renderDevelopers();
      renderProjects();
      updateMonthsPreview();
    });
  </script>
</body>
</html>
