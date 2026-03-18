<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Myrna & Tenho — 25.04.2026</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@200;300;400&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --cream: #f2f1ea;
      --warm-white: #f6f5ee;
      --gold: #7a7d3a;        /* olive — main accent */
      --gold-light: #a4a760;  /* lighter olive */
      --dark: #252410;        /* deep olive-black */
      --brown: #4a4a1e;       /* dark olive for body text */
      --blush: #e8cdd2;       /* rose blush for photo bg */
      --env: #d4d5a0;         /* olive envelope body */
      --env-dark: #b8ba78;    /* deeper olive fold */
      --env-shadow: #9a9c58;  /* shadow fold */
      --burgundy: #6e2535;    /* burgundy/wine */
      --rose: #b8707a;        /* medium rose */
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--cream);
      color: var(--dark);
      font-family: 'Jost', sans-serif;
      font-weight: 300;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 9999;
      opacity: 0.6;
    }

    /* ═══════════════════════════════
       ENVELOPE SCREEN
    ═══════════════════════════════ */
    #envelope-screen {
      position: fixed;
      inset: 0;
      z-index: 500;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 0;
      background:
        radial-gradient(ellipse 100% 70% at 50% 120%, rgba(122,125,58,0.2) 0%, transparent 60%),
        radial-gradient(ellipse 60% 40% at 15% 10%, rgba(110,37,53,0.07) 0%, transparent 50%),
        var(--warm-white);
      transition: opacity 0.9s ease, visibility 0.9s ease;
    }

    #envelope-screen.hidden {
      opacity: 0;
      visibility: hidden;
      pointer-events: none;
    }

    .env-intro {
      font-size: 0.7rem;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      color: var(--brown);
      font-weight: 400;
      margin-bottom: 3.5rem;
      opacity: 0;
      animation: fadeUp 1s 0.8s ease forwards;
    }

    /* ── SCENE — padding-top creates the space photos slide up into ── */
    .env-scene {
      position: relative;
      width: min(400px, 86vw);
      padding-top: min(260px, 56vw);
      cursor: pointer;
      opacity: 0;
      animation: fadeUp 1.4s 0.3s cubic-bezier(0.16,1,0.3,1) forwards;
    }

    /* ── PHOTOS — absolutely positioned in the padding area above the envelope ── */
    .photos-row {
      position: absolute;
      top: 0;
      left: 0; right: 0;
      height: min(260px, 56vw);
      display: flex;
      gap: 10px;
      justify-content: center;
      align-items: flex-end;
      padding: 0 8px 16px;
      /* start: tucked below, hidden behind the envelope top edge */
      transform: translateY(85%);
      opacity: 0;
      transition:
        transform 1s cubic-bezier(0.34, 1.2, 0.64, 1) 0.4s,
        opacity   0.01s linear 0.4s; /* snap visible the moment motion starts */
    }

    .photos-row.risen {
      transform: translateY(0);
      opacity: 1;
    }

    .photo-card {
      flex: 1;
      max-width: 32%;
      aspect-ratio: 3 / 4;
      border-radius: 3px;
      overflow: hidden;
      border: 4px solid white;
      background: var(--blush);
      box-shadow: 0 10px 28px rgba(26,22,18,0.28);
    }

    .photo-card:nth-child(1) { transform: rotate(-5deg); }
    .photo-card:nth-child(2) { transform: rotate(0deg);  }
    .photo-card:nth-child(3) { transform: rotate(5deg);  }

    .photo-card img { width: 100%; height: 100%; object-fit: cover; display: block; }

    .photo-placeholder {
      width: 100%; height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
      background: linear-gradient(145deg, #e8d0d4, #c9a0aa);
      color: var(--brown);
    }

    .photo-placeholder svg { width: 26px; height: 26px; fill: var(--brown); opacity: 0.35; }

    .photo-placeholder span {
      font-size: 0.52rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      opacity: 0.5;
      text-align: center;
      padding: 0 0.4rem;
    }

    /* ── ENVELOPE BOX ── */
    .envelope-box {
      position: relative;
      width: 100%;
    }

    .envelope-box svg {
      width: 100%;
      height: auto;
      display: block;
      filter: drop-shadow(0 22px 48px rgba(26,22,18,0.22)) drop-shadow(0 6px 14px rgba(26,22,18,0.12));
    }

    /* ── PROMPT ── */
    .env-prompt {
      margin-top: 2.8rem;
      text-align: center;
      opacity: 0;
      animation: fadeIn 1s 2s ease forwards;
      transition: opacity 0.3s ease;
    }

    .env-prompt.hide { opacity: 0 !important; pointer-events: none; }

    .env-prompt span {
      font-size: 0.65rem;
      letter-spacing: 0.28em;
      text-transform: uppercase;
      color: var(--brown);
      font-weight: 400;
    }

    .dot-pulse {
      display: inline-block;
      width: 5px; height: 5px;
      border-radius: 50%;
      background: var(--burgundy);
      margin: 0 0.5rem;
      vertical-align: middle;
      animation: pulseDot 1.6s 2s ease-in-out infinite;
    }

    /* ── SCROLL CTA ── */
    .scroll-cta {
      margin-top: 2rem;
      text-align: center;
      opacity: 0;
      transform: translateY(12px);
      transition: opacity 0.7s ease, transform 0.7s ease;
      pointer-events: none;
    }

    .scroll-cta.show {
      opacity: 1;
      transform: translateY(0);
      pointer-events: auto;
    }

    .scroll-cta button {
      background: none;
      border: 1px solid var(--burgundy);
      color: var(--burgundy);
      font-family: 'Jost', sans-serif;
      font-size: 0.65rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      padding: 0.8rem 2rem;
      cursor: pointer;
      font-weight: 400;
      transition: background 0.3s, color 0.3s;
    }

    .scroll-cta button:hover {
      background: var(--burgundy);
      color: var(--warm-white);
    }

    /* ═══════════════════════════════
       MAIN CONTENT
    ═══════════════════════════════ */
    #main-content {
      visibility: hidden;
      opacity: 0;
      transition: opacity 0.8s ease;
    }

    #main-content.visible {
      visibility: visible;
      opacity: 1;
    }

    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      position: relative;
      padding: 4rem 2rem;
      overflow: hidden;
    }

    .hero-bg {
      position: absolute;
      inset: 0;
      background:
        radial-gradient(ellipse 80% 60% at 50% 110%, rgba(122,125,58,0.15) 0%, transparent 60%),
        radial-gradient(ellipse 60% 40% at 20% 20%, rgba(110,37,53,0.07) 0%, transparent 50%),
        var(--warm-white);
    }

    .hero-bg::before {
      content: '';
      position: absolute;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg width='400' height='600' viewBox='0 0 400 600' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' stroke='%237a7d3a' stroke-width='0.8' opacity='0.3'%3E%3Cpath d='M50 600 Q80 400 60 200 Q40 100 80 0'/%3E%3Cpath d='M60 500 Q30 450 10 380'/%3E%3Cpath d='M65 420 Q90 380 70 330'/%3E%3Cpath d='M58 350 Q20 310 30 260'/%3E%3Cpath d='M63 280 Q95 250 75 200'/%3E%3Cellipse cx='15' cy='370' rx='18' ry='12' transform='rotate(-20 15 370)'/%3E%3Cellipse cx='88' cy='320' rx='22' ry='14' transform='rotate(15 88 320)'/%3E%3Cellipse cx='22' cy='250' rx='16' ry='10' transform='rotate(-30 22 250)'/%3E%3Cellipse cx='92' cy='195' rx='20' ry='13' transform='rotate(10 92 195)'/%3E%3C/g%3E%3C/svg%3E");
      background-repeat: no-repeat;
      background-position: left bottom;
      background-size: 280px auto;
    }

    .hero-bg::after {
      content: '';
      position: absolute;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg width='400' height='600' viewBox='0 0 400 600' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' stroke='%237a7d3a' stroke-width='0.8' opacity='0.3'%3E%3Cpath d='M350 600 Q320 400 340 200 Q360 100 320 0'/%3E%3Cpath d='M340 500 Q370 450 390 380'/%3E%3Cpath d='M335 420 Q310 380 330 330'/%3E%3Cpath d='M342 350 Q380 310 370 260'/%3E%3Cellipse cx='385' cy='370' rx='18' ry='12' transform='rotate(20 385 370)'/%3E%3Cellipse cx='312' cy='320' rx='22' ry='14' transform='rotate(-15 312 320)'/%3E%3Cellipse cx='378' cy='250' rx='16' ry='10' transform='rotate(30 378 250)'/%3E%3Cellipse cx='308' cy='195' rx='20' ry='13' transform='rotate(-10 308 195)'/%3E%3C/g%3E%3C/svg%3E");
      background-repeat: no-repeat;
      background-position: right bottom;
      background-size: 280px auto;
    }

    .hero-content { position: relative; text-align: center; }

    .pre-title {
      font-weight: 400;
      font-size: 0.72rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--brown);
      margin-bottom: 2rem;
      opacity: 0;
      animation: fadeUp 1s 0.3s cubic-bezier(0.16,1,0.3,1) forwards;
    }

    .divider-line {
      width: 60px; height: 1px;
      background: var(--gold);
      margin: 0 auto 2rem;
      opacity: 0;
      animation: expand 1s 0.5s ease forwards;
    }

    .names {
      font-family: 'Cormorant Garamond', serif;
      font-weight: 300;
      font-style: italic;
      font-size: clamp(3rem, 9vw, 6.5rem);
      line-height: 1.1;
      color: var(--dark);
      margin-bottom: 1.2rem;
      opacity: 0;
      animation: fadeUp 1.2s 0.6s cubic-bezier(0.16,1,0.3,1) forwards;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .ampersand {
      color: var(--burgundy);
      font-size: 0.72em;
      line-height: 1;
      display: block;
      text-align: center;
      width: 100%;
    }

    .date-block {
      margin: 2.5rem auto;
      opacity: 0;
      animation: fadeUp 1s 0.9s ease forwards;
    }

    .date-text {
      font-weight: 200;
      font-size: 0.75rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--brown);
    }

    .date-number {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 5vw, 3.2rem);
      font-weight: 300;
      color: var(--dark);
      letter-spacing: 0.08em;
      line-height: 1.2;
    }

    .scroll-hint {
      position: absolute;
      bottom: 2.5rem;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.5rem;
      opacity: 0;
      animation: fadeIn 1s 2s ease forwards;
    }

    .scroll-hint span {
      font-size: 0.65rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--brown);
      font-weight: 400;
    }

    .scroll-arrow {
      width: 1px; height: 40px;
      background: linear-gradient(to bottom, var(--gold), transparent);
      animation: scrollPulse 2s 2s ease-in-out infinite;
    }

    section {
      padding: 6rem 2rem;
      max-width: 760px;
      margin: 0 auto;
    }

    .section-label {
      font-size: 0.68rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--brown);
      font-weight: 400;
      margin-bottom: 1rem;
    }

    .ornament {
      width: 40px; height: 1px;
      background: var(--gold);
      display: inline-block;
      vertical-align: middle;
      margin: 0 1rem;
    }

    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-weight: 300;
      font-style: italic;
      font-size: clamp(2rem, 5vw, 3rem);
      color: var(--dark);
      margin-bottom: 1.5rem;
      line-height: 1.2;
    }

    .body-text {
      font-size: 0.95rem;
      line-height: 1.9;
      color: var(--brown);
      font-weight: 300;
    }

    .sep {
      text-align: center;
      padding: 1rem 0;
      color: var(--gold);
      font-size: 1.2rem;
      letter-spacing: 0.5em;
      opacity: 0.6;
    }

    .details-section {
      background: #272610;
      color: var(--cream);
      padding: 6rem 2rem;
    }

    .details-inner { max-width: 760px; margin: 0 auto; }

    .details-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
      margin-top: 3rem;
    }

    @media (max-width: 560px) {
      .details-grid { grid-template-columns: 1fr; gap: 2rem; }
    }

    .detail-card { border-top: 1px solid rgba(122,125,58,0.4); padding-top: 1.5rem; }
    .detail-card .label { font-size: 0.62rem; letter-spacing: 0.32em; text-transform: uppercase; color: var(--gold-light); font-weight: 400; margin-bottom: 0.6rem; }
    .detail-card .value { font-family: 'Cormorant Garamond', serif; font-size: 1.5rem; font-weight: 300; font-style: italic; line-height: 1.3; color: var(--cream); }
    .detail-card .sub { font-size: 0.8rem; color: rgba(240,243,239,0.5); margin-top: 0.4rem; line-height: 1.6; }

    .time-row {
      display: flex;
      align-items: baseline;
      gap: 0.8rem;
      margin-top: 0.9rem;
    }
    .time-row + .time-row { margin-top: 0.5rem; }
    .time-hour {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.3rem;
      font-weight: 300;
      font-style: italic;
      color: var(--cream);
      white-space: nowrap;
    }
    .time-desc {
      font-size: 0.75rem;
      color: rgba(240,243,239,0.55);
      line-height: 1.4;
    }

    .map-btn {
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      margin-top: 1rem;
      padding: 0.6rem 1.4rem;
      border: 1px solid var(--gold);
      color: var(--gold);
      text-decoration: none;
      font-size: 0.65rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      transition: all 0.3s ease;
      font-weight: 300;
    }

    .map-btn:hover { background: var(--gold); color: var(--dark); }
    .map-btn svg { width: 14px; height: 14px; fill: currentColor; }

    .location-block { margin-top: 1.6rem; }
    .location-block:first-of-type { margin-top: 1rem; }

    .venue-tag {
      font-size: 0.58rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--gold);
      font-weight: 400;
      margin-bottom: 0.35rem;
    }

    .venue-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.25rem;
      font-weight: 300;
      font-style: italic;
      color: var(--cream);
      line-height: 1.3;
    }

    .venue-divider {
      width: 100%;
      height: 1px;
      background: rgba(122,125,58,0.25);
      margin: 1.4rem 0;
    }

    .countdown-section {
      text-align: center;
      padding: 6rem 2rem;
      background: var(--warm-white);
    }

    .countdown-inner { max-width: 760px; margin: 0 auto; }

    .countdown-grid {
      display: flex;
      justify-content: center;
      gap: clamp(1.5rem, 5vw, 4rem);
      margin-top: 3rem;
      flex-wrap: wrap;
    }

    .count-item { display: flex; flex-direction: column; align-items: center; gap: 0.4rem; }

    .count-number {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3rem, 8vw, 5rem);
      font-weight: 300;
      color: var(--dark);
      line-height: 1;
      min-width: 2ch;
    }

    .count-label { font-size: 0.62rem; letter-spacing: 0.25em; text-transform: uppercase; color: var(--brown); font-weight: 400; }
    .count-dot { font-family: 'Cormorant Garamond', serif; font-size: 3rem; color: var(--gold-light); align-self: center; line-height: 1; margin-top: -0.5rem; }

    .closing { text-align: center; padding: 6rem 2rem 8rem; }

    /* ── RSVP ── */
    .rsvp-section {
      padding: 6rem 2rem;
      background: var(--warm-white);
      text-align: center;
    }

    .rsvp-inner {
      max-width: 680px;
      margin: 0 auto;
    }

    .rsvp-frame-wrap {
      margin-top: 0;
      border-radius: 6px;
      overflow: hidden;
    }

    .rsvp-frame-wrap iframe {
      display: block;
      width: 100%;
      border: none;
      border-radius: 6px;
      box-shadow: 0 8px 32px rgba(26,22,18,0.1);
    }

    .rsvp-placeholder {
      background: var(--cream);
      border: 1px dashed rgba(122,125,58,0.4);
      border-radius: 6px;
      padding: 3.5rem 2rem;
      color: var(--brown);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1rem;
    }

    .rsvp-placeholder svg { opacity: 0.3; }

    .rsvp-placeholder-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.3rem;
      font-style: italic;
      font-weight: 300;
      color: var(--dark);
    }

    .rsvp-placeholder-sub {
      font-size: 0.8rem;
      line-height: 1.7;
      color: var(--brown);
      opacity: 0.6;
      max-width: 420px;
    }



    .closing-quote {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1.3rem, 3vw, 1.8rem);
      font-weight: 300;
      font-style: italic;
      color: var(--brown);
      line-height: 1.7;
      max-width: 500px;
      margin: 0 auto 2.5rem;
    }

    .closing-names { font-family: 'Cormorant Garamond', serif; font-size: clamp(1.8rem, 4vw, 2.6rem); font-weight: 300; color: var(--dark); }
    .closing-date { font-size: 0.72rem; letter-spacing: 0.3em; text-transform: uppercase; color: var(--brown); font-weight: 400; margin-top: 1rem; }
    .floral-center { margin: 2rem auto; opacity: 0.5; }

    footer {
      background: #272610;
      color: rgba(240,243,239,0.3);
      text-align: center;
      padding: 2rem;
      font-size: 0.65rem;
      letter-spacing: 0.15em;
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeIn {
      from { opacity: 0; } to { opacity: 1; }
    }
    @keyframes expand {
      from { opacity: 0; width: 0; } to { opacity: 1; width: 60px; }
    }
    @keyframes scrollPulse {
      0%, 100% { opacity: 0.3; } 50% { opacity: 1; }
    }
    @keyframes pulseDot {
      0%, 100% { opacity: 0.35; transform: scale(1); }
      50%       { opacity: 1;   transform: scale(1.5); }
    }
    @keyframes wobble {
      0%,100% { transform: translateY(0) rotate(0); }
      25%      { transform: translateY(-4px) rotate(-1deg); }
      75%      { transform: translateY(-2px) rotate(1deg); }
    }

    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.9s ease, transform 0.9s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }
  </style>
