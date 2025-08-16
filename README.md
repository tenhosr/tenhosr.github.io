<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Tenho Saavedra — Project Manager</title>
  <meta name="description" content="Project manager focused on delivery, Agile/DevOps practices, and AI/ML initiatives." />
  <meta property="og:title" content="Tenho Saavedra — Project Manager" />
  <meta property="og:description" content="Project manager focused on delivery, Agile/DevOps practices, and AI/ML initiatives." />
  <meta property="og:type" content="website" />
  <meta property="og:image" content="/og-image.png" />
  <meta name="twitter:card" content="summary_large_image" />
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='0.9em' font-size='90'%3E🧭%3C/text%3E%3C/svg%3E">

  <!-- CSS: minimal, fast, accessible -->
  <style>
    :root{
      --bg: #0b0c0f; --fg: #e7eaf0; --muted:#9aa3b2; --card:#141821; --accent:#6ea8fe; --line:#232838;
      --ink:#101418; --paper:#ffffff;
      --radius: 16px; --shadow: 0 10px 30px rgba(0,0,0,.25);
      --maxw: 980px;
    }
    @media (prefers-color-scheme: light) { :root{ --bg:#f7f8fb; --fg:#101418; --muted:#5b6574; --card:#ffffff; --accent:#2b59ff; --line:#e6e9ef; } }
    :root[data-theme="light"]{ --bg:#f7f8fb; --fg:#101418; --muted:#5b6574; --card:#ffffff; --accent:#2b59ff; --line:#e6e9ef; }

    *{box-sizing:border-box}
    html,body{margin:0;padding:0;background:var(--bg);color:var(--fg);font:16px/1.6 system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,Cantarell,Noto Sans,sans-serif}
    a{color:var(--accent);text-decoration:none}
    a:hover{text-decoration:underline}
    .wrap{max-width:var(--maxw);margin-inline:auto;padding:32px}
    header{display:grid;grid-template-columns:1fr auto;gap:16px;align-items:center}
    .brand{display:flex;gap:16px;align-items:center}
    .avatar{width:72px;height:72px;border-radius:50%;background:linear-gradient(135deg,#6ea8fe,transparent),linear-gradient(135deg,transparent,#a8ffe0);box-shadow:var(--shadow)}
    h1{margin:0;font-size:clamp(28px,3.5vw,40px);letter-spacing:-.02em}
    .tagline{color:var(--muted);margin-top:4px}
    .toolbar{display:flex;gap:10px}
    .btn{display:inline-flex;align-items:center;gap:8px;background:var(--card);color:var(--fg);border:1px solid var(--line);padding:10px 14px;border-radius:12px;cursor:pointer}
    .btn:hover{transform:translateY(-1px)}

    .grid{display:grid;grid-template-columns: 1.2fr .8fr; gap:24px; margin-top:28px}
    @media (max-width: 900px){ .grid{grid-template-columns:1fr} }

    section{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:22px 22px 10px;box-shadow:var(--shadow)}
    section h2{margin:0 0 14px;font-size:clamp(18px,2.4vw,22px)}

    .hero{display:grid;grid-template-columns:1fr 1fr;gap:24px}
    .hero .callout{background:linear-gradient(180deg,rgba(110,168,254,.15),transparent 60%);border:1px dashed var(--line);padding:16px;border-radius:12px}
    .hero ul{margin:8px 0 0 18px}

    .chips{display:flex;flex-wrap:wrap;gap:8px;margin-top:10px}
    .chip{border:1px solid var(--line);border-radius:999px;padding:6px 10px;font-size:13px;background:rgba(46, 120, 255, .08)}

    .timeline{position:relative;margin:0;padding:0;list-style:none}
    .timeline li{display:grid;grid-template-columns:16px 1fr;gap:12px;margin:0 0 18px}
    .dot{width:16px;height:16px;border-radius:50%;background:var(--accent);margin-top:7px}
    .card{border:1px solid var(--line);border-radius:12px;padding:12px;background:rgba(255,255,255,.02)}
    .meta{color:var(--muted);font-size:13px}

    .skills{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px}
    @media (max-width: 520px){ .skills{grid-template-columns:1fr} }
    .skill{display:flex;align-items:center;justify-content:space-between;border:1px solid var(--line);border-radius:10px;padding:10px}
    .skill meter{width:46%; height:10px}

    footer{display:flex;flex-wrap:wrap;gap:12px;align-items:center;justify-content:space-between;margin-top:24px;color:var(--muted)}
    .links{display:flex;gap:12px;flex-wrap:wrap}

    /* Print styles: A4 portrait, clean */
    @media print{
      :root{ --bg:#fff; --fg:#000; --line:#ddd; --card:#fff }
      body{background:#fff}
      .btn,.toolbar{display:none!important}
      a{text-decoration:none;color:inherit}
      section{box-shadow:none}
      .wrap{padding:0}
      @page{ size:A4; margin:18mm }
    }
  </style>

  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Person",
    "name": "Tenho Saavedra",
    "jobTitle": "Project Manager",
    "url": "https://<your-username>.github.io/",
    "sameAs": [
      "https://www.linkedin.com/in/<your-handle>",
      "https://github.com/<your-username>"
    ],
    "knowsAbout": ["Agile", "Scrum", "Kanban", "DevOps", "AI/ML", "Stakeholder Management", "Risk Management"],
    "worksFor": {"@type":"Organization","name":"Ecomond"}
  }
  </script>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="avatar" aria-hidden="true"></div>
        <div>
          <h1>Tenho Saavedra</h1>
          <div class="tagline">Project Manager · Delivery, Agile/DevOps, AI/ML initiatives</div>
        </div>
      </div>
      <div class="toolbar">
        <button class="btn" id="themeBtn" title="Toggle dark/light">🌓 Theme</button>
        <a class="btn" href="#" id="downloadPdf">⬇️ PDF</a>
        <a class="btn" href="mailto:tenho.saavedra@ecomond.com">✉️ Contact</a>
      </div>
    </header>

    <div class="grid">
      <section>
        <h2>Summary</h2>
        <div class="hero">
          <div>
            <p>Project manager with a track record of shipping complex, cross-functional work. I make scope legible, unblock teams, and convert ambiguity into delivery—especially where data and ML touch real products.</p>
            <div class="chips" aria-label="Impact highlights">
              <span class="chip">↑ On-time delivery +23%</span>
              <span class="chip">↓ Cycle time −18%</span>
              <span class="chip">↺ Incident MTTR −35%</span>
              <span class="chip">⚙️ CI/CD adoption across 5 teams</span>
            </div>
          </div>
          <div class="callout">
            <strong>Focus areas</strong>
            <ul>
              <li>Agile facilitation (Scrum/Kanban), outcome-driven roadmaps</li>
              <li>DevOps practices: CI/CD, observability, incident response</li>
              <li>AI/ML project orchestration: data readiness, evaluation gates</li>
            </ul>
          </div>
        </div>
      </section>

      <section>
        <h2>Core Skills</h2>
        <div class="skills">
          <div class="skill">
            <span>Stakeholder Management</span>
            <meter min="0" max="5" value="5">5/5</meter>
          </div>
          <div class="skill">
            <span>Agile Delivery</span>
            <meter min="0" max="5" value="5">5/5</meter>
          </div>
          <div class="skill">
            <span>Risk & Dependency Mgmt</span>
            <meter min="0" max="5" value="4">4/5</meter>
          </div>
          <div class="skill">
            <span>DevOps / CI-CD</span>
            <meter min="0" max="5" value="4">4/5</meter>
          </div>
          <div class="skill">
            <span>AI/ML Delivery</span>
            <meter min="0" max="5" value="4">4/5</meter>
          </div>
          <div class="skill">
            <span>Budget & Forecasting</span>
            <meter min="0" max="5" value="4">4/5</meter>
          </div>
        </div>
      </section>

      <section>
        <h2>Selected Projects</h2>
        <ul class="timeline">
          <li>
            <div class="dot" aria-hidden="true"></div>
            <div class="card">
              <strong>Data Platform Modernization</strong>
              <div class="meta">2024–2025 · PM · Ecomond</div>
              <p>Led migration to a modular data platform. Coordinated 4 teams across ingestion, modeling, and observability. Introduced a productized backlog and evaluation gates for ML features.</p>
              <div class="chips">
                <span class="chip">Cost −22%</span>
                <span class="chip">Freshness +3×</span>
                <span class="chip">SLAs 99.9%</span>
              </div>
            </div>
          </li>
          <li>
            <div class="dot" aria-hidden="true"></div>
            <div class="card">
              <strong>Incident Response Overhaul</strong>
              <div class="meta">2023–2024 · PM</div>
              <p>Rolled out unified on-call, playbooks, and postmortem discipline. Established error budgets and dashboards.</p>
              <div class="chips">
                <span class="chip">MTTR −35%</span>
                <span class="chip">Sev1 count −40%</span>
              </div>
            </div>
          </li>
          <li>
            <div class="dot" aria-hidden="true"></div>
            <div class="card">
              <strong>ML-Powered Forecasting MVP</strong>
              <div class="meta">2022–2023 · PM</div>
              <p>Launched a forecasting MVP with offline/online evaluation. Drove alignment across DS/Eng/Product, created risks register and decision logs.</p>
              <div class="chips">
                <span class="chip">MAPE −12%</span>
                <span class="chip">Time-to-insight −50%</span>
              </div>
            </div>
          </li>
        </ul>
      </section>

      <section>
        <h2>Credentials</h2>
        <ul>
          <li>Certified Scrum Master (CSM), 2023</li>
          <li>ITIL Foundation, 2022</li>
          <li>Google Project Management Cert, 2021</li>
        </ul>
        <h2>Contact</h2>
        <p><a href="mailto:tenho.saavedra@ecomond.com">tenho.saavedra@ecomond.com</a> · <a href="https://github.com/<your-username>">github.com/&lt;your-username&gt;</a> · <a href="https://www.linkedin.com/in/<your-handle>">LinkedIn</a></p>
      </section>
    </div>

    <footer>
      <div>© <span id="year"></span> Tenho Saavedra</div>
      <div class="links">
        <a href="#projects">Projects</a>
        <a href="#skills">Skills</a>
        <a href="#">Back to top ↑</a>
      </div>
    </footer>
  </div>

  <script>
    // Theme toggle: remember preference
    const root = document.documentElement;
    const themeBtn = document.getElementById('themeBtn');
    const stored = localStorage.getItem('theme');
    if(stored){ root.setAttribute('data-theme', stored); }
    themeBtn.addEventListener('click', () => {
      const now = root.getAttribute('data-theme') === 'light' ? '' : 'light';
      if(now) root.setAttribute('data-theme', now); else root.removeAttribute('data-theme');
      localStorage.setItem('theme', now);
    });

    // PDF download: triggers print dialog for clean export
    document.getElementById('downloadPdf').addEventListener('click', (e)=>{
      e.preventDefault();
      window.print();
    });

    // Year
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
