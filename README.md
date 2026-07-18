<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NextPath Blog</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Inter:wght@300;400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{
  --vert:#1B4D3E;
  --vert-clair:#2D7A5F;
  --vert-pale:#E8F4EF;
  --vert-mid:#4FA882;
  --encre:#111A14;
  --gris:#6B7B72;
  --gris-pale:#F8FAF9;
  --blanc:#FFFFFF;
  --border:#D4E4DA;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--blanc);color:var(--encre);font-family:'Inter',sans-serif;font-size:16px;line-height:1.7;}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;background:var(--blanc);border-bottom:1px solid var(--border);padding:0 48px;height:64px;display:flex;align-items:center;justify-content:space-between;}
.nav-logo{display:flex;align-items:center;gap:8px;font-family:'Inter',sans-serif;font-size:18px;font-weight:700;color:var(--encre);cursor:pointer;text-decoration:none;}
.nav-logo-dot{width:8px;height:8px;border-radius:50%;background:var(--vert-mid);}
.nav-logo-np{color:var(--encre);}
.nav-logo-blog{color:var(--vert-mid);}
.nav-links{display:flex;gap:40px;list-style:none;align-items:center;}
.nav-links a{font-size:14px;font-weight:400;color:var(--gris);text-decoration:none;transition:color .2s;cursor:pointer;padding-bottom:4px;border-bottom:2px solid transparent;}
.nav-links a:hover{color:var(--encre);}
.nav-links a.active{color:var(--encre);border-bottom-color:var(--vert);}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:4px;}
.hamburger span{display:block;width:20px;height:1.5px;background:var(--encre);}
.mobile-menu{display:none;position:fixed;top:64px;left:0;right:0;background:var(--blanc);border-bottom:1px solid var(--border);padding:16px 24px;z-index:199;flex-direction:column;}
.mobile-menu.open{display:flex;}
.mobile-menu a{font-size:14px;color:var(--encre);text-decoration:none;padding:12px 0;border-bottom:1px solid var(--border);cursor:pointer;display:block;}

/* PAGES */
.page{display:none;padding-top:64px;min-height:100vh;}
.page.active{display:block;}

/* HERO */
.hero{background:var(--vert-pale);padding:100px 48px 80px;text-align:center;}
.hero-eyebrow{font-family:'DM Mono',monospace;font-size:11px;font-weight:500;letter-spacing:.18em;text-transform:uppercase;color:var(--vert);margin-bottom:28px;display:block;}
.hero h1{font-family:'Playfair Display',serif;font-size:clamp(40px,6vw,72px);font-weight:700;line-height:1.1;letter-spacing:-.02em;color:var(--vert);margin-bottom:20px;}
.hero-desc{font-size:17px;color:var(--gris);line-height:1.8;max-width:580px;margin:0 auto 32px;}
.hero-divider{width:48px;height:2px;background:var(--vert-mid);margin:0 auto;}

/* ARTICLES */
.articles-wrap{padding:80px 48px;max-width:1100px;margin:0 auto;}
.articles-header{text-align:center;margin-bottom:48px;}
.articles-title{font-family:'Playfair Display',serif;font-size:clamp(26px,3vw,38px);font-weight:700;color:var(--encre);margin-bottom:8px;}
.articles-sub{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.18em;text-transform:uppercase;color:var(--vert-mid);}
.articles-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:32px;}

/* CARD */
.article-card{background:var(--blanc);border-radius:12px;overflow:hidden;box-shadow:0 2px 16px rgba(27,77,62,.06);border:1px solid var(--border);cursor:pointer;transition:transform .25s,box-shadow .25s;}
.article-card:hover{transform:translateY(-4px);box-shadow:0 12px 32px rgba(27,77,62,.12);}
.card-img{width:100%;aspect-ratio:16/9;object-fit:cover;display:block;background:var(--vert-pale);}
.card-img-placeholder{width:100%;aspect-ratio:16/9;background:linear-gradient(135deg,var(--vert) 0%,var(--vert-clair) 100%);display:flex;align-items:center;justify-content:center;}
.card-img-placeholder-text{font-family:'Playfair Display',serif;font-size:clamp(16px,2vw,24px);font-weight:300;font-style:italic;color:rgba(255,255,255,.3);text-align:center;padding:20px;line-height:1.3;}
.card-body{padding:24px;}
.card-tags{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:16px;}
.card-tag{font-family:'DM Mono',monospace;font-size:9px;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--blanc);background:var(--vert);padding:4px 10px;border-radius:4px;}
.card-meta{display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;}
.card-date{font-family:'DM Mono',monospace;font-size:10px;color:var(--gris);display:flex;align-items:center;gap:6px;}
.card-date::before{content:'📅';font-size:10px;}
.card-likes{font-family:'DM Mono',monospace;font-size:10px;color:var(--gris);display:flex;align-items:center;gap:4px;}
.card-title{font-family:'Playfair Display',serif;font-size:20px;font-weight:700;line-height:1.3;color:var(--encre);margin-bottom:10px;transition:color .2s;}
.article-card:hover .card-title{color:var(--vert);}
.card-excerpt{font-size:13px;color:var(--gris);line-height:1.7;margin-bottom:20px;}
.card-cta{font-family:'DM Mono',monospace;font-size:10px;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--vert);display:flex;align-items:center;gap:6px;}
.card-cta::after{content:'→';}

/* EMPTY STATE */
.empty-state{padding:100px 48px;text-align:center;}
.empty-icon{font-size:56px;margin-bottom:24px;opacity:.35;}
.empty-title{font-family:'Playfair Display',serif;font-size:28px;font-weight:400;color:var(--vert);margin-bottom:12px;}
.empty-desc{font-size:15px;color:var(--gris);line-height:1.75;}

