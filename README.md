<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NextPath Blog</title>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,300;0,400;0,600;0,900;1,300;1,400;1,600&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --vert:#1B4D3E;
  --vert-clair:#2D7A5F;
  --vert-pale:#E8F4EF;
  --vert-mid:#4FA882;
  --encre:#111A14;
  --gris:#6B7B72;
  --gris-pale:#F2F5F3;
  --blanc:#FFFFFF;
  --or-vert:#8DB87A;
  --border:#D4E4DA;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--blanc);color:var(--encre);font-family:'DM Sans',sans-serif;font-size:16px;line-height:1.7;}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:100;background:var(--blanc);border-bottom:1px solid var(--border);padding:0 40px;height:64px;display:flex;align-items:center;justify-content:space-between;}
.nav-logo{font-family:'Fraunces',serif;font-size:20px;font-weight:600;color:var(--vert);cursor:pointer;text-decoration:none;letter-spacing:-.02em;}
.nav-logo span{color:var(--vert-mid);}
.nav-links{display:flex;gap:32px;list-style:none;align-items:center;}
.nav-links a{font-size:13px;font-weight:500;color:var(--gris);text-decoration:none;letter-spacing:.01em;transition:color .2s;cursor:pointer;}
.nav-links a:hover{color:var(--vert);}
.nav-write{background:var(--vert);color:var(--blanc)!important;padding:8px 18px;border-radius:100px;font-size:12px!important;font-weight:600!important;letter-spacing:.04em!important;transition:background .2s!important;}
.nav-write:hover{background:var(--vert-clair)!important;}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:4px;}
.hamburger span{display:block;width:20px;height:1.5px;background:var(--encre);}
.mobile-menu{display:none;position:fixed;top:64px;left:0;right:0;background:var(--blanc);border-bottom:1px solid var(--border);padding:20px 24px;z-index:99;flex-direction:column;gap:0;}
.mobile-menu.open{display:flex;}
.mobile-menu a{font-size:14px;font-weight:500;color:var(--encre);text-decoration:none;padding:12px 0;border-bottom:1px solid var(--border);cursor:pointer;}

/* PAGES */
.page{display:none;padding-top:64px;min-height:100vh;}
.page.active{display:block;}

/* HERO */
.hero{padding:80px 40px 64px;max-width:860px;margin:0 auto;border-bottom:1px solid var(--border);}
.hero-eyebrow{display:inline-flex;align-items:center;gap:8px;font-family:'DM Mono',monospace;font-size:11px;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--vert-mid);margin-bottom:24px;}
.hero-eyebrow::before{content:'';display:block;width:20px;height:1px;background:var(--vert-mid);}
.hero h1{font-family:'Fraunces',serif;font-size:clamp(36px,6vw,72px);font-weight:300;line-height:1.05;letter-spacing:-.03em;color:var(--vert);margin-bottom:24px;}
.hero h1 em{font-style:italic;color:var(--vert-mid);}
.hero-desc{font-size:17px;color:var(--gris);line-height:1.8;max-width:560px;}

/* FEATURED */
.featured{padding:64px 40px;max-width:860px;margin:0 auto;border-bottom:1px solid var(--border);}
.section-label{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.16em;text-transform:uppercase;color:var(--gris);margin-bottom:32px;}
.featured-card{display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:start;cursor:pointer;}
.featured-card:hover .featured-title{color:var(--vert-mid);}
.featured-tag{display:inline-block;font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--vert-clair);background:var(--vert-pale);padding:4px 10px;border-radius:100px;margin-bottom:16px;}
.featured-title{font-family:'Fraunces',serif;font-size:clamp(22px,3vw,36px);font-weight:400;line-height:1.2;letter-spacing:-.02em;color:var(--encre);margin-bottom:16px;transition:color .2s;}
.featured-excerpt{font-size:15px;color:var(--gris);line-height:1.75;margin-bottom:20px;}
.featured-meta{display:flex;align-items:center;gap:12px;font-family:'DM Mono',monospace;font-size:11px;color:var(--gris);}
.featured-meta span{color:var(--border);}
.featured-visual{background:var(--vert);border-radius:8px;aspect-ratio:4/3;display:flex;align-items:center;justify-content:center;overflow:hidden;position:relative;}
.featured-visual-text{font-family:'Fraunces',serif;font-size:clamp(28px,4vw,52px);font-weight:300;font-style:italic;color:rgba(255,255,255,.15);text-align:center;padding:24px;line-height:1.2;}
.featured-visual-tag{position:absolute;bottom:20px;left:20px;font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.1em;text-transform:uppercase;color:var(--or-vert);}