</head>
<body>

<!-- ═════════════════════════════════
     ENVELOPE SCREEN
═════════════════════════════════ -->
<div id="envelope-screen">

  <p class="env-intro">Tu invitación de boda</p>

  <div class="env-scene" id="envScene">

    <!-- Envelope: body + photos + flap all stacked by z-index -->
    <!-- Photos slide up from behind envelope on open -->
    <div class="photos-row" id="photosRow">
      <div class="photo-card">
        <!--★ FOTO 1 — reemplaza con: <img src="foto1.jpg" alt="Myrna y Tenho"> -->
        <div class="photo-placeholder">
          <svg viewBox="0 0 24 24"><path d="M21 19V5c0-1.1-.9-2-2-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2zM8.5 13.5l2.5 3.01L14.5 12l4.5 6H5l3.5-4.5z"/></svg>
          <span>Foto 1</span>
        </div>
      </div>
      <div class="photo-card">
        <!--★ FOTO 2 — reemplaza con: <img src="foto2.jpg" alt="Myrna y Tenho"> -->
        <div class="photo-placeholder">
          <svg viewBox="0 0 24 24"><path d="M21 19V5c0-1.1-.9-2-2-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2zM8.5 13.5l2.5 3.01L14.5 12l4.5 6H5l3.5-4.5z"/></svg>
          <span>Foto 2</span>
        </div>
      </div>
      <div class="photo-card">
        <!--★ FOTO 3 — reemplaza con: <img src="foto3.jpg" alt="Myrna y Tenho"> -->
        <div class="photo-placeholder">
          <svg viewBox="0 0 24 24"><path d="M21 19V5c0-1.1-.9-2-2-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2zM8.5 13.5l2.5 3.01L14.5 12l4.5 6H5l3.5-4.5z"/></svg>
          <span>Foto 3</span>
        </div>
      </div>
    </div>

    <div class="envelope-box">
      <!--
        SVG envelope — 500 x 309 viewBox (golden ratio).
        All shading done with SVG gradients to simulate real paper folds.
        No filters, no grain — pure geometry and light.
      -->
      <svg viewBox="0 0 500 309" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <defs>
          <!-- Ivory paper base gradient: warm light top-left, slight amber shadow bottom-right -->
          <linearGradient id="paperBase" x1="0%" y1="0%" x2="100%" y2="100%">
            <stop offset="0%"   stop-color="#faf5e8"/>
            <stop offset="40%"  stop-color="#f5edda"/>
            <stop offset="100%" stop-color="#e8dcc4"/>
          </linearGradient>

          <!-- Left side flap shading -->
          <linearGradient id="leftFlap" x1="0%" y1="0%" x2="100%" y2="0%">
            <stop offset="0%"   stop-color="#ddd0b0" stop-opacity="0.7"/>
            <stop offset="100%" stop-color="#f5edda" stop-opacity="0"/>
          </linearGradient>

          <!-- Right side flap shading -->
          <linearGradient id="rightFlap" x1="100%" y1="0%" x2="0%" y2="0%">
            <stop offset="0%"   stop-color="#ddd0b0" stop-opacity="0.65"/>
            <stop offset="100%" stop-color="#f5edda" stop-opacity="0"/>
          </linearGradient>

          <!-- Bottom flap: darker crease near fold point -->
          <linearGradient id="bottomFlap" x1="50%" y1="0%" x2="50%" y2="100%">
            <stop offset="0%"   stop-color="#c8b88a" stop-opacity="0.5"/>
            <stop offset="60%"  stop-color="#e0d4b4" stop-opacity="0.3"/>
            <stop offset="100%" stop-color="#f0e8d0" stop-opacity="0.1"/>
          </linearGradient>

          <!-- Top flap (closed): warm ivory slightly cooler than body -->
          <linearGradient id="topFlap" x1="50%" y1="0%" x2="50%" y2="100%">
            <stop offset="0%"   stop-color="#f8f2e2"/>
            <stop offset="100%" stop-color="#e8dcc6"/>
          </linearGradient>

          <!-- Crease highlight: thin bright line at fold edges -->
          <linearGradient id="creaseH" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="0%"   stop-color="#ffffff" stop-opacity="0.8"/>
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0"/>
          </linearGradient>

          <!-- Soft inner shadow below top flap fold -->
          <linearGradient id="innerShadow" x1="50%" y1="0%" x2="50%" y2="100%">
            <stop offset="0%"   stop-color="#b8a878" stop-opacity="0.35"/>
            <stop offset="100%" stop-color="#b8a878" stop-opacity="0"/>
          </linearGradient>

          <!-- Wax seal radial gradient -->
          <radialGradient id="sealGrad" cx="38%" cy="32%" r="60%">
            <stop offset="0%"   stop-color="#a83a4a"/>
            <stop offset="100%" stop-color="#4a1520"/>
          </radialGradient>
        </defs>

        <!-- ① BASE: full envelope rectangle — ivory paper -->
        <rect x="0" y="0" width="500" height="309" rx="5" ry="5" fill="url(#paperBase)"/>

        <!-- ② LEFT SIDE FLAP SHADOW (triangle from top-left & bottom-left to center) -->
        <polygon points="0,0 0,309 250,154" fill="url(#leftFlap)"/>

        <!-- ③ RIGHT SIDE FLAP SHADOW -->
        <polygon points="500,0 500,309 250,154" fill="url(#rightFlap)"/>

        <!-- ④ BOTTOM FLAP (folds up from bottom center) — slightly warm -->
        <polygon points="0,309 500,309 250,154" fill="#ede2c4"/>
        <!-- Bottom flap inner shading — crease near center point -->
        <polygon points="0,309 500,309 250,154" fill="url(#bottomFlap)"/>

        <!-- ⑤ FOLD LINES: diagonal from corners to center — crisp paper crease -->
        <!-- Left fold line -->
        <line x1="0" y1="0"   x2="250" y2="154" stroke="#c4b48c" stroke-width="0.7" opacity="0.6"/>
        <line x1="0" y1="309" x2="250" y2="154" stroke="#c4b48c" stroke-width="0.7" opacity="0.6"/>
        <!-- Right fold line -->
        <line x1="500" y1="0"   x2="250" y2="154" stroke="#c4b48c" stroke-width="0.7" opacity="0.6"/>
        <line x1="500" y1="309" x2="250" y2="154" stroke="#c4b48c" stroke-width="0.7" opacity="0.6"/>

        <!-- ⑥ TOP FLAP (closed, pointing down) — slightly different ivory tone -->
        <polygon points="0,0 500,0 250,168" fill="url(#topFlap)"/>
        <!-- Top flap subtle edge shadow to separate it from body -->
        <polygon points="0,0 500,0 250,168" fill="url(#innerShadow)" opacity="0.5"/>

        <!-- ⑦ CREASE HIGHLIGHT on top flap fold edge — thin bright line -->
        <line x1="0" y1="0" x2="250" y2="168" stroke="rgba(255,255,255,0.55)" stroke-width="1"/>
        <line x1="500" y1="0" x2="250" y2="168" stroke="rgba(255,255,255,0.55)" stroke-width="1"/>

        <!-- ⑧ TOP FLAP BOTTOM EDGE — subtle shadow line where flap meets body -->
        <line x1="0" y1="0" x2="250" y2="168" stroke="#b8a470" stroke-width="0.8" opacity="0.4"/>
        <line x1="500" y1="0" x2="250" y2="168" stroke="#b8a470" stroke-width="0.8" opacity="0.4"/>

        <!-- ⑨ OUTER BORDER — subtle edge definition -->
        <rect x="0.5" y="0.5" width="499" height="308" rx="4.5" ry="4.5" fill="none" stroke="#c8b888" stroke-width="0.8" opacity="0.5"/>

        <!-- ⑩ WAX SEAL — centered on flap meeting point -->
        <g id="svgSeal" style="transition: opacity 0.4s ease;">
        <circle cx="250" cy="154" r="38" fill="url(#sealGrad)"/>
        <!-- Seal inner ring -->
        <circle cx="250" cy="154" r="31" fill="none" stroke="rgba(255,230,200,0.2)" stroke-width="1"/>
        <!-- Seal highlight -->
        <ellipse cx="240" cy="144" rx="12" ry="8" fill="rgba(255,255,255,0.12)" transform="rotate(-20,240,144)"/>
        <!-- Seal monogram -->
        <text x="250" y="161"
          font-family="'Cormorant Garamond', Georgia, serif"
          font-size="22"
          font-style="italic"
          font-weight="400"
          fill="rgba(255,238,215,0.92)"
          text-anchor="middle"
          letter-spacing="-1">M&amp;T</text>
        </g>
      </svg>
    </div>

  </div><!-- /.env-scene -->

  <!-- Prompt -->
  <div class="env-prompt" id="envPrompt">
    <span><span class="dot-pulse"></span>Toca para abrir<span class="dot-pulse"></span></span>
  </div>

  <!-- Scroll CTA -->
  <div class="scroll-cta" id="scrollCta">
    <button onclick="revealMain()">Ver la invitación completa</button>
  </div>