/* ARTICLE FULL */
.article-full{max-width:720px;margin:0 auto;padding:64px 40px 80px;}
.article-full-back{display:inline-flex;align-items:center;gap:8px;font-size:13px;color:var(--gris);cursor:pointer;background:none;border:none;font-family:'Inter',sans-serif;margin-bottom:36px;transition:color .2s;padding:0;}
.article-full-back:hover{color:var(--vert);}
.article-full-tags{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:20px;}
.article-full-meta{font-family:'DM Mono',monospace;font-size:11px;color:var(--gris);margin-bottom:40px;display:flex;align-items:center;gap:16px;}
.article-full h1{font-family:'Playfair Display',serif;font-size:clamp(28px,4vw,48px);font-weight:700;line-height:1.15;letter-spacing:-.02em;color:var(--vert);margin-bottom:20px;}
.article-full-img{width:100%;border-radius:12px;margin-bottom:40px;object-fit:cover;max-height:400px;}
.article-body{font-size:17px;color:var(--encre);line-height:1.9;}
.article-body p{margin-bottom:28px;}
.article-body strong{color:var(--vert);font-weight:600;}
.article-body em{font-style:italic;}
.article-body blockquote{border-left:3px solid var(--vert-mid);padding:18px 28px;background:var(--vert-pale);border-radius:0 8px 8px 0;margin:32px 0;font-family:'Playfair Display',serif;font-size:20px;font-style:italic;color:var(--vert);line-height:1.6;}
.article-body img{max-width:100%;border-radius:10px;margin:24px 0;display:block;}
.article-body a{color:var(--vert-clair);text-decoration:underline;}
.article-body ul{margin:0 0 28px 24px;}
.article-body li{margin-bottom:8px;}

/* LIKES */
.likes-bar{display:flex;align-items:center;gap:16px;padding:28px 0;border-top:1px solid var(--border);margin-top:48px;}
.like-big{display:inline-flex;align-items:center;gap:8px;background:var(--vert-pale);border:1px solid var(--border);padding:10px 22px;border-radius:100px;font-size:14px;font-weight:500;color:var(--vert);cursor:pointer;transition:all .2s;font-family:'Inter',sans-serif;}
.like-big:hover,.like-big.liked{background:var(--vert);color:var(--blanc);border-color:var(--vert);}
.like-count{font-family:'DM Mono',monospace;font-size:12px;color:var(--gris);}

/* COMMENTAIRES */
.comments-wrap{max-width:720px;margin:0 auto;padding:0 40px 80px;}
.comments-hr{border:none;border-top:1px solid var(--border);margin-bottom:40px;}
.comments-heading{font-family:'Playfair Display',serif;font-size:22px;font-weight:600;color:var(--encre);margin-bottom:24px;}
.comment-form{background:var(--gris-pale);border-radius:12px;padding:24px;margin-bottom:40px;}
.comment-input{width:100%;padding:11px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:14px;outline:none;background:var(--blanc);color:var(--encre);margin-bottom:10px;transition:border-color .2s;}
.comment-input:focus{border-color:var(--vert-mid);}
.comment-textarea{width:100%;padding:11px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:14px;outline:none;background:var(--blanc);color:var(--encre);resize:vertical;min-height:100px;transition:border-color .2s;margin-bottom:10px;}
.comment-textarea:focus{border-color:var(--vert-mid);}
.comment-btn{background:var(--vert);color:var(--blanc);border:none;padding:10px 26px;border-radius:100px;font-family:'Inter',sans-serif;font-size:13px;font-weight:600;cursor:pointer;transition:background .2s;}
.comment-btn:hover{background:var(--vert-clair);}
.comment-ok{display:none;font-size:12px;color:var(--vert-clair);margin-left:12px;font-weight:500;}
.comment-item{padding:20px 0;border-bottom:1px solid var(--border);}
.comment-author{font-weight:600;font-size:14px;color:var(--encre);margin-bottom:3px;}
.comment-date{font-family:'DM Mono',monospace;font-size:10px;color:var(--gris);margin-bottom:10px;}
.comment-text{font-size:14px;color:var(--gris);line-height:1.7;}

