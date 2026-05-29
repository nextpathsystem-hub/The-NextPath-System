<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NextPath System</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{--navy:#0D1B3E;--gold:#C9A84C;--cream:#F5F0E8;--light:#F8F7F4;--dark:#1A1A2E;--mid:#4A4A6A;--light-text:#8A8AAA;--border:#E8E4DC;--gold-bg:rgba(201,168,76,0.12);}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:#fff;color:var(--dark);font-family:'Montserrat',sans-serif;font-size:15px;line-height:1.7;}
nav{position:fixed;top:0;left:0;right:0;z-index:200;background:rgba(255,255,255,0.97);backdrop-filter:blur(12px);border-bottom:1px solid var(--border);padding:0 40px;height:70px;display:flex;align-items:center;justify-content:space-between;}
.nav-logo{display:flex;align-items:center;gap:10px;text-decoration:none;flex-shrink:0;cursor:pointer;}
.nav-logo span{font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--navy);}
.nav-links{display:flex;gap:0;list-style:none;align-items:center;}
.nav-links a{font-size:11px;font-weight:500;letter-spacing:.07em;text-transform:uppercase;color:var(--mid);text-decoration:none;padding:0 12px;height:70px;display:flex;align-items:center;border-bottom:2px solid transparent;transition:all .2s;}
.nav-links a:hover{color:var(--navy);border-bottom-color:var(--gold);}
.nav-cta{background:var(--navy)!important;color:#fff!important;border-bottom-color:transparent!important;padding:9px 18px!important;height:auto!important;border-radius:2px;margin-left:8px;}
.nav-cta:hover{background:var(--gold)!important;color:var(--navy)!important;}
.lang-switcher{display:flex;gap:4px;margin-left:8px;}
.lang-btn{font-size:11px;font-weight:600;padding:4px 8px;border-radius:2px;cursor:pointer;border:1px solid var(--border);background:transparent;color:var(--light-text);transition:all .15s;}
.lang-btn.active{background:var(--navy);color:#fff;border-color:var(--navy);}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:8px;background:none;border:none;}
.hamburger span{display:block;width:22px;height:2px;background:var(--navy);border-radius:1px;}
.mobile-menu{display:none;position:fixed;top:70px;left:0;right:0;z-index:199;background:#fff;border-bottom:1px solid var(--border);padding:16px 24px;flex-direction:column;gap:0;box-shadow:0 8px 24px rgba(0,0,0,.08);}
.mobile-menu.open{display:flex;}
.mobile-menu a{font-size:13px;font-weight:500;letter-spacing:.06em;text-transform:uppercase;color:var(--dark);text-decoration:none;padding:12px 0;border-bottom:1px solid var(--border);display:block;cursor:pointer;}
.page{min-height:100vh;padding-top:70px;display:none;}
.page.active{display:block;}
.hero{min-height:calc(100vh - 70px);display:grid;grid-template-columns:1fr 1fr;align-items:stretch;overflow:hidden;}
.hero-left{padding:80px 60px 80px 80px;display:flex;flex-direction:column;justify-content:center;}
.hero-tag{display:inline-flex;align-items:center;gap:10px;font-size:11px;font-weight:600;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);margin-bottom:28px;}
.hero-tag::before{content:'';display:block;width:28px;height:1.5px;background:var(--gold);}
.hero h1{font-family:'Playfair Display',serif;font-size:clamp(32px,4vw,56px);font-weight:900;line-height:1.1;color:var(--navy);margin-bottom:20px;}
.hero h1 em{color:var(--gold);font-style:italic;}
.hero-sub{font-size:15px;color:var(--mid);line-height:1.8;margin-bottom:40px;max-width:460px;}
.hero-actions{display:flex;gap:14px;flex-wrap:wrap;margin-bottom:48px;}
.btn{display:inline-flex;align-items:center;justify-content:center;gap:8px;font-size:11px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;padding:14px 28px;border-radius:2px;text-decoration:none;transition:all .25s;border:2px solid transparent;cursor:pointer;}
.btn-navy{background:var(--navy);color:#fff;border-color:var(--navy);}
.btn-navy:hover{background:var(--gold);border-color:var(--gold);color:var(--navy);}
.btn-outline{border-color:var(--navy);color:var(--navy);background:transparent;}
.btn-outline:hover{background:var(--navy);color:#fff;}
.btn-gold{background:var(--gold);color:var(--navy);border-color:var(--gold);}
.btn-gold:hover{background:var(--navy);border-color:var(--navy);color:#fff;}
.hero-quote{padding:22px 26px;border-left:3px solid var(--gold);background:var(--light);border-radius:0 4px 4px 0;max-width:420px;}
.hero-quote p{font-family:'Playfair Display',serif;font-size:15px;font-style:italic;color:var(--navy);line-height:1.65;margin-bottom:8px;}
.hero-quote cite{font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);}
.hero-right{background:var(--navy);display:flex;align-items:center;justify-content:center;padding:60px 48px;}
.hero-right-content{text-align:center;}
.hero-right-content .line{width:48px;height:1.5px;background:rgba(201,168,76,0.4);margin:24px auto;}
.hero-right-content h2{font-family:'Playfair Display',serif;font-size:clamp(20px,2.5vw,30px);font-weight:700;color:var(--gold);line-height:1.3;}
.stats-strip{background:var(--navy);border-top:3px solid var(--gold);padding:52px 80px;}
.stats-inner{max-width:900px;margin:0 auto;display:flex;align-items:center;justify-content:center;}
.stat-col{flex:1;text-align:left;padding:0 48px;border-right:1px solid rgba(201,168,76,0.2);}
.stat-col:last-child{border-right:none;}
.stat-col:first-child{padding-left:0;}
.stat-num{font-family:'Playfair Display',serif;font-size:48px;font-weight:900;color:var(--gold);display:block;line-height:1;}
.stat-lbl{font-size:11px;color:rgba(245,240,232,0.6);letter-spacing:.08em;text-transform:uppercase;margin-top:8px;display:block;}
.section{padding:96px 80px;}
.container{max-width:1140px;margin:0 auto;}
.stag{display:inline-flex;align-items:center;gap:10px;font-size:11px;font-weight:600;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);margin-bottom:16px;}
.stag::before{content:'';display:block;width:24px;height:1.5px;background:var(--gold);}
h2.stitle{font-family:'Playfair Display',serif;font-size:clamp(26px,3.5vw,44px);font-weight:700;color:var(--navy);line-height:1.15;margin-bottom:20px;}
h2.stitle em{color:var(--gold);font-style:italic;}
.sbody{font-size:15px;color:var(--mid);line-height:1.85;max-width:580px;}
.divider{width:48px;height:2px;background:var(--gold);margin:24px 0;opacity:.7;}
.pillars-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;margin-top:48px;}
.pillar-card{background:#fff;border:1px solid var(--border);border-radius:4px;padding:40px 32px;transition:all .3s;border-top:3px solid transparent;}
.pillar-card:hover{border-top-color:var(--gold);box-shadow:0 8px 32px rgba(13,27,62,.08);transform:translateY(-4px);}
.pnum{font-family:'Playfair Display',serif;font-size:52px;font-weight:900;color:var(--gold);line-height:1;margin-bottom:16px;}
.ptitle{font-family:'Playfair Display',serif;font-size:20px;font-weight:700;color:var(--navy);margin-bottom:12px;text-transform:uppercase;letter-spacing:.04em;}
.ptext{font-size:14px;color:var(--mid);line-height:1.8;}
.yt-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px;margin-top:40px;}
.yt-card{border:1px solid var(--border);border-radius:4px;overflow:hidden;transition:all .25s;text-decoration:none;display:block;background:#fff;}
.yt-card:hover{border-color:var(--gold);box-shadow:0 8px 24px rgba(13,27,62,.1);transform:translateY(-3px);}
.yt-thumb{position:relative;aspect-ratio:16/9;overflow:hidden;background:var(--navy);display:flex;align-items:center;justify-content:center;}
.yt-play{width:48px;height:48px;border-radius:50%;background:rgba(201,168,76,0.9);display:flex;align-items:center;justify-content:center;transition:transform .2s;}
.yt-card:hover .yt-play{transform:scale(1.1);}
.yt-play::after{content:'';border-style:solid;border-width:8px 0 8px 16px;border-color:transparent transparent transparent var(--navy);margin-left:3px;}
.yt-info{padding:16px;}
.yt-title{font-size:13px;font-weight:600;color:var(--dark);line-height:1.5;margin-bottom:6px;}
.yt-meta{font-size:11px;color:var(--light-text);}
.bitem{display:flex;gap:12px;align-items:flex-start;font-size:14px;color:var(--mid);line-height:1.6;margin-bottom:10px;}
.bdot{width:20px;height:20px;border-radius:50%;background:var(--gold-bg);border:1px solid var(--gold);display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:2px;font-size:10px;color:var(--gold);}
.profile-card{padding:28px 20px;border:1px solid var(--border);border-radius:4px;text-align:center;transition:all .25s;}
.profile-card:hover{border-color:var(--gold);background:var(--gold-bg);}
.picon{font-size:28px;margin-bottom:12px;display:block;}
.pname{font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;}

/* PDF GRID STYLES */
.pdf-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:20px;margin-top:32px;}
.pdf-card{border:1px solid var(--border);border-radius:4px;padding:24px;display:flex;gap:16px;align-items:flex-start;transition:all .25s;text-decoration:none;background:#fff;}
.pdf-card:hover{border-color:var(--gold);box-shadow:0 6px 20px rgba(13,27,62,.08);transform:translateY(-2px);}
.pdf-card.bientot{opacity:.65;cursor:default;pointer-events:none;}
.pdf-icon{width:44px;height:44px;border-radius:8px;background:var(--navy);display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0;}
.pdf-title{font-size:14px;font-weight:700;color:var(--dark);line-height:1.4;margin-bottom:4px;}
.pdf-desc{font-size:12px;color:var(--light-text);line-height:1.6;margin-bottom:8px;}
.pdf-dl{display:inline-flex;align-items:center;gap:6px;font-size:11px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--gold);}
.pdf-badge{font-size:9px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:#C9A84C;margin-bottom:4px;display:block;}

/* AVIS */
.avis-card{background:#fff;border:1px solid var(--border);border-radius:4px;padding:32px;border-top:3px solid var(--gold);}
.stars{color:var(--gold);font-size:14px;margin-bottom:14px;}
.grace-grid{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:start;}
.grace-photo{position:relative;border-radius:4px;overflow:hidden;aspect-ratio:4/5;box-shadow:0 20px 60px rgba(13,27,62,.15);}
.grace-photo img{width:100%;height:100%;object-fit:cover;object-position:center top;}
.quote-box{margin-top:28px;padding:22px 26px;border-left:3px solid var(--gold);background:var(--light);}
.quote-box p{font-family:'Playfair Display',serif;font-size:16px;font-style:italic;color:var(--navy);line-height:1.65;}
.slink{display:flex;align-items:center;gap:16px;padding:14px 18px;border:1px solid var(--border);border-radius:4px;text-decoration:none;transition:all .2s;color:var(--dark);margin-bottom:10px;}
.slink:hover{border-color:var(--navy);background:rgba(13,27,62,.04);}
.splat{font-size:10px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--gold);min-width:70px;}
.shandle{font-size:14px;font-weight:500;color:var(--dark);}
footer{background:var(--navy);padding:40px 80px;display:flex;justify-content:space-between;align-items:center;border-top:3px solid var(--gold);flex-wrap:wrap;gap:16px;}
.flogo{font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--gold);}
.flinks{display:flex;gap:20px;flex-wrap:wrap;}
.flinks a{font-size:11px;color:rgba(245,240,232,.5);text-decoration:none;letter-spacing:.06em;transition:color .2s;cursor:pointer;}
.flinks a:hover{color:var(--gold);}
.fcopy{font-size:11px;color:rgba(245,240,232,.3);letter-spacing:.06em;}

/* ADMIN PANEL */
#admin-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.88);z-index:9999;overflow-y:auto;}
.admin-box{background:#fff;max-width:780px;margin:40px auto;border-radius:8px;padding:48px;position:relative;}
.admin-close{position:absolute;top:20px;right:20px;background:#f0f0f0;border:none;padding:8px 16px;border-radius:4px;cursor:pointer;font-size:13px;font-weight:600;}
.admin-title{font-family:'Playfair Display',serif;color:var(--navy);font-size:26px;margin-bottom:6px;}
.admin-sub{font-size:13px;color:var(--mid);margin-bottom:32px;}
.admin-section{margin-bottom:36px;padding-bottom:36px;border-bottom:1px solid var(--border);}
.admin-section:last-child{border-bottom:none;margin-bottom:0;padding-bottom:0;}
.admin-section h3{font-family:'Playfair Display',serif;font-size:18px;color:var(--navy);margin-bottom:16px;}
.admin-label{display:block;font-size:11px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--mid);margin-bottom:6px;}
.admin-input{width:100%;padding:10px 14px;border:1px solid var(--border);border-radius:4px;font-family:inherit;font-size:13px;outline:none;margin-bottom:10px;transition:border-color .2s;}
.admin-input:focus{border-color:var(--gold);}
.admin-select{width:100%;padding:10px 14px;border:1px solid var(--border);border-radius:4px;font-family:inherit;font-size:13px;outline:none;margin-bottom:10px;background:#fff;}
.admin-btn{background:var(--navy);color:#fff;border:none;padding:11px 24px;border-radius:4px;cursor:pointer;font-size:12px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;transition:background .2s;}
.admin-btn:hover{background:var(--gold);color:var(--navy);}
.admin-msg{display:none;font-size:13px;color:var(--gold);font-weight:600;margin-top:10px;}
.admin-list{margin-top:16px;}
.admin-item{display:flex;align-items:center;gap:10px;padding:10px 14px;border:1px solid var(--border);border-radius:4px;margin-bottom:8px;font-size:13px;}
.admin-item-title{flex:1;font-weight:600;color:var(--dark);}
.admin-item-link{font-size:11px;color:var(--mid);max-width:200px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}
.admin-del{background:#fee;border:1px solid #fcc;color:#c00;border-radius:3px;padding:4px 8px;font-size:11px;cursor:pointer;}

@media(max-width:768px){
  nav{padding:0 20px;}
  .nav-links{display:none;}
  .hamburger{display:flex;}
  .hero{grid-template-columns:1fr;min-height:auto;}
  .hero-left{padding:40px 24px;}
  .hero-right{min-height:200px;padding:40px 24px;}
  .stats-strip{padding:40px 24px;}
  .stats-inner{flex-direction:column;gap:28px;padding:0;}
  .stat-col{border-right:none;border-bottom:1px solid rgba(201,168,76,.2);padding:0 0 24px;text-align:center;}
  .stat-col:last-child{border-bottom:none;padding-bottom:0;}
  .section{padding:56px 24px;}
  .pillars-grid,.yt-grid,.pdf-grid{grid-template-columns:1fr;}
  .grace-grid{grid-template-columns:1fr;gap:32px;}
  footer{padding:32px 24px;flex-direction:column;text-align:center;}
  .flinks{justify-content:center;}
  .hero-actions{flex-direction:column;}
  .btn{width:100%;justify-content:center;}
  .admin-box{margin:16px;padding:28px;}
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo" onclick="go('home')">
    <span>NextPath System</span>
  </div>
  <ul class="nav-links">
    <li><a href="#" onclick="go('home')">Accueil</a></li>
    <li><a href="#" onclick="go('mission')">Notre mission</a></li>
    <li><a href="#" onclick="go('programmes')">Devenir membre</a></li>
    <li><a href="#" onclick="go('ressources')">Nos ressources</a></li>
    <li><a href="#" onclick="go('avis')">Avis</a></li>
    <li><a href="#" onclick="go('opportunites')">Opportunités</a></li>
    <li><a href="#" onclick="go('grace')">À propos</a></li>
    <li><a href="#" onclick="go('contact')">Contact</a></li>
    <li><a href="https://tally.so/r/81Jey5" target="_blank" class="nav-cta">Rejoindre</a></li>
    <li>
      <div class="lang-switcher">
        <button class="lang-btn active" id="btn-fr" onclick="setLang('fr')">FR</button>
        <button class="lang-btn" id="btn-en" onclick="setLang('en')">EN</button>
      </div>
    </li>
  </ul>
  <button class="hamburger" onclick="toggleMenu()"><span></span><span></span><span></span></button>
</nav>

<div class="mobile-menu" id="mobile-menu">
  <a onclick="go('home');toggleMenu()">Accueil</a>
  <a onclick="go('mission');toggleMenu()">Notre mission</a>
  <a onclick="go('programmes');toggleMenu()">Devenir membre</a>
  <a onclick="go('ressources');toggleMenu()">Nos ressources</a>
  <a onclick="go('avis');toggleMenu()">Avis</a>
  <a onclick="go('opportunites');toggleMenu()">Opportunités</a>
  <a onclick="go('grace');toggleMenu()">À propos</a>
  <a onclick="go('contact');toggleMenu()">Contact</a>
  <a href="https://tally.so/r/81Jey5" target="_blank" style="color:var(--gold);font-weight:700;">Rejoindre</a>
  <div style="display:flex;gap:8px;padding:12px 0;">
    <button class="lang-btn active" onclick="setLang('fr')">FR</button>
    <button class="lang-btn" onclick="setLang('en')">EN</button>
  </div>
</div>

<!-- ══ ACCUEIL ══ -->
<div class="page active" id="page-home">
  <div class="hero">
    <div class="hero-left">
      <div class="hero-tag">NextPath System · Pour la Jeunesse Africaine</div>
      <h1>Tu as plus de valeur<br>que tu ne <em>le crois.</em></h1>
      <p class="hero-sub">Une plateforme dédiée à la jeunesse africaine — 15 à 30 ans — pour se connaître, explorer son potentiel et construire un chemin qui lui ressemble vraiment.</p>
      <div class="hero-actions">
        <a href="https://tally.so/r/ZjGJQB" target="_blank" class="btn btn-navy">Rejoindre The Grace Effect</a>
        <a href="#" onclick="go('programmes')" class="btn btn-outline">Devenir membre</a>
      </div>
      <div class="hero-quote">
        <p>"Un jeune qui se connaît ne se perd jamais."</p>
        <cite>— Grace Kabondo, Fondatrice</cite>
      </div>
    </div>
    <div class="hero-right">
      <div class="hero-right-content">
        <div class="line"></div>
        <h2>Devenir la référence<br>de la jeunesse africaine</h2>
        <div class="line"></div>
      </div>
    </div>
  </div>

  <div class="stats-strip">
    <div class="stats-inner">
      <div class="stat-col">
        <span class="stat-num">300+</span>
        <span class="stat-lbl">Jeunes dans la communauté d'ici 2028</span>
      </div>
      <div class="stat-col">
        <span class="stat-num">15–30</span>
        <span class="stat-lbl">Tranche d'âge prioritaire</span>
      </div>
      <div class="stat-col">
        <span class="stat-num">2</span>
        <span class="stat-lbl">Programmes en cours de création</span>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="container">
      <div style="text-align:center;margin-bottom:56px;">
        <div class="stag" style="justify-content:center;">Notre approche</div>
        <h2 class="stitle" style="text-align:center;">Le Cycle NextPath</h2>
        <p class="sbody" style="margin:0 auto;text-align:center;">Trois étapes concrètes pour transformer la découverte de soi en chemin d'action.</p>
      </div>
      <div class="pillars-grid">
        <div class="pillar-card">
          <div class="pnum">01</div>
          <div class="ptitle">Connais-toi</div>
          <p class="ptext">Découvre ta personnalité, tes forces naturelles et tes valeurs profondes. Ce que tu es naturellement — pas ce qu'on t'a dit d'être.</p>
        </div>
        <div class="pillar-card">
          <div class="pnum">02</div>
          <div class="ptitle">Libère-toi</div>
          <p class="ptext">Identifie ce qui te bloque — pression familiale, peur du jugement, croyances limitantes. Comprendre le frein, c'est déjà commencer à le dépasser.</p>
        </div>
        <div class="pillar-card">
          <div class="pnum">03</div>
          <div class="ptitle">Construis-toi</div>
          <p class="ptext">Passe à l'action avec des outils concrets et une communauté qui avance avec toi. Pas juste de l'inspiration — des résultats réels.</p>
        </div>
      </div>
      <div style="text-align:center;margin-top:48px;">
        <a href="#" onclick="go('mission')" class="btn btn-outline">En savoir plus sur notre mission</a>
      </div>
    </div>
  </div>
</div>

<!-- ══ MISSION ══ -->
<div class="page" id="page-mission">
  <div class="section" style="padding-top:80px;">
    <div class="container">
      <div class="stag">Notre mission</div>
      <h2 class="stitle">NextPath System est né d'une <em>observation.</em></h2>
      <div class="divider"></div>
      <div style="max-width:760px;margin:0 auto;">
        <p style="font-size:17px;color:var(--dark);line-height:1.9;margin-bottom:24px;">J'ai longtemps regardé la jeunesse — ma génération — se perdre dans ce que j'appelle la <strong>médiocrité</strong>.</p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">Le terme est cru. Mais laisse-moi t'expliquer.</p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">On observe une jeunesse qui crie partout son droit d'exister, son droit d'être entendue, son droit qu'on lui donne une chance. Mais en observant de plus près, je me suis posé une question fondamentale :</p>
        <div style="background:var(--navy);border-left:4px solid var(--gold);padding:28px 32px;border-radius:4px;margin:32px 0;">
          <p style="font-family:Georgia,serif;font-size:20px;color:var(--gold);font-style:italic;line-height:1.7;margin:0;">«&nbsp;Qu'est-ce qu'elle a réellement à offrir&nbsp;?&nbsp;»</p>
        </div>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:32px;">Sans chercher à critiquer, j'en suis arrivée à une conclusion claire : <strong style="color:var(--dark);">le problème de la jeunesse africaine n'est pas seulement le manque de ressources. C'est le manque de connaissance de ce qu'elle possède déjà à l'intérieur d'elle-même.</strong></p>
        <div style="border-top:1px solid var(--border);margin:32px 0;"></div>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">Moi-même, je suis passée par des moments de doute profond. Il a fallu que mon système de pensée change complètement pour que je commence à croire que je pouvais <strong style="color:var(--dark);">être celle qu'il fallait.</strong></p>
        <div style="background:var(--light);border-left:4px solid var(--gold);padding:24px 28px;border-radius:4px;margin:0 0 40px;">
          <p style="font-family:Georgia,serif;font-size:18px;color:var(--navy);font-style:italic;line-height:1.7;margin:0;">«&nbsp;L'aide de l'Homme, c'est l'Homme.&nbsp;»</p>
        </div>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:40px;">C'est de là qu'est né <strong style="color:var(--dark);">Le Système NextPath</strong> — un système de pensée conçu pour te repositionner et te rappeler que tu vaux infiniment plus que ce que tu crois.</p>
      </div>
      <div style="max-width:760px;margin:0 auto 56px;">
        <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:20px;">
          <div style="padding:32px 24px;background:var(--navy);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
            <div style="font-size:28px;font-weight:700;color:var(--gold);font-family:Georgia,serif;margin-bottom:8px;">01</div>
            <div style="font-size:16px;font-weight:700;color:white;margin-bottom:10px;">Connais-toi</div>
            <p style="font-size:13px;color:rgba(245,240,232,.7);line-height:1.7;margin:0;">Découvre ta personnalité, tes forces naturelles et tes valeurs profondes.</p>
          </div>
          <div style="padding:32px 24px;background:var(--gold);border-radius:4px;border-top:3px solid var(--navy);text-align:center;">
            <div style="font-size:28px;font-weight:700;color:var(--navy);font-family:Georgia,serif;margin-bottom:8px;">02</div>
            <div style="font-size:16px;font-weight:700;color:var(--navy);margin-bottom:10px;">Libère-toi</div>
            <p style="font-size:13px;color:var(--navy);line-height:1.7;margin:0;opacity:.8;">Identifie ce qui te bloque — croyances limitantes, peur du regard, pression extérieure.</p>
          </div>
          <div style="padding:32px 24px;background:var(--navy);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
            <div style="font-size:28px;font-weight:700;color:var(--gold);font-family:Georgia,serif;margin-bottom:8px;">03</div>
            <div style="font-size:16px;font-weight:700;color:white;margin-bottom:10px;">Construis-toi</div>
            <p style="font-size:13px;color:rgba(245,240,232,.7);line-height:1.7;margin:0;">Passe à l'action avec des outils concrets et une communauté qui avance avec toi.</p>
          </div>
        </div>
      </div>
      <div style="text-align:center;max-width:600px;margin:0 auto;">
        <p style="font-size:15px;color:var(--mid);margin-bottom:32px;">Cette jeunesse — nous avons décidé de la construire ensemble. Et nous y arriverons.</p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold">Rejoindre le système</a>
      </div>
    </div>
  </div>
</div>

<!-- ══ PROGRAMMES ══ -->
<div class="page" id="page-programmes">
  <div class="section" style="padding-top:80px;">
    <div class="container">
      <div class="stag">Rejoins le mouvement</div>
      <h2 class="stitle">Devenir <em>membre</em> de la communauté</h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:56px;">NextPath System c'est plus qu'une page Instagram. C'est une communauté de jeunes africains de 15 à 30 ans qui avancent ensemble. Rejoins-nous.</p>

      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:20px;margin-bottom:56px;">
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">🎙️</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;">Lives & webinaires</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;">Accès aux sessions exclusives et événements en ligne de la communauté NextPath.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">💬</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;">Groupe WhatsApp</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;">Intègre le groupe privé NextPath pour échanger avec Grace et les autres membres.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">📚</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;">Ressources NextPath</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;">Accès en priorité aux guides, outils et contenus exclusifs de NextPath System.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">🎯</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;">Opportunités</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;">Accès aux offres de stages, missions et mentorats via NextPath Opportunities.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">✨</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;">Priorité aux programmes</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;">Tu seras prioritaire pour rejoindre les prochains programmes d'accompagnement NextPath.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">🌍</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;">Communauté RDC & diaspora</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;">Rejoins des jeunes africains engagés qui partagent les mêmes ambitions que toi.</p>
        </div>
      </div>

      <div style="background:var(--navy);border-radius:4px;padding:64px;text-align:center;margin-bottom:56px;">
        <div style="font-size:40px;margin-bottom:16px;">🌐</div>
        <h3 style="font-family:Georgia,serif;font-size:30px;color:var(--gold);margin-bottom:12px;">Rejoins la communauté NextPath</h3>
        <p style="font-size:15px;color:rgba(245,240,232,0.7);max-width:520px;margin:0 auto 32px;line-height:1.8;">Tu t'inscris en 2 minutes. Tu seras contacté(e) sur WhatsApp pour être accueilli(e) personnellement.</p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold" style="font-size:13px;padding:16px 48px;">Devenir membre — Gratuit</a>
        <p style="font-size:11px;color:rgba(245,240,232,0.4);margin-top:16px;">100% gratuit · Sans engagement · Accessible depuis la RDC et la diaspora</p>
      </div>

      <div style="background:var(--light);border-radius:4px;padding:48px;display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:center;">
        <div>
          <div class="stag">Outil gratuit</div>
          <h3 class="stitle" style="font-size:30px;">Le <em>NextPath Test</em></h3>
          <div class="divider"></div>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:24px;">13 questions. 5 minutes. Un portrait complet de qui tu es — ta personnalité, tes forces naturelles et les directions qui te correspondent vraiment.</p>
          <div class="bitem"><div class="bdot">✦</div><span>Profil de personnalité parmi 4 types NextPath</span></div>
          <div class="bitem"><div class="bdot">✦</div><span>Tes forces naturelles identifiées</span></div>
          <div class="bitem"><div class="bdot">✦</div><span>Les directions qui te correspondent</span></div>
          <div class="bitem"><div class="bdot">✦</div><span>Gratuit · Sans inscription</span></div>
        </div>
        <div style="background:#fff;border-radius:4px;padding:40px;text-align:center;border:1px solid var(--border);">
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:28px;">
            <div class="profile-card"><span class="picon">🧠</span><div class="pname" style="font-size:13px;">L'Éclaireur</div></div>
            <div class="profile-card"><span class="picon">🌐</span><div class="pname" style="font-size:13px;">Le Connecteur</div></div>
            <div class="profile-card"><span class="picon">🏗️</span><div class="pname" style="font-size:13px;">Le Bâtisseur</div></div>
            <div class="profile-card"><span class="picon">🌿</span><div class="pname" style="font-size:13px;">Le Semeur</div></div>
          </div>
          <a href="https://docs.google.com/forms/d/e/1FAIpQLSdvA440a9h65ZcFT4XXJUoPJBelQbqrmUgU27X1pDnX6I-XkQ/viewform?usp=header" target="_blank" class="btn btn-navy" style="width:100%;justify-content:center;">Passer le NextPath Test — Gratuit</a>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══ NOS RESSOURCES ══ -->
<div class="page" id="page-ressources">
  <div class="section" style="padding-top:80px;">
    <div class="container">
      <div class="stag">Nos ressources</div>
      <h2 class="stitle">Vidéos &amp; <em>guides</em></h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:56px;">Retrouve ici tous nos guides PDF et nos vidéos YouTube — des contenus concrets pour te connaître, te libérer et construire ton chemin.</p>

      <!-- GUIDES PDF -->
      <div style="margin-bottom:64px;">
        <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:24px;flex-wrap:wrap;gap:12px;">
          <div>
            <h3 style="font-family:Georgia,serif;font-size:26px;font-weight:700;color:var(--navy);">Guides &amp; outils PDF</h3>
            <p style="font-size:13px;color:var(--light-text);margin-top:4px;">Série 1 — Éveil &amp; Découverte de soi</p>
          </div>
          <span style="font-size:12px;color:var(--gold);font-weight:600;">Téléchargement direct</span>
        </div>

        <!-- GRILLE PDF DYNAMIQUE -->
        <div class="pdf-grid" id="pdf-grid">
          <!-- Rempli automatiquement par JavaScript -->
        </div>
      </div>

      <!-- SÉPARATEUR -->
      <div style="border-top:1px solid var(--border);margin-bottom:64px;"></div>

      <!-- VIDÉOS YOUTUBE -->
      <div style="margin-bottom:64px;">
        <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:28px;flex-wrap:wrap;gap:12px;">
          <h3 style="font-family:Georgia,serif;font-size:26px;font-weight:700;color:var(--navy);" id="yt-titre">Dernières vidéos</h3>
          <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="btn btn-outline" style="font-size:11px;padding:10px 20px;">Voir toutes les vidéos ↗</a>
        </div>
        <div class="yt-grid" id="yt-grid">
          <!-- Rempli automatiquement par JavaScript -->
        </div>
      </div>

      <!-- CTA -->
      <div style="background:var(--navy);border-radius:4px;padding:48px;text-align:center;">
        <div style="font-size:32px;margin-bottom:14px;">📬</div>
        <h3 style="font-family:Georgia,serif;font-size:24px;color:var(--gold);margin-bottom:10px;">Prêt(e) à commencer ton parcours ?</h3>
        <p style="font-size:14px;color:rgba(245,240,232,.7);max-width:480px;margin:0 auto 28px;line-height:1.7;">Les guides NextPath System sont disponibles maintenant. Télécharge-les et commence ton parcours aujourd'hui.</p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold">Obtenir les guides</a>
      </div>
    </div>
  </div>
</div>

<!-- ══ AVIS ══ -->
<div class="page" id="page-avis">
  <div class="section" style="padding-top:80px;">
    <div class="container" style="max-width:720px;">
      <div class="stag">Témoignages</div>
      <h2 class="stitle">Ce qu'ils disent de <em>NextPath</em></h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:40px;">Des retours réels de la communauté. Chaque témoignage compte.</p>
      <div id="avis-feed" style="margin-bottom:48px;"></div>
      <div style="background:var(--light);border-radius:4px;padding:28px;border:1px solid var(--border);">
        <h3 style="font-family:Georgia,serif;font-size:17px;font-weight:700;color:var(--navy);margin-bottom:4px;">Laisse ton avis</h3>
        <p style="font-size:13px;color:var(--mid);margin-bottom:18px;">Ton témoignage peut changer la trajectoire d'un autre jeune.</p>
        <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px;">
          <div><label class="admin-label">Prénom *</label><input type="text" id="a-prenom" placeholder="Ex : Grace" class="admin-input"></div>
          <div><label class="admin-label">Ville & Pays *</label><input type="text" id="a-ville" placeholder="Ex : Kinshasa, RDC" class="admin-input"></div>
        </div>
        <div style="margin-bottom:10px;">
          <label class="admin-label">Note *</label>
          <div id="star-rating" style="display:flex;gap:3px;">
            <span onclick="setRating(1)" data-star="1" style="font-size:20px;cursor:pointer;color:#ddd;">★</span>
            <span onclick="setRating(2)" data-star="2" style="font-size:20px;cursor:pointer;color:#ddd;">★</span>
            <span onclick="setRating(3)" data-star="3" style="font-size:20px;cursor:pointer;color:#ddd;">★</span>
            <span onclick="setRating(4)" data-star="4" style="font-size:20px;cursor:pointer;color:#ddd;">★</span>
            <span onclick="setRating(5)" data-star="5" style="font-size:20px;cursor:pointer;color:#ddd;">★</span>
          </div>
        </div>
        <div style="margin-bottom:14px;">
          <label class="admin-label">Témoignage *</label>
          <textarea id="a-texte" rows="3" placeholder="Partage ton expérience avec NextPath System..." class="admin-input" style="resize:vertical;"></textarea>
        </div>
        <div style="display:flex;align-items:center;gap:14px;">
          <button onclick="soumettreAvis()" class="btn btn-navy" style="padding:9px 24px;font-size:11px;">Envoyer</button>
          <span id="avis-ok" style="display:none;font-size:13px;color:var(--gold);font-weight:500;">✔ Merci ! Ton avis sera lu personnellement.</span>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══ OPPORTUNITÉS ══ -->
<div class="page" id="page-opportunites">
  <div class="section" style="padding-top:80px;">
    <div class="container">
      <div class="stag">NextPath Opportunities</div>
      <h2 class="stitle">Des opportunités <em>sélectionnées</em><br>pour toi.</h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:16px;">Grace sélectionne et publie régulièrement des opportunités concrètes pour les jeunes africains — bourses, formations, programmes, concours, stages.</p>
      <p style="font-size:13px;color:var(--light-text);margin-bottom:48px;">Mise à jour régulière · Vérifiées et sélectionnées · Accessibles depuis la RDC et la diaspora</p>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-bottom:56px;">
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">🎓</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Bourses &amp; financements</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Bourses d'études, programmes de financement, aides à la formation.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">📖</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Formations &amp; certifications</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Cours en ligne gratuits ou certifiés pour développer des compétences clés.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">🏆</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Concours &amp; challenges</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Compétitions, hackathons, prix pour les jeunes africains.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">🌏</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Programmes internationaux</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Programmes d'échanges, leadership et développement pour jeunes africains.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">🎯</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Stages &amp; expériences</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Premières expériences professionnelles pour construire ton parcours.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">💻</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Compétences du futur</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Digital, IA, entrepreneuriat, communication — les compétences essentielles.</div>
        </div>
      </div>
      <div style="background:var(--navy);border-radius:4px;padding:56px;text-align:center;">
        <div style="font-size:36px;margin-bottom:16px;">🔔</div>
        <h3 style="font-family:Georgia,serif;font-size:26px;color:var(--gold);margin-bottom:12px;">Sois notifié(e) en premier</h3>
        <p style="font-size:14px;color:rgba(245,240,232,0.7);max-width:520px;margin:0 auto 28px;line-height:1.8;">Chaque nouvelle opportunité est partagée en priorité dans la communauté WhatsApp NextPath.</p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold">Rejoindre la communauté</a>
      </div>
    </div>
  </div>
</div>

<!-- ══ À PROPOS ══ -->
<div class="page" id="page-grace">
  <div style="background:var(--navy);padding:80px 80px 0;display:grid;grid-template-columns:1fr 1fr;gap:0;align-items:end;min-height:380px;overflow:hidden;">
    <div style="padding-bottom:60px;">
      <div style="font-size:11px;font-weight:600;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);margin-bottom:16px;display:flex;align-items:center;gap:10px;"><span style="display:block;width:24px;height:1.5px;background:var(--gold);"></span>À propos</div>
      <h1 style="font-family:Georgia,serif;font-size:clamp(36px,5vw,56px);font-weight:900;color:var(--cream);line-height:1.1;margin-bottom:18px;">Grace<br><em style="color:var(--gold);">Kabondo</em></h1>
      <p style="font-size:15px;color:rgba(245,240,232,.65);line-height:1.7;max-width:440px;margin-bottom:28px;">Fondatrice · NextPath System</p>
      <div style="display:flex;gap:8px;flex-wrap:wrap;">
        <span style="font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;padding:6px 14px;border:1px solid rgba(201,168,76,.4);border-radius:2px;color:var(--gold);">Master Sciences du Médicament</span>
        <span style="font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;padding:6px 14px;border:1px solid rgba(201,168,76,.4);border-radius:2px;color:var(--gold);">Nantes Université</span>
      </div>
    </div>
    <div style="position:relative;height:380px;overflow:hidden;border-radius:4px 4px 0 0;background:var(--navy);display:flex;align-items:center;justify-content:center;">
      <div style="font-size:80px;opacity:.3;">👤</div>
    </div>
  </div>
  <div class="section">
    <div class="container">
      <div class="grace-grid">
        <div>
          <div class="stag">Mon histoire</div>
          <h2 class="stitle" style="font-size:34px;">Je suis passée<br>par là, <em>moi aussi.</em></h2>
          <div class="divider"></div>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:18px;">J'ai fait mon école secondaire à Lubumbashi, en RDC — au cœur du système, de la pression, des choix imposés et des questions sans réponses.</p>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:18px;">Puis j'ai poursuivi mes études supérieures en France, où j'ai obtenu une Licence en Chimie-Biologie à Nantes Université, avant de poursuivre un Master en Sciences du Médicament.</p>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:28px;">Ce parcours entre deux mondes m'a révélé une vérité : personne ne m'avait appris à me connaître. À transformer ce que j'avais en quelque chose de concret.</p>
          <div class="quote-box"><p>"NextPath System c'est ce que j'aurais voulu avoir à 17 ans. C'est ce que je construis aujourd'hui — pour toi."</p></div>
        </div>
        <div>
          <div style="display:flex;flex-direction:column;gap:0;border:1px solid var(--border);border-radius:4px;overflow:hidden;">
            <div style="display:flex;gap:14px;padding:14px 18px;border-bottom:1px solid var(--border);"><span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);min-width:80px;margin-top:2px;">Formation</span><span style="font-size:14px;color:var(--dark);line-height:1.6;">Licence Chimie-Biologie · France<br>Master Sciences du Médicament · France</span></div>
            <div style="display:flex;gap:14px;padding:14px 18px;border-bottom:1px solid var(--border);"><span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);min-width:80px;margin-top:2px;">Rôle</span><span style="font-size:14px;color:var(--dark);">Fondatrice · NextPath System</span></div>
            <div style="display:flex;gap:14px;padding:14px 18px;"><span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);min-width:80px;margin-top:2px;">Contact</span><span style="font-size:14px;color:var(--dark);">nextpathsystem@gmail.com</span></div>
          </div>
          <div style="margin-top:24px;background:var(--navy);border-radius:4px;padding:40px;text-align:center;">
            <p style="font-family:Georgia,serif;font-size:18px;font-style:italic;color:var(--cream);line-height:1.65;margin-bottom:16px;">"Un jeune qui se connaît ne se perd jamais."</p>
            <cite style="font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);">— Grace Kabondo</cite>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══ CONTACT ══ -->
<div class="page" id="page-contact">
  <div class="section" style="padding-top:80px;">
    <div class="container">
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:start;">
        <div>
          <div class="stag">Nous contacter</div>
          <h2 class="stitle">Ensemble,<br>on <em>construit</em><br>une génération.</h2>
          <div class="divider"></div>
          <a href="https://instagram.com/nextpath.system" target="_blank" class="slink"><span class="splat">Instagram</span><span class="shandle">@nextpath.system</span></a>
          <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="slink"><span class="splat">YouTube</span><span class="shandle">The NextPath System</span></a>
          <a href="https://tiktok.com/@nextpath.system" target="_blank" class="slink"><span class="splat">TikTok</span><span class="shandle">@nextpath.system</span></a>
          <a href="https://wa.me/33766131603" target="_blank" class="slink"><span class="splat">WhatsApp</span><span class="shandle">+33 7 66 13 16 03</span></a>
          <a href="mailto:nextpathsystem@gmail.com" class="slink"><span class="splat">Email</span><span class="shandle">nextpathsystem@gmail.com</span></a>
        </div>
        <div style="background:var(--light);border-radius:4px;padding:40px;">
          <h3 style="font-family:Georgia,serif;font-size:22px;color:var(--navy);margin-bottom:8px;">Rejoins The Grace Effect</h3>
          <p style="font-size:14px;color:var(--mid);margin-bottom:24px;line-height:1.7;">15 places. Totalement gratuit. Tu recevras une réponse sous 48h.</p>
          <a href="https://tally.so/r/ZjGJQB" target="_blank" class="btn btn-navy" style="width:100%;margin-bottom:14px;">Rejoindre The Grace Effect</a>
          <div style="text-align:center;margin:12px 0;font-size:12px;color:var(--light-text);">ou</div>
          <a href="#" onclick="go('ressources')" class="btn btn-outline" style="width:100%;">Devenir membre de la communauté</a>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="flogo">NextPath System</div>
  <div class="flinks">
    <a onclick="go('home')">Accueil</a>
    <a onclick="go('mission')">Mission</a>
    <a onclick="go('programmes')">Devenir membre</a>
    <a onclick="go('ressources')">Ressources</a>
    <a onclick="go('avis')">Avis</a>
    <a onclick="go('opportunites')">Opportunités</a>
    <a onclick="go('grace')">À propos</a>
    <a onclick="go('contact')">Contact</a>
  </div>
  <div class="fcopy">© 2026 NextPath System</div>
</footer>

<!-- ══ PANNEAU ADMIN (NPADMIN au clavier) ══ -->
<div id="admin-overlay">
  <div class="admin-box">
    <button class="admin-close" onclick="closeAdmin()">✕ Fermer</button>
    <div class="admin-title">Panneau NextPath</div>
    <div class="admin-sub">Tape <strong>NPADMIN</strong> sur ton clavier pour ouvrir ce panneau depuis n'importe quelle page.</div>

    <!-- SECTION PDF -->
    <div class="admin-section">
      <h3>📄 Ajouter un guide PDF</h3>
      <label class="admin-label">Titre du guide *</label>
      <input type="text" id="adm-pdf-titre" placeholder="Ex : Bienvenue dans NextPath" class="admin-input">
      <label class="admin-label">Description courte</label>
      <input type="text" id="adm-pdf-desc" placeholder="Ex : Comprends le parcours et écris ta lettre de départ." class="admin-input">
      <label class="admin-label">Badge (ex : Guide de démarrage, Module 1...)</label>
      <input type="text" id="adm-pdf-badge" placeholder="Ex : Module 1" class="admin-input">
      <label class="admin-label">Lien Google Drive (direct ou partageable) *</label>
      <input type="text" id="adm-pdf-lien" placeholder="https://drive.google.com/..." class="admin-input">
      <button class="admin-btn" onclick="ajouterPDF()">➕ Ajouter ce guide</button>
      <div class="admin-msg" id="msg-pdf">✔ Guide ajouté ! Il apparaît maintenant dans la section Ressources.</div>

      <div style="margin-top:24px;">
        <div style="font-size:11px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--mid);margin-bottom:10px;">Guides actuels</div>
        <div class="admin-list" id="admin-pdf-list"></div>
      </div>
    </div>

    <!-- SECTION YOUTUBE -->
    <div class="admin-section">
      <h3>▶️ Ajouter une vidéo YouTube</h3>
      <label class="admin-label">Titre de la vidéo *</label>
      <input type="text" id="adm-yt-titre" placeholder="Ex : Ton diplôme peut te rendre utile si tu sais l'utiliser" class="admin-input">
      <label class="admin-label">Lien YouTube *</label>
      <input type="text" id="adm-yt-lien" placeholder="https://www.youtube.com/watch?v=..." class="admin-input">
      <button class="admin-btn" onclick="ajouterVideo()">➕ Ajouter cette vidéo</button>
      <div class="admin-msg" id="msg-yt">✔ Vidéo ajoutée ! Elle apparaît maintenant dans la section Ressources.</div>

      <div style="margin-top:24px;">
        <div style="font-size:11px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--mid);margin-bottom:10px;">Vidéos actuelles</div>
        <div class="admin-list" id="admin-yt-list"></div>
      </div>
    </div>
  </div>
</div>

<script>
// ══ DONNÉES ══
// PDFs et vidéos stockés en mémoire (persistants pendant la session)
var pdfs = [
  {titre:'Bienvenue dans NextPath', desc:'Comprends le parcours, pose les bases et écris ta lettre de départ.', badge:'Guide de démarrage', lien:'https://drive.google.com/file/d/14iZ9DMlzC2ts84Zw624tUPInLKIxCUGY/view?usp=sharing', icone:'📘'},
  {titre:'Connais-toi', desc:'Profil de personnalité, forces naturelles, valeurs fondamentales. Exercices écrits complets.', badge:'Module 1', lien:'', icone:'🧠'},
  {titre:'Libère-toi', desc:'Les 5 blocages les plus courants, lettre à ton blocage, plan de libération concret.', badge:'Module 2', lien:'', icone:'🔓'},
  {titre:'Construis-toi', desc:'Méthode des 3 cercles, tes 3 chemins possibles, orientation post-diplôme, plan 90 jours.', badge:'Module 3', lien:'', icone:'🏗️'}
];

var videos = [
  {titre:'Ton diplôme d\'État peut te rendre utile si tu sais l\'utiliser', lien:'https://www.youtube.com/@NextPathSystem'},
  {titre:'On nous a tout appris sauf à construire notre avenir', lien:'https://www.youtube.com/@NextPathSystem'},
  {titre:'Comment construire son identité et augmenter sa valeur ?', lien:'https://www.youtube.com/@NextPathSystem'}
];

// ══ RENDU RESSOURCES ══
function renderPDFs() {
  var grid = document.getElementById('pdf-grid');
  if (!grid) return;
  grid.innerHTML = '';
  pdfs.forEach(function(p, i) {
    var hasLink = p.lien && p.lien.trim() !== '';
    var tag = hasLink ? 'a' : 'div';
    var attrs = hasLink ? 'href="'+p.lien+'" target="_blank"' : '';
    var className = 'pdf-card' + (hasLink ? '' : ' bientot');
    grid.innerHTML += '<'+tag+' '+attrs+' class="'+className+'">'
      +'<div class="pdf-icon">'+p.icone+'</div>'
      +'<div>'
      +'<div class="pdf-badge">'+p.badge+'</div>'
      +'<div class="pdf-title">'+p.titre+'</div>'
      +'<div class="pdf-desc">'+p.desc+'</div>'
      +(hasLink ? '<div class="pdf-dl">⬇️ Télécharger</div>' : '<div style="font-size:11px;color:var(--light-text);margin-top:8px;font-style:italic;">⏰ Bientôt disponible</div>')
      +'</div>'
      +'</'+tag+'>';
  });
}

function renderVideos() {
  var grid = document.getElementById('yt-grid');
  if (!grid) return;
  grid.innerHTML = '';
  if (videos.length === 0) {
    grid.innerHTML = '<p style="color:var(--mid);font-size:13px;grid-column:1/-1;">Aucune vidéo pour l\'instant. Ajoutes-en depuis le panneau NPADMIN.</p>';
    return;
  }
  videos.forEach(function(v) {
    var vid = '';
    var m = v.lien.match(/(?:v=|youtu\.be\/)([a-zA-Z0-9_-]{11})/);
    if (m) vid = m[1];
    var thumb = vid ? 'https://img.youtube.com/vi/'+vid+'/mqdefault.jpg' : '';
    grid.innerHTML += '<a href="'+v.lien+'" target="_blank" class="yt-card">'
      +'<div class="yt-thumb" style="'+(thumb ? 'background:url('+thumb+') center/cover;' : '')+'"><div class="yt-play"></div></div>'
      +'<div class="yt-info"><div class="yt-title">'+v.titre+'</div><div class="yt-meta">NextPath System · YouTube</div></div>'
      +'</a>';
  });
}

function renderAdminLists() {
  // PDF list
  var el = document.getElementById('admin-pdf-list');
  if (el) {
    el.innerHTML = '';
    pdfs.forEach(function(p, i) {
      el.innerHTML += '<div class="admin-item">'
        +'<span style="font-size:18px;">'+p.icone+'</span>'
        +'<span class="admin-item-title">'+p.badge+' — '+p.titre+'</span>'
        +(p.lien ? '<span class="admin-item-link">'+p.lien+'</span>' : '<span style="font-size:11px;color:#aaa;font-style:italic;">Pas de lien</span>')
        +'<button class="admin-del" onclick="supprimerPDF('+i+')">🗑</button>'
        +'</div>';
    });
  }
  // Video list
  var el2 = document.getElementById('admin-yt-list');
  if (el2) {
    el2.innerHTML = '';
    videos.forEach(function(v, i) {
      el2.innerHTML += '<div class="admin-item">'
        +'<span style="font-size:18px;">▶️</span>'
        +'<span class="admin-item-title">'+v.titre+'</span>'
        +'<span class="admin-item-link">'+v.lien+'</span>'
        +'<button class="admin-del" onclick="supprimerVideo('+i+')">🗑</button>'
        +'</div>';
    });
  }
}

// ══ ADMIN ACTIONS ══
function ajouterPDF() {
  var titre = document.getElementById('adm-pdf-titre').value.trim();
  var desc = document.getElementById('adm-pdf-desc').value.trim();
  var badge = document.getElementById('adm-pdf-badge').value.trim();
  var lien = document.getElementById('adm-pdf-lien').value.trim();
  if (!titre) { alert('Le titre est obligatoire.'); return; }
  pdfs.push({titre:titre, desc:desc||'Guide NextPath System', badge:badge||'Guide', lien:lien, icone:'📄'});
  document.getElementById('adm-pdf-titre').value = '';
  document.getElementById('adm-pdf-desc').value = '';
  document.getElementById('adm-pdf-badge').value = '';
  document.getElementById('adm-pdf-lien').value = '';
  var msg = document.getElementById('msg-pdf');
  msg.style.display = 'block';
  setTimeout(function(){msg.style.display='none';},3000);
  renderPDFs();
  renderAdminLists();
}

function supprimerPDF(i) {
  if (!confirm('Supprimer ce guide ?')) return;
  pdfs.splice(i, 1);
  renderPDFs();
  renderAdminLists();
}

function ajouterVideo() {
  var titre = document.getElementById('adm-yt-titre').value.trim();
  var lien = document.getElementById('adm-yt-lien').value.trim();
  if (!titre || !lien) { alert('Le titre et le lien sont obligatoires.'); return; }
  videos.push({titre:titre, lien:lien});
  document.getElementById('adm-yt-titre').value = '';
  document.getElementById('adm-yt-lien').value = '';
  var msg = document.getElementById('msg-yt');
  msg.style.display = 'block';
  setTimeout(function(){msg.style.display='none';},3000);
  renderVideos();
  renderAdminLists();
}

function supprimerVideo(i) {
  if (!confirm('Supprimer cette vidéo ?')) return;
  videos.splice(i, 1);
  renderVideos();
  renderAdminLists();
}

// ══ NAVIGATION ══
function go(p) {
  document.querySelectorAll('.page').forEach(function(x){x.classList.remove('active');});
  var t = document.getElementById('page-'+p);
  if (t) { t.classList.add('active'); window.scrollTo(0,0); }
  document.getElementById('mobile-menu').classList.remove('open');
  if (p === 'ressources') { renderPDFs(); renderVideos(); }
}

function toggleMenu() {
  document.getElementById('mobile-menu').classList.toggle('open');
}

// ══ ADMIN OVERLAY ══
var adminKeys = [];
var adminCode = [78,80,65,68,77,73,78];
document.addEventListener('keydown', function(e) {
  adminKeys.push(e.keyCode);
  if (adminKeys.length > 7) adminKeys.shift();
  if (adminKeys.join(',') === adminCode.join(',')) {
    document.getElementById('admin-overlay').style.display = 'block';
    renderAdminLists();
    adminKeys = [];
  }
});
function closeAdmin() {
  document.getElementById('admin-overlay').style.display = 'none';
}

// ══ AVIS ══
var rating = 0;
function setRating(n) {
  rating = n;
  document.querySelectorAll('#star-rating span').forEach(function(s) {
    s.style.color = parseInt(s.dataset.star) <= n ? 'var(--gold)' : '#ddd';
  });
}
function soumettreAvis() {
  var p = document.getElementById('a-prenom').value.trim();
  var v = document.getElementById('a-ville').value.trim();
  var t = document.getElementById('a-texte').value.trim();
  if (!p||!v||!t||rating===0) { alert('Merci de remplir tous les champs et de donner une note.'); return; }
  var stars = '';
  for (var i=0;i<rating;i++) stars += '★';
  var now = new Date();
  var date = now.toLocaleDateString('fr-FR',{day:'2-digit',month:'2-digit',year:'numeric'});
  var item = document.createElement('div');
  item.style.cssText = 'display:flex;gap:12px;align-items:flex-start;padding:14px 0;border-bottom:1px solid var(--border);';
  item.innerHTML = '<div style="width:34px;height:34px;border-radius:50%;background:var(--navy);display:flex;align-items:center;justify-content:center;font-family:Georgia,serif;font-weight:700;color:var(--gold);font-size:12px;flex-shrink:0;">'+p.charAt(0).toUpperCase()+'</div>'
    +'<div style="flex:1;"><div style="display:flex;align-items:center;flex-wrap:wrap;gap:8px;margin-bottom:3px;">'
    +'<span style="font-size:13px;font-weight:600;color:var(--navy);">'+p+'</span>'
    +'<span style="font-size:10px;color:var(--light-text);text-transform:uppercase;">'+v+'</span>'
    +'<span style="font-size:12px;color:var(--gold);">'+stars+'</span>'
    +'<span style="font-size:11px;color:var(--light-text);margin-left:auto;">'+date+'</span>'
    +'</div><p style="font-size:13px;color:var(--mid);line-height:1.65;margin:0;">"'+t+'"</p></div>';
  var feed = document.getElementById('avis-feed');
  if (feed) feed.insertBefore(item, feed.firstChild);
  document.getElementById('avis-ok').style.display = 'inline';
  document.getElementById('a-prenom').value = '';
  document.getElementById('a-ville').value = '';
  document.getElementById('a-texte').value = '';
  rating = 0;
  document.querySelectorAll('#star-rating span').forEach(function(s){s.style.color='#ddd';});
}

// ══ LANGUE ══
function setLang(l) {
  document.getElementById('btn-fr').classList.toggle('active', l==='fr');
  document.getElementById('btn-en').classList.toggle('active', l==='en');
}

// ══ INITIALISATION ══
window.addEventListener('load', function() {
  renderPDFs();
  renderVideos();
});
</script>
</body>
</html>
