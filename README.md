
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Our Wedding – Ana & Luis</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta
    name="description"
    content="Join us in celebrating the wedding of Ana & Luis."
  />

  <!-- Google Font -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Nunito:wght@300;400;600&display=swap"
    rel="stylesheet"
  />

  <style>
    :root {
      --bg: #fff9f7;
      --bg-alt: #ffffff;
      --accent: #e49ba3;
      --accent-dark: #c7747f;
      --text: #3b3233;
      --muted: #8b7a7b;
      --card-shadow: 0 16px 35px rgba(0, 0, 0, 0.06);
      --radius-lg: 24px;
      --radius-pill: 999px;
      --max-width: 1100px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: "Nunito", system-ui, -apple-system, BlinkMacSystemFont,
        "Segoe UI", sans-serif;
      background: radial-gradient(circle at top, #ffe6e9 0, #fff9f7 45%, #fff 100%);
      color: var(--text);
      line-height: 1.6;
      scroll-behavior: smooth;
    }

    a {
      color: var(--accent-dark);
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(255, 249, 247, 0.92);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(0, 0, 0, 0.03);
    }

    .nav-inner {
      max-width: var(--max-width);
      margin: 0 auto;
      padding: 0.75rem 1.25rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
    }

    .brand {
      font-family: "Playfair Display", serif;
      font-size: 1.3rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--accent-dark);
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 0.75rem;
      flex-wrap: wrap;
      justify-content: flex-end;
    }

    nav a {
      font-size: 0.9rem;
      padding: 0.4rem 0.9rem;
      border-radius: var(--radius-pill);
      border: 1px solid transparent;
      transition: all 0.2s ease;
      color: var(--muted);
      font-weight: 600;
    }

    nav a:hover {
      border-color: var(--accent);
      background: #fff;
      color: var(--accent-dark);
    }

    .hero {
      max-width: var(--max-width);
      margin: 1.5rem auto 2rem;
      padding: 1.5rem 1.25rem 2.5rem;
      display: grid;
      grid-template-columns: minmax(0, 1.3fr) minmax(0, 1fr);
      gap: 2rem;
      align-items: center;
    }

    @media (max-width: 800px) {
      .hero {
        grid-template-columns: 1fr;
        text-align: center;
      }
    }

    .hero-card {
      background: linear-gradient(145deg, #ffffff, #ffeef1);
      border-radius: var(--radius-lg);
      padding: 2rem;
      box-shadow: var(--card-shadow);
      position: relative;
      overflow: hidden;
    }

    .hero-card::before {
      content: "♥";
      position: absolute;
      font-size: 8rem;
      opacity: 0.05;
      right: -1rem;
      top: -2rem;
    }

    .hero-subtitle {
      text-transform: uppercase;
      letter-spacing: 0.2em;
      font-size: 0.75rem;
      color: var(--muted);
      margin-bottom: 0.75rem;
    }

    .hero-names {
      font-family: "Playfair Display", serif;
      font-size: clamp(2.2rem, 4vw, 3rem);
      margin-bottom: 0.2rem;
    }

    .hero-names span {
      color: var(--accent-dark);
    }

    .hero-date {
      font-size: 1rem;
      color: var(--muted);
      margin-bottom: 1.2rem;
    }

    .hero-cta {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      align-items: center;
      margin-top: 1.5rem;
    }

    .pill {
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      padding: 0.45rem 0.9rem;
      border-radius: var(--radius-pill);
      background: rgba(255, 255, 255, 0.9);
      border: 1px solid rgba(0, 0, 0, 0.04);
      font-size: 0.8rem;
      color: var(--muted);
      white-space: nowrap;
    }

    .pill-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #49c469;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.7rem 1.3rem;
      border-radius: var(--radius-pill);
      border: none;
      cursor: pointer;
      background: linear-gradient(135deg, var(--accent), var(--accent-dark));
      color: #fff;
      font-weight: 600;
      font-size: 0.9rem;
      box-shadow: 0 12px 25px rgba(199, 116, 127, 0.35);
      transition: transform 0.12s ease, box-shadow 0.12s ease,
        filter 0.12s ease;
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      box-shadow: 0 16px 32px rgba(199, 116, 127, 0.4);
      filter: brightness(1.03);
    }

    .btn-ghost {
      background: rgba(255, 255, 255, 0.9);
      border-radius: var(--radius-pill);
      border: 1px solid rgba(0, 0, 0, 0.05);
      padding: 0.55rem 1.1rem;
      font-size: 0.85rem;
      cursor: pointer;
      color: var(--muted);
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      transition: background 0.15s ease, transform 0.1s ease;
    }

    .btn-ghost:hover {
      background: #fff;
      transform: translateY(-1px);
    }

    .hero-side {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .countdown-card,
    .music-card {
      background: var(--bg-alt);
      border-radius: var(--radius-lg);
      padding: 1.3rem 1.4rem;
      box-shadow: var(--card-shadow);
    }

    .section-label {
      text-transform: uppercase;
      letter-spacing: 0.18em;
      font-size: 0.7rem;
      color: var(--muted);
      margin-bottom: 0.5rem;
    }

    .countdown-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 0.5rem;
    }

    @media (max-width: 500px) {
      .countdown-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
    }

    .countdown-item {
      background: #fff6f8;
      border-radius: 18px;
      padding: 0.7rem 0.4rem;
      text-align: center;
    }

    .count-number {
      font-size: 1.3rem;
      font-weight: 700;
      color: var(--accent-dark);
      font-family: "Playfair Display", serif;
      margin-bottom: 0.2rem;
    }

    .count-label {
      font-size: 0.7rem;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--muted);
    }

    .music-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 0.75rem;
      flex-wrap: wrap;
    }

    main {
      max-width: var(--max-width);
      margin: 0 auto 3rem;
      padding: 0 1.25rem 2rem;
    }

    section {
      margin-bottom: 3rem;
    }

    .section-title {
      font-family: "Playfair Display", serif;
      font-size: 1.6rem;
      margin-bottom: 0.5rem;
    }

    .section-intro {
      max-width: 600px;
      color: var(--muted);
      font-size: 0.95rem;
      margin-bottom: 1.4rem;
    }

    .card-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 1.5rem;
    }

    @media (max-width: 800px) {
      .card-grid {
        grid-template-columns: 1fr;
      }
    }

    .card {
      background: var(--bg-alt);
      border-radius: var(--radius-lg);
      padding: 1.5rem 1.4rem;
      box-shadow: var(--card-shadow);
    }

    .card h3 {
      font-family: "Playfair Display", serif;
      font-size: 1.2rem;
      margin-bottom: 0.4rem;
    }

    .card p {
      font-size: 0.92rem;
      color: var(--muted);
    }

    .chip {
      display: inline-block;
      margin-top: 0.4rem;
      padding: 0.2rem 0.6rem;
      border-radius: 999px;
      font-size: 0.75rem;
      background: #fff4f6;
      color: var(--accent-dark);
    }

    .details-list {
      list-style: none;
      margin-top: 0.8rem;
      font-size: 0.9rem;
      color: var(--muted);
    }

    .details-list li + li {
      margin-top: 0.3rem;
    }

    .details-label {
      font-weight: 600;
      color: var(--text);
      margin-right: 0.25rem;
    }

    .timeline {
      margin-top: 0.75rem;
      border-left: 2px dashed #f3c0c7;
      padding-left: 1.1rem;
    }

    .timeline-item {
      margin-bottom: 0.7rem;
      position: relative;
    }

    .timeline-item::before {
      content: "";
      position: absolute;
      left: -1.17rem;
      top: 0.1rem;
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: var(--accent-dark);
    }

    .timeline-time {
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--accent-dark);
    }

    .timeline-desc {
      font-size: 0.9rem;
      color: var(--muted);
    }

    /* Carousel */
    .carousel {
      position: relative;
      overflow: hidden;
      border-radius: var(--radius-lg);
      box-shadow: var(--card-shadow);
      background: #000;
    }

    .carousel-track {
      display: flex;
      transition: transform 0.4s ease;
    }

    .carousel-slide {
      min-width: 100%;
      max-height: 420px;
      position: relative;
    }

    .carousel-slide img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    .carousel-caption {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 0.8rem 1rem;
      background: linear-gradient(to top, rgba(0, 0, 0, 0.65), transparent);
      color: #fff;
      font-size: 0.9rem;
    }

    .carousel-controls {
      position: absolute;
      inset: 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
      pointer-events: none;
      padding: 0 0.4rem;
    }

    .carousel-btn {
      pointer-events: auto;
      border: none;
      background: rgba(255, 255, 255, 0.85);
      width: 34px;
      height: 34px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      font-size: 1.1rem;
      color: var(--accent-dark);
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
      transition: transform 0.15s ease, box-shadow 0.15s ease;
    }

    .carousel-btn:hover {
      transform: translateY(-1px);
      box-shadow: 0 10px 22px rgba(0, 0, 0, 0.25);
    }

    .carousel-dots {
      position: absolute;
      bottom: 0.6rem;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      gap: 0.3rem;
    }

    .carousel-dot {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      border: 2px solid rgba(255, 255, 255, 0.9);
      background: transparent;
      cursor: pointer;
      opacity: 0.7;
      transition: background 0.15s ease, transform 0.15s ease, opacity 0.15s ease;
    }

    .carousel-dot.active {
      background: #fff;
      transform: scale(1.1);
      opacity: 1;
    }

    /* RSVP */
    .rsvp-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.3fr) minmax(0, 1fr);
      gap: 1.5rem;
    }

    @media (max-width: 800px) {
      .rsvp-grid {
        grid-template-columns: 1fr;
      }
    }

    .rsvp-form {
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
    }

    label {
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--text);
    }

    input,
    select,
    textarea {
      width: 100%;
      border-radius: 16px;
      border: 1px solid rgba(0, 0, 0, 0.08);
      padding: 0.55rem 0.7rem;
      font-family: inherit;
      font-size: 0.9rem;
      outline: none;
      transition: border 0.15s ease, box-shadow 0.15s ease;
      background: #fff;
    }

    input:focus,
    select:focus,
    textarea:focus {
      border-color: var(--accent-dark);
      box-shadow: 0 0 0 1px rgba(196, 83, 104, 0.25);
    }

    textarea {
      resize: vertical;
      min-height: 90px;
    }

    .rsvp-list {
      font-size: 0.9rem;
      max-height: 270px;
      overflow: auto;
      padding-right: 0.4rem;
    }

    .rsvp-item {
      padding: 0.5rem 0.3rem;
      border-bottom: 1px dashed #f2d0d6;
    }

    .rsvp-item:last-child {
      border-bottom: none;
    }

    .rsvp-name {
      font-weight: 600;
    }

    .rsvp-status {
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--muted);
    }

    .rsvp-note {
      font-size: 0.85rem;
      color: var(--muted);
    }

    .badge-yes {
      color: #1c8d4a;
    }

    .badge-no {
      color: #b24040;
    }

    footer {
      text-align: center;
      font-size: 0.8rem;
      color: var(--muted);
      padding: 1.5rem 1.25rem 2rem;
      border-top: 1px solid rgba(0, 0, 0, 0.03);
      background: #fff;
    }
  </style>