/* ÉDITEUR */
.editor-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.75);z-index:9999;overflow-y:auto;padding:24px;}
.editor-box{background:var(--blanc);max-width:820px;margin:0 auto;border-radius:16px;overflow:hidden;}
.editor-head{background:var(--vert);padding:20px 28px;display:flex;align-items:center;justify-content:space-between;}
.editor-head-title{font-family:'Playfair Display',serif;font-size:20px;font-weight:400;font-style:italic;color:var(--blanc);}
.editor-head-close{background:rgba(255,255,255,.15);border:none;color:var(--blanc);padding:7px 16px;border-radius:100px;cursor:pointer;font-size:13px;font-family:'Inter',sans-serif;transition:background .2s;}
.editor-head-close:hover{background:rgba(255,255,255,.25);}
.editor-body{padding:32px;}
.ed-label{display:block;font-family:'DM Mono',monospace;font-size:10px;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--gris);margin-bottom:8px;}
.ed-input{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:15px;outline:none;color:var(--encre);transition:border-color .2s;margin-bottom:20px;}
.ed-input:focus{border-color:var(--vert-mid);}
.ed-select{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:15px;outline:none;color:var(--encre);background:var(--blanc);margin-bottom:20px;}
.ed-toolbar{display:flex;gap:6px;flex-wrap:wrap;padding:12px 14px;background:var(--gris-pale);border:1px solid var(--border);border-bottom:none;border-radius:8px 8px 0 0;}
.tool{background:var(--blanc);border:1px solid var(--border);color:var(--encre);padding:6px 12px;border-radius:6px;cursor:pointer;font-size:13px;font-family:'Inter',sans-serif;transition:all .2s;}
.tool:hover{background:var(--vert);color:var(--blanc);border-color:var(--vert);}
.tool-div{width:1px;background:var(--border);margin:0 4px;align-self:stretch;}
.ed-content{width:100%;min-height:300px;padding:20px;border:1px solid var(--border);border-radius:0 0 8px 8px;font-family:'Inter',sans-serif;font-size:16px;line-height:1.8;outline:none;color:var(--encre);margin-bottom:20px;}
.ed-content:empty::before{content:'Commence à écrire ton article ici...';color:#aaa;font-style:italic;}
.ed-content blockquote{border-left:3px solid var(--vert-mid);padding:12px 20px;background:var(--vert-pale);margin:16px 0;font-style:italic;color:var(--vert);border-radius:0 6px 6px 0;}
.ed-content img{max-width:100%;border-radius:8px;margin:12px 0;}
.ed-content a{color:var(--vert-clair);text-decoration:underline;}
.ed-actions{display:flex;align-items:center;gap:12px;padding-top:20px;border-top:1px solid var(--border);}
.ed-publish{background:var(--vert);color:var(--blanc);border:none;padding:12px 32px;border-radius:100px;font-family:'Inter',sans-serif;font-size:14px;font-weight:600;cursor:pointer;transition:background .2s;}
.ed-publish:hover{background:var(--vert-clair);}
.ed-cancel{background:transparent;color:var(--gris);border:1px solid var(--border);padding:12px 24px;border-radius:100px;font-family:'Inter',sans-serif;font-size:14px;cursor:pointer;}
.ed-msg{display:none;font-size:13px;color:var(--vert-clair);font-weight:600;}

/* ABOUT */
.about-wrap{padding:80px 48px;display:flex;justify-content:center;}
.about-card{background:var(--vert-pale);border-radius:16px;padding:56px;max-width:640px;width:100%;text-align:center;}
.about-icon{width:56px;height:56px;border-radius:50%;background:var(--vert);display:flex;align-items:center;justify-content:center;margin:0 auto 28px;font-size:22px;}
.about-card h2{font-family:'Playfair Display',serif;font-size:28px;font-weight:700;color:var(--vert);margin-bottom:20px;}
.about-card p{font-size:15px;color:var(--gris);line-height:1.8;margin-bottom:32px;}
.about-divider{width:48px;height:1px;background:var(--border);margin:0 auto 32px;}
.about-socials-title{font-family:'Playfair Display',serif;font-size:18px;font-weight:600;color:var(--encre);margin-bottom:20px;}
.about-socials{display:grid;grid-template-columns:1fr 1fr;gap:12px;text-align:left;}
.social-link{display:flex;align-items:center;gap:12px;padding:14px 18px;background:var(--blanc);border:1px solid var(--border);border-radius:10px;text-decoration:none;transition:all .2s;color:var(--encre);}
.social-link:hover{border-color:var(--vert);background:var(--blanc);box-shadow:0 4px 12px rgba(27,77,62,.08);}
.social-icon{width:32px;height:32px;border-radius:8px;background:var(--gris-pale);display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0;}
.social-plat{font-family:'DM Mono',monospace;font-size:9px;letter-spacing:.1em;text-transform:uppercase;color:var(--gris);display:block;margin-bottom:2px;}
.social-handle{font-size:13px;font-weight:500;color:var(--encre);}

/* CONTACT */
.contact-wrap{padding:80px 48px;display:flex;justify-content:center;}
.contact-card{background:var(--blanc);border:1px solid var(--border);border-radius:16px;padding:48px;max-width:560px;width:100%;box-shadow:0 4px 24px rgba(27,77,62,.06);}
.contact-card h2{font-family:'Playfair Display',serif;font-size:28px;font-weight:700;color:var(--vert);margin-bottom:12px;}
.contact-card p{font-size:14px;color:var(--gris);line-height:1.7;margin-bottom:32px;}
.contact-label{display:block;font-size:13px;font-weight:500;color:var(--encre);margin-bottom:8px;}
.contact-input{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:15px;outline:none;color:var(--encre);margin-bottom:16px;background:var(--gris-pale);transition:border-color .2s,background .2s;}
.contact-input:focus{border-color:var(--vert-mid);background:var(--blanc);}
.contact-textarea{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:15px;outline:none;color:var(--encre);resize:vertical;min-height:150px;margin-bottom:24px;background:var(--gris-pale);transition:border-color .2s,background .2s;}
.contact-textarea:focus{border-color:var(--vert-mid);background:var(--blanc);}
.contact-submit{background:var(--vert);color:var(--blanc);border:none;padding:14px 32px;border-radius:8px;font-family:'Inter',sans-serif;font-size:15px;font-weight:600;cursor:pointer;transition:background .2s;display:inline-flex;align-items:center;gap:8px;}
.contact-submit:hover{background:var(--vert-clair);}
.contact-ok{display:none;margin-top:16px;font-size:13px;color:var(--vert-clair);font-weight:500;}

/* FOOTER */
footer{background:var(--vert);padding:48px;text-align:center;}
.footer-logo{display:inline-flex;align-items:center;gap:8px;font-family:'Inter',sans-serif;font-size:18px;font-weight:700;color:var(--blanc);margin-bottom:12px;}
.footer-logo-dot{width:8px;height:8px;border-radius:50%;background:var(--vert-mid);}
.footer-copy{font-family:'DM Mono',monospace;font-size:11px;color:rgba(255,255,255,.4);letter-spacing:.06em;}

/* BLOG CATEGORIES */
.cat-section{margin-bottom:56px;}
.cat-title{font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--vert);margin-bottom:20px;padding-bottom:12px;border-bottom:2px solid var(--vert-pale);display:flex;align-items:center;gap:10px;}
.cat-count{font-family:'DM Mono',monospace;font-size:11px;color:var(--gris);font-weight:400;}
.cat-filter{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:32px;}
.cat-btn{background:var(--gris-pale);border:1px solid var(--border);color:var(--gris);padding:6px 16px;border-radius:100px;font-size:12px;font-weight:500;cursor:pointer;transition:all .2s;font-family:'Inter',sans-serif;}
.cat-btn:hover,.cat-btn.active{background:var(--vert);color:var(--blanc);border-color:var(--vert);}

