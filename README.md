<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="description" content="Personal website of Tenho Saavedra — project manager." />
  <style>
    /* === Mac OS X Snow Leopard (2010) vibes === */
    :root{
      --window-bg: #f6f6f8;
      --chrome:#e9e9ee;
      --chrome-dark:#d4d4db;
      --text:#222;
      --muted:#667;
      --blue:#3a8bff;
      --green:#2aca44;
      --yellow:#f5c02a;
      --red:#ff5f57;
      --link:#0071e3;
    }
    html,body{height:100%;}
    body{
      margin:0; 
      font-family: "Lucida Grande", "Lucida Sans Unicode", Helvetica, Arial, sans-serif;
      color:var(--text);
      background:
        radial-gradient(1200px 600px at 70% -10%, rgba(90,120,255,.15), transparent 60%),
        radial-gradient(1200px 700px at -10% -20%, rgba(0,0,0,.2), transparent 60%),
        #2b3a55 url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" viewBox="0 0 60 60"><defs><pattern id="p" width="60" height="60" patternUnits="userSpaceOnUse"><g opacity="0.08"><path d="M0 59.5h60v1H0z" fill="%23fff"/><path d="M59.5 0v60V0z" fill="%23fff"/></g></pattern></defs><rect fill="%231a2538" width="100%" height="100%"/><rect fill="url(%23p)" width="100%" height="100%"/></svg>') fixed;
      background-size: cover;
    }

    .menu-bar{
      position:fixed;top:0;left:0;right:0;height:24px;z-index:20;
      display:flex;align-items:center;gap:14px;padding:0 10px;
      color:#fff;backdrop-filter:saturate(1.2) blur(10px);
      background:linear-gradient(#3b4c6b,#2a3a59);
      box-shadow:0 1px 0 rgba(255,255,255,.2), 0 1px 16px rgba(0,0,0,.25);
      font-size:12px;
      user-select:none;
    }
    .menu-apple{font-weight:700;font-size:14px;margin-right:6px}
    .menu-item{opacity:.9}

    .desktop{min-height:100%; padding:48px 24px 120px; box-sizing:border-box;}

    .window{
      width:min(980px, 96vw); margin:32px auto; border-radius:10px; overflow:hidden;
      background:var(--window-bg); box-shadow:0 30px 70px rgba(0,0,0,.35), 0 2px 0 rgba(255,255,255,.3) inset;
      border:1px solid rgba(0,0,0,.12);
    }
    .traffic{
      height:24px; display:flex; align-items:center; gap:8px; padding:10px; background:linear-gradient(#fdfdff,#e9e9ee);
      border-bottom:1px solid rgba(0,0,0,.08);
    }
    .dot{width:12px;height:12px;border-radius:50%; box-shadow:0 1px 0 rgba(255,255,255,.8) inset, 0 0 0 1px rgba(0,0,0,.08);
      position:relative}
    .dot.red{background:var(--red)}
    .dot.yellow{background:var(--yellow)}
    .dot.green{background:var(--green)}

    .toolbar{display:flex;align-items:center;gap:10px;padding:8px 12px;background:linear-gradient(#f6f6f8,#e4e4ea);border-bottom:1px solid rgba(0,0,0,.06)}
    .seg{display:inline-flex;border-radius:6px;overflow:hidden;border:1px solid var(--chrome-dark);box-shadow:0 1px 0 #fff inset}
    .seg button{background:linear-gradient(#fff,#eaeaef);border:0;padding:6px 10px;font-size:12px}
    .seg button+button{border-left:1px solid var(--chrome-dark)}

    .content{display:grid;grid-template-columns:220px 1fr;min-height:420px}
    .sidebar{background:linear-gradient(#f5f5f9,#ececf2);border-right:1px solid rgba(0,0,0,.08);padding:12px}
    .side-h{font-size:11px;color:#556;letter-spacing:.4px;margin:14px 8px 6px;text-transform:uppercase}
    .nav{list-style:none;padding:0;margin:0}
    .nav a{display:flex;align-items:center;gap:8px;padding:8px 10px;border-radius:6px;color:#223;text-decoration:none;font-size:14px}
    .nav a:hover{background:#e9eefc}
    .nav a.active{background:#dce9ff;border:1px solid #c7dafc}
    .nav .icon{width:16px;height:16px;opacity:.9}

    .main{padding:18px 22px 28px}
    .title{font-size:20px;font-weight:600;margin:6px 0 12px}
    .lead{color:var(--muted);line-height:1.5;margin:0 0 18px;font-size:15px}

    .card{
      border:1px solid rgba(0,0,0,.08); border-radius:10px; padding:16px; background:#fff;
      box-shadow:0 1px 0 rgba(255,255,255,.8) inset, 0 14px 30px rgba(0,0,0,.08);
      margin:12px 0;
    }
    .card h3{margin:0 0 8px;font-size:16px}
    .meta{color:#555; font-size:13px; margin-top:6px}

    .toolbar .search{margin-left:auto}
    .search input{border:1px solid var(--chrome-dark);border-radius:20px;padding:6px 10px;font-size:12px;min-width:200px; box-shadow:0 1px 0 #fff inset}

    .btn{
      display:inline-flex;align-items:center;gap:8px; padding:8px 12px;border-radius:8px;border:1px solid #bfc7d8;
      background:linear-gradient(#fefefe,#e9edf6); cursor:pointer; font-size:14px; text-decoration:none; color:#123;
      box-shadow:0 1px 0 #fff inset, 0 2px 0 rgba(0,0,0,.04);
    }
    .btn:hover{background:linear-gradient(#fff,#eef3ff)}

    .dock{
      position:fixed;left:50%;transform:translateX(-50%);bottom:10px;z-index:30; display:flex; gap:14px;
      padding:8px 18px;border-radius:16px;background:linear-gradient(180deg, rgba(255,255,255,.55), rgba(255,255,255,.28));
      box-shadow:0 20px 60px rgba(0,0,0,.35), inset 0 1px 0 rgba(255,255,255,.8); backdrop-filter: blur(8px) saturate(1.2);
      border:1px solid rgba(255,255,255,.6);
    }
    .dock a{display:block; width:52px; height:52px; border-radius:12px; background:#fff; box-shadow:0 3px 0 rgba(0,0,0,.15);
      position:relative; text-decoration:none}
    .dock a span{position:absolute; left:50%; transform:translateX(-50%); bottom:64px; background:rgba(0,0,0,.8); color:#fff; font-size:11px; padding:4px 8px; border-radius:6px; opacity:0; pointer-events:none; transition:.15s}
    .dock a:hover span{opacity:1}
    .dock img{width:100%; height:100%; border-radius:12px}

    .footer{color:#cfd7ec; text-align:center; font-size:12px; margin:18px 0 80px;}

    /* tiny responsive tweak */
    @media (max-width: 720px){
      .content{grid-template-columns:1fr}
      .sidebar{border-right:0;border-bottom:1px solid rgba(0,0,0,.08)}
    }
  </style>
</head>
<body>
  <!-- Menu bar -->
  <div class="menu-bar">
    <div class="menu-apple"></div>
    <div class="menu-item"><strong>Finder</strong></div>
    <div class="menu-item">File</div>
    <div class="menu-item">Edit</div>
    <div class="menu-item">View</div>
    <div class="menu-item">Go</div>
    <div class="menu-item">Window</div>
    <div class="menu-item">Help</div>
  </div>

  <main class="desktop" id="desktop">
    <!-- Main window -->
    <section class="window" role="region" aria-label="Profile window">
      <div class="traffic" aria-hidden="true">
        <div class="dot red" title="Close"></div>
        <div class="dot yellow" title="Minimize"></div>
        <div class="dot green" title="Zoom"></div>
      </div>
      <div class="toolbar">
        <div class="seg" role="tablist" aria-label="Sections">
          <button role="tab" data-section="about" aria-selected="true">About</button>
          <button role="tab" data-section="work">Work</button>
          <button role="tab" data-section="contact">Contact</button>
        </div>
        <div class="search">
          <input id="search" type="search" placeholder="Search in window" aria-label="Search" />
        </div>
      </div>
      <div class="content">
        <aside class="sidebar">
          <div class="side-h">Places</div>
          <nav>
            <ul class="nav">
              <li><a href="#about" class="active" data-section="about"><svg class="icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M12 2a7 7 0 100 14 7 7 0 000-14zm0 16c-4.418 0-8 2.239-8 5 0 1.104.896 1 2 12c1.104 0 2 .104 2-1 0-2.761-3.582-5-8-5z"/></svg> About Me</a></li>
              <li><a href="#work" data-section="work"><svg class="icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M9 2h6a2 2 0 012 2v2h3a2 2 0 012 2v2H2V8a2 2 0 012-2h3V4a2 2 0 012-2zm8 6H7V40v4zM2 12h22v8a2 2 0 01-2 2H4a2 2 0 01-2-2v-8z"/></svg> Projects</a></li>
              <li><a href="#contact" data-section="contact"><svg class="icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M12 12a5 5 0 100-10 5 5 0 000 10zm-9 9a9 9 0 1118 0H3z"/></svg> Contact</a></li>
            </ul>
          </nav>
        </aside>
        <section class="main" id="panel">
          <!-- About -->
          <div class="view" data-view="about">
            <h1 class="title">Tenho Saavedra</h1>
            <p class="lead">Project manager who enjoys turning messy ideas into clean, shippable plans. I work across product, people, and process to make teams fast, sane, and customer‑focused.</p>
            <div class="card">
              <h3>Snapshot</h3>
              <ul>
                <li>🏷️ Role: Project Manager / Business development / Product and service development</li>
                <li>🧭 Strengths: scope shaping, risk tracking, stakeholder comms, data‑informed prioritization</li>
                <li>🛠 Tooling: Atlassian Suite & homebrew</li>
                <li>🤖 Interests: Products, business and Scuba</li>
              </ul>
            </div>
            <div class="card">
              <h3>CV / Resume</h3>
              <p class="meta">Grab the latest copy as a PDF. Replace the file at <code>assets/Tenho_Saavedra_CV.pdf</code> when you deploy.</p>
              <a class="btn" href="assets/Tenho_Saavedra_CV.pdf" download>
                <!-- simple floppy icon -->
                <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M20 7v12a3 3 0 01-3 3H7a3 3 0 01-3-3V5a3 3 0 013-3h9l4 5zM7 4v6h8V4H7zm5 12H7v3h5v-3z"/></svg>
                Download my CV (PDF)
              </a>
            </div>
          </div>

          <!-- Work -->
          <div class="view" data-view="work" hidden>
            <h2 class="title">Selected Projects</h2>
            <div class="card">
              <h3>Delivery Operating Model Refresh</h3>
              <p>Redesigned team ceremonies and definition of done across three squads, improving lead time by 22% over two quarters.</p>
              <p class="meta">Methods: value stream mapping, WIP limits, Monte Carlo forecasting.</p>
            </div>
            <div class="card">
              <h3>Customer Portal Rollout</h3>
              <p>Coordinated cross‑functional release of a self‑service portal; drove cutover plan, risk register, and stakeholder updates.</p>
              <p class="meta">Outcome: 38% reduction in support tickets in 60 days.</p>
            </div>
          </div>

          <!-- Contact -->
          <div class="view" data-view="contact" hidden>
            <h2 class="title">Contact</h2>
            <div class="card">
              <p>Best way to reach me: <a href="mailto:tenhosaavedra@gmail.com">tenhosaavedra (@) gmail.com</a></p>
              <p class="meta">I’m open to interesting collaborations and hard problems with friendly people.</p>
            </div>
            <div class="card">
              <h3>Elsewhere</h3>
               <ul>
                
  <a href="https://www.linkedin.com/in/tenhosaavedra/" target="_blank" rel="noopener noreferrer" style="display: inline-flex; align-items: center; gap: 6px; text-decoration: none;">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="#0A66C2">
      <path d="M19 0h-14c-2.76 0-5 2.24-5 
               5v14c0 2.76 2.24 5 5 
               54c2.76 0 5-2.24 
               5-5v-14c0-2.76-2.24-5-5-5zm-11 
               19h-3v-10h3v10zm-1.5-11.29c-.96 
               0-1.75-.79-1.75-1.75s.79-1.75 
               1.75-1.75 1.75.79 
               1.75 1.75-.79 1.75-1.75 
               1.75zm13.5 11.29h-3v-5.6c0-1.34-.03-3.07-1.87-3.07-1.87 
               0-2.16 1.46-2.16 2.97v5.7h-3v-10h2.88v1.37h.04c.4-.75 
               1.38-1.54 2.84-1.54 3.04 0 3.6 
               2 3.6 4.59v5.58z"/>
    </svg>
    <span style="color:#0A66C2; font-weight:600;">LinkedIn</span>
  </a>

                <!-- <li>GitHub — <a href="#" aria-disabled="true" onclick="alert('Replace with your profile URL'); return false;">Add your link</a></li> -->
              </ul>
            </div>
          </div>
        </section>
      </div>
    </section>

    
  </main>

  <!-- Dock -->
  <nav class="dock" aria-label="Dock">
    <a href="#about" data-section="about" title="About"><span>About</span><img alt="About icon" src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='64' height='64' viewBox='0 0 24 24'><rect width='24' height='24' rx='6' fill='%23dbe5ff'/><path d='M12 12a5 5 0 100-10 5 5 0 000 10zm-9 9a9 9 0 1118 0H3z' fill='%23224477'/></svg>" /></a>
    <a href="#work" data-section="work" title="Work"><span>Work</span><img alt="Work icon" src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='64' height='64' viewBox='0 0 24 24'><rect width='24' height='24' rx='6' fill='%23e7f7ef'/><path d='M9 2h6a2 2 0 012 2v2h3a2 2 0 012 2v2H2V8a2 2 0 012-2h3V4a2 2 0 012-2zm8 6H7V40v4zM2 12h22v8a2 2 0 01-2 2H4a2 2 0 01-2-2v-8z' fill='%231b6f42'/></svg>" /></a>
    <a href="#contact" data-section="contact" title="Contact"><span>Contact</span><img alt="Contact icon" src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='64' height='64' viewBox='0 0 24 24'><rect width='24' height='24' rx='6' fill='%23ffe9e9'/><path d='M12 12a5 5 0 100-10 5 5 0 000 10zm-9 9a9 9 0 1118 0H3z' fill='%239c2a2a'/></svg>" /></a>
    <a href="#" title="Download CV" onclick="document.querySelector('[href^=\'assets/\']').click(); return false;">
      <span>Download CV</span>
      <img alt="CV icon" src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='64' height='64' viewBox='0 0 24 24'><rect width='24' height='24' rx='6' fill='%23fff8e1'/><path d='M6 2h9l5 5v13a2 2 0 01-2 2H6a2 2 0 01-2-2V4a2 2 0 012-2zm7 0v5h5' fill='%238a6d00'/><path d='M12 12v6m0 0l-3-3m3 3l3-3' stroke='%238a6d00' stroke-width='1.5' fill='none' stroke-linecap='round' stroke-linejoin='round'/></svg>" /></a>
  </nav>

  <script>
    // simple tab + nav sync and in-window search
    const views = [...document.querySelectorAll('.view')];
    const tabButtons = [...document.querySelectorAll('[data-section]')];
    function show(section){
      views.forEach(v=>{ v.hidden = v.dataset.view !== section; });
      document.querySelectorAll('.nav a').forEach(a=>{
        a.classList.toggle('active', a.dataset.section === section);
      });
      window.location.hash = section;
    }
    tabButtons.forEach(b=>{
      b.addEventListener('click', (e)=>{
        const sec = e.currentTarget.dataset.section;
        if(sec) show(sec);
      });
    });
    // hash routing
    const initial = (location.hash || '#about').replace('#','');
    show(initial);

    // In-window search filter (very lightweight)
    const search = document.getElementById('search');
    search.addEventListener('input', (e)=>{
      const q = e.target.value.trim().toLowerCase();
      const active = views.find(v=>!v.hidden);
      [...active.querySelectorAll('.card, .lead, .title, li, p, h3')].forEach(el=>{
        const match = el.textContent.toLowerCase().includes(q);
        el.style.display = q && !match && el.className.includes('card') ? 'none' : '';
      });
    });
  </script>
</body>
</html>
