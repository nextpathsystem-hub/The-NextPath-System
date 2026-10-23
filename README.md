<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NextPath Blog</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Inter:wght@300;400;500;600;700&family=DM+Mono:wght@400;500&family=Caveat:wght@500;600&display=swap" rel="stylesheet">
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

/* MULTI TAGS */
.ed-tags-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:20px;}
.ed-tag-check{display:flex;align-items:center;gap:8px;font-size:13px;color:var(--encre);padding:8px 12px;border:1px solid var(--border);border-radius:8px;cursor:pointer;transition:all .2s;background:var(--blanc);}
.ed-tag-check:hover{border-color:var(--vert-mid);background:var(--vert-pale);}
.ed-tag-check input[type="checkbox"]{accent-color:var(--vert);width:14px;height:14px;cursor:pointer;}
.ed-tag-check input[type="checkbox"]:checked + *{color:var(--vert);font-weight:600;}
.ed-tag-check:has(input:checked){border-color:var(--vert);background:var(--vert-pale);}

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
/* ══ AJOUTS ══ */
.contact-select{appearance:auto;cursor:pointer;}
.contact-note{background:var(--vert-pale);border-radius:8px;padding:10px 14px;font-size:13px!important;color:var(--vert)!important;margin:-4px 0 20px!important;}
.article-auteur{font-weight:600;color:var(--vert);}
.home-bloc{padding:0 48px 80px;max-width:1100px;margin:0 auto;}
.home-bloc .articles-header{margin-bottom:32px;}
.home-coeur{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;}
.home-coeur .cc{transform:none;}
.avis-liste{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:20px;}
.avis-carte{background:var(--gris-pale);border:1px solid var(--border);border-radius:12px;padding:28px;text-align:left;}
.avis-carte blockquote{font-size:15px;color:var(--encre);line-height:1.7;margin-bottom:12px;}
.avis-carte figcaption{font-size:13px;color:var(--gris);}
.avis-appel{background:var(--vert-pale);border:none;text-align:center;}
.avis-appel b{display:block;font-family:'Playfair Display',serif;font-size:22px;color:var(--vert);margin-bottom:8px;}
.avis-appel p{font-size:14px;color:var(--gris);margin-bottom:20px;}
/* ══ COUPS DE CŒUR (page colorée) ══ */
:root{--corail:#FF6B57;--soleil:#FFC93C;--violet:#7C5CFF;--ciel:#2FA4FF;}
#page-coeur{background:#FFFBF4;}
.c-video{--c:var(--corail);--t:#fff;--pale:#FFE3DD;}
.c-article{--c:var(--soleil);--t:#111A14;--pale:#FFF2CC;}
.c-cours{--c:var(--violet);--t:#fff;--pale:#E9E3FF;}
.c-livre{--c:var(--ciel);--t:#fff;--pale:#DDF0FF;}
.c-nextpath{--c:#1B4D3E;--t:#fff;--pale:#E8F4EF;}
.c-tout{--c:#111A14;--t:#fff;--pale:#eee;}
.cdc-hero{position:relative;overflow:hidden;padding:84px 48px 56px;text-align:center;}
.bulle{position:absolute;border-radius:50%;opacity:.9;animation:flotte2 9s ease-in-out infinite alternate;}
.b1{width:180px;height:180px;background:var(--soleil);left:-40px;top:40px;}
.b2{width:120px;height:120px;background:var(--corail);right:8%;top:-30px;animation-delay:-3s;}
.b3{width:90px;height:90px;background:var(--violet);right:-20px;bottom:30px;animation-delay:-5s;}
.b4{width:60px;height:60px;background:var(--ciel);left:16%;bottom:10px;animation-delay:-2s;}
@keyframes flotte2{to{transform:translate(14px,-18px) scale(1.06);}}
.cdc-hero-in{position:relative;max-width:820px;margin:0 auto;}
.cdc-coeur{display:inline-grid;place-items:center;width:64px;height:64px;border-radius:50%;background:var(--corail);color:#fff;font-size:30px;transform:rotate(-8deg);box-shadow:0 10px 24px rgba(255,107,87,.35);}
.cdc-hero h1{font-family:'Playfair Display',serif;font-size:clamp(40px,6.4vw,82px);line-height:1.02;color:#111A14;margin:20px 0 16px;letter-spacing:-.02em;}
.cdc-hero h1 span{display:inline-block;background:var(--soleil);padding:0 .18em;border-radius:12px;transform:rotate(-1.5deg);}
.cdc-hero p{font-size:17px;line-height:1.65;color:#4a5a50;max-width:56ch;margin:0 auto;}
.cdc-filtres{display:flex;flex-wrap:wrap;justify-content:center;gap:10px;margin-top:30px;}
.cdc-filtre{display:inline-flex;align-items:center;gap:8px;padding:11px 20px;border-radius:100px;border:2px solid var(--c);background:#fff;color:#111A14;font-family:'Inter',sans-serif;font-weight:600;font-size:14px;cursor:pointer;transition:all .2s;}
.cdc-filtre svg{color:var(--c);}
.cdc-filtre.c-article svg{color:#C79200;}
.cdc-filtre:hover{background:var(--pale);}
.cdc-filtre.active{background:var(--c);color:var(--t);}
.cdc-filtre.active svg{color:var(--t);}
.cdc-grille{max-width:1180px;margin:0 auto;padding:16px 48px 96px;display:grid;grid-template-columns:repeat(3,1fr);gap:26px;align-items:start;}
.cc{position:relative;display:flex;flex-direction:column;border-radius:26px;overflow:hidden;text-decoration:none;background:var(--c);color:var(--t);transform:rotate(var(--r,0deg));box-shadow:0 14px 34px rgba(17,26,20,.12);transition:transform .35s cubic-bezier(.2,.8,.3,1.3),box-shadow .3s;}
.cc:hover{transform:rotate(0deg) translateY(-6px) scale(1.02);box-shadow:0 24px 50px rgba(17,26,20,.2);}
.cc.large{grid-column:span 2;}
.cc-visuel{position:relative;aspect-ratio:16/9;overflow:hidden;display:grid;place-items:center;}
.cc.large .cc-visuel{aspect-ratio:21/9;}
.cc-visuel img{width:100%;height:100%;object-fit:cover;}
.cc-forme{position:absolute;border-radius:50%;background:rgba(255,255,255,.18);}
.c-article .cc-forme{background:rgba(255,255,255,.45);}
.cc-forme.f1{width:70%;aspect-ratio:1;left:-12%;top:-30%;}
.cc-forme.f2{width:34%;aspect-ratio:1;right:6%;bottom:-14%;background:rgba(17,26,20,.1);}
.cc-picto{position:relative;width:108px;height:108px;border-radius:30px;background:rgba(255,255,255,.22);display:grid;place-items:center;transform:rotate(-6deg);}
.c-article .cc-picto{background:rgba(255,255,255,.55);}
.cc-sticker{position:absolute;top:16px;left:16px;display:inline-flex;align-items:center;gap:6px;background:#fff;color:#111A14;font-size:12.5px;font-weight:700;padding:7px 13px;border-radius:100px;transform:rotate(-4deg);box-shadow:0 4px 12px rgba(0,0,0,.12);}
.cc-sticker svg{color:var(--c);}
.c-article .cc-sticker svg{color:#C79200;}
.cc-exemple{position:absolute;top:18px;right:16px;font-size:11px;font-weight:600;padding:5px 10px;border-radius:100px;background:rgba(17,26,20,.25);color:#fff;}
.cc-corps{padding:22px 24px 24px;display:flex;flex-direction:column;gap:10px;}
.cc-sujet{font-size:13px;font-weight:600;opacity:.8;}
.cc-corps b{font-family:'Playfair Display',serif;font-size:24px;line-height:1.2;}
.cc.large .cc-corps b{font-size:30px;}
.cc-note{font-family:'Caveat',cursive;font-size:23px;line-height:1.25;background:#fff;color:#111A14;padding:14px 16px 12px;border-radius:14px;transform:rotate(-1deg);margin:6px 0 2px;}
.cc-note span{display:block;text-align:right;font-size:19px;color:var(--c);margin-top:2px;}
.c-article .cc-note span{color:#C79200;}
.cc-lien{font-weight:700;font-size:14px;}
@media(max-width:900px){.cdc-grille{grid-template-columns:repeat(2,1fr);}}
@media(max-width:600px){
  .cdc-hero{padding:56px 20px 36px;}
  .b1{width:110px;height:110px;left:-50px;}
  .cdc-grille{grid-template-columns:1fr;padding:8px 20px 64px;gap:20px;}
  .cc.large{grid-column:auto;}
  .cc.large .cc-visuel{aspect-ratio:16/9;}
}
@media(prefers-reduced-motion:reduce){.bulle{animation:none;}}


@media(max-width:900px){.home-coeur{grid-template-columns:1fr 1fr;}}
@media(max-width:768px){.home-bloc{padding:0 20px 56px;}.home-coeur{grid-template-columns:1fr;}}
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
    <li><a onclick="go('coeur')" id="nav-coeur">Coups de cœur</a></li>
    <li><a onclick="go('about')" id="nav-about">À propos</a></li>
    <li><a onclick="go('contact')" id="nav-contact">Contact</a></li>
  </ul>
  <button class="hamburger" onclick="toggleMenu()"><span></span><span></span><span></span></button>
</nav>

<div class="mobile-menu" id="mobile-menu">
  <a onclick="go('home');toggleMenu()">Accueil</a>
  <a onclick="go('blog');toggleMenu()">Blog</a>
  <a onclick="go('coeur');toggleMenu()">Coups de cœur</a>
  <a onclick="go('about');toggleMenu()">À propos</a>
  <a onclick="go('contact');toggleMenu()">Contact</a>
</div>

<!-- ACCUEIL -->
<div class="page active" id="page-home">
  <div class="hero">
    <h1>L'endroit où les idées deviennent des actions.</h1>
    <p class="hero-desc">Ressources, réflexions et partages d'idées.</p>
    <div class="hero-divider"></div>
  </div>
  <div id="home-articles"></div>
  <div class="home-bloc">
    <div class="articles-header"><span class="featured-label">Nos coups de cœur</span><div class="articles-title">Ce que nous vous conseillons de voir</div></div>
    <div class="home-coeur" id="home-coeur"></div>
    <div style="text-align:center;"><button class="voir-plus" onclick="go('coeur')">Tous nos coups de cœur →</button></div>
  </div>
  <div class="home-bloc">
    <div class="articles-header"><span class="featured-label">Témoignages et avis</span><div class="articles-title">Ce qu'en disent les lecteurs</div></div>
    <div class="avis-liste" id="home-avis"></div>
  </div>
</div>

<!-- COUPS DE CŒUR -->
<div class="page" id="page-coeur">
  <section class="cdc-hero">
    <span class="bulle b1"></span><span class="bulle b2"></span><span class="bulle b3"></span><span class="bulle b4"></span>
    <div class="cdc-hero-in">
      <span class="cdc-coeur" aria-hidden="true">♥</span>
      <h1>Nos coups <span>de cœur</span></h1>
      <p>Ce que nous apprenons, nous le partageons. Des vidéos, des articles, des cours et des livres qui nous ont aidés, choisis pour vous.</p>
      <div class="cdc-filtres" id="coeur-filtres"></div>
    </div>
  </section>
  <section class="cdc-grille" id="coeur-liste"></section>
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
        <label class="contact-label">Objet</label>
        <select name="objet" id="c-objet" class="contact-input contact-select"><option>Question</option><option>Suggestion</option><option>Proposer un article</option><option>Avis / témoignage</option><option>Partenariat</option><option>Autre</option></select>
        <p class="contact-note">Vous avez un sujet intéressant et souhaitez qu'il soit publié ? Choisissez « Proposer un article » dans l'objet.</p>
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

      <label class="ed-label">Signé par</label>
      <select class="ed-select" id="ed-auteur"><option>Grace Kabundo</option><option>Équipe NextPath</option></select>

      <label class="ed-label">Catégories * (choisis une ou plusieurs)</label>
      <div class="ed-tags-grid" id="ed-tags-grid">
        <label class="ed-tag-check"><input type="checkbox" value="Éducation"> Éducation</label>
        <label class="ed-tag-check"><input type="checkbox" value="Science"> Science</label>
        <label class="ed-tag-check"><input type="checkbox" value="Orientation"> Orientation</label>
        <label class="ed-tag-check"><input type="checkbox" value="Développement personnel"> Développement personnel</label>
        <label class="ed-tag-check"><input type="checkbox" value="Foi"> Foi</label>
        <label class="ed-tag-check"><input type="checkbox" value="NextPath"> NextPath</label>
        <label class="ed-tag-check"><input type="checkbox" value="Jeunesse"> Jeunesse</label>
        <label class="ed-tag-check"><input type="checkbox" value="Afrique"> Afrique</label>
        <label class="ed-tag-check"><input type="checkbox" value="Carrière"> Carrière</label>
        <label class="ed-tag-check"><input type="checkbox" value="Santé"> Santé</label>
      </div>

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
// ══ PERSISTANCE — window.storage ══
async function sauvegarder() {
  try {
    await window.storage.set('np_articles', JSON.stringify(articles));
    await window.storage.set('np_comments', JSON.stringify(comments));
    await window.storage.set('np_liked', JSON.stringify(liked));
  } catch(e) {
    // Fallback localStorage
    try {
      localStorage.setItem('np_articles', JSON.stringify(articles));
      localStorage.setItem('np_comments', JSON.stringify(comments));
      localStorage.setItem('np_liked', JSON.stringify(liked));
    } catch(e2) { console.log('Storage error:', e2); }
  }
}

async function charger() {
  try {
    var a = await window.storage.get('np_articles');
    var c = await window.storage.get('np_comments');
    var l = await window.storage.get('np_liked');
    if (a && a.value) articles = JSON.parse(a.value);
    if (c && c.value) comments = JSON.parse(c.value);
    if (l && l.value) liked = JSON.parse(l.value);
  } catch(e) {
    // Fallback localStorage
    try {
      var a2 = localStorage.getItem('np_articles');
      var c2 = localStorage.getItem('np_comments');
      var l2 = localStorage.getItem('np_liked');
      if (a2) articles = JSON.parse(a2);
      if (c2) comments = JSON.parse(c2);
      if (l2) liked = JSON.parse(l2);
    } catch(e2) { console.log('Load error:', e2); }
  }
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
    +'<div class="article-full-meta">'+(a.auteur?'<span class="article-auteur">Par '+(a.auteur==='Équipe NextPath'?'l\'équipe NextPath':a.auteur)+'</span> · ':'')+a.date+' · '+a.lecture+' de lecture</div>'
    +imgHtml
    +'<div class="article-body">'+a.corps+'</div>'
    +'<div class="likes-bar">'
    +'<button class="like-big'+(isLiked?' liked':'')+'" id="lbtn-'+id+'" onclick="toggleLike('+id+')">'+(isLiked?'♥ Tu as aimé':'♡ J\'aime cet article')+'</button>'
    +'<span class="like-count" id="lcnt-'+id+'">'+a.likes+' likes</span>'
    +'</div>';

  renderComments(id);
  go('article');
}

async function toggleLike(id) {
  var a = articles.find(function(x){return x.id===id;});
  if (!a) return;
  liked[id] = !liked[id];
  a.likes += liked[id] ? 1 : -1;
  await sauvegarder();
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

async function ajouterComment(id) {
  var p = document.getElementById('cm-prenom').value.trim();
  var t = document.getElementById('cm-texte').value.trim();
  if (!p||!t) { alert('Merci de remplir tous les champs.'); return; }
  if (!comments[id]) comments[id]=[];
  var date = new Date().toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});
  comments[id].unshift({prenom:p,texte:t,date:date});
  await sauvegarder();
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
async function publier() {
  var titre=document.getElementById('ed-titre').value.trim();
  var img=document.getElementById('ed-img').value.trim();
  var corps=document.getElementById('ed-content').innerHTML.trim();

  // Récupérer les tags cochés
  var checkboxes = document.querySelectorAll('#ed-tags-grid input[type="checkbox"]:checked');
  var tags = Array.from(checkboxes).map(function(cb){ return cb.value; });
  if (!titre || !corps || corps === '') { alert('Le titre et le contenu sont obligatoires.'); return; }
  if (tags.length === 0) { alert('Choisis au moins une catégorie.'); return; }

  var texte=document.getElementById('ed-content').innerText||'';
  var mots=texte.split(/\s+/).length;
  var mins=Math.max(1,Math.round(mots/200));
  var extrait=texte.substring(0,160).trim()+(texte.length>160?'...':'');
  var date=new Date().toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});

  articles.unshift({
    id: Date.now(),
    titre: titre,
    tag: tags[0],
    tags: tags,
    img: img||'',
    auteur: document.getElementById('ed-auteur').value,
    extrait: extrait,
    corps: corps,
    date: date,
    lecture: mins+' min',
    likes: 0
  });

  await sauvegarder();

  // Reset form
  document.getElementById('ed-titre').value='';
  document.getElementById('ed-img').value='';
  document.getElementById('ed-content').innerHTML='';
  document.querySelectorAll('#ed-tags-grid input[type="checkbox"]').forEach(function(cb){ cb.checked=false; });

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
  if(p==='home') { renderHome(); renderExtras(); }
  if(p==='blog') renderBlog();
  if(p==='coeur') renderCoeur();
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

// ══ NOS COUPS DE CŒUR ══
// Une ligne par ressource. Ajoute les nouvelles EN HAUT : l'accueil montre les 3 premières.
// type : 'Vidéo', 'Article', 'Cours' ou 'Livre'. Pour une vidéo YouTube, colle le lien de la vidéo : la miniature s'affiche toute seule.
var COUPS_DE_COEUR = [
  {type:'Vidéo', sujet:'Science', titre:'ScienceEtonnante', pourquoi:"Pour comprendre des grandes idées scientifiques, expliquées simplement.", lien:'https://www.youtube.com/@ScienceEtonnante', image:''},
  {type:'Cours', sujet:'Apprendre', titre:'Learning How to Learn (Coursera, gratuit)', pourquoi:"Pour apprendre à apprendre : mémoire, concentration, procrastination.", lien:'https://www.coursera.org/learn/learning-how-to-learn', image:''},
  {type:'Article', sujet:'Actualité scientifique', titre:'The Conversation France', pourquoi:"Des chercheurs qui expliquent eux-mêmes leurs travaux.", lien:'https://theconversation.com/fr', image:''}
];

// ══ TÉMOIGNAGES ET AVIS ══
// Ajoute les avis reçus (avec l'accord de la personne). Exemple :
// {texte:"Cet article m'a aidée à préparer mes examens.", nom:'Sarah', contexte:'Étudiante'},
var AVIS = [];

var PICTO = {
  'Vidéo':'<rect x="2" y="5" width="20" height="14" rx="4"/><path d="m10 9 5 3-5 3z" fill="currentColor"/>',
  'Article':'<path d="M6 3h9l4 4v14H6z"/><path d="M14 3v5h5M9 13h7M9 17h7"/>',
  'Cours':'<path d="M2 9l10-5 10 5-10 5z"/><path d="M6 11v5c3 2 9 2 12 0v-5"/>',
  'Livre':'<path d="M4 4h6a3 3 0 0 1 3 3v13a2 2 0 0 0-2-2H4z"/><path d="M20 4h-6a3 3 0 0 0-3 3"/><path d="M20 4v14h-7"/>',
  'NextPath':'<circle cx="12" cy="12" r="9"/><path d="m15 9-2 4-4 2 2-4z" fill="currentColor"/>'
};
function svgPicto(t, taille){ return '<svg viewBox="0 0 24 24" width="' + taille + '" height="' + taille + '" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">' + (PICTO[t] || PICTO['Article']) + '</svg>'; }
function idYoutube(u){ var m = String(u).match(/(?:youtu\.be\/|[?&]v=|\/shorts\/|\/embed\/)([\w-]{11})/); return m ? m[1] : ''; }
function plat(s){ return String(s || '').toLowerCase().normalize('NFD').replace(/[\u0300-\u036f]/g,''); }
function esc(s){ return String(s==null?'':s).replace(/[&<>"']/g,function(c){return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c];}); }
function carteCoeur(r, i){
  var yt = idYoutube(r.lien), img = r.image || (yt ? 'https://i.ytimg.com/vi/' + yt + '/hqdefault.jpg' : '');
  var visuel = img ? '<img src="' + esc(img) + '" alt="" loading="lazy">'
    : '<span class="cc-forme f1"></span><span class="cc-forme f2"></span><span class="cc-picto">' + svgPicto(r.type, 64) + '</span>';
  return '<a class="cc c-' + esc(plat(r.type)) + (i % 5 === 0 ? ' large' : '') + '" style="--r:' + ((i % 3) - 1) * 1.2 + 'deg" href="' + esc(r.lien) + '" target="_blank" rel="noopener">'
    + '<div class="cc-visuel">' + visuel + (yt ? '<span class="r-play">▶</span>' : '') + '</div>'
    + '<span class="cc-sticker">' + svgPicto(r.type, 14) + esc(r.type) + '</span>'
    + '<div class="cc-corps"><span class="cc-sujet">' + esc(r.sujet) + '</span><b>' + esc(r.titre) + '</b>'
    + '<p class="cc-note">« ' + esc(r.pourquoi) + ' »</p>'
    + '<span class="cc-lien">J\'y vais →</span></div></a>';
}
var typeCoeur = 'Tout';
var TYPES_COEUR = [['Tout','Tout'],['Vidéo','Vidéos'],['Article','Articles'],['Cours','Cours'],['Livre','Livres']];
function renderCoeur(){
  var presents = TYPES_COEUR.filter(function(t){ return t[0] === 'Tout' || COUPS_DE_COEUR.some(function(r){ return r.type === t[0]; }); });
  document.getElementById('coeur-filtres').innerHTML = presents.map(function(t){
    return '<button class="cdc-filtre c-' + esc(plat(t[0])) + (t[0] === typeCoeur ? ' active' : '') + '" type="button" onclick="typeCoeur=\'' + t[0] + '\';renderCoeur()">' + (t[0] === 'Tout' ? '' : svgPicto(t[0], 16)) + esc(t[1]) + '</button>';
  }).join('');
  var liste = typeCoeur === 'Tout' ? COUPS_DE_COEUR : COUPS_DE_COEUR.filter(function(r){ return r.type === typeCoeur; });
  document.getElementById('coeur-liste').innerHTML = liste.map(carteCoeur).join('');
}
function renderExtras(){
  document.getElementById('home-coeur').innerHTML = COUPS_DE_COEUR.slice(0,3).map(function(r, i){ return carteCoeur(r, 1).replace(' large',''); }).join('');
  document.getElementById('home-avis').innerHTML = AVIS.map(function(v){
    return '<figure class="avis-carte"><blockquote>« ' + esc(v.texte) + ' »</blockquote><figcaption><b>' + esc(v.nom) + '</b>' + (v.contexte ? ' · ' + esc(v.contexte) : '') + '</figcaption></figure>';
  }).join('') + '<div class="avis-carte avis-appel"><b>' + (AVIS.length ? 'Et vous ?' : 'Les premiers avis arrivent bientôt.') + '</b><p>Un article vous a aidé ou fait réfléchir ? Racontez-le-nous en quelques mots.</p><button class="voir-plus" style="margin-top:0" onclick="go(\'contact\');document.getElementById(\'c-objet\').value=\'Avis / témoignage\'">Donner mon avis</button></div>';
}

// ══ NPADMIN ══
var kbuf=[];
var kcode=[78,80,65,68,77,73,78];
document.addEventListener('keydown',function(e){
  kbuf.push(e.keyCode);
  if(kbuf.length>7) kbuf.shift();
  if(kbuf.join(',')===kcode.join(',')) { openEditor(); kbuf=[]; }
});


// ══ DÉMARRAGE : charge les articles enregistrés, puis affiche l'accueil ══
charger().then(function(){ renderHome(); renderExtras(); });
</script>
</body>
</html>