/* FEATURED HOME */
.featured-label{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.18em;text-transform:uppercase;color:var(--vert-mid);margin-bottom:16px;display:block;}
.voir-plus{display:inline-flex;align-items:center;gap:8px;margin-top:40px;background:transparent;border:1px solid var(--vert);color:var(--vert);padding:10px 24px;border-radius:100px;font-family:'Inter',sans-serif;font-size:13px;font-weight:500;cursor:pointer;transition:all .2s;}
.voir-plus:hover{background:var(--vert);color:var(--blanc);}

/* SCROLL TOP */
.scroll-top{position:fixed;bottom:24px;right:24px;width:40px;height:40px;border-radius:50%;background:var(--vert);border:none;color:var(--blanc);cursor:pointer;font-size:16px;display:flex;align-items:center;justify-content:center;box-shadow:0 4px 12px rgba(27,77,62,.3);transition:background .2s;z-index:100;}
.scroll-top:hover{background:var(--vert-clair);}

@media(max-width:768px){
  nav{padding:0 20px;}
  .nav-links{display:none;}
  .hamburger{display:flex;}
  .hero{padding:60px 20px 48px;}
  .articles-wrap{padding:48px 20px;}
  .articles-grid{grid-template-columns:1fr;}
  .article-full,.comments-wrap{padding-left:20px;padding-right:20px;}
  .about-wrap,.contact-wrap{padding:48px 20px;}
  .about-socials{grid-template-columns:1fr;}
  footer{padding:32px 20px;}
  .editor-overlay{padding:0;}
  .editor-box{border-radius:0;min-height:100vh;}
}
</style>
</head>
<body>

<nav>
  <a class="nav-logo" onclick="go('home')">
    <div class="nav-logo-dot"></div>
    <span><span class="nav-logo-np">NextPath</span> <span class="nav-logo-blog">Blog</span></span>
  </a>
  <ul class="nav-links">
    <li><a onclick="go('home')" id="nav-home" class="active">Accueil</a></li>
    <li><a onclick="go('blog')" id="nav-blog">Blog</a></li>
    <li><a onclick="go('about')" id="nav-about">À propos</a></li>
    <li><a onclick="go('contact')" id="nav-contact">Contact</a></li>
  </ul>
  <button class="hamburger" onclick="toggleMenu()"><span></span><span></span><span></span></button>
</nav>

<div class="mobile-menu" id="mobile-menu">
  <a onclick="go('home');toggleMenu()">Accueil</a>
  <a onclick="go('blog');toggleMenu()">Blog</a>
  <a onclick="go('about');toggleMenu()">À propos</a>
  <a onclick="go('contact');toggleMenu()">Contact</a>
</div>

<!-- ACCUEIL -->
<div class="page active" id="page-home">
  <div class="hero">
    <span class="hero-eyebrow">NextPath Blog</span>
    <h1>L'endroit où les idées deviennent des actions.</h1>
    <p class="hero-desc">Ressources, réflexions et partages d'idées.</p>
    <div class="hero-divider"></div>
  </div>
  <div id="home-articles"></div>
</div>

<!-- BLOG -->
<div class="page" id="page-blog">
  <div class="articles-wrap">
    <div class="articles-header">
      <div class="articles-title">Tous les articles</div>
      
    </div>
    <div id="blog-categories"></div>
  </div>
</div>

<!-- ARTICLE -->
<div class="page" id="page-article">
  <div class="article-full" id="article-full-content"></div>
  <div class="comments-wrap" id="comments-wrap"></div>
</div>

<!-- À PROPOS -->
<div class="page" id="page-about">
  <div class="about-wrap">
    <div class="about-card">
      <div class="about-icon">🧭</div>
      <h2>À propos de nous</h2>
      <p>NextPath System est une plateforme dédiée à la jeunesse africaine pour aider les jeunes à savoir dans quoi se lancer, à identifier leur voie, et à avoir les outils pour y arriver.</p>
      <div class="about-divider"></div>
      <div class="about-socials-title">Rejoignez notre communauté</div>
      <div class="about-socials">
        <a href="https://instagram.com/nextpath.system" target="_blank" class="social-link">
          <div class="social-icon">📸</div>
          <div><span class="social-plat">Instagram</span><span class="social-handle">@nextpath.system</span></div>
        </a>
        <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="social-link">
          <div class="social-icon">▶️</div>
          <div><span class="social-plat">YouTube</span><span class="social-handle">@NextPathSystem</span></div>
        </a>
        <a href="https://tiktok.com/@nextpath.system" target="_blank" class="social-link">
          <div class="social-icon">🎵</div>
          <div><span class="social-plat">TikTok</span><span class="social-handle">@nextpath.system</span></div>
        </a>
        <a href="mailto:nextpathsystem@gmail.com" class="social-link">
          <div class="social-icon">✉️</div>
          <div><span class="social-plat">Email</span><span class="social-handle">nextpathsystem@gmail.com</span></div>
        </a>
      </div>
    </div>
  </div>