/* GRID ARTICLES */
.articles-section{padding:64px 40px;max-width:860px;margin:0 auto;}
.articles-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:40px 32px;margin-top:32px;}
.article-card{cursor:pointer;border-top:1px solid var(--border);padding-top:24px;transition:all .2s;}
.article-card:hover .article-title{color:var(--vert-mid);}
.article-tag{font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--vert-clair);margin-bottom:10px;display:block;}
.article-title{font-family:'Fraunces',serif;font-size:20px;font-weight:400;line-height:1.3;letter-spacing:-.01em;color:var(--encre);margin-bottom:10px;transition:color .2s;}
.article-excerpt{font-size:13px;color:var(--gris);line-height:1.7;margin-bottom:14px;}
.article-meta{font-family:'DM Mono',monospace;font-size:10px;color:var(--gris);display:flex;align-items:center;gap:8px;}
.likes{display:inline-flex;align-items:center;gap:4px;font-family:'DM Mono',monospace;font-size:11px;color:var(--gris);cursor:pointer;transition:color .2s;background:none;border:none;padding:0;}
.likes:hover{color:var(--vert-clair);}
.likes.liked{color:var(--vert-clair);}

/* ARTICLE PAGE */
.article-page{max-width:680px;margin:0 auto;padding:64px 40px;}
.article-page-eyebrow{display:flex;align-items:center;gap:12px;margin-bottom:32px;}
.back-btn{font-size:12px;color:var(--gris);cursor:pointer;background:none;border:none;font-family:'DM Sans',sans-serif;display:flex;align-items:center;gap:6px;transition:color .2s;padding:0;}
.back-btn:hover{color:var(--vert);}
.article-page-tag{font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--vert-clair);background:var(--vert-pale);padding:4px 10px;border-radius:100px;}
.article-page h1{font-family:'Fraunces',serif;font-size:clamp(28px,4vw,48px);font-weight:300;line-height:1.15;letter-spacing:-.03em;color:var(--vert);margin-bottom:20px;}
.article-page-meta{font-family:'DM Mono',monospace;font-size:11px;color:var(--gris);margin-bottom:40px;display:flex;align-items:center;gap:12px;}
.article-page-meta span{color:var(--border);}
.article-body{font-size:17px;color:var(--encre);line-height:1.85;}
.article-body p{margin-bottom:24px;}
.article-body strong{color:var(--vert);font-weight:600;}
.article-body blockquote{border-left:3px solid var(--vert-mid);padding:16px 24px;background:var(--vert-pale);border-radius:0 6px 6px 0;margin:32px 0;font-family:'Fraunces',serif;font-size:19px;font-style:italic;color:var(--vert);line-height:1.6;}

/* COMMENTS */
.comments-section{max-width:680px;margin:0 auto;padding:0 40px 80px;}
.comments-divider{border:none;border-top:1px solid var(--border);margin-bottom:40px;}
.comments-title{font-family:'Fraunces',serif;font-size:22px;font-weight:400;color:var(--encre);margin-bottom:28px;}
.comment-form{background:var(--gris-pale);border-radius:8px;padding:24px;margin-bottom:40px;}
.comment-form input,.comment-form textarea{width:100%;padding:10px 14px;border:1px solid var(--border);border-radius:6px;font-family:'DM Sans',sans-serif;font-size:14px;outline:none;background:var(--blanc);color:var(--encre);margin-bottom:10px;transition:border-color .2s;}
.comment-form input:focus,.comment-form textarea:focus{border-color:var(--vert-mid);}
.comment-form textarea{resize:vertical;min-height:100px;}
.comment-submit{background:var(--vert);color:var(--blanc);border:none;padding:10px 24px;border-radius:100px;font-family:'DM Sans',sans-serif;font-size:13px;font-weight:600;cursor:pointer;transition:background .2s;}
.comment-submit:hover{background:var(--vert-clair);}
.comment-item{padding:20px 0;border-bottom:1px solid var(--border);}
.comment-author{font-weight:600;font-size:14px;color:var(--encre);margin-bottom:4px;}
.comment-date{font-family:'DM Mono',monospace;font-size:10px;color:var(--gris);margin-bottom:10px;}
.comment-text{font-size:14px;color:var(--gris);line-height:1.7;}
.likes-bar{display:flex;align-items:center;gap:16px;padding:24px 0;border-top:1px solid var(--border);margin-top:40px;}
.like-big-btn{display:inline-flex;align-items:center;gap:8px;background:var(--vert-pale);border:1px solid var(--border);padding:10px 20px;border-radius:100px;font-size:14px;font-weight:500;color:var(--vert);cursor:pointer;transition:all .2s;font-family:'DM Sans',sans-serif;}
.like-big-btn:hover,.like-big-btn.liked{background:var(--vert);color:var(--blanc);border-color:var(--vert);}

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
.about-link-handle{font-size:14px;font-weight:500;}

