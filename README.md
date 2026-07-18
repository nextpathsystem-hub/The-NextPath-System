<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NextPath Blog</title>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,300;0,400;0,600;0,900;1,300;1,400;1,600&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{--vert:#1B4D3E;--vert-clair:#2D7A5F;--vert-pale:#E8F4EF;--vert-mid:#4FA882;--encre:#111A14;--gris:#6B7B72;--gris-pale:#F2F5F3;--blanc:#FFFFFF;--or-vert:#8DB87A;--border:#D4E4DA;}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--blanc);color:var(--encre);font-family:'DM Sans',sans-serif;font-size:16px;line-height:1.7;}
nav{position:fixed;top:0;left:0;right:0;z-index:100;background:var(--blanc);border-bottom:1px solid var(--border);padding:0 40px;height:64px;display:flex;align-items:center;justify-content:space-between;}
.nav-logo{font-family:'Fraunces',serif;font-size:20px;font-weight:600;color:var(--vert);cursor:pointer;text-decoration:none;letter-spacing:-.02em;}
.nav-logo span{color:var(--vert-mid);}
.nav-links{display:flex;gap:32px;list-style:none;align-items:center;}
.nav-links a{font-size:13px;font-weight:500;color:var(--gris);text-decoration:none;letter-spacing:.01em;transition:color .2s;cursor:pointer;}
.nav-links a:hover{color:var(--vert);}
.nav-write{background:var(--vert);color:var(--blanc)!important;padding:8px 18px;border-radius:100px;font-size:12px!important;font-weight:600!important;}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:4px;}
.hamburger span{display:block;width:20px;height:1.5px;background:var(--encre);}
.mobile-menu{display:none;position:fixed;top:64px;left:0;right:0;background:var(--blanc);border-bottom:1px solid var(--border);padding:20px 24px;z-index:99;flex-direction:column;gap:0;}
.mobile-menu.open{display:flex;}
.mobile-menu a{font-size:14px;font-weight:500;color:var(--encre);text-decoration:none;padding:12px 0;border-bottom:1px solid var(--border);cursor:pointer;display:block;}
.page{display:none;padding-top:64px;min-height:100vh;}
.page.active{display:block;}

/* HERO */
.hero{padding:80px 40px 64px;max-width:860px;margin:0 auto;border-bottom:1px solid var(--border);}
.hero-eyebrow{display:inline-flex;align-items:center;gap:8px;font-family:'DM Mono',monospace;font-size:11px;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--vert-mid);margin-bottom:24px;}
.hero-eyebrow::before{content:'';display:block;width:20px;height:1px;background:var(--vert-mid);}
.hero h1{font-family:'Fraunces',serif;font-size:clamp(36px,6vw,72px);font-weight:300;line-height:1.05;letter-spacing:-.03em;color:var(--vert);margin-bottom:24px;}
.hero h1 em{font-style:italic;color:var(--vert-mid);}
.hero-desc{font-size:17px;color:var(--gris);line-height:1.8;max-width:560px;}

/* VIDE */
.empty-state{padding:80px 40px;max-width:860px;margin:0 auto;text-align:center;}
.empty-icon{font-size:48px;margin-bottom:20px;opacity:.4;}
.empty-title{font-family:'Fraunces',serif;font-size:24px;font-weight:300;color:var(--vert);margin-bottom:12px;}
.empty-desc{font-size:15px;color:var(--gris);line-height:1.7;margin-bottom:32px;}

/* ARTICLES */
.articles-section{padding:64px 40px;max-width:860px;margin:0 auto;}
.section-label{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.16em;text-transform:uppercase;color:var(--gris);margin-bottom:32px;}
.articles-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:40px 32px;}
.article-card{cursor:pointer;border-top:1px solid var(--border);padding-top:24px;transition:all .2s;}
.article-card:hover .article-title{color:var(--vert-mid);}
.article-tag{font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--vert-clair);margin-bottom:10px;display:block;}
.article-title{font-family:'Fraunces',serif;font-size:20px;font-weight:400;line-height:1.3;letter-spacing:-.01em;color:var(--encre);margin-bottom:10px;transition:color .2s;}
.article-excerpt{font-size:13px;color:var(--gris);line-height:1.7;margin-bottom:14px;}
.article-meta{font-family:'DM Mono',monospace;font-size:10px;color:var(--gris);display:flex;align-items:center;gap:8px;flex-wrap:wrap;}
.like-btn{display:inline-flex;align-items:center;gap:4px;font-family:'DM Mono',monospace;font-size:11px;color:var(--gris);cursor:pointer;transition:color .2s;background:none;border:none;padding:0;}
.like-btn:hover,.like-btn.liked{color:var(--vert-clair);}

