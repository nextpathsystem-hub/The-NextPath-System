<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NextPath System — Éveiller. Orienter. Transformer.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #0D1B3E;
    --gold: #C9A84C;
    --cream: #F5F0E8;
    --gold-light: rgba(201,168,76,0.15);
    --gold-mid: rgba(201,168,76,0.35);
    --navy-light: rgba(13,27,62,0.85);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--navy);
    color: var(--cream);
    font-family: 'Montserrat', sans-serif;
    font-weight: 400;
    overflow-x: hidden;
  }

  /* TEXTURE */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      repeating-linear-gradient(135deg, rgba(255,255,255,0.012) 0px, transparent 2px, transparent 10px),
      repeating-linear-gradient(45deg, rgba(255,255,255,0.008) 0px, transparent 3px, transparent 12px);
    pointer-events: none;
    z-index: 0;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 20px 60px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(13,27,62,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(201,168,76,0.15);
  }

  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-weight: 700;
    color: var(--gold);
    letter-spacing: 0.04em;
    text-decoration: none;
  }

  .nav-logo span {
    color: var(--cream);
    font-weight: 400;
    font-style: italic;
  }

  .nav-links {
    display: flex;
    gap: 36px;
    list-style: none;
  }

  .nav-links a {
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: rgba(245,240,232,0.65);
    text-decoration: none;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--gold); }

  .nav-cta {
    background: var(--gold);
    color: var(--navy) !important;
    padding: 10px 22px;
    border-radius: 2px;
    font-weight: 600 !important;
    color: var(--navy) !important;
  }

  /* HERO */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 120px 60px 80px;
    overflow: hidden;
  }

  .hero::after {
    content: '';
    position: absolute;
    top: -20%;
    right: -10%;
    width: 600px;
    height: 600px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(201,168,76,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-frame {
    position: absolute;
    top: 40px; right: 40px; bottom: 40px; left: 40px;
    border: 1px solid rgba(201,168,76,0.12);
    border-radius: 4px;
    pointer-events: none;
  }

  .hero-content {
    position: relative;
    z-index: 1;
    max-width: 780px;
  }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 32px;
  }

  .hero-tag::before {
    content: '';
    display: block;
    width: 32px;
    height: 1px;
    background: var(--gold);
  }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(42px, 6vw, 76px);
    font-weight: 900;
    line-height: 1.1;
    color: var(--cream);
    margin-bottom: 12px;
  }

  .hero h1 em {
    color: var(--gold);
    font-style: italic;
  }

  .hero-sub {
    font-size: clamp(16px, 2vw, 20px);
    font-weight: 300;
    color: rgba(245,240,232,0.6);
    line-height: 1.7;
    margin-bottom: 48px;
    max-width: 560px;
  }

  .hero-actions {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }

  .btn-primary {
    display: inline-block;
    background: var(--gold);
    color: var(--navy);
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 16px 36px;
    border-radius: 2px;
    text-decoration: none;
    transition: all 0.25s;
  }

  .btn-primary:hover {
    background: var(--cream);
    transform: translateY(-2px);
  }

  .btn-secondary {
    display: inline-block;
    border: 1px solid rgba(201,168,76,0.4);
    color: var(--gold);
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 16px 36px;
    border-radius: 2px;
    text-decoration: none;
    transition: all 0.25s;
  }

  .btn-secondary:hover {
    border-color: var(--gold);
    background: var(--gold-light);
  }

  .hero-quote {
    position: absolute;
    bottom: 80px;
    right: 80px;
    max-width: 340px;
    text-align: right;
    z-index: 1;
  }

  .hero-quote p {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-style: italic;
    color: rgba(245,240,232,0.55);
    line-height: 1.6;
    margin-bottom: 8px;
  }

  .hero-quote cite {
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gold);
    opacity: 0.7;
  }

  /* SECTION BASE */
  section {
    position: relative;
    z-index: 1;
    padding: 100px 60px;
  }

  .section-tag {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-tag::before {
    content: '';
    display: block;
    width: 24px;
    height: 1px;
    background: var(--gold);
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(32px, 4vw, 52px);
    font-weight: 700;
    color: var(--cream);
    line-height: 1.15;
    margin-bottom: 24px;
  }

  .section-title em { color: var(--gold); font-style: italic; }

  .section-body {
    font-size: 15px;
    color: rgba(245,240,232,0.7);
    line-height: 1.85;
    max-width: 620px;
  }

  /* DIVIDER */
  .divider {
    width: 48px;
    height: 1.5px;
    background: var(--gold);
    margin: 28px 0;
    opacity: 0.6;
  }

  /* ABOUT */
  .about {
    background: rgba(201,168,76,0.04);
    border-top: 1px solid rgba(201,168,76,0.1);
    border-bottom: 1px solid rgba(201,168,76,0.1);
  }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
    max-width: 1100px;
    margin: 0 auto;
  }

  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
    margin-top: 48px;
  }

  .stat-box {
    border: 1px solid rgba(201,168,76,0.2);
    padding: 24px;
    border-radius: 2px;
  }

  .stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 36px;
    font-weight: 700;
    color: var(--gold);
    display: block;
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 12px;
    color: rgba(245,240,232,0.5);
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }

  .about-visual {
    position: relative;
    height: 480px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .about-card {
    background: rgba(201,168,76,0.06);
    border: 1px solid rgba(201,168,76,0.25);
    border-radius: 4px;
    padding: 40px;
    width: 100%;
    position: relative;
  }

  .about-card::before {
    content: '"';
    font-family: 'Playfair Display', serif;
    font-size: 100px;
    color: rgba(201,168,76,0.12);
    position: absolute;
    top: -20px;
    left: 24px;
    line-height: 1;
  }

  .about-card-text {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    font-style: italic;
    color: var(--cream);
    line-height: 1.65;
    margin-bottom: 24px;
  }

  .about-card-author {
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gold);
  }

  /* PILLARS */
  .pillars { max-width: 1100px; margin: 0 auto; }

  .pillars-header {
    text-align: center;
    margin-bottom: 64px;
  }

  .pillars-header .section-tag { justify-content: center; }
  .pillars-header .section-tag::before { display: none; }

  .pillars-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }

  .pillar-card {
    border: 1px solid rgba(201,168,76,0.18);
    padding: 40px 32px;
    border-radius: 2px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .pillar-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--gold);
    transform: scaleX(0);
    transition: transform 0.3s;
  }

  .pillar-card:hover {
    background: rgba(201,168,76,0.05);
    border-color: rgba(201,168,76,0.4);
  }

  .pillar-card:hover::after { transform: scaleX(1); }

  .pillar-num {
    font-family: 'Playfair Display', serif;
    font-size: 48px;
    font-weight: 700;
    color: rgba(201,168,76,0.15);
    line-height: 1;
    margin-bottom: 16px;
  }

  .pillar-title {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--gold);
    margin-bottom: 14px;
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }

  .pillar-text {
    font-size: 14px;
    color: rgba(245,240,232,0.65);
    line-height: 1.8;
  }

  /* PROGRAMME */
  .programme {
    background: linear-gradient(135deg, rgba(201,168,76,0.08) 0%, transparent 60%);
    border-top: 1px solid rgba(201,168,76,0.1);
  }

  .programme-inner {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
  }

  .programme-modules {
    display: flex;
    flex-direction: column;
    gap: 16px;
    margin-top: 40px;
  }

  .module {
    display: flex;
    gap: 20px;
    align-items: flex-start;
    padding: 20px;
    border: 1px solid rgba(201,168,76,0.12);
    border-radius: 2px;
    transition: all 0.25s;
  }

  .module:hover {
    border-color: rgba(201,168,76,0.35);
    background: rgba(201,168,76,0.04);
  }

  .module-week {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--gold);
    background: var(--gold-light);
    padding: 4px 10px;
    border-radius: 20px;
    white-space: nowrap;
    flex-shrink: 0;
    margin-top: 3px;
  }

  .module-content h4 {
    font-family: 'Playfair Display', serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--cream);
    margin-bottom: 6px;
  }

  .module-content p {
    font-size: 13px;
    color: rgba(245,240,232,0.6);
    line-height: 1.6;
  }

  .programme-info {
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-top: 40px;
  }

  .info-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 0;
    border-bottom: 1px solid rgba(201,168,76,0.1);
    font-size: 14px;
  }

  .info-row span:first-child {
    color: rgba(245,240,232,0.5);
    font-size: 12px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }

  .info-row span:last-child {
    color: var(--cream);
    font-weight: 500;
  }

  .programme-cta {
    margin-top: 40px;
    padding: 32px;
    border: 1px solid rgba(201,168,76,0.3);
    background: rgba(201,168,76,0.06);
    border-radius: 4px;
    text-align: center;
  }

  .programme-cta h3 {
    font-family: 'Playfair Display', serif;
    font-size: 24px;
    color: var(--gold);
    margin-bottom: 12px;
  }

  .programme-cta p {
    font-size: 14px;
    color: rgba(245,240,232,0.6);
    margin-bottom: 24px;
    line-height: 1.7;
  }

  /* TEST */
  .test-section {
    border-top: 1px solid rgba(201,168,76,0.1);
    border-bottom: 1px solid rgba(201,168,76,0.1);
  }

  .test-inner {
    max-width: 1100px;
    margin: 0 auto;
    text-align: center;
  }

  .test-inner .section-tag { justify-content: center; }
  .test-inner .section-tag::before { display: none; }

  .test-inner .section-title { margin: 0 auto 16px; }
  .test-inner .section-body { margin: 0 auto 48px; text-align: center; }

  .profiles-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin-bottom: 48px;
  }

  .profile-card {
    padding: 28px 20px;
    border: 1px solid rgba(201,168,76,0.15);
    border-radius: 2px;
    transition: all 0.25s;
  }

  .profile-card:hover {
    border-color: var(--gold);
    background: rgba(201,168,76,0.05);
  }

  .profile-icon {
    font-size: 28px;
    margin-bottom: 14px;
    display: block;
  }

  .profile-name {
    font-family: 'Playfair Display', serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--gold);
    margin-bottom: 8px;
  }

  .profile-desc {
    font-size: 12px;
    color: rgba(245,240,232,0.55);
    line-height: 1.7;
  }

  /* ABOUT GRACE */
  .grace-section {
    background: rgba(201,168,76,0.04);
  }

  .grace-inner {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }

  .grace-visual {
    position: relative;
    height: 420px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .grace-frame {
    width: 100%;
    height: 100%;
    border: 1px solid rgba(201,168,76,0.3);
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: rgba(201,168,76,0.04);
    gap: 16px;
    position: relative;
    overflow: hidden;
  }

  .grace-initials {
    font-family: 'Playfair Display', serif;
    font-size: 80px;
    font-weight: 700;
    color: rgba(201,168,76,0.25);
    line-height: 1;
  }

  .grace-name-tag {
    font-size: 13px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gold);
    border: 1px solid rgba(201,168,76,0.3);
    padding: 8px 20px;
    border-radius: 20px;
  }

  .grace-location {
    font-size: 12px;
    color: rgba(245,240,232,0.4);
    letter-spacing: 0.08em;
  }

  .tagline-box {
    margin-top: 32px;
    padding: 24px;
    border-left: 2px solid var(--gold);
    background: rgba(201,168,76,0.06);
  }

  .tagline-box p {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-style: italic;
    color: var(--cream);
    line-height: 1.65;
  }

  /* COMPARISON */
  .compare-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
    margin-top: 40px;
    max-width: 900px;
  }

  .compare-col {
    padding: 32px;
    border-radius: 2px;
  }

  .compare-col.others {
    border: 1px solid rgba(245,240,232,0.08);
    opacity: 0.6;
  }

  .compare-col.nextpath {
    border: 1px solid rgba(201,168,76,0.35);
    background: rgba(201,168,76,0.05);
  }

  .compare-col h4 {
    font-size: 12px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .compare-col.others h4 { color: rgba(245,240,232,0.4); }
  .compare-col.nextpath h4 { color: var(--gold); }

  .compare-item {
    display: flex;
    gap: 10px;
    align-items: flex-start;
    margin-bottom: 12px;
    font-size: 13px;
    line-height: 1.6;
  }

  .compare-item .marker {
    width: 16px;
    height: 16px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    font-size: 9px;
    margin-top: 2px;
  }

  .compare-col.others .marker {
    background: rgba(245,240,232,0.08);
    color: rgba(245,240,232,0.3);
  }

  .compare-col.nextpath .marker {
    background: var(--gold-light);
    color: var(--gold);
  }

  .compare-col.others .compare-item { color: rgba(245,240,232,0.5); }
  .compare-col.nextpath .compare-item { color: var(--cream); }

  /* CONTACT */
  .contact {
    border-top: 1px solid rgba(201,168,76,0.1);
    text-align: center;
  }

  .contact-inner {
    max-width: 700px;
    margin: 0 auto;
  }

  .social-links {
    display: flex;
    justify-content: center;
    gap: 16px;
    margin: 40px 0;
    flex-wrap: wrap;
  }

  .social-link {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 12px 24px;
    border: 1px solid rgba(201,168,76,0.25);
    border-radius: 2px;
    color: var(--cream);
    text-decoration: none;
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.06em;
    transition: all 0.2s;
  }

  .social-link:hover {
    border-color: var(--gold);
    color: var(--gold);
  }

  .social-link .platform {
    font-size: 11px;
    color: var(--gold);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .contact-email {
    font-size: 14px;
    color: rgba(245,240,232,0.5);
    margin-bottom: 48px;
  }

  .contact-email a {
    color: var(--gold);
    text-decoration: none;
  }

  /* FOOTER */
  footer {
    border-top: 1px solid rgba(201,168,76,0.1);
    padding: 32px 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 12px;
    color: rgba(245,240,232,0.3);
    position: relative;
    z-index: 1;
  }

  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 15px;
    color: var(--gold);
    font-weight: 700;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-content { animation: fadeUp 0.8s ease both; }
  .hero-quote { animation: fadeUp 0.8s ease 0.3s both; }

  /* MOBILE */
  @media (max-width: 768px) {
    nav { padding: 16px 24px; }
    .nav-links { display: none; }
    section { padding: 64px 24px; }
    .hero { padding: 100px 24px 60px; }
    .hero-quote { display: none; }
    .about-grid, .programme-inner, .grace-inner { grid-template-columns: 1fr; gap: 40px; }
    .pillars-grid { grid-template-columns: 1fr; }
    .profiles-grid { grid-template-columns: 1fr 1fr; }
    .compare-grid { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 12px; text-align: center; }
    .about-stats { grid-template-columns: 1fr 1fr; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">
    <img src="/mnt/user-data/uploads/Use_AI_Image_Apr_7__2026__15_56_42.png" alt="NextPath System Logo" style="height:36px;width:auto;vertical-align:middle;margin-right:10px;filter:brightness(1.1);">
    NextPath<span> System</span>
  </a>
  <ul class="nav-links">
    <li><a href="#about">À propos</a></li>
    <li><a href="#pillars">Notre approche</a></li>
    <li><a href="#programme">The Grace Effect</a></li>
    <li><a href="#test">NextPath Test</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#programme" class="nav-cta">Rejoindre</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-frame"></div>
  <div class="hero-content">
    <div class="hero-tag">NextPath System · Jeunesse Africaine</div>
    <h1>Tu as plus de valeur<br>que tu ne <em>le crois.</em></h1>
    <p class="hero-sub">
      Une plateforme dédiée à la jeunesse africaine pour se connaître, explorer son potentiel et construire un chemin qui lui ressemble vraiment.
    </p>
    <div class="hero-actions">
      <a href="#test" class="btn-primary">Passer le NextPath Test</a>
      <a href="#programme" class="btn-secondary">The Grace Effect</a>
    </div>
  </div>
  <div class="hero-quote">
    <p>"Un jeune qui se connaît ne se perd jamais."</p>
    <cite>— Grace Kabondo, Fondatrice</cite>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-grid">
    <div>
      <div class="section-tag">Notre mission</div>
      <h2 class="section-title">Éveiller.<br><em>Orienter.</em><br>Transformer.</h2>
      <div class="divider"></div>
      <p class="section-body">
        La jeunesse africaine a un potentiel immense. Mais personne ne lui a appris à le voir, à le nommer, à le construire. NextPath System comble ce vide — avec du contenu, des outils concrets et un accompagnement réel. En ligne. En présentiel. Pour la jeunesse en RDC et dans la diaspora.
      </p>
      <div class="about-stats">
        <div class="stat-box">
          <span class="stat-number">230M</span>
          <span class="stat-label">Jeunes en Afrique subsaharienne</span>
        </div>
        <div class="stat-box">
          <span class="stat-number">1M</span>
          <span class="stat-label">Jeunes visés d'ici 2026</span>
        </div>
        <div class="stat-box">
          <span class="stat-number">10</span>
          <span class="stat-label">Pays africains ciblés</span>
        </div>
        <div class="stat-box">
          <span class="stat-number">4</span>
          <span class="stat-label">Semaines pour transformer ta trajectoire</span>
        </div>
      </div>
    </div>
    <div class="about-visual">
      <div class="about-card">
        <div class="about-card-text">
          "NextPath System n'oriente pas les jeunes, il les réveille."
        </div>
        <div class="about-card-author">Grace Kabondo · Fondatrice & CEO</div>
      </div>
    </div>
  </div>
</section>

<!-- PILLARS -->
<section id="pillars">
  <div class="pillars">
    <div class="pillars-header">
      <div class="section-tag">Notre approche</div>
      <h2 class="section-title">Le Cycle NextPath</h2>
      <p class="section-body" style="margin: 0 auto; text-align: center;">
        Un parcours intégré en 3 étapes pour transformer la découverte de soi en impact concret.
      </p>
    </div>
    <div class="pillars-grid">
      <div class="pillar-card">
        <div class="pillar-num">01</div>
        <div class="pillar-title">Connais-toi</div>
        <p class="pillar-text">Découvre ta personnalité, tes forces naturelles et tes valeurs profondes grâce au NextPath Test. Ce que tu es naturellement — pas ce qu'on t'a dit d'être.</p>
      </div>
      <div class="pillar-card">
        <div class="pillar-num">02</div>
        <div class="pillar-title">Libère-toi</div>
        <p class="pillar-text">Identifie ce qui te bloque — pression familiale, peur du jugement, croyances limitantes. Comprendre le frein, c'est déjà commencer à le dépasser.</p>
      </div>
      <div class="pillar-card">
        <div class="pillar-num">03</div>
        <div class="pillar-title">Construis-toi</div>
        <p class="pillar-text">Passe à l'action avec des outils concrets, un plan clair et une communauté qui avance avec toi. Pas juste de l'inspiration — des résultats mesurables.</p>
      </div>
    </div>

    <div style="margin-top: 60px;">
      <h3 class="section-title" style="font-size: 28px; margin-bottom: 24px;">Ce qui nous différencie</h3>
      <div class="compare-grid">
        <div class="compare-col others">
          <h4>Les autres</h4>
          <div class="compare-item"><div class="marker">✕</div><span>Tests psychométriques froids et académiques</span></div>
          <div class="compare-item"><div class="marker">✕</div><span>Coaching individuel coûteux et inaccessible</span></div>
          <div class="compare-item"><div class="marker">✕</div><span>Discours motivationnels temporaires</span></div>
          <div class="compare-item"><div class="marker">✕</div><span>Contenu générique, déconnecté du contexte africain</span></div>
        </div>
        <div class="compare-col nextpath">
          <h4>NextPath System</h4>
          <div class="compare-item"><div class="marker">✓</div><span>Approche humaine, culturelle et spirituelle de la connaissance de soi</span></div>
          <div class="compare-item"><div class="marker">✓</div><span>Programmes collectifs accessibles, hybrides (en ligne + présentiel)</span></div>
          <div class="compare-item"><div class="marker">✓</div><span>Transformation mesurable sur 4 à 8 semaines</span></div>
          <div class="compare-item"><div class="marker">✓</div><span>Ancré dans la réalité de la RDC et de la diaspora africaine</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROGRAMME -->
<section class="programme" id="programme">
  <div class="programme-inner">
    <div>
      <div class="section-tag">Programme phare</div>
      <h2 class="section-title">The <em>Grace Effect</em></h2>
      <div class="divider"></div>
      <p class="section-body">
        En 4 semaines, tu sais qui tu es, tu comprends ce qui te bloque, et tu repars avec un plan concret pour construire ton chemin. Pas juste de la motivation — une transformation réelle.
      </p>
      <div class="programme-modules">
        <div class="module">
          <span class="module-week">Semaine 1</span>
          <div class="module-content">
            <h4>Qui es-tu vraiment ?</h4>
            <p>Découverte de ton profil NextPath, tes forces naturelles et tes valeurs fondamentales.</p>
          </div>
        </div>
        <div class="module">
          <span class="module-week">Semaine 2</span>
          <div class="module-content">
            <h4>Qu'est-ce qui te bloque ?</h4>
            <p>Identification de tes 5 blocages principaux et outils concrets pour commencer à t'en libérer.</p>
          </div>
        </div>
        <div class="module">
          <span class="module-week">Semaine 3</span>
          <div class="module-content">
            <h4>Comment construire ton chemin ?</h4>
            <p>Méthode NextPath pour connecter tes forces à un chemin académique ou professionnel concret.</p>
          </div>
        </div>
        <div class="module">
          <span class="module-week">Semaine 4</span>
          <div class="module-content">
            <h4>Ton plan pour avancer</h4>
            <p>Construction de ton plan d'action sur 90 jours — clair, réaliste, ancré dans qui tu es.</p>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div class="programme-info">
        <div class="info-row">
          <span>Format</span>
          <span>100% en ligne · Sessions de groupe</span>
        </div>
        <div class="info-row">
          <span>Durée</span>
          <span>4 semaines · 90 min/session</span>
        </div>
        <div class="info-row">
          <span>Participants</span>
          <span>15 places maximum</span>
        </div>
        <div class="info-row">
          <span>Cible</span>
          <span>15 à 35 ans · RDC & Diaspora</span>
        </div>
        <div class="info-row">
          <span>Plateforme</span>
          <span>Zoom · Groupe WhatsApp privé</span>
        </div>
        <div class="info-row">
          <span>Lancement</span>
          <span>Mai 2026 · Première cohorte</span>
        </div>
      </div>
      <div class="programme-cta">
        <h3>Rejoins The Grace Effect</h3>
        <p>15 places disponibles pour la première cohorte. Prix de lancement accessible. Ne laisse pas ta place à quelqu'un d'autre.</p>
        <a href="mailto:nextpathsystem@gmail.com" class="btn-primary">Réserver ma place</a>
      </div>
    </div>
  </div>
</section>

<!-- TEST -->
<section class="test-section" id="test">
  <div class="test-inner">
    <div class="section-tag">Outil gratuit</div>
    <h2 class="section-title">Le <em>NextPath Test</em></h2>
    <p class="section-body">
      20 questions. 10 minutes. Un portrait complet de qui tu es — ta personnalité, tes forces naturelles, tes blocages et les directions qui t'correspondent vraiment.
    </p>
    <div class="profiles-grid">
      <div class="profile-card">
        <span class="profile-icon">🧠</span>
        <div class="profile-name">L'Éclaireur</div>
        <p class="profile-desc">Analytique, rigoureux(se), expert(e). Sciences, recherche, enseignement.</p>
      </div>
      <div class="profile-card">
        <span class="profile-icon">🌐</span>
        <div class="profile-name">Le Connecteur</div>
        <p class="profile-desc">Communicant(e), fédérateur(trice). Médias, diplomatie, entrepreneuriat social.</p>
      </div>
      <div class="profile-card">
        <span class="profile-icon">🏗️</span>
        <div class="profile-name">Le Bâtisseur</div>
        <p class="profile-desc">Déterminé(e), orienté(e) résultats. Entrepreneuriat, management, commerce.</p>
      </div>
      <div class="profile-card">
        <span class="profile-icon">🌱</span>
        <div class="profile-name">Le Semeur</div>
        <p class="profile-desc">Créatif(ve), humain(e), porteur de sens. Éducation, santé, social, arts.</p>
      </div>
    </div>
    <a href="https://forms.gle/jc4x5bEjDUYNAW5" class="btn-primary" target="_blank">Passer le test gratuitement</a>
  </div>
</section>

<!-- GRACE -->
<section class="grace-section" id="grace">
  <div class="grace-inner">
    <div class="grace-visual">
      <div class="grace-frame">
        <img src="/mnt/user-data/uploads/Use_AI_Image_Apr_7__2026__15_56_42.png"
             alt="Logo NextPath System"
             style="width:140px;height:auto;margin-bottom:20px;opacity:.9;" />
        <div class="grace-name-tag">Grace Kabondo</div>
        <div class="grace-location">Nantes, France · Fondatrice NextPath System</div>
        <div style="margin-top:12px;display:flex;gap:8px;flex-wrap:wrap;justify-content:center;padding:0 20px;">
          <span style="font-size:10px;padding:3px 10px;border:1px solid rgba(201,168,76,0.3);border-radius:20px;color:rgba(201,168,76,0.8);">MSc Sciences du Médicament</span>
          <span style="font-size:10px;padding:3px 10px;border:1px solid rgba(201,168,76,0.3);border-radius:20px;color:rgba(201,168,76,0.8);">Nantes Université</span>
        </div>
      </div>
    </div>
    <div>
      <div class="section-tag">La fondatrice</div>
      <h2 class="section-title">Je suis passée<br>par là, <em>moi aussi.</em></h2>
      <div class="divider"></div>
      <p class="section-body">
        J'ai grandi à Lubumbashi, en RDC. Toute ma scolarité là-bas — le système, la pression, les choix imposés, les questions sans réponses. Le jour où j'ai quitté le Congo, j'ai réalisé une chose brutale : personne ne m'avait appris à me connaître. À savoir ce que je valais vraiment.
      </p>
      <div class="tagline-box" style="margin-top: 28px;">
        <p>"NextPath System c'est ce que j'aurais voulu avoir à 17 ans. C'est ce que je construis aujourd'hui — pour toi."</p>
      </div>
      <div style="display:flex;flex-direction:column;gap:12px;margin-top:32px;">
        <div style="padding:16px 20px;border:1px solid rgba(201,168,76,0.15);border-radius:2px;">
          <div style="font-size:11px;color:var(--gold);letter-spacing:.1em;text-transform:uppercase;margin-bottom:6px;">Formation</div>
          <div style="font-size:14px;color:var(--cream);line-height:1.6;">MSc Sciences du Médicament<br><span style="font-size:12px;color:rgba(245,240,232,0.5);">Nantes Université · France</span></div>
        </div>
        <div style="padding:16px 20px;border:1px solid rgba(201,168,76,0.15);border-radius:2px;">
          <div style="font-size:11px;color:var(--gold);letter-spacing:.1em;text-transform:uppercase;margin-bottom:10px;">Expériences</div>
          <div style="display:flex;flex-direction:column;gap:10px;">
            <div style="font-size:13px;color:var(--cream);line-height:1.5;">
              <span style="color:var(--gold);font-weight:500;">Analytical Chemist</span><br>
              <span style="font-size:12px;color:rgba(245,240,232,0.5);">CentraleSupélec · Stage · 2026</span>
            </div>
            <div style="font-size:13px;color:var(--cream);line-height:1.5;">
              <span style="color:var(--gold);font-weight:500;">Biomedical Lab Technician</span><br>
              <span style="font-size:12px;color:rgba(245,240,232,0.5);">Grand Labo de Lubumbashi · 2025</span>
            </div>
            <div style="font-size:13px;color:var(--cream);line-height:1.5;">
              <span style="color:var(--gold);font-weight:500;">Molecular Biologist</span><br>
              <span style="font-size:12px;color:rgba(245,240,232,0.5);">INRB · Kinshasa · 2024</span>
            </div>
          </div>
        </div>
        <div style="padding:16px 20px;border:1px solid rgba(201,168,76,0.15);border-radius:2px;">
          <div style="font-size:11px;color:var(--gold);letter-spacing:.1em;text-transform:uppercase;margin-bottom:6px;">Contact</div>
          <div style="font-size:14px;color:var(--cream);">nextpathsystem@gmail.com</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-inner">
    <div class="section-tag" style="justify-content: center;">
      <span style="display:none;"></span>Rejoins le mouvement
    </div>
    <h2 class="section-title">Ensemble,<br>on <em>construit</em> une génération.</h2>
    <div class="divider" style="margin: 28px auto;"></div>
    <p class="section-body" style="text-align: center; margin: 0 auto 40px;">
      Que tu sois étudiant(e) en RDC, membre de la diaspora ou partenaire institutionnel — il y a une place pour toi dans le mouvement NextPath System.
    </p>
    <div class="social-links">
      <a href="https://instagram.com/nextpath.system" target="_blank" class="social-link">
        <span class="platform">Instagram</span>
        <span>@nextpath.system</span>
      </a>
      <a href="https://www.youtube.com/@TheNextPathSystem" target="_blank" class="social-link">
        <span class="platform">YouTube</span>
        <span>The NextPath System</span>
      </a>
      <a href="https://tiktok.com/@nextpath.system" target="_blank" class="social-link">
        <span class="platform">TikTok</span>
        <span>@nextpath.system</span>
      </a>
    </div>
    <p class="contact-email">
      Pour toute collaboration ou question : <a href="mailto:nextpathsystem@gmail.com">nextpathsystem@gmail.com</a>
    </p>
    <a href="#programme" class="btn-primary">Rejoindre The Grace Effect</a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">NextPath System</div>
  <div>Éveiller · Orienter · Transformer · © 2026</div>
  <div>Fondé par Grace Kabondo · Nantes, France</div>
</footer>

</body>
</html>