/* CONTACT */
.contact-page{max-width:560px;margin:0 auto;padding:64px 40px;}
.contact-page h1{font-family:'Fraunces',serif;font-size:clamp(28px,4vw,44px);font-weight:300;color:var(--vert);margin-bottom:12px;letter-spacing:-.02em;}
.contact-page p{font-size:15px;color:var(--gris);line-height:1.8;margin-bottom:40px;}
.contact-form input,.contact-form textarea{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'DM Sans',sans-serif;font-size:15px;outline:none;background:var(--blanc);color:var(--encre);margin-bottom:12px;transition:border-color .2s;}
.contact-form input:focus,.contact-form textarea:focus{border-color:var(--vert-mid);}
.contact-form textarea{resize:vertical;min-height:140px;}
.contact-submit{background:var(--vert);color:var(--blanc);border:none;padding:12px 32px;border-radius:100px;font-family:'DM Sans',sans-serif;font-size:14px;font-weight:600;cursor:pointer;transition:background .2s;display:inline-block;}
.contact-submit:hover{background:var(--vert-clair);}

/* FOOTER */
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
  .hero,.featured,.articles-section,.article-page,.comments-section,.about-page,.contact-page{padding-left:20px;padding-right:20px;}
  .featured-card{grid-template-columns:1fr;}
  .featured-visual{display:none;}
  .articles-grid{grid-template-columns:1fr;}
  footer{padding:32px 20px;flex-direction:column;text-align:center;}
  .footer-links{justify-content:center;}
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
    <div class="hero-eyebrow">NextPath Blog · Grace Kabondo</div>
    <h1>Des idées qui <em>construisent</em><br>des vies.</h1>
    <p class="hero-desc">Un espace pour réfléchir, partager et grandir ensemble — sur l'éducation, la science, l'orientation et la construction de soi.</p>
  </div>

  <div class="featured" id="featured-section">
    <div class="section-label">À la une</div>
    <div id="featured-container"></div>
  </div>

  <div class="articles-section">
    <div class="section-label">Tous les articles</div>
    <div class="articles-grid" id="articles-grid"></div>
  </div>
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
      <p>Pendant longtemps j'ai attendu que les opportunités viennent à moi. Un jour j'ai décidé que c'était fini. J'ai fondé NextPath System — une plateforme dédiée à la jeunesse africaine pour aider les jeunes à savoir dans quoi se lancer, à identifier leur voie, et à avoir les outils pour y arriver.</p>
      <p>Ce blog c'est mon espace d'expression. Je parle d'éducation, de science, d'orientation, de foi et de construction de soi. Je n'ai pas toutes les réponses. Mais j'apprends en public — et j'invite les autres à en faire autant.</p>
      <p><em>"Plus tu te caches de ce que tu es, plus tu donnes l'image de quelqu'un qui n'a rien à offrir."</em></p>
    </div>
    <div class="about-links">
      <a href="https://instagram.com/nextpath.system" target="_blank" class="about-link"><span class="about-link-plat">Instagram</span><span class="about-link-handle">@nextpath.system</span></a>
      <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="about-link"><span class="about-link-plat">YouTube</span><span class="about-link-handle">NextPath System</span></a>
      <a href="https://tiktok.com/@nextpath.system" target="_blank" class="about-link"><span class="about-link-plat">TikTok</span><span class="about-link-handle">@nextpath.system</span></a>
      <a href="mailto:nextpathsystem@gmail.com" class="about-link"><span class="about-link-plat">Email</span><span class="about-link-handle">nextpathsystem@gmail.com</span></a>
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
  <div class="footer-copy">© 2026 Grace Kabondo</div>
</footer>