/* ARTICLE PAGE */
.article-page{max-width:680px;margin:0 auto;padding:64px 40px;}
.back-btn{font-size:12px;color:var(--gris);cursor:pointer;background:none;border:none;font-family:'DM Sans',sans-serif;display:inline-flex;align-items:center;gap:6px;transition:color .2s;padding:0;margin-bottom:32px;}
.back-btn:hover{color:var(--vert);}
.article-page-tag{font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--vert-clair);background:var(--vert-pale);padding:4px 10px;border-radius:100px;display:inline-block;margin-bottom:20px;}
.article-page h1{font-family:'Fraunces',serif;font-size:clamp(28px,4vw,48px);font-weight:300;line-height:1.15;letter-spacing:-.03em;color:var(--vert);margin-bottom:20px;}
.article-page-meta{font-family:'DM Mono',monospace;font-size:11px;color:var(--gris);margin-bottom:40px;display:flex;align-items:center;gap:12px;}
.article-body{font-size:17px;color:var(--encre);line-height:1.85;}
.article-body p{margin-bottom:24px;}
.article-body strong{color:var(--vert);font-weight:600;}
.article-body blockquote{border-left:3px solid var(--vert-mid);padding:16px 24px;background:var(--vert-pale);border-radius:0 6px 6px 0;margin:32px 0;font-family:'Fraunces',serif;font-size:19px;font-style:italic;color:var(--vert);line-height:1.6;}
.article-body img{max-width:100%;border-radius:8px;margin:24px 0;}
.article-body a{color:var(--vert-clair);text-decoration:underline;}

/* LIKES & COMMENTAIRES */
.likes-bar{display:flex;align-items:center;gap:16px;padding:24px 0;border-top:1px solid var(--border);margin-top:40px;}
.like-big-btn{display:inline-flex;align-items:center;gap:8px;background:var(--vert-pale);border:1px solid var(--border);padding:10px 20px;border-radius:100px;font-size:14px;font-weight:500;color:var(--vert);cursor:pointer;transition:all .2s;font-family:'DM Sans',sans-serif;}
.like-big-btn:hover,.like-big-btn.liked{background:var(--vert);color:var(--blanc);border-color:var(--vert);}
.comments-section{max-width:680px;margin:0 auto;padding:0 40px 80px;}
.comments-divider{border:none;border-top:1px solid var(--border);margin-bottom:40px;}
.comments-title{font-family:'Fraunces',serif;font-size:22px;font-weight:400;color:var(--encre);margin-bottom:28px;}
.comment-form{background:var(--gris-pale);border-radius:8px;padding:24px;margin-bottom:40px;}
.comment-form input,.comment-form textarea{width:100%;padding:10px 14px;border:1px solid var(--border);border-radius:6px;font-family:'DM Sans',sans-serif;font-size:14px;outline:none;background:var(--blanc);color:var(--encre);margin-bottom:10px;transition:border-color .2s;}
.comment-form input:focus,.comment-form textarea:focus{border-color:var(--vert-mid);}
.comment-form textarea{resize:vertical;min-height:100px;}
.comment-submit{background:var(--vert);color:var(--blanc);border:none;padding:10px 24px;border-radius:100px;font-family:'DM Sans',sans-serif;font-size:13px;font-weight:600;cursor:pointer;}
.comment-item{padding:20px 0;border-bottom:1px solid var(--border);}
.comment-author{font-weight:600;font-size:14px;color:var(--encre);margin-bottom:4px;}
.comment-date{font-family:'DM Mono',monospace;font-size:10px;color:var(--gris);margin-bottom:10px;}
.comment-text{font-size:14px;color:var(--gris);line-height:1.7;}