</div><!-- /#envelope-screen -->


<!-- ═════════════════════════════════
     MAIN CONTENT
═════════════════════════════════ -->
<div id="main-content">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-bg"></div>
    <div class="hero-content">
      <p class="pre-title">Nos casamos</p>
      <div class="divider-line"></div>
      <h1 class="names">
        <span>Myrna</span>
        <span class="ampersand">&amp;</span>
        <span>Tenho</span>
      </h1>
      <div class="date-block">
        <p class="date-text">Sábado</p>
        <p class="date-number">25 · 04 · 2026</p>
      </div>
    </div>
    <div class="scroll-hint">
      <span>Descubre más</span>
      <div class="scroll-arrow"></div>
    </div>
  </div>

  <!-- INVITACIÓN -->
  <section>
    <div class="reveal">
      <p class="section-label"><span class="ornament"></span> Con amor <span class="ornament"></span></p>
      <h2 class="section-title">Querida familia y amigos,</h2>
      <p class="body-text">
        Con el corazón lleno de alegría, tenemos el honor de invitarles a celebrar con nosotros el inicio de nuestra vida juntos. Será una tarde llena de amor, música y momentos que guardaremos para siempre.
      </p>
      <br>
      <p class="body-text">
        Su presencia es el regalo más grande que podemos recibir en este día tan especial.
      </p>
    </div>
  </section>

  <div class="sep">✦ ✦ ✦</div>

  <!-- DETALLES -->
  <div class="details-section">
    <div class="details-inner">
      <div class="reveal">
        <p class="section-label" style="color:var(--gold-light)">Detalles de la celebración</p>
        <h2 class="section-title" style="color:var(--cream)">Todo lo que necesitas saber</h2>
      </div>
      <div class="details-grid reveal">
        <div class="detail-card">
          <p class="label">Fecha</p>
          <p class="value">Sábado 25 de Abril, 2026</p>
          <div class="time-row">
            <span class="time-hour">4:00 PM</span>
            <span class="time-desc">Misa</span>
          </div>
          <div class="time-row">
            <span class="time-hour">5:45 PM</span>
            <span class="time-desc">Brindis · Ex-Hacienda San Cayetano</span>
          </div>
        </div>
        <div class="detail-card">
          <p class="label">Novios</p>
          <p class="value">Myrna del Carmen Villaseñor Aguirre</p>
          <p class="value" style="margin-top:0.5rem">Tenho Juan Saavedra Rautiainen</p>
        </div>
        <div class="detail-card" style="grid-column:1/-1">
          <p class="label">Ubicación</p>

          <!-- MISA -->
          <div class="location-block">
            <p class="venue-tag">⛪ Misa · 4:00 PM</p>
            <p class="venue-name">Capilla de los Sagrados Corazones</p>
            <p class="sub" style="margin-top:0.3rem">Tepic, Nayarit. Haz clic para ver la ubicación en Google Maps.</p>
            <a class="map-btn" href="https://maps.app.goo.gl/p63ge9WCLMDCv8SX9" target="_blank" rel="noopener">
              <svg viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
              Ver en Google Maps
            </a>
          </div>

          <div class="venue-divider"></div>

          <!-- FIESTA -->
          <div class="location-block">
            <p class="venue-tag">🥂 Brindis & Fiesta · 5:45 PM</p>
            <p class="venue-name">Ex-Hacienda San Cayetano</p>
            <p class="sub" style="margin-top:0.3rem">Haz clic para ver la dirección exacta en Google Maps.</p>
            <a class="map-btn" href="https://maps.app.goo.gl/epyY4Vkc6UiFmBZk6" target="_blank" rel="noopener">
              <svg viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
              Ver en Google Maps
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- COUNTDOWN -->
  <div class="countdown-section">
    <div class="countdown-inner">
      <div class="reveal">
        <p class="section-label"><span class="ornament"></span> Faltan <span class="ornament"></span></p>
        <h2 class="section-title">El día se acerca</h2>
      </div>
      <div class="countdown-grid reveal">
        <div class="count-item"><span class="count-number" id="days">--</span><span class="count-label">Días</span></div>
        <div class="count-dot">·</div>
        <div class="count-item"><span class="count-number" id="hours">--</span><span class="count-label">Horas</span></div>
        <div class="count-dot">·</div>
        <div class="count-item"><span class="count-number" id="minutes">--</span><span class="count-label">Minutos</span></div>
        <div class="count-dot">·</div>
        <div class="count-item"><span class="count-number" id="seconds">--</span><span class="count-label">Segundos</span></div>
      </div>
    </div>
  </div>

  <!-- CLOSING -->
  <!-- RSVP -->
  <div class="rsvp-section">
    <div class="rsvp-inner reveal">
      <p class="section-label"><span class="ornament"></span> Confirmación <span class="ornament"></span></p>
      <h2 class="section-title">¿Nos acompañas?</h2>
      <p class="body-text" style="max-width:480px; margin: 0 auto 2.5rem;">
        Por favor confirma tu asistencia antes del <strong>10 de abril de 2026</strong>. Tu respuesta nos ayuda a preparar cada detalle para que todo sea perfecto.
      </p>
      <!--
        ★ RSVP FORM ★
        Cuando tengas tu Google Form listo:
        1. Abre el formulario → Enviar → ícono < >
        2. Copia el src del iframe y reemplaza la URL de abajo
      -->
      <div class="rsvp-frame-wrap">
        <iframe
          src="https://docs.google.com/forms/d/e/1FAIpQLSdrElmir_b_sES9V9hpZDTOb1ykNLwr-teNHcLM_8GWUeyj3g/viewform?embedded=true"
          width="100%" height="700" frameborder="0" marginheight="0" marginwidth="0">
          Cargando…
        </iframe>
      </div>
    </div>
  </div>

  <!-- CLOSING -->
  <div class="closing">
    <div class="reveal">
      <svg class="floral-center" width="120" height="40" viewBox="0 0 120 40" xmlns="http://www.w3.org/2000/svg">
        <g fill="none" stroke="#7a7d3a" stroke-width="1">
          <path d="M10 20 Q30 5 60 20 Q90 35 110 20"/>
          <path d="M10 20 Q30 35 60 20 Q90 5 110 20"/>
          <circle cx="60" cy="20" r="3" fill="#7a7d3a"/>
          <circle cx="10" cy="20" r="2" fill="#7a7d3a"/>
          <circle cx="110" cy="20" r="2" fill="#7a7d3a"/>
          <path d="M40 12 Q45 8 50 12" stroke-width="0.8"/>
          <path d="M70 12 Q75 8 80 12" stroke-width="0.8"/>
          <path d="M40 28 Q45 32 50 28" stroke-width="0.8"/>
          <path d="M70 28 Q75 32 80 28" stroke-width="0.8"/>
        </g>
      </svg>
      <p class="closing-quote">"El amor no es mirarse el uno al otro, sino mirar juntos en la misma dirección."</p>
      <p class="closing-names">Myrna & Tenho</p>
      <p class="closing-date">25 · Abril · 2026</p>
    </div>
  </div>

  <footer><p>Con amor · Myrna & Tenho · 25.04.2026</p></footer>