<script>
// ══ DONNÉES ══
var articles = [
  {
    id: 1,
    titre: "La discipline — ce que personne ne t'a vraiment dit",
    tag: "Développement personnel",
    extrait: "Brian Tracy la définit comme faire ce qu'on doit faire quand on doit le faire. Mais quelque chose m'a choquée dans cette définition.",
    corps: `<p>Brian Tracy définit l'autodiscipline comme l'habileté de faire ce qu'on doit faire, quand on doit le faire — qu'on en ait envie ou pas.</p><p>J'aime cette définition. Mais elle m'a choquée.</p><blockquote>Si c'est ça la discipline — alors il y a des gens disciplinés dans ce qui les détruit.</blockquote><p>Alors j'ai reformulé à ma façon. <strong>La discipline c'est se battre avec soi-même pour faire sortir le meilleur de soi — afin de servir les autres.</strong></p><p>Et la science me donne raison. Les neurosciences nous montrent que chaque fois que tu répètes une action — bonne ou mauvaise — ton cerveau renforce les connexions neuronales liées à cette action. C'est ce qu'on appelle la neuroplasticité. Ton cerveau se reconfigure littéralement autour de ce que tu répètes.</p><p>La discipline n'est pas une punition. C'est une reprogrammation.</p><p>Elle ne commence pas par les grandes choses. Elle commence par faire une liste et la barrer. Par lire ce livre qu'on repousse depuis des semaines. Par reprendre le sport.</p><p>J'aimais pas lire. Mais j'ai appris. Et aujourd'hui je me tiens debout grâce à ça.</p><p>Que tu aies 20 ans, 30 ans ou 50 ans — la discipline c'est cette chose qui te fait te battre avec toi-même pour faire sortir le meilleur de toi. Pas pour toi seulement. Pour cette génération qui va s'identifier à toi un jour.</p><p><strong>Commence par les petites choses. Aujourd'hui.</strong></p>`,
    date: "1 juillet 2026",
    lecture: "4 min",
    likes: 0
  }
];

var comments = {};
var likedArticles = {};
var currentArticle = null;

// ══ RENDU ACCUEIL ══
function renderHome() {
  // Featured
  var fc = document.getElementById('featured-container');
  if (articles.length > 0) {
    var a = articles[0];
    fc.innerHTML = '<div class="featured-card" onclick="openArticle('+a.id+')">'
      +'<div>'
      +'<span class="featured-tag">'+a.tag+'</span>'
      +'<div class="featured-title">'+a.titre+'</div>'
      +'<div class="featured-excerpt">'+a.extrait+'</div>'
      +'<div class="featured-meta">'+a.date+' <span>·</span> '+a.lecture+' de lecture <span>·</span> <button class="likes" onclick="toggleLike(event,'+a.id+')">♡ <span id="like-count-'+a.id+'">'+a.likes+'</span></button></div>'
      +'</div>'
      +'<div class="featured-visual"><div class="featured-visual-text">'+a.titre+'</div><div class="featured-visual-tag">'+a.tag+'</div></div>'
      +'</div>';
  } else {
    fc.innerHTML = '<p style="font-size:15px;color:var(--gris);font-style:italic;">Le premier article arrive bientôt.</p>';
  }

  // Grid
  var grid = document.getElementById('articles-grid');
  if (articles.length === 0) {
    grid.innerHTML = '<p style="font-size:15px;color:var(--gris);font-style:italic;grid-column:1/-1;">Aucun article pour l\'instant.</p>';
    return;
  }
  grid.innerHTML = '';
  articles.forEach(function(a) {
    grid.innerHTML += '<div class="article-card" onclick="openArticle('+a.id+')">'
      +'<span class="article-tag">'+a.tag+'</span>'
      +'<div class="article-title">'+a.titre+'</div>'
      +'<div class="article-excerpt">'+a.extrait+'</div>'
      +'<div class="article-meta">'+a.date+' <span style="color:var(--border)">·</span> '+a.lecture+' <span style="color:var(--border)">·</span> <button class="likes" onclick="toggleLike(event,'+a.id+')">♡ <span id="like-count-grid-'+a.id+'">'+a.likes+'</span></button></div>'
      +'</div>';
  });
}