/* EDITEUR */
.editor-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.7);z-index:9999;overflow-y:auto;}
.editor-box{background:var(--blanc);max-width:860px;margin:32px auto;border-radius:12px;overflow:hidden;}
.editor-header{background:var(--vert);padding:20px 28px;display:flex;align-items:center;justify-content:space-between;}
.editor-header-title{font-family:'Fraunces',serif;font-size:20px;font-weight:300;font-style:italic;color:var(--blanc);}
.editor-close{background:rgba(255,255,255,.15);border:none;color:var(--blanc);padding:6px 14px;border-radius:100px;cursor:pointer;font-size:13px;font-family:'DM Sans',sans-serif;}
.editor-body{padding:28px;}
.editor-field{margin-bottom:20px;}
.editor-label{display:block;font-size:11px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--gris);margin-bottom:8px;font-family:'DM Mono',monospace;}
.editor-input{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'DM Sans',sans-serif;font-size:15px;outline:none;color:var(--encre);transition:border-color .2s;}
.editor-input:focus{border-color:var(--vert-mid);}
.editor-select{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'DM Sans',sans-serif;font-size:15px;outline:none;color:var(--encre);background:var(--blanc);}

/* TOOLBAR */
.editor-toolbar{display:flex;gap:6px;flex-wrap:wrap;padding:12px 16px;background:var(--gris-pale);border:1px solid var(--border);border-bottom:none;border-radius:8px 8px 0 0;}
.tool-btn{background:var(--blanc);border:1px solid var(--border);color:var(--encre);padding:6px 12px;border-radius:6px;cursor:pointer;font-size:13px;font-family:'DM Sans',sans-serif;transition:all .2s;display:inline-flex;align-items:center;gap:4px;}
.tool-btn:hover{background:var(--vert);color:var(--blanc);border-color:var(--vert);}
.tool-sep{width:1px;background:var(--border);margin:0 4px;}
.editor-content{width:100%;min-height:320px;padding:20px;border:1px solid var(--border);border-radius:0 0 8px 8px;font-family:'DM Sans',sans-serif;font-size:16px;line-height:1.8;outline:none;color:var(--encre);}
.editor-content:empty::before{content:'Commence à écrire ton article ici...';color:var(--gris);font-style:italic;}
.editor-content blockquote{border-left:3px solid var(--vert-mid);padding:12px 20px;background:var(--vert-pale);margin:16px 0;font-style:italic;color:var(--vert);border-radius:0 6px 6px 0;}
.editor-content img{max-width:100%;border-radius:8px;margin:12px 0;}
.editor-content a{color:var(--vert-clair);text-decoration:underline;}
.editor-actions{display:flex;gap:12px;margin-top:24px;padding-top:24px;border-top:1px solid var(--border);}
.btn-publier{background:var(--vert);color:var(--blanc);border:none;padding:12px 32px;border-radius:100px;font-family:'DM Sans',sans-serif;font-size:14px;font-weight:600;cursor:pointer;transition:background .2s;}
.btn-publier:hover{background:var(--vert-clair);}
.btn-annuler{background:transparent;color:var(--gris);border:1px solid var(--border);padding:12px 24px;border-radius:100px;font-family:'DM Sans',sans-serif;font-size:14px;cursor:pointer;}
.editor-msg{display:none;font-size:13px;color:var(--vert-clair);font-weight:600;align-self:center;}

/* ADMIN KEY */


/* ABOUT */
.about-page{max-width:680px;margin:0 auto;padding:64px 40px;}
.about-name{font-family:'Fraunces',serif;font-size:clamp(36px,5vw,56px);font-weight:300;font-style:italic;color:var(--vert);margin-bottom:8px;letter-spacing:-.03em;}
.about-role{font-family:'DM Mono',monospace;font-size:12px;letter-spacing:.12em;text-transform:uppercase;color:var(--vert-mid);margin-bottom:40px;}
.about-body{font-size:17px;color:var(--encre);line-height:1.85;}
.about-body p{margin-bottom:24px;}
.about-links{display:flex;flex-direction:column;gap:10px;margin-top:40px;}
.about-link{display:flex;align-items:center;gap:14px;padding:14px 18px;border:1px solid var(--border);border-radius:8px;text-decoration:none;transition:all .2s;color:var(--encre);}
.about-link:hover{border-color:var(--vert);background:var(--vert-pale);}
.about-link-plat{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.1em;text-transform:uppercase;color:var(--vert-mid);min-width:80px;}