</div>

<!-- CONTACT -->
<div class="page" id="page-contact">
  <div class="contact-wrap">
    <div class="contact-card">
      <h2>Contactez-nous</h2>
      <p>Une question, une suggestion ou besoin de nous parler ? Remplissez ce formulaire et nous vous répondrons par email.</p>
      <form action="https://formspree.io/f/xdaqgdyw" method="POST" id="contact-form" onsubmit="handleSubmit(event)">
        <label class="contact-label">Nom complet</label>
        <input type="text" name="nom" class="contact-input" placeholder="Ex: Koffi Mensah" required>
        <label class="contact-label">Adresse Email</label>
        <input type="email" name="email" class="contact-input" placeholder="Ex: koffi.mensah@example.com" required>
        <label class="contact-label">Message</label>
        <textarea name="message" class="contact-textarea" placeholder="Décrivez votre besoin ou votre question en détails..." required></textarea>
        <button type="submit" class="contact-submit">Envoyer le message ✈</button>
        <div class="contact-ok" id="contact-ok" style="display:none;">✔ Message envoyé — nous vous répondrons bientôt !</div>
      </form>
    </div>
  </div>
</div>

<footer>
  <div class="footer-logo">
    <div class="footer-logo-dot"></div>
    NextPath Blog
  </div>
  <div class="footer-copy">© 2026 NextPath Blog</div>
</footer>

<button class="scroll-top" onclick="window.scrollTo({top:0,behavior:'smooth'})">↑</button>

<!-- ÉDITEUR ADMIN -->
<div class="editor-overlay" id="editor-overlay">
  <div class="editor-box">
    <div class="editor-head">
      <div class="editor-head-title">Rédiger un article</div>
      <button class="editor-head-close" onclick="closeEditor()">✕ Fermer</button>
    </div>
    <div class="editor-body">
      <label class="ed-label">Titre de l'article *</label>
      <input type="text" class="ed-input" id="ed-titre" placeholder="Ex : La discipline — ce que personne ne t'a dit">

      <label class="ed-label">Catégorie *</label>
      <select class="ed-select" id="ed-tag">
        <option value="Éducation">Éducation</option>
        <option value="Science">Science</option>
        <option value="Orientation">Orientation</option>
        <option value="Développement personnel">Développement personnel</option>
        <option value="Foi">Foi</option>
        <option value="NextPath">NextPath</option>
        <option value="Jeunesse">Jeunesse</option>
        <option value="Afrique">Afrique</option>
      </select>

      <label class="ed-label">URL d'image de couverture (optionnel)</label>
      <input type="text" class="ed-input" id="ed-img" placeholder="https://... (lien d'une image en ligne)">

      <label class="ed-label">Contenu *</label>
      <div class="ed-toolbar">
        <button class="tool" onclick="fmt('bold')"><b>G</b></button>
        <button class="tool" onclick="fmt('italic')"><i>I</i></button>
        <button class="tool" onclick="fmt('underline')"><u>S</u></button>
        <div class="tool-div"></div>
        <button class="tool" onclick="insQuote()">❝ Citation</button>
        <button class="tool" onclick="insLink()">🔗 Lien</button>
        <button class="tool" onclick="insImg()">🖼 Image</button>
        <div class="tool-div"></div>
        <button class="tool" onclick="fmt('insertUnorderedList')">• Liste</button>
        <button class="tool" onclick="fmt('insertOrderedList')">1. Liste num.</button>
      </div>
      <div class="ed-content" id="ed-content" contenteditable="true"></div>

      <div class="ed-actions">
        <button class="ed-publish" onclick="publier()">Publier l'article</button>
        <button class="ed-cancel" onclick="closeEditor()">Annuler</button>
        <span class="ed-msg" id="ed-msg">✔ Article publié !</span>
      </div>
    </div>
  </div>
</div>

<script>
// ══ PERSISTANCE ══
function sauvegarder() {
  try {
    localStorage.setItem('np_articles', JSON.stringify(articles));
    localStorage.setItem('np_comments', JSON.stringify(comments));
    localStorage.setItem('np_liked', JSON.stringify(liked));
  } catch(e) { console.log('Storage error:', e); }
}

function charger() {
  try {
    var a = localStorage.getItem('np_articles');
    var c = localStorage.getItem('np_comments');
    var l = localStorage.getItem('np_liked');
    if (a) articles = JSON.parse(a);
    if (c) comments = JSON.parse(c);
    if (l) liked = JSON.parse(l);
  } catch(e) { console.log('Load error:', e); }
}

var articles = [];
var comments = {};
var liked = {};

// ══ RENDU ACCUEIL — 3 articles à la une ══
function renderHome() {
  var c = document.getElementById('home-articles');
  if (articles.length === 0) {
    c.innerHTML = '<div class="empty-state">'
      +'<div class="empty-icon">✍️</div>'
      +'<div class="empty-title">Le premier article arrive bientôt.</div>'
      +'<div class="empty-desc">Reviens très vite — des idées qui construisent des vies.</div>'
      +'</div>';
    return;
  }
  var featured = articles.slice(0,3);
  var html = '<div class="articles-wrap">'
    +'<div class="articles-header">'
    +'<span class="featured-label">À la une</span>'
    +'<div class="articles-title">Dernières Publications</div>'
    +'<div class="articles-sub">Explorer nos perspectives</div>'
    +'</div>'
    +'<div class="articles-grid">';
  featured.forEach(function(a) {
    html += buildCard(a);
  });
  html += '</div>';
  if (articles.length > 3) {
    html += '<div style="text-align:center;margin-top:40px;">'
      +'<button class="voir-plus" onclick="go(\'blog\')">Voir tous les articles →</button>'
      +'</div>';
  }
  html += '</div>';
  c.innerHTML = html;
}