// ══ ARTICLE ══
function openArticle(id) {
  currentArticle = id;
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  
  var content = document.getElementById('article-content');
  content.innerHTML = '<div class="article-page-eyebrow">'
    +'<button class="back-btn" onclick="go(\'home\')">← Retour</button>'
    +'<span class="article-page-tag">'+a.tag+'</span>'
    +'</div>'
    +'<h1>'+a.titre+'</h1>'
    +'<div class="article-page-meta">'+a.date+' <span>·</span> '+a.lecture+' de lecture</div>'
    +'<div class="article-body">'+a.corps+'</div>';

  var liked = likedArticles[id] || false;
  var likeClass = liked ? 'like-big-btn liked' : 'like-big-btn';
  var likeText = liked ? '♥ Tu as aimé cet article' : '♡ J\'ai aimé cet article';

  var cs = document.getElementById('comments-section');
  var comms = comments[id] || [];
  var commHtml = '';
  comms.forEach(function(c) {
    commHtml += '<div class="comment-item">'
      +'<div class="comment-author">'+c.prenom+'</div>'
      +'<div class="comment-date">'+c.date+'</div>'
      +'<div class="comment-text">'+c.texte+'</div>'
      +'</div>';
  });

  cs.innerHTML = '<div class="likes-bar">'
    +'<button class="'+likeClass+'" id="like-big-'+id+'" onclick="toggleLikePage('+id+')">'+likeText+'</button>'
    +'<span style="font-family:\'DM Mono\',monospace;font-size:12px;color:var(--gris);" id="like-big-count-'+id+'">'+a.likes+' likes</span>'
    +'</div>'
    +'<hr class="comments-divider">'
    +'<div class="comments-title">Commentaires ('+comms.length+')</div>'
    +'<div class="comment-form">'
    +'<input type="text" id="cm-prenom" placeholder="Ton prénom">'
    +'<textarea id="cm-texte" placeholder="Ton commentaire..."></textarea>'
    +'<button class="comment-submit" onclick="ajouterCommentaire('+id+')">Publier</button>'
    +'<span id="cm-ok" style="display:none;font-size:12px;color:var(--vert-clair);margin-left:12px;">✔ Commentaire publié !</span>'
    +'</div>'
    +'<div id="comments-list-'+id+'">'+commHtml+'</div>';

  go('article');
}

function toggleLike(e, id) {
  e.stopPropagation();
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  if (likedArticles[id]) {
    a.likes--;
    likedArticles[id] = false;
  } else {
    a.likes++;
    likedArticles[id] = true;
  }
  var el1 = document.getElementById('like-count-'+id);
  var el2 = document.getElementById('like-count-grid-'+id);
  if (el1) el1.textContent = a.likes;
  if (el2) el2.textContent = a.likes;
}

function toggleLikePage(id) {
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  if (likedArticles[id]) {
    a.likes--;
    likedArticles[id] = false;
    document.getElementById('like-big-'+id).className = 'like-big-btn';
    document.getElementById('like-big-'+id).textContent = '♡ J\'aime cet article';
  } else {
    a.likes++;
    likedArticles[id] = true;
    document.getElementById('like-big-'+id).className = 'like-big-btn liked';
    document.getElementById('like-big-'+id).textContent = '♥ Tu as aimé cet article';
  }
  document.getElementById('like-big-count-'+id).textContent = a.likes+' likes';
}

function ajouterCommentaire(id) {
  var prenom = document.getElementById('cm-prenom').value.trim();
  var texte = document.getElementById('cm-texte').value.trim();
  if (!prenom || !texte) { alert('Merci de remplir tous les champs.'); return; }
  if (!comments[id]) comments[id] = [];
  var now = new Date();
  var date = now.toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});
  comments[id].unshift({prenom:prenom,texte:texte,date:date});
  document.getElementById('cm-prenom').value = '';
  document.getElementById('cm-texte').value = '';
  var ok = document.getElementById('cm-ok');
  ok.style.display = 'inline';
  setTimeout(function(){ok.style.display='none';},3000);
  var list = document.getElementById('comments-list-'+id);
  var commHtml = '';
  comments[id].forEach(function(c) {
    commHtml += '<div class="comment-item">'
      +'<div class="comment-author">'+c.prenom+'</div>'
      +'<div class="comment-date">'+c.date+'</div>'
      +'<div class="comment-text">'+c.texte+'</div>'
      +'</div>';
  });
  list.innerHTML = commHtml;
  document.querySelector('.comments-title').textContent = 'Commentaires ('+comments[id].length+')';
}

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

// ══ INIT ══
window.addEventListener('load', function() {
  renderHome();
});
</script>
</body>
</html>
