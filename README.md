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
  <!-- Replace the favicon below with your custom favicon file -->
  <link rel="icon" type="image/png" href="/favicon.png">

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
  ... (rest of the file unchanged) ...