</div>


<script>
  /* ── ENVELOPE OPEN SEQUENCE ── */
  const scene     = document.getElementById('envScene');
  const prompt    = document.getElementById('envPrompt');
  const cta       = document.getElementById('scrollCta');
  const photosRow = document.getElementById('photosRow');
  let opened = false;

  scene.addEventListener('click', openEnvelope);

  function openEnvelope() {
    if (opened) return;
    opened = true;

    // Hide prompt
    prompt.classList.add('hide');

    // Step 1: fade out wax seal
    const svgSeal = document.getElementById('svgSeal');
    if (svgSeal) svgSeal.style.opacity = '0';

    // Step 2: photos slide up
    setTimeout(() => {
      photosRow.classList.add('risen');
    }, 350);

    // Step 3: show CTA — always runs regardless of seal animation
    setTimeout(() => {
      cta.classList.add('show');
    }, 1600);
  }

  /* ── REVEAL MAIN ── */
  function revealMain() {
    document.getElementById('envelope-screen').classList.add('hidden');
    const main = document.getElementById('main-content');
    main.classList.add('visible');
    window.scrollTo({ top: 0, behavior: 'instant' });
    document.querySelectorAll('.reveal').forEach(el => revealObs.observe(el));
  }

  /* ── COUNTDOWN ── */
  function tick() {
    const diff = new Date('2026-04-25T00:00:00') - new Date();
    if (diff <= 0) return;
    document.getElementById('days').textContent    = Math.floor(diff / 86400000);
    document.getElementById('hours').textContent   = String(Math.floor((diff % 86400000) / 3600000)).padStart(2,'0');
    document.getElementById('minutes').textContent = String(Math.floor((diff % 3600000) / 60000)).padStart(2,'0');
    document.getElementById('seconds').textContent = String(Math.floor((diff % 60000) / 1000)).padStart(2,'0');
  }
  tick(); setInterval(tick, 1000);

  /* ── SCROLL REVEAL ── */
  const revealObs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); revealObs.unobserve(e.target); }
    });
  }, { threshold: 0.15 });
</script>
</body>
</html>
