<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Shivneri Fort — Birthplace of a Legend</title>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel+Decorative:wght@400;700;900&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --saffron:   #E87722;
      --deep:      #1A0A00;
      --gold:      #C9920A;
      --cream:     #F5EDD6;
      --stone:     #8B7355;
      --ink:       #2C1A0E;
      --glow:      #F4A622;
      --muted:     #6B5540;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background-color: var(--deep);
      color: var(--cream);
      font-family: 'Cormorant Garamond', serif;
      overflow-x: hidden;
    }

    /* ── GRAIN OVERLAY ── */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none; opacity: 0.35;
    }

    /* ── HERO ── */
    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      padding: 2rem;
    }

    .hero-bg {
      position: absolute; inset: 0; z-index: 0;
      background:
        radial-gradient(ellipse 80% 60% at 50% 110%, #E8772240 0%, transparent 70%),
        radial-gradient(ellipse 60% 40% at 20% -10%, #C9920A18 0%, transparent 60%),
        linear-gradient(175deg, #0D0500 0%, #1A0A00 45%, #2A1200 100%);
    }

    /* Animated fort silhouette */
    .fort-silhouette {
      position: absolute;
      bottom: 0; left: 50%;
      transform: translateX(-50%);
      width: min(900px, 120vw);
      opacity: 0.12;
      z-index: 0;
    }

    .stars {
      position: absolute; inset: 0; z-index: 0;
      overflow: hidden;
    }
    .star {
      position: absolute;
      background: #fff;
      border-radius: 50%;
      animation: twinkle var(--d, 3s) ease-in-out infinite alternate;
    }
    @keyframes twinkle { from { opacity: 0.1; } to { opacity: 0.8; } }

    .hero-badge {
      position: relative; z-index: 2;
      font-family: 'Rajdhani', sans-serif;
      font-size: 0.75rem;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      color: var(--gold);
      border: 1px solid #C9920A55;
      padding: 0.4rem 1.4rem;
      margin-bottom: 1.8rem;
      animation: fadeUp 1s ease both;
    }

    .hero-title {
      position: relative; z-index: 2;
      font-family: 'Cinzel Decorative', serif;
      font-size: clamp(2.4rem, 7vw, 6rem);
      font-weight: 900;
      text-align: center;
      line-height: 1.05;
      background: linear-gradient(135deg, #F5EDD6 30%, #E87722 65%, #C9920A 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-shadow: none;
      animation: fadeUp 1s 0.2s ease both;
    }

    .hero-sub {
      position: relative; z-index: 2;
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1.1rem, 2.5vw, 1.6rem);
      font-style: italic;
      color: #D4B896;
      margin-top: 1rem;
      letter-spacing: 0.06em;
      text-align: center;
      animation: fadeUp 1s 0.4s ease both;
    }

    .scroll-hint {
      position: absolute; bottom: 2rem; z-index: 2;
      display: flex; flex-direction: column; align-items: center; gap: 0.4rem;
      opacity: 0.5; animation: pulse 2s infinite;
    }
    .scroll-hint span {
      font-family: 'Rajdhani', sans-serif;
      font-size: 0.65rem; letter-spacing: 0.3em;
      text-transform: uppercase;
    }
    .arrow { width: 18px; height: 18px; border-right: 1.5px solid var(--cream); border-bottom: 1.5px solid var(--cream); transform: rotate(45deg); }

    /* ── DIVIDER ── */
    .divider {
      display: flex; align-items: center; gap: 1rem;
      padding: 0 2rem; margin: 0 auto 3rem;
      max-width: 800px;
    }
    .divider-line { flex: 1; height: 1px; background: linear-gradient(to right, transparent, var(--gold), transparent); }
    .divider-icon { color: var(--saffron); font-size: 1.2rem; }

    /* ── IMAGE SECTION ── */
    .image-section {
      position: relative; z-index: 1;
      padding: 4rem 2rem 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .image-frame {
      position: relative;
      max-width: 780px;
      width: 100%;
      animation: fadeUp 1s 0.6s ease both;
    }

    .image-frame::before {
      content: '';
      position: absolute;
      inset: -3px;
      background: linear-gradient(135deg, var(--gold), var(--saffron), var(--gold), transparent, var(--gold));
      border-radius: 4px;
      z-index: 0;
    }

    .image-frame img {
      position: relative; z-index: 1;
      width: 100%;
      height: 440px;
      object-fit: cover;
      display: block;
      border-radius: 3px;
      filter: sepia(20%) contrast(1.05) brightness(0.92);
    }

    .image-caption {
      position: absolute; bottom: 0; left: 0; right: 0; z-index: 2;
      background: linear-gradient(to top, rgba(26,10,0,0.95) 0%, transparent 100%);
      padding: 3rem 2rem 1.5rem;
      text-align: center;
    }
    .image-caption p {
      font-family: 'Rajdhani', sans-serif;
      font-size: 0.7rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: #C9920A;
    }

    .year-tag {
      position: absolute;
      top: -1.2rem; right: 2rem; z-index: 3;
      background: var(--saffron);
      color: var(--deep);
      font-family: 'Cinzel Decorative', serif;
      font-size: 0.85rem;
      font-weight: 700;
      padding: 0.4rem 1rem;
      letter-spacing: 0.05em;
    }

    /* ── CONTENT ── */
    .content {
      position: relative; z-index: 1;
      max-width: 860px;
      margin: 0 auto;
      padding: 4rem 2rem;
    }

    .section { margin-bottom: 4rem; }

    .section-label {
      font-family: 'Rajdhani', sans-serif;
      font-size: 0.68rem;
      letter-spacing: 0.4em;
      text-transform: uppercase;
      color: var(--saffron);
      margin-bottom: 0.6rem;
    }

    h2 {
      font-family: 'Cinzel Decorative', serif;
      font-size: clamp(1.4rem, 3vw, 2.2rem);
      font-weight: 700;
      color: var(--cream);
      margin-bottom: 1.6rem;
      line-height: 1.2;
    }

    h2 .accent { color: var(--saffron); }

    p {
      font-size: clamp(1rem, 2vw, 1.22rem);
      line-height: 1.85;
      color: #D4B896;
      margin-bottom: 1.2rem;
      font-weight: 300;
    }

    p strong {
      color: var(--cream);
      font-weight: 600;
    }

    /* ── PULL QUOTE ── */
    .pull-quote {
      border-left: 3px solid var(--saffron);
      padding: 1rem 2rem;
      margin: 2.5rem 0;
      background: rgba(232,119,34,0.06);
    }
    .pull-quote p {
      font-size: clamp(1.15rem, 2.2vw, 1.5rem);
      font-style: italic;
      color: var(--cream);
      margin: 0;
    }

    /* ── FACTS GRID ── */
    .facts-section {
      background: linear-gradient(135deg, rgba(201,146,10,0.07), rgba(232,119,34,0.04));
      border: 1px solid rgba(201,146,10,0.2);
      border-radius: 2px;
      padding: 3rem;
      margin-bottom: 4rem;
    }

    .facts-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 1.5rem;
      margin-top: 2rem;
    }

    .fact-card {
      display: flex;
      gap: 1rem;
      align-items: flex-start;
      padding: 1.2rem;
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(201,146,10,0.15);
      transition: border-color 0.3s, background 0.3s;
    }
    .fact-card:hover {
      border-color: rgba(232,119,34,0.5);
      background: rgba(232,119,34,0.06);
    }

    .fact-number {
      font-family: 'Cinzel Decorative', serif;
      font-size: 1.4rem;
      color: var(--saffron);
      opacity: 0.5;
      line-height: 1;
      flex-shrink: 0;
    }

    .fact-text {
      font-size: 0.95rem;
      color: #C8AD8F;
      line-height: 1.65;
      font-weight: 300;
    }
    .fact-text strong { color: var(--cream); display: block; margin-bottom: 0.25rem; font-weight: 600; }

    /* ── STATS ROW ── */
    .stats-row {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 1px;
      background: rgba(201,146,10,0.2);
      margin: 3rem 0;
      border: 1px solid rgba(201,146,10,0.2);
    }

    .stat {
      background: var(--deep);
      padding: 1.8rem 1rem;
      text-align: center;
    }
    .stat-value {
      font-family: 'Cinzel Decorative', serif;
      font-size: clamp(1.4rem, 3vw, 2.2rem);
      color: var(--saffron);
      display: block;
      margin-bottom: 0.3rem;
    }
    .stat-label {
      font-family: 'Rajdhani', sans-serif;
      font-size: 0.65rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--muted);
    }

    /* ── TIMELINE ── */
    .timeline { position: relative; padding-left: 2.5rem; margin-top: 2rem; }
    .timeline::before {
      content: '';
      position: absolute; left: 0.5rem; top: 0; bottom: 0;
      width: 1px;
      background: linear-gradient(to bottom, var(--saffron), transparent);
    }

    .timeline-item {
      position: relative;
      margin-bottom: 2rem;
      animation: fadeUp 0.6s ease both;
    }
    .timeline-item::before {
      content: '';
      position: absolute;
      left: -2.1rem; top: 0.4rem;
      width: 8px; height: 8px;
      background: var(--saffron);
      border-radius: 50%;
      box-shadow: 0 0 10px var(--saffron);
    }

    .timeline-year {
      font-family: 'Rajdhani', sans-serif;
      font-size: 0.7rem;
      letter-spacing: 0.25em;
      color: var(--gold);
      text-transform: uppercase;
      margin-bottom: 0.2rem;
    }
    .timeline-event {
      font-size: 1rem;
      color: #C8AD8F;
      line-height: 1.6;
    }
    .timeline-event strong { color: var(--cream); }

    /* ── FOOTER ── */
    footer {
      position: relative; z-index: 1;
      border-top: 1px solid rgba(201,146,10,0.2);
      padding: 3rem 2rem;
      text-align: center;
    }

    .footer-logo {
      font-family: 'Cinzel Decorative', serif;
      font-size: 1.1rem;
      color: var(--gold);
      margin-bottom: 0.8rem;
    }

    footer p {
      font-size: 0.85rem;
      color: var(--muted);
      margin: 0;
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes pulse {
      0%, 100% { opacity: 0.4; }
      50%       { opacity: 0.8; }
    }

    /* Scroll reveal */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }
    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 600px) {
      .image-frame img { height: 260px; }
      .facts-section { padding: 1.5rem; }
      .stats-row { grid-template-columns: repeat(2, 1fr); }
    }
  </style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="stars" id="stars"></div>

  <!-- Fort SVG Silhouette -->
  <svg class="fort-silhouette" viewBox="0 0 900 300" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M0 300 L0 200 L40 200 L40 180 L55 180 L55 160 L70 160 L70 140 L80 140 L80 100 L90 80 L100 100 L100 140 L120 140 L120 160 L140 160 L140 180 L155 180 L155 200 L200 200 L200 220 L220 220 L220 180 L240 180 L240 160 L260 160 L260 140 L270 120 L280 100 L285 80 L290 100 L295 120 L310 140 L310 160 L330 160 L330 180 L350 180 L350 200 L380 200 L380 160 L395 120 L400 80 L410 60 L420 40 L430 60 L440 80 L445 120 L460 160 L460 200 L490 200 L490 180 L510 180 L510 160 L530 160 L530 140 L545 120 L555 100 L560 80 L565 100 L575 120 L590 140 L590 160 L610 160 L610 180 L630 180 L630 200 L660 200 L660 180 L680 180 L680 160 L700 160 L700 140 L710 120 L720 100 L730 80 L740 100 L750 120 L760 140 L760 160 L780 160 L780 180 L800 180 L800 200 L840 200 L840 180 L860 180 L860 200 L900 200 L900 300 Z" fill="white"/>
  </svg>

  <div class="hero-badge">Maharashtra · India · 1595 AD</div>
  <h1 class="hero-title">Shivneri Fort</h1>
  <p class="hero-sub">Where a Legend Was Born</p>

  <div class="scroll-hint">
    <span>Explore</span>
    <div class="arrow"></div>
  </div>
</section>

<!-- IMAGE -->
<section class="image-section">
  <div class="image-frame reveal">
    <span class="year-tag">Est. 1595</span>
    <img
      src="https://kevinstandagephotography.wordpress.com/wp-content/uploads/2024/12/ksp_0752-2.jpg?w=1000px-Shivneri_fort.jpg"
      alt="Shivneri Fort, birthplace of Chhatrapati Shivaji Maharaj"
      onerror="this.src='https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Shivneri_Fort_Maharashtra.jpg/1280px-Shivneri_Fort_Maharashtra.jpg'"
    />
    <div class="image-caption">
      <p>Shivneri Fort · Junnar, Pune District · Maharashtra</p>
    </div>
  </div>
</section>

<!-- STATS -->
<div class="content">
  <div class="stats-row reveal">
    <div class="stat">
      <span class="stat-value">3000+</span>
      <span class="stat-label">Feet Elevation</span>
    </div>
    <div class="stat">
      <span class="stat-value">1630</span>
      <span class="stat-label">Year of Birth</span>
    </div>
    <div class="stat">
      <span class="stat-value">7</span>
      <span class="stat-label">Defensive Gates</span>
    </div>
    <div class="stat">
      <span class="stat-value">16th C</span>
      <span class="stat-label">Century Built</span>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section reveal">
    <p class="section-label">About the Fort</p>
    <h2>A <span class="accent">Sacred</span> Hill of Stone</h2>
    <p>
      Shivneri Fort is a <strong>16th-century hill fortress</strong> perched dramatically atop a steep, rocky hill in the Junnar region of Pune district, Maharashtra, India. Rising over 3,000 feet above sea level, it is classified as a <strong>giridurga</strong> — a mountain fort — and is considered one of the most strategically formidable fortresses of the Deccan plateau. The fort was constructed during the reign of the Nizam Shahi dynasty and later came under the control of the Mughals and, eventually, the Marathas.
    </p>
    <p>
      The fort's architecture reflects centuries of layered history. Its <strong>seven successive gates</strong> — each a formidable barrier — were designed to slow and exhaust any attacking force long before they could reach the inner citadel. The approach winds through dense jungle and sheer cliffs, making Shivneri nearly impregnable to conventional assault. Within its walls, ancient cisterns, temples, and residential quarters tell the story of a thriving royal community.
    </p>

    <div class="pull-quote">
      <p>"From these ramparts, a boy would grow to reshape the destiny of an entire subcontinent."</p>
    </div>
  </div>

  <!-- HISTORY -->
  <div class="section reveal">
    <p class="section-label">Historical Significance</p>
    <h2>The <span class="accent">Birthplace</span> of Shivaji Maharaj</h2>
    <p>
      Shivneri Fort holds its supreme place in Indian history as the <strong>birthplace of Chhatrapati Shivaji Maharaj</strong>, the founder of the Maratha Empire, born here on <strong>February 19, 1630</strong>. His mother, Jijabai, took shelter in the fort during uncertain political times, and it was within these protected walls that the child who would one day challenge the Mughal Empire first opened his eyes to the world. The fort's goddess, <strong>Shivai Devi</strong>, is believed to have blessed the newborn, and it is from her name that "Shivaji" is derived.
    </p>
    <p>
      Long before Shivaji's birth, Shivneri served as a key administrative and military stronghold. It was held by the <strong>Nizam Shahi sultans of Ahmadnagar</strong> during the 15th and 16th centuries, then briefly occupied by Mughal forces. The fort's location along ancient trade routes between the Deccan and the Konkan coast made it invaluable to any power seeking to dominate western India. <strong>Shahaji Bhonsale</strong>, Shivaji's father, entrusted the safety of his family to Shivneri during one of the most turbulent periods of Deccan politics.
    </p>
    <p>
      Today, Shivneri Fort stands as a <strong>protected monument under the Archaeological Survey of India</strong> and draws thousands of pilgrims, history enthusiasts, and trekkers every year. A bronze statue of young Shivaji and his mother Jijabai sits within the fort's courtyard — a stirring reminder that India's most celebrated warrior-king spent his earliest years within these ancient walls.
    </p>
  </div>

  <!-- INTERESTING FACTS -->
  <div class="facts-section reveal">
    <p class="section-label">Did You Know?</p>
    <h2>Fascinating <span class="accent">Facts</span></h2>
    <div class="facts-grid">
      <div class="fact-card">
        <span class="fact-number">01</span>
        <p class="fact-text"><strong>Seven Gates of Defence</strong>The fort has seven sequential entrance gates — Maha Darwaja, Pir Darwaja, Parag Darwaja, Hatti Darwaja, Shivai Darwaja, Kulup Darwaja, and Ambar Khana Darwaja — each a formidable obstacle for invaders.</p>
      </div>
      <div class="fact-card">
        <span class="fact-number">02</span>
        <p class="fact-text"><strong>Named After a Goddess</strong>The fort's presiding deity is Goddess Shivai. Jijabai prayed fervently to her for a son, and the child born was named Shivaji in her honour.</p>
      </div>
      <div class="fact-card">
        <span class="fact-number">03</span>
        <p class="fact-text"><strong>Ancient Water Tanks</strong>Two large ancient tanks, "Badami" and "Sitamai", supply fresh water within the fort. They were designed to sustain a garrison for months without resupply.</p>
      </div>
      <div class="fact-card">
        <span class="fact-number">04</span>
        <p class="fact-text"><strong>Rock-Cut Caves</strong>The fort contains Buddhist rock-cut caves dating back to the 3rd–6th century AD, attesting to the site's religious and cultural significance long before the Maratha period.</p>
      </div>
      <div class="fact-card">
        <span class="fact-number">05</span>
        <p class="fact-text"><strong>Jijabai's Residence</strong>A small, preserved stone chamber inside the fort is identified as the room where Jijabai lived during her stay — and where Shivaji was born.</p>
      </div>
      <div class="fact-card">
        <span class="fact-number">06</span>
        <p class="fact-text"><strong>Treacherous Trek</strong>The only path to the fort winds through dense hillside vegetation and multiple locked gates. This natural and artificial layering made the fort extraordinarily difficult to storm.</p>
      </div>
    </div>
  </div>

  <!-- TIMELINE -->
  <div class="section reveal">
    <p class="section-label">Through the Ages</p>
    <h2>A <span class="accent">Timeline</span> of Shivneri</h2>
    <div class="timeline">
      <div class="timeline-item">
        <p class="timeline-year">3rd–6th Century AD</p>
        <p class="timeline-event">Buddhist monks carve <strong>rock-cut caves</strong> into the hillside, establishing Shivneri as a sacred site centuries before the fort was built.</p>
      </div>
      <div class="timeline-item">
        <p class="timeline-year">15th–16th Century</p>
        <p class="timeline-event">The <strong>Nizam Shahi Sultanate</strong> of Ahmadnagar constructs and expands the stone fortifications, building the seven gates and main battlements.</p>
      </div>
      <div class="timeline-item">
        <p class="timeline-year">1595</p>
        <p class="timeline-event">Shahaji Bhonsale takes charge of the fort. His wife <strong>Jijabai</strong> arrives seeking refuge amid Deccan political turmoil.</p>
      </div>
      <div class="timeline-item">
        <p class="timeline-year">19 Feb 1630</p>
        <p class="timeline-event"><strong>Shivaji Maharaj is born</strong> within the fort's walls — an event that would echo through centuries of Indian history.</p>
      </div>
      <div class="timeline-item">
        <p class="timeline-year">17th–18th Century</p>
        <p class="timeline-event">The fort changes hands between <strong>Mughal and Maratha</strong> forces multiple times, bearing witness to the wars that defined the Deccan.</p>
      </div>
      <div class="timeline-item">
        <p class="timeline-year">Present Day</p>
        <p class="timeline-event">Shivneri is a <strong>protected monument</strong> under the Archaeological Survey of India and an iconic pilgrimage site, visited by hundreds of thousands annually.</p>
      </div>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <p class="footer-logo">Shivneri Fort</p>
  <p>A tribute to the birthplace of Chhatrapati Shivaji Maharaj · Junnar, Pune, Maharashtra, India</p>
  <p style="margin-top:0.6rem; font-size:0.75rem;">Historical record · Educational reference · Created with reverence</p>
</footer>

<script>
  // Generate starfield
  const starsContainer = document.getElementById('stars');
  for (let i = 0; i < 120; i++) {
    const star = document.createElement('div');
    star.classList.add('star');
    const size = Math.random() * 2.5 + 0.5;
    star.style.cssText = `
      width: ${size}px;
      height: ${size}px;
      left: ${Math.random() * 100}%;
      top: ${Math.random() * 80}%;
      --d: ${(Math.random() * 3 + 2).toFixed(1)}s;
      animation-delay: ${(Math.random() * 4).toFixed(1)}s;
    `;
    starsContainer.appendChild(star);
  }

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));

  // Stagger timeline items
  document.querySelectorAll('.timeline-item').forEach((item, i) => {
    item.style.animationDelay = `${i * 0.12}s`;
  });
</script>
</body>
</html>