/* CONTACT */
.contact-page{max-width:560px;margin:0 auto;padding:64px 40px;}
.contact-page h1{font-family:'Fraunces',serif;font-size:clamp(28px,4vw,44px);font-weight:300;color:var(--vert);margin-bottom:12px;letter-spacing:-.02em;}
.contact-page p{font-size:15px;color:var(--gris);line-height:1.8;margin-bottom:40px;}
.contact-form input,.contact-form textarea{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'DM Sans',sans-serif;font-size:15px;outline:none;color:var(--encre);margin-bottom:12px;transition:border-color .2s;}
.contact-form input:focus,.contact-form textarea:focus{border-color:var(--vert-mid);}
.contact-form textarea{resize:vertical;min-height:140px;}
.contact-submit{background:var(--vert);color:var(--blanc);border:none;padding:12px 32px;border-radius:100px;font-family:'DM Sans',sans-serif;font-size:14px;font-weight:600;cursor:pointer;}

footer{background:var(--vert);padding:48px 40px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:16px;}
.footer-logo{font-family:'Fraunces',serif;font-size:18px;font-weight:300;font-style:italic;color:rgba(255,255,255,.9);}
.footer-links{display:flex;gap:24px;flex-wrap:wrap;}
.footer-links a{font-size:12px;color:rgba(255,255,255,.5);text-decoration:none;transition:color .2s;cursor:pointer;}
.footer-links a:hover{color:rgba(255,255,255,.9);}
.footer-copy{font-family:'DM Mono',monospace;font-size:10px;color:rgba(255,255,255,.3);}

@media(max-width:768px){
  nav{padding:0 20px;}
  .nav-links{display:none;}
  .hamburger{display:flex;}
  .hero,.articles-section,.article-page,.comments-section,.about-page,.contact-page{padding-left:20px;padding-right:20px;}
  .articles-grid{grid-template-columns:1fr;}
  footer{padding:32px 20px;flex-direction:column;text-align:center;}
  .footer-links{justify-content:center;}
  .editor-box{margin:0;border-radius:0;min-height:100vh;}
}
</style>
</head>
<body>

<nav>
  <a class="nav-logo" onclick="go('home')">NextPath<span>Blog</span></a>
  <ul class="nav-links">
    <li><a onclick="go('home')">Accueil</a></li>
    <li><a onclick="go('about')">À propos</a></li>
    <li><a onclick="go('contact')">Contact</a></li>
    <li><a href="https://instagram.com/nextpath.system" target="_blank" class="nav-write">Me suivre</a></li>
  </ul>
  <button class="hamburger" onclick="toggleMenu()"><span></span><span></span><span></span></button>
</nav>

<div class="mobile-menu" id="mobile-menu">
  <a onclick="go('home');toggleMenu()">Accueil</a>
  <a onclick="go('about');toggleMenu()">À propos</a>
  <a onclick="go('contact');toggleMenu()">Contact</a>
  <a href="https://instagram.com/nextpath.system" target="_blank">Me suivre →</a>
</div>

<!-- ACCUEIL -->
<div class="page active" id="page-home">
  <div class="hero">
    <div class="hero-eyebrow">NextPath Blog </div>
    <h1>Des idées qui <em>construisent</em><br>des vies.</h1>
    <p class="hero-desc">Un espace pour réfléchir, partager et grandir ensemble — sur l'éducation, la science, l'orientation et la construction de soi.</p>
  </div>
  <div id="home-content"></div>
</div>

<!-- ARTICLE -->
<div class="page" id="page-article">
  <div class="article-page" id="article-content"></div>
  <div class="comments-section" id="comments-section"></div>
</div>

<!-- ABOUT -->
<div class="page" id="page-about">
  <div class="about-page">
    <div class="about-name">Grace Kabondo</div>
    <div class="about-role">Fondatrice · NextPath System · Scientifique</div>
    <div class="about-body">
      <p>J'ai grandi à Lubumbashi, en RDC. J'ai fait mes études en France — une Licence en Chimie-Biologie, puis un Master en Sciences du Médicament à Nantes Université.</p>
      <p>Pendant longtemps j'ai attendu que les opportunités viennent à moi. Un jour j'ai décidé que c'était fini. J'ai fondé NextPath System pour aider les jeunes africains à savoir dans quoi se lancer, à identifier leur voie, et à avoir les outils pour y arriver.</p>
      <p>Ce blog c'est mon espace d'expression. Je parle d'éducation, de science, d'orientation, de foi et de construction de soi.</p>
      <p><em>"Plus tu te caches de ce que tu es, plus tu donnes l'image de quelqu'un qui n'a rien à offrir."</em></p>
    </div>
    <div class="about-links">
      <a href="https://instagram.com/nextpath.system" target="_blank" class="about-link"><span class="about-link-plat">Instagram</span><span>@nextpath.system</span></a>
      <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="about-link"><span class="about-link-plat">YouTube</span><span>NextPath System</span></a>
      <a href="https://tiktok.com/@nextpath.system" target="_blank" class="about-link"><span class="about-link-plat">TikTok</span><span>@nextpath.system</span></a>
      <a href="mailto:nextpathsystem@gmail.com" class="about-link"><span class="about-link-plat">Email</span><span>nextpathsystem@gmail.com</span></a>
    </div>
  </div>