// ══ RENDU BLOG — tous les articles par catégorie ══
function renderBlog() {
  var c = document.getElementById('blog-categories');
  if (articles.length === 0) {
    c.innerHTML = '<div class="empty-state">'
      +'<div class="empty-icon">✍️</div>'
      +'<div class="empty-title">Aucun article pour l\'instant.</div>'
      +'<div class="empty-desc">Reviens très vite.</div>'
      +'</div>';
    return;
  }

  // Filtre actif
  var activeFilter = window.activeCat || 'Tous';
  var cats = ['Tous'];
  articles.forEach(function(a){
    var tag = a.tag || (a.tags && a.tags[0]) || '';
    if (tag && cats.indexOf(tag) === -1) cats.push(tag);
  });

  var filterHtml = '<div class="cat-filter">';
  cats.forEach(function(cat){
    filterHtml += '<button class="cat-btn'+(cat===activeFilter?' active':'')+'" onclick="filterBlog(\''+cat+'\')">'+cat+'</button>';
  });
  filterHtml += '</div>';

  var filtered = activeFilter === 'Tous' ? articles : articles.filter(function(a){
    return a.tag === activeFilter || (a.tags && a.tags.indexOf(activeFilter) !== -1);
  });

  // Grouper par catégorie si "Tous"
  var html = filterHtml;
  if (activeFilter === 'Tous') {
    var groups = {};
    filtered.forEach(function(a){
      var cat = a.tag || (a.tags && a.tags[0]) || 'Autre';
      if (!groups[cat]) groups[cat] = [];
      groups[cat].push(a);
    });
    Object.keys(groups).forEach(function(cat){
      html += '<div class="cat-section">'
        +'<div class="cat-title">'+cat+' <span class="cat-count">'+groups[cat].length+' article'+(groups[cat].length>1?'s':'')+'</span></div>'
        +'<div class="articles-grid">';
      groups[cat].forEach(function(a){ html += buildCard(a); });
      html += '</div></div>';
    });
  } else {
    html += '<div class="cat-section">'
      +'<div class="cat-title">'+activeFilter+' <span class="cat-count">'+filtered.length+' article'+(filtered.length>1?'s':'')+'</span></div>'
      +'<div class="articles-grid">';
    filtered.forEach(function(a){ html += buildCard(a); });
    html += '</div></div>';
  }

  c.innerHTML = html;
}

function filterBlog(cat) {
  window.activeCat = cat;
  renderBlog();
}

// ══ CARTE ARTICLE ══
function buildCard(a) {
  var tags = (a.tags||[a.tag]).map(function(t){return '<span class="card-tag">'+t+'</span>';}).join('');
  var imgHtml = a.img
    ? '<img class="card-img" src="'+a.img+'" alt="'+a.titre+'">'
    : '<div class="card-img-placeholder"><div class="card-img-placeholder-text">'+a.titre+'</div></div>';
  return '<div class="article-card" onclick="openArticle('+a.id+')">'
    +imgHtml
    +'<div class="card-body">'
    +'<div class="card-tags">'+tags+'</div>'
    +'<div class="card-meta">'
    +'<span class="card-date">'+a.date+'</span>'
    +'<span class="card-likes">♥ '+a.likes+'</span>'
    +'</div>'
    +'<div class="card-title">'+a.titre+'</div>'
    +'<div class="card-excerpt">'+a.extrait+'</div>'
    +'<div class="card-cta">Lire l\'article </div>'
    +'</div></div>';
}

// ══ ARTICLE ══
function openArticle(id) {
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  var tags = (a.tags||[a.tag]).map(function(t){return '<span class="card-tag">'+t+'</span>';}).join('');
  var imgHtml = a.img ? '<img class="article-full-img" src="'+a.img+'" alt="'+a.titre+'">' : '';
  var isLiked = liked[id]||false;

  document.getElementById('article-full-content').innerHTML =
    '<button class="article-full-back" onclick="go(\'home\')">← Retour</button>'
    +'<div class="article-full-tags">'+tags+'</div>'
    +'<h1>'+a.titre+'</h1>'
    +'<div class="article-full-meta">'+a.date+' · '+a.lecture+' de lecture</div>'
    +imgHtml
    +'<div class="article-body">'+a.corps+'</div>'
    +'<div class="likes-bar">'
    +'<button class="like-big'+(isLiked?' liked':'')+'" id="lbtn-'+id+'" onclick="toggleLike('+id+')">'+(isLiked?'♥ Tu as aimé':'♡ J\'aime cet article')+'</button>'
    +'<span class="like-count" id="lcnt-'+id+'">'+a.likes+' likes</span>'
    +'</div>';

  renderComments(id);
  go('article');
}

function toggleLike(id) {
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  liked[id] = !liked[id];
  a.likes += liked[id] ? 1 : -1;
  sauvegarder();
  var btn = document.getElementById('lbtn-'+id);
  var cnt = document.getElementById('lcnt-'+id);
  if (btn) { btn.className='like-big'+(liked[id]?' liked':''); btn.textContent=liked[id]?'♥ Tu as aimé':'♡ J\'aime cet article'; }
  if (cnt) cnt.textContent = a.likes+' likes';
}