</head>
<body>
  <!-- Background music -->
  <!-- Replace assets/music.mp3 with your own file path -->
  <audio id="bg-music" src="assets/music.mp3" loop></audio>

  <header>
    <div class="nav-inner">
      <div class="brand">Ana &amp; Luis</div>
      <nav>
        <ul>
          <li><a href="#countdown">Countdown</a></li>
          <li><a href="#venue">Ceremony &amp; Party</a></li>
          <li><a href="#gallery">Photos</a></li>
          <li><a href="#gifts">Gifts</a></li>
          <li><a href="#program">Program</a></li>
          <li><a href="#stay">Stay &amp; Activities</a></li>
          <li><a href="#rsvp">RSVP</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <section class="hero">
    <div class="hero-card">
      <div class="hero-subtitle">We are getting married</div>
      <div class="hero-names"><span>Ana</span> &amp; <span>Luis</span></div>
      <div class="hero-date">Saturday · June 20, 2026 · 4:00 PM</div>
      <p>
        Family and friends, we would love to celebrate our wedding day with you.
        Below you will find all the details about the ceremony, party, hotels,
        and how to confirm your attendance.
      </p>

      <div class="hero-cta">
        <button class="btn-primary" onclick="document.getElementById('rsvp').scrollIntoView({behavior:'smooth'});">
          Confirm your attendance
        </button>
        <div class="pill">
          <div class="pill-dot"></div>
          <span>Counting the days until we say “I do”</span>
        </div>
      </div>
    </div>

    <div class="hero-side">
      <div class="countdown-card" id="countdown">
        <div class="section-label">Countdown</div>
        <h2 style="font-family:'Playfair Display',serif;font-size:1.3rem;margin-bottom:0.7rem;">
          Until our wedding day
        </h2>
        <div class="countdown-grid">
          <div class="countdown-item">
            <div class="count-number" id="days">0</div>
            <div class="count-label">Days</div>
          </div>
          <div class="countdown-item">
            <div class="count-number" id="hours">0</div>
            <div class="count-label">Hours</div>
          </div>
          <div class="countdown-item">
            <div class="count-number" id="minutes">0</div>
            <div class="count-label">Minutes</div>
          </div>
          <div class="countdown-item">
            <div class="count-number" id="seconds">0</div>
            <div class="count-label">Seconds</div>
          </div>
        </div>
      </div>

      <div class="music-card">
        <div class="section-label">Music</div>
        <div class="music-row">
          <div>
            <strong>Our song is playing</strong>
            <p style="font-size:0.85rem;color:var(--muted);margin-top:0.2rem;">
              Tap play to listen to the soundtrack of our story.
            </p>
          </div>
          <button id="music-toggle" class="btn-ghost">
            <span id="music-icon">▶</span>
            <span id="music-label">Play</span>
          </button>
        </div>
      </div>
    </div>
  </section>

  <main>
    <!-- Ceremony & Reception -->
    <section id="venue">
      <div class="section-label">Ceremony &amp; Party</div>
      <h2 class="section-title">Where to celebrate with us</h2>
      <p class="section-intro">
        We will celebrate our union with a wedding mass followed by a dinner and
        party nearby. You can find directions and parking information below.
      </p>

      <div class="card-grid">
        <div class="card">
          <h3>Wedding Mass</h3>
          <p>Join us as we exchange our vows.</p>
          <ul class="details-list">
            <li><span class="details-label">Location:</span>St. Mary’s Church</li>
            <li><span class="details-label">Address:</span>Main Street 123, City</li>
            <li><span class="details-label">Time:</span>4:00 PM</li>
          </ul>
          <p style="margin-top:0.6rem;">
            <a href="https://maps.google.com" target="_blank" rel="noopener">
              Open church in Google Maps →
            </a>
          </p>
        </div>

        <div class="card">
          <h3>Dinner &amp; Party</h3>
          <p>Let’s eat, dance and celebrate together.</p>
          <ul class="details-list">
            <li><span class="details-label">Location:</span>Garden View Hall</li>
            <li><span class="details-label">Address:</span>Lake Avenue 45, City</li>
            <li><span class="details-label">Starts:</span>6:00 PM</li>
          </ul>
          <p style="margin-top:0.6rem;">
            <a href="https://maps.google.com" target="_blank" rel="noopener">
              Open reception in Google Maps →
            </a>
          </p>
          <p style="margin-top:0.6rem;font-size:0.86rem;color:var(--muted);">
            A shuttle will depart from the church directly after the ceremony.
          </p>
        </div>
      </div>
    </section>

    <!-- Gallery / Carousel -->
    <section id="gallery">
      <div class="section-label">Photos</div>
      <h2 class="section-title">A few moments from our story</h2>
      <p class="section-intro">
        From the first coffee together to saying “yes”, these are some of the
        little moments that brought us here. Replace these photos with your
        favorites.
      </p>

      <div class="carousel" aria-label="Photo carousel of the couple">
        <div class="carousel-track" id="carousel-track">
          <!-- Slide 1 -->
          <div class="carousel-slide">
            <!-- Replace image paths with your own -->
            <img src="images/photo1.jpg" alt="The couple smiling on a sunny afternoon" />
            <div class="carousel-caption">The day everything started.</div>
          </div>
          <!-- Slide 2 -->
          <div class="carousel-slide">
            <img src="images/photo2.jpg" alt="The couple walking by the sea at sunset" />
            <div class="carousel-caption">Sunsets, long walks and shared dreams.</div>
          </div>
          <!-- Slide 3 -->
          <div class="carousel-slide">
            <img src="images/photo3.jpg" alt="The proposal moment with a ring" />
            <div class="carousel-caption">The moment we said “forever”.</div>
          </div>
        </div>

        <div class="carousel-controls">
          <button class="carousel-btn" id="prev-slide" aria-label="Previous photo">
            ‹
          </button>
          <button class="carousel-btn" id="next-slide" aria-label="Next photo">
            ›
          </button>
        </div>

        <div class="carousel-dots" id="carousel-dots">
          <button class="carousel-dot active" data-index="0" aria-label="Go to photo 1"></button>
          <button class="carousel-dot" data-index="1" aria-label="Go to photo 2"></button>
          <button class="carousel-dot" data-index="2" aria-label="Go to photo 3"></button>
        </div>
      </div>
    </section>

    <!-- Gift board / Mesa de regalos -->
    <section id="gifts">
      <div class="section-label">Gifts · Mesa de regalos</div>
      <h2 class="section-title">Your presence is the greatest gift</h2>
      <p class="section-intro">
        Having you with us on this day is what matters most. If you would still
        like to give us a gift, here are some options that will help us build
        our home together.
      </p>

      <div class="card-grid">
        <div class="card">
          <h3>Gift Registry</h3>
          <p>We have created a small list of things for our new home.</p>
          <ul class="details-list">
            <li>
              <span class="details-label">Store 1:</span>
              <a href="https://example.com/registry1" target="_blank" rel="noopener">
                Home Store Registry
              </a>
            </li>
            <li>
              <span class="details-label">Store 2:</span>
              <a href="https://example.com/registry2" target="_blank" rel="noopener">
                Online Registry
              </a>
            </li>
          </ul>
        </div>

        <div class="card">
          <h3>Honeymoon fund</h3>
          <p>
            If you prefer, you can contribute to our honeymoon and future
            adventures together.
          </p>
          <ul class="details-list">
            <li><span class="details-label">Bank:</span>Romantic Bank</li>
            <li><span class="details-label">Account:</span>1234 · 5678 · 90</li>
            <li><span class="details-label">Reference:</span>Ana &amp; Luis Wedding</li>
          </ul>
          <span class="chip">Thank you for your love and generosity</span>
        </div>
      </div>
    </section>

    <!-- Program -->
    <section id="program">
      <div class="section-label">Program</div>
      <h2 class="section-title">Wedding day schedule</h2>
      <p class="section-intro">
        Here is the approximate schedule for the day. Times may vary slightly,
        but this will help you plan your trip and outfit changes.
      </p>

      <div class="card">
        <h3>June 20, 2026</h3>
        <div class="timeline">
          <div class="timeline-item">
            <div class="timeline-time">3:30 PM</div>
            <div class="timeline-desc">Guests arrive at the church.</div>
          </div>
          <div class="timeline-item">
            <div class="timeline-time">4:00 PM</div>
            <div class="timeline-desc">Wedding mass and ceremony.</div>
          </div>
          <div class="timeline-item">
            <div class="timeline-time">5:30 PM</div>
            <div class="timeline-desc">Transfer to reception venue.</div>
          </div>
          <div class="timeline-item">
            <div class="timeline-time">6:00 PM</div>
            <div class="timeline-desc">Welcome drinks &amp; photos.</div>
          </div>
          <div class="timeline-item">
            <div class="timeline-time">7:30 PM</div>
            <div class="timeline-desc">Dinner is served.</div>
          </div>
          <div class="timeline-item">
            <div class="timeline-time">9:30 PM</div>
            <div class="timeline-desc">First dance &amp; cake.</div>
          </div>
          <div class="timeline-item">
            <div class="timeline-time">10:00 PM – late</div>
            <div class="timeline-desc">Party &amp; dancing.</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Hotel & Activities -->
    <section id="stay">
      <div class="section-label">Stay &amp; Activities</div>
      <h2 class="section-title">Where to stay &amp; what to do</h2>
      <p class="section-intro">
        We are delighted that you are travelling to be with us. Here are some
        hotel suggestions and activities nearby for the weekend.
      </p>

      <div class="card-grid">
        <div class="card">
          <h3>Hotel suggestions</h3>
          <ul class="details-list">
            <li>
              <span class="details-label">Hotel Lakeview</span> – 5 min from the
              reception, special “Ana &amp; Luis Wedding” rate.
            </li>
            <li>