</div>

<!-- CONTACT -->
<div class="page" id="page-contact">
  <div class="contact-page">
    <h1>Écris-moi.</h1>
    <p>Une question, une idée, un témoignage — je lis tout personnellement.</p>
    <div class="contact-form">
      <input type="text" id="c-nom" placeholder="Ton prénom">
      <input type="email" id="c-email" placeholder="Ton email">
      <textarea id="c-msg" placeholder="Ton message..."></textarea>
      <button class="contact-submit" onclick="envoyerContact()">Envoyer</button>
      <p id="contact-ok" style="display:none;margin-top:12px;font-size:13px;color:var(--vert-clair);">✔ Merci — je te répondrai bientôt.</p>
    </div>
  </div>
</div>

<footer>
  <div class="footer-logo">NextPath Blog</div>
  <div class="footer-links">
    <a onclick="go('home')">Accueil</a>
    <a onclick="go('about')">À propos</a>
    <a onclick="go('contact')">Contact</a>
    <a href="https://instagram.com/nextpath.system" target="_blank">Instagram</a>
  </div>
  <div class="footer-copy">© 2026 </div>
</footer>

<!-- ÉDITEUR -->
<div class="editor-overlay" id="editor-overlay">
  <div class="editor-box">
    <div class="editor-header">
      <div class="editor-header-title">Rédiger un article</div>
      <button class="editor-close" onclick="closeEditor()">✕ Fermer</button>
    </div>
    <div class="editor-body">
      <div class="editor-field">
        <label class="editor-label">Titre de l'article *</label>
        <input type="text" class="editor-input" id="ed-titre" placeholder="Ex : La discipline — ce que personne ne t'a dit">
      </div>
      <div class="editor-field">
        <label class="editor-label">Catégorie *</label>
        <select class="editor-select" id="ed-tag">
          <option value="Éducation">Éducation</option>
          <option value="Science">Science</option>
          <option value="Orientation">Orientation</option>
          <option value="Développement personnel">Développement personnel</option>
          <option value="Foi">Foi</option>
          <option value="NextPath">NextPath</option>
        </select>
      </div>
      <div class="editor-field">
        <label class="editor-label">Contenu *</label>
        <div class="editor-toolbar">
          <button class="tool-btn" onclick="format('bold')"><strong>G</strong></button>
          <button class="tool-btn" onclick="format('italic')"><em>I</em></button>
          <button class="tool-btn" onclick="format('underline')"><u>S</u></button>
          <div class="tool-sep"></div>
          <button class="tool-btn" onclick="insertQuote()">❝ Citation</button>
          <button class="tool-btn" onclick="insertLink()">🔗 Lien</button>
          <button class="tool-btn" onclick="insertImage()">🖼 Image</button>
          <div class="tool-sep"></div>
          <button class="tool-btn" onclick="format('insertUnorderedList')">• Liste</button>
        </div>
        <div class="editor-content" id="ed-content" contenteditable="true"></div>
      </div>
      <div class="editor-actions">
        <button class="btn-publier" onclick="publierArticle()">Publier l'article</button>
        <button class="btn-annuler" onclick="closeEditor()">Annuler</button>
        <span class="editor-msg" id="ed-msg">✔ Article publié !</span>
      </div>
    </div>
  </div>
</div>



<script>
var articles = [];
var comments = {};
var likedArticles = {};
var editingId = null;