function renderComments(id) {
  var comms = comments[id]||[];
  var list = comms.map(function(c){
    return '<div class="comment-item"><div class="comment-author">'+c.prenom+'</div>'
      +'<div class="comment-date">'+c.date+'</div>'
      +'<div class="comment-text">'+c.texte+'</div></div>';
  }).join('');

  document.getElementById('comments-wrap').innerHTML =
    '<hr class="comments-hr">'
    +'<div class="comments-heading">Commentaires ('+comms.length+')</div>'
    +'<div class="comment-form">'
    +'<input type="text" class="comment-input" id="cm-prenom" placeholder="Ton prénom">'
    +'<textarea class="comment-textarea" id="cm-texte" placeholder="Ton commentaire..."></textarea>'
    +'<button class="comment-btn" onclick="ajouterComment('+id+')">Publier</button>'
    +'<span class="comment-ok" id="cm-ok">✔ Commentaire publié !</span>'
    +'</div>'
    +'<div id="clist-'+id+'">'+list+'</div>';
}

function ajouterComment(id) {
  var p = document.getElementById('cm-prenom').value.trim();
  var t = document.getElementById('cm-texte').value.trim();
  if (!p||!t) { alert('Merci de remplir tous les champs.'); return; }
  if (!comments[id]) comments[id]=[];
  var date = new Date().toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});
  comments[id].unshift({prenom:p,texte:t,date:date});
  sauvegarder();
  document.getElementById('cm-prenom').value='';
  document.getElementById('cm-texte').value='';
  var ok = document.getElementById('cm-ok');
  ok.style.display='inline';
  setTimeout(function(){ok.style.display='none';},3000);
  renderComments(id);
  document.getElementById('comments-wrap').querySelector('.comments-heading').textContent='Commentaires ('+comments[id].length+')';
}

// ══ ÉDITEUR ══
function openEditor() {
  document.getElementById('ed-titre').value='';
  document.getElementById('ed-img').value='';
  document.getElementById('ed-content').innerHTML='';
  document.getElementById('ed-msg').style.display='none';
  document.getElementById('editor-overlay').style.display='block';
  document.body.style.overflow='hidden';
}
function closeEditor() {
  document.getElementById('editor-overlay').style.display='none';
  document.body.style.overflow='';
}
function fmt(cmd) { document.getElementById('ed-content').focus(); document.execCommand(cmd,false,null); }
function insQuote() { document.getElementById('ed-content').focus(); document.execCommand('formatBlock',false,'blockquote'); }
function insLink() {
  var url=prompt('URL du lien :'); if(!url) return;
  var txt=prompt('Texte du lien :')||url;
  document.getElementById('ed-content').focus();
  document.execCommand('insertHTML',false,'<a href="'+url+'" target="_blank">'+txt+'</a>');
}
function insImg() {
  var url=prompt('URL de l\'image :'); if(!url) return;
  document.getElementById('ed-content').focus();
  document.execCommand('insertHTML',false,'<img src="'+url+'" style="max-width:100%;border-radius:8px;margin:16px 0;">');
}
function publier() {
  var titre=document.getElementById('ed-titre').value.trim();
  var tag=document.getElementById('ed-tag').value;
  var img=document.getElementById('ed-img').value.trim();
  var corps=document.getElementById('ed-content').innerHTML.trim();
  if(!titre||!corps) { alert('Le titre et le contenu sont obligatoires.'); return; }
  var texte=document.getElementById('ed-content').innerText||'';
  var mots=texte.split(/\s+/).length;
  var mins=Math.max(1,Math.round(mots/200));
  var extrait=texte.substring(0,160).trim()+(texte.length>160?'...':'');
  var date=new Date().toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});
  articles.unshift({id:Date.now(),titre:titre,tag:tag,tags:[tag],img:img||'',extrait:extrait,corps:corps,date:date,lecture:mins+' min',likes:0});
  sauvegarder();
  var msg=document.getElementById('ed-msg');
  msg.style.display='inline';
  setTimeout(function(){ closeEditor(); go('home'); },1200);
}

// ══ CONTACT ══
function handleSubmit(e) {
  e.preventDefault();
  var form = document.getElementById('contact-form');
  var data = new FormData(form);
  fetch('https://formspree.io/f/xdaqgdyw', {
    method: 'POST',
    body: data,
    headers: { 'Accept': 'application/json' }
  }).then(function(response) {
    if (response.ok) {
      form.reset();
      var ok = document.getElementById('contact-ok');
      ok.style.display = 'block';
      setTimeout(function(){ ok.style.display='none'; }, 5000);
    } else {
      alert('Une erreur est survenue. Réessaie ou écris directement à nextpathsystem@gmail.com');
    }
  }).catch(function() {
    alert('Une erreur est survenue. Réessaie ou écris directement à nextpathsystem@gmail.com');
  });
}

// ══ NAV ══
function go(p) {
  document.querySelectorAll('.page').forEach(function(x){x.classList.remove('active');});
  document.querySelectorAll('.nav-links a').forEach(function(x){x.classList.remove('active');});
  document.getElementById('page-'+p).classList.add('active');
  var navEl=document.getElementById('nav-'+p);
  if(navEl) navEl.classList.add('active');
  window.scrollTo(0,0);
  document.getElementById('mobile-menu').classList.remove('open');
  if(p==='home') renderHome();
  if(p==='blog') renderBlog();
}
function toggleMenu() { document.getElementById('mobile-menu').classList.toggle('open'); }

// Fermer le menu mobile en cliquant en dehors
document.addEventListener('click', function(e) {
  var menu = document.getElementById('mobile-menu');
  var hamburger = document.querySelector('.hamburger');
  if (menu.classList.contains('open') && !menu.contains(e.target) && !hamburger.contains(e.target)) {
    menu.classList.remove('open');
  }
});