// ══ RENDU ACCUEIL ══
function renderHome() {
  var c = document.getElementById('home-content');
  if (articles.length === 0) {
    c.innerHTML = '<div class="empty-state">'
      +'<div class="empty-icon">✍️</div>'
      +'<div class="empty-title">Aucun article pour l\'instant.</div>'
      +'<div class="empty-desc">Le premier article arrive bientôt.<br>Tape <strong>NPADMIN</strong> pour commencer à écrire.</div>'
      +'</div>';
    return;
  }
  var grid = '<div class="articles-section"><div class="section-label">Tous les articles</div><div class="articles-grid">';
  articles.forEach(function(a) {
    var liked = likedArticles[a.id] || false;
    grid += '<div class="article-card" onclick="openArticle('+a.id+')">'
      +'<span class="article-tag">'+a.tag+'</span>'
      +'<div class="article-title">'+a.titre+'</div>'
      +'<div class="article-excerpt">'+a.extrait+'</div>'
      +'<div class="article-meta">'+a.date+' · '+a.lecture
      +' · <button class="like-btn'+(liked?' liked':'')
      +'" onclick="toggleLike(event,'+a.id+')">'+(liked?'♥':'♡')
      +' <span id="lc-'+a.id+'">'+a.likes+'</span></button>'
      +'</div></div>';
  });
  grid += '</div></div>';
  c.innerHTML = grid;
}

// ══ ARTICLE ══
function openArticle(id) {
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  var liked = likedArticles[id] || false;

  document.getElementById('article-content').innerHTML =
    '<button class="back-btn" onclick="go(\'home\')">← Retour</button>'
    +'<span class="article-page-tag">'+a.tag+'</span>'
    +'<h1>'+a.titre+'</h1>'
    +'<div class="article-page-meta">'+a.date+' · '+a.lecture+' de lecture</div>'
    +'<div class="article-body">'+a.corps+'</div>';

  renderComments(id, liked, a);
  go('article');
}

function renderComments(id, liked, a) {
  var comms = comments[id] || [];
  var commHtml = comms.map(function(c){
    return '<div class="comment-item">'
      +'<div class="comment-author">'+c.prenom+'</div>'
      +'<div class="comment-date">'+c.date+'</div>'
      +'<div class="comment-text">'+c.texte+'</div>'
      +'</div>';
  }).join('');

  document.getElementById('comments-section').innerHTML =
    '<div class="likes-bar">'
    +'<button class="like-big-btn'+(liked?' liked':'')+'" id="lbtn-'+id+'" onclick="toggleLikePage('+id+')">'+(liked?'♥ Tu as aimé':'♡ J\'aime cet article')+'</button>'
    +'<span style="font-family:\'DM Mono\',monospace;font-size:12px;color:var(--gris);" id="lbig-'+id+'">'+a.likes+' likes</span>'
    +'</div>'
    +'<hr class="comments-divider">'
    +'<div class="comments-title">Commentaires ('+comms.length+')</div>'
    +'<div class="comment-form">'
    +'<input type="text" id="cm-prenom" placeholder="Ton prénom">'
    +'<textarea id="cm-texte" placeholder="Ton commentaire..."></textarea>'
    +'<button class="comment-submit" onclick="ajouterCommentaire('+id+')">Publier</button>'
    +'<span id="cm-ok" style="display:none;font-size:12px;color:var(--vert-clair);margin-left:12px;">✔ Publié !</span>'
    +'</div>'
    +'<div id="clist-'+id+'">'+commHtml+'</div>';
}

function toggleLike(e, id) {
  e.stopPropagation();
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  likedArticles[id] = !likedArticles[id];
  a.likes += likedArticles[id] ? 1 : -1;
  var el = document.getElementById('lc-'+id);
  if (el) el.textContent = a.likes;
}

function toggleLikePage(id) {
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  likedArticles[id] = !likedArticles[id];
  a.likes += likedArticles[id] ? 1 : -1;
  var btn = document.getElementById('lbtn-'+id);
  var cnt = document.getElementById('lbig-'+id);
  if (btn) { btn.className = 'like-big-btn'+(likedArticles[id]?' liked':''); btn.textContent = likedArticles[id]?'♥ Tu as aimé':'♡ J\'aime cet article'; }
  if (cnt) cnt.textContent = a.likes+' likes';
}

function ajouterCommentaire(id) {
  var p = document.getElementById('cm-prenom').value.trim();
  var t = document.getElementById('cm-texte').value.trim();
  if (!p||!t) { alert('Merci de remplir tous les champs.'); return; }
  if (!comments[id]) comments[id] = [];
  var date = new Date().toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});
  comments[id].unshift({prenom:p,texte:t,date:date});
  document.getElementById('cm-prenom').value = '';
  document.getElementById('cm-texte').value = '';
  var ok = document.getElementById('cm-ok');
  ok.style.display = 'inline';
  setTimeout(function(){ok.style.display='none';},3000);
  var list = document.getElementById('clist-'+id);
  list.innerHTML = comments[id].map(function(c){
    return '<div class="comment-item"><div class="comment-author">'+c.prenom+'</div><div class="comment-date">'+c.date+'</div><div class="comment-text">'+c.texte+'</div></div>';
  }).join('');
  document.querySelector('.comments-title').textContent = 'Commentaires ('+comments[id].length+')';
}

// ══ ÉDITEUR ══
function openEditor() {
  editingId = null;
  document.getElementById('ed-titre').value = '';
  document.getElementById('ed-content').innerHTML = '';
  document.getElementById('ed-msg').style.display = 'none';
  document.getElementById('editor-overlay').style.display = 'block';
  document.body.style.overflow = 'hidden';
}

function closeEditor() {
  document.getElementById('editor-overlay').style.display = 'none';
  document.body.style.overflow = '';
}

function format(cmd) {
  document.getElementById('ed-content').focus();
  document.execCommand(cmd, false, null);
}

function insertQuote() {
  document.getElementById('ed-content').focus();
  document.execCommand('formatBlock', false, 'blockquote');
}

function insertLink() {
  var url = prompt('URL du lien :');
  if (!url) return;
  var text = prompt('Texte du lien :') || url;
  document.getElementById('ed-content').focus();
  document.execCommand('insertHTML', false, '<a href="'+url+'" target="_blank">'+text+'</a>');
}

function insertImage() {
  var url = prompt('URL de l\'image (ou lien Google Drive partageable) :');
  if (!url) return;
  document.getElementById('ed-content').focus();
  document.execCommand('insertHTML', false, '<img src="'+url+'" alt="image" style="max-width:100%;border-radius:8px;margin:16px 0;">');
}

function publierArticle() {
  var titre = document.getElementById('ed-titre').value.trim();
  var tag = document.getElementById('ed-tag').value;
  var corps = document.getElementById('ed-content').innerHTML.trim();
  if (!titre || !corps || corps === '') { alert('Le titre et le contenu sont obligatoires.'); return; }
  
  var texte = document.getElementById('ed-content').innerText || '';
  var mots = texte.split(/\s+/).length;
  var mins = Math.max(1, Math.round(mots / 200));
  var extrait = texte.substring(0, 160).trim() + (texte.length > 160 ? '...' : '');
  var date = new Date().toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});
  var id = Date.now();

  articles.unshift({id:id, titre:titre, tag:tag, extrait:extrait, corps:corps, date:date, lecture:mins+' min', likes:0});

  var msg = document.getElementById('ed-msg');
  msg.style.display = 'inline';
  setTimeout(function(){
    closeEditor();
    go('home');
  }, 1200);
}

// ══ NAVIGATION ══
function go(p) {
  document.querySelectorAll('.page').forEach(function(x){x.classList.remove('active');});
  var t = document.getElementById('page-'+p);
  if (t) { t.classList.add('active'); window.scrollTo(0,0); }
  document.getElementById('mobile-menu').classList.remove('open');
  if (p === 'home') renderHome();
}

function toggleMenu() {
  document.getElementById('mobile-menu').classList.toggle('open');
}

// ══ NPADMIN ══
var adminKeys = [];
var adminCode = [78,80,65,68,77,73,78];
document.addEventListener('keydown', function(e) {
  adminKeys.push(e.keyCode);
  if (adminKeys.length > 7) adminKeys.shift();
  if (adminKeys.join(',') === adminCode.join(',')) { openEditor(); adminKeys = []; }
});

function envoyerContact() {
  var n = document.getElementById('c-nom').value.trim();
  var e = document.getElementById('c-email').value.trim();
  var m = document.getElementById('c-msg').value.trim();
  if (!n||!e||!m) { alert('Merci de remplir tous les champs.'); return; }
  document.getElementById('contact-ok').style.display = 'block';
  document.getElementById('c-nom').value = '';
  document.getElementById('c-email').value = '';
  document.getElementById('c-msg').value = '';
}

window.addEventListener('load', renderHome);
</script>
</body>
</html>