// ══ NPADMIN ══
var kbuf=[];
var kcode=[78,80,65,68,77,73,78];
document.addEventListener('keydown',function(e){
  kbuf.push(e.keyCode);
  if(kbuf.length>7) kbuf.shift();
  if(kbuf.join(',')===kcode.join(',')) { openEditor(); kbuf=[]; }
});



// ══ ARTICLE PAR DÉFAUT ══
var articleDefaut = {
  id: 1001,
  titre: "Identifier son potentiel dès le plus jeune âge : une clé pour mieux vivre",
  tag: "Développement personnel",
  tags: ["Développement personnel", "Jeunesse"],
  img: "",
  extrait: "Trop de jeunes avancent dans la vie sans jamais avoir appris à se connaître. Pourtant, en chacun réside un potentiel unique capable d'éclairer un monde trop souvent conformiste.",
  date: "1 juillet 2026",
  lecture: "4 min",
  likes: 0,
  corps: "<p>Trop de jeunes avancent dans la vie sans jamais avoir appris à se connaître. Ils s'adaptent, se taisent, se comparent… et finissent par douter de leur valeur. Pourtant, en chacun réside un potentiel unique, une touche personnelle capable d'éclairer un monde trop souvent conformiste. Apprendre à reconnaître ce que nous portons en nous dès le plus jeune âge, c'est se donner une chance de vivre avec sens, indépendance et confiance.</p><h3 style='font-family:Playfair Display,serif;font-size:22px;color:var(--vert);margin:32px 0 16px;font-weight:600;'>1. Pourquoi avons-nous peur de nous révéler ?</h3><p>La peur d'échouer, de ne pas être compris, ou de ne pas être à la hauteur, pousse bien des jeunes à se cacher. Se découvrir suppose d'assumer une part de responsabilité : celle de devenir acteur de sa vie. Et cela peut effrayer. Il est plus simple, en apparence, de se fondre dans la masse, d'ignorer ses particularités, que de faire face à ses dons inexploités.</p><p>Mais cette peur est une prison. Elle enferme notre originalité, étouffe notre créativité, et repousse notre épanouissement.</p><blockquote>Plus nous cachons ce que nous sommes, plus nous donnons l'image de quelqu'un qui n'a rien à offrir.</blockquote><h3 style='font-family:Playfair Display,serif;font-size:22px;color:var(--vert);margin:32px 0 16px;font-weight:600;'>2. Se connaître, c'est se libérer</h3><p>Chaque personne porte une particularité : un parfum, un ton, une énergie unique. L'ignorer revient à se couper de ce qui fait notre force. Oser explorer ses dons, même imparfaits, c'est ouvrir une voie vers la croissance personnelle et vers l'impact positif dans notre entourage.</p><p>Se connaître tôt, c'est éviter les pièges de la comparaison, des attentes extérieures, et de la perte de soi. C'est poser les bases d'une vie alignée avec qui l'on est, et non avec ce que les autres attendent.</p><h3 style='font-family:Playfair Display,serif;font-size:22px;color:var(--vert);margin:32px 0 16px;font-weight:600;'>3. Les bénéfices : relations vraies, indépendance, avenir préparé</h3><p><strong>Des relations sincères :</strong> quand on sait qui on est, on sait aussi avec qui on peut avancer. On cesse de se forcer à plaire, on attire ceux qui partagent notre vision, nos valeurs.</p><p><strong>Une indépendance intérieure :</strong> bien plus qu'une question financière, l'indépendance réside dans la capacité à ne pas dépendre du regard des autres ni des normes sociales. Se connaître, c'est se libérer de ce carcan.</p><p><strong>Une vie d'adulte préparée :</strong> l'âge adulte ne s'improvise pas. Il demande de la discipline, des choix, des responsabilités. Et ces choix sont plus justes quand ils viennent d'une connaissance solide de soi.</p><h3 style='font-family:Playfair Display,serif;font-size:22px;color:var(--vert);margin:32px 0 16px;font-weight:600;'>4. Le rôle clé des adultes : encadrer sans éteindre</h3><p>Aucun jeune ne peut se construire seul. Parents, enseignants, mentors : vous avez le pouvoir d'éveiller ou d'éteindre un potentiel. Vos mots peuvent soit révéler une graine de génie, soit briser une confiance naissante. Apprenez à écouter, à encourager, à guider sans étouffer.</p><blockquote>Au fond, l'aide de l'homme… c'est l'homme.</blockquote><h3 style='font-family:Playfair Display,serif;font-size:22px;color:var(--vert);margin:32px 0 16px;font-weight:600;'>Conclusion</h3><p>Identifier son potentiel dès le jeune âge, ce n'est pas une simple bonne idée : c'est une nécessité. Pour vivre avec clarté, pour impacter le monde, pour bâtir une génération solide, libre et lucide. Et cela commence maintenant — par une simple décision : apprendre à se connaître, oser se révéler, et ne plus jamais enterrer ce qui nous rend unique.</p><p style='font-style:italic;color:var(--gris);font-size:14px;margin-top:40px;padding-top:20px;border-top:1px solid var(--border);'>Écrit par Grace Kabondo, passionnée des sciences, de développement personnel et d'éducation.</p>"
};

window.addEventListener('load', function() {
  charger();
  // Ajouter l'article par défaut s'il n'existe pas déjà
  var existe = articles.find(function(a){ return a.id === 1001; });
  if (!existe) {
    articles.push(articleDefaut);
    sauvegarder();
  }
  renderHome();
});
</script>
</body>
</html>
