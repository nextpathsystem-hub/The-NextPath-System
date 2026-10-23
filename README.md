<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NextPath Blog</title>
<meta name="description" content="Ressources, réflexions et partages d'idées : des articles signés, sourcés et relus sur l'éducation, la science, l'orientation, la carrière et le développement personnel.">
<meta name="theme-color" content="#1B4D3E">
<!-- Remplace https://TON-DOMAINE par l'adresse réelle du site -->
<meta property="og:type" content="website">
<meta property="og:site_name" content="NextPath Blog">
<meta property="og:title" content="NextPath Blog">
<meta property="og:description" content="Ressources, réflexions et partages d'idées : des articles signés, sourcés et relus sur l'éducation, la science, l'orientation, la carrière et le développement personnel.">
<meta property="og:url" content="https://TON-DOMAINE/">
<meta property="og:image" content="https://TON-DOMAINE/og-image.png">
<meta property="og:locale" content="fr_FR">
<meta name="twitter:card" content="summary_large_image">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Inter:wght@300;400;500;600;700&family=Caveat:wght@500;600&display=swap" rel="stylesheet">
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
img{max-width:100%;}
[hidden]{display:none!important;}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;background:var(--blanc);border-bottom:1px solid var(--border);padding:0 48px;height:64px;display:flex;align-items:center;justify-content:space-between;}
.nav-logo{display:flex;align-items:center;gap:8px;font-family:'Inter',sans-serif;font-size:18px;font-weight:700;color:var(--encre);cursor:pointer;text-decoration:none;}
.nav-logo-dot{width:8px;height:8px;border-radius:50%;background:var(--vert-mid);}
.nav-logo-np{color:var(--encre);}
.nav-logo-blog{color:var(--vert-mid);}
.nav-links{display:flex;gap:36px;list-style:none;align-items:center;}
.nav-links a{font-size:14px;font-weight:400;color:var(--gris);text-decoration:none;transition:color .2s;cursor:pointer;padding-bottom:4px;border-bottom:2px solid transparent;}
.nav-links a:hover{color:var(--encre);}
.nav-links a.active{color:var(--encre);border-bottom-color:var(--vert);}
.nav-links a.nav-ecrire{background:var(--vert);color:var(--blanc);padding:8px 18px;border-radius:100px;border:none;font-weight:500;}
.nav-links a.nav-ecrire:hover{background:var(--vert-clair);}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:4px;}
.hamburger span{display:block;width:20px;height:1.5px;background:var(--encre);}
.mobile-menu{display:none;position:fixed;top:64px;left:0;right:0;background:var(--blanc);border-bottom:1px solid var(--border);padding:16px 24px;z-index:199;flex-direction:column;}
.mobile-menu.open{display:flex;}
.mobile-menu a{font-size:14px;color:var(--encre);text-decoration:none;padding:12px 0;border-bottom:1px solid var(--border);cursor:pointer;display:block;}

/* PAGES */
.page{display:none;padding-top:64px;min-height:100vh;}
.page.active{display:block;}

/* HERO */
.hero{background:var(--vert-pale);padding:96px 48px 80px;text-align:center;position:relative;overflow:hidden;}
.hero-deco{position:absolute;inset:0;width:100%;height:100%;pointer-events:none;}
.hero > *:not(.hero-deco){position:relative;}
.hero-eyebrow{font-family:'Inter',sans-serif;font-size:11px;font-weight:500;letter-spacing:.18em;text-transform:uppercase;color:var(--vert);margin-bottom:28px;display:block;}
.hero h1{font-family:'Playfair Display',serif;font-size:clamp(40px,6vw,72px);font-weight:700;line-height:1.1;letter-spacing:-.02em;color:var(--vert);margin-bottom:20px;}
.hero-desc{font-size:17px;color:var(--gris);line-height:1.8;max-width:580px;margin:0 auto 32px;}
.hero-divider{width:48px;height:2px;background:var(--vert-mid);margin:0 auto;}
.hero-cta{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-bottom:36px;}
.btn-vert{display:inline-flex;align-items:center;gap:8px;background:var(--vert);color:var(--blanc);border:1px solid var(--vert);padding:12px 26px;border-radius:100px;font-family:'Inter',sans-serif;font-size:14px;font-weight:600;cursor:pointer;text-decoration:none;transition:background .2s;}
.btn-vert:hover{background:var(--vert-clair);}
.btn-ligne{display:inline-flex;align-items:center;gap:8px;background:var(--blanc);color:var(--vert);border:1px solid var(--vert);padding:12px 26px;border-radius:100px;font-family:'Inter',sans-serif;font-size:14px;font-weight:600;cursor:pointer;text-decoration:none;transition:background .2s;}
.btn-ligne:hover{background:var(--vert-pale);}
.hero-preuves{display:flex;gap:28px;justify-content:center;flex-wrap:wrap;margin-top:36px;font-size:13px;color:var(--vert);}
.hero-preuves span{display:inline-flex;align-items:center;gap:8px;}
.hero-preuves svg{width:16px;height:16px;}

/* ARTICLES */
.articles-wrap{padding:80px 48px;max-width:1100px;margin:0 auto;}
.articles-header{text-align:center;margin-bottom:48px;}
.articles-title{font-family:'Playfair Display',serif;font-size:clamp(26px,3vw,38px);font-weight:700;color:var(--encre);margin-bottom:8px;}
.articles-sub{font-family:'Inter',sans-serif;font-size:10px;letter-spacing:.18em;text-transform:uppercase;color:var(--vert-mid);}
.articles-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:32px;}

/* À LA UNE */
.une{display:grid;grid-template-columns:1.15fr 1fr;background:var(--blanc);border:1px solid var(--border);border-radius:16px;overflow:hidden;box-shadow:0 10px 40px rgba(27,77,62,.10);cursor:pointer;margin-bottom:40px;text-decoration:none;color:inherit;transition:transform .25s,box-shadow .25s;}
.une:hover{transform:translateY(-4px);box-shadow:0 18px 48px rgba(27,77,62,.16);}
.une .cover{height:100%;min-height:320px;}
.une-corps{padding:40px;display:flex;flex-direction:column;justify-content:center;gap:14px;}
.une-titre{font-family:'Playfair Display',serif;font-size:clamp(24px,2.8vw,34px);font-weight:700;line-height:1.2;color:var(--encre);}
.une:hover .une-titre{color:var(--vert);}

/* CARD */
.article-card{display:flex;flex-direction:column;background:var(--blanc);border-radius:12px;overflow:hidden;box-shadow:0 2px 16px rgba(27,77,62,.06);border:1px solid var(--border);cursor:pointer;transition:transform .25s,box-shadow .25s;text-decoration:none;color:inherit;}
.article-card:hover{transform:translateY(-4px);box-shadow:0 12px 32px rgba(27,77,62,.12);}
.cover{position:relative;width:100%;aspect-ratio:16/9;overflow:hidden;background:var(--vert-pale);}
.cover img,.cover svg{display:block;width:100%;height:100%;object-fit:cover;transition:transform .5s;}
.article-card:hover .cover img,.article-card:hover .cover svg,.une:hover .cover svg,.une:hover .cover img{transform:scale(1.04);}
.cover-cat{position:absolute;left:14px;top:14px;font-family:'Inter',sans-serif;font-size:9px;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--vert);background:rgba(255,255,255,.92);padding:5px 10px;border-radius:4px;}
.exemple{position:absolute;right:14px;top:14px;font-family:'Inter',sans-serif;font-size:9px;letter-spacing:.1em;text-transform:uppercase;color:var(--gris);background:var(--blanc);border:1px solid var(--border);padding:4px 8px;border-radius:4px;}
.card-body{padding:24px;display:flex;flex-direction:column;flex:1;}
.card-tags{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:16px;}
.card-tag{font-family:'Inter',sans-serif;font-size:9px;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--blanc);background:var(--vert);padding:4px 10px;border-radius:4px;}
.card-meta{display:flex;align-items:center;gap:14px;margin-bottom:12px;font-family:'Inter',sans-serif;font-size:10px;color:var(--gris);}
.card-title{font-family:'Playfair Display',serif;font-size:20px;font-weight:700;line-height:1.3;color:var(--encre);margin-bottom:10px;transition:color .2s;}
.article-card:hover .card-title{color:var(--vert);}
.card-excerpt{font-size:13px;color:var(--gris);line-height:1.7;margin-bottom:20px;}
.card-pied{margin-top:auto;display:flex;align-items:center;justify-content:space-between;gap:12px;padding-top:16px;border-top:1px solid var(--border);}
.card-cta{font-family:'Inter',sans-serif;font-size:10px;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--vert);display:flex;align-items:center;gap:6px;white-space:nowrap;}
.card-cta::after{content:'→';}

/* AUTEUR (petit) */
.auteur-mini{display:flex;align-items:center;gap:10px;min-width:0;}
.avatar{flex:none;width:32px;height:32px;border-radius:50%;background:var(--vert);color:var(--blanc);display:grid;place-items:center;font-family:'Playfair Display',serif;font-weight:700;font-size:13px;overflow:hidden;}
.avatar img{width:100%;height:100%;object-fit:cover;}
.avatar.grand{width:72px;height:72px;font-size:26px;}
.avatar.moyen{width:48px;height:48px;font-size:18px;}
.auteur-mini b{display:block;font-size:13px;font-weight:600;color:var(--encre);line-height:1.3;}
.auteur-mini small{display:block;font-size:11.5px;color:var(--gris);line-height:1.3;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}

/* EMPTY STATE */
.empty-state{padding:100px 48px;text-align:center;}
.empty-icon{font-size:56px;margin-bottom:24px;opacity:.35;}
.empty-title{font-family:'Playfair Display',serif;font-size:28px;font-weight:400;color:var(--vert);margin-bottom:12px;}
.empty-desc{font-size:15px;color:var(--gris);line-height:1.75;}

/* ARTICLE FULL */
.progression{position:fixed;top:64px;left:0;height:3px;width:0;background:var(--vert-mid);z-index:201;}
.article-full{max-width:760px;margin:0 auto;padding:56px 40px 40px;}
.article-full-back{display:inline-flex;align-items:center;gap:8px;font-size:13px;color:var(--gris);cursor:pointer;background:none;border:none;font-family:'Inter',sans-serif;margin-bottom:32px;transition:color .2s;padding:0;}
.article-full-back:hover{color:var(--vert);}
.article-full-tags{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:20px;}
.article-full h1{font-family:'Playfair Display',serif;font-size:clamp(30px,4.4vw,50px);font-weight:700;line-height:1.15;letter-spacing:-.02em;color:var(--vert);margin-bottom:18px;}
.chapo{font-family:'Playfair Display',serif;font-style:italic;font-size:20px;line-height:1.55;color:var(--encre);opacity:.82;margin-bottom:28px;}
.signature{display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:16px;padding:18px 0;border-top:1px solid var(--border);border-bottom:1px solid var(--border);margin-bottom:36px;}
.signature .auteur-mini b{font-size:14.5px;}
.signature .auteur-mini small{font-size:12.5px;white-space:normal;}
.signature-meta{font-family:'Inter',sans-serif;font-size:11px;color:var(--gris);display:flex;flex-wrap:wrap;gap:6px 16px;}
.relu{display:inline-flex;align-items:center;gap:6px;color:var(--vert);background:var(--vert-pale);padding:3px 10px;border-radius:100px;}
.relu svg{width:12px;height:12px;}
.article-full-img{width:100%;border-radius:12px;margin-bottom:40px;overflow:hidden;aspect-ratio:16/8;}
.article-full-img img,.article-full-img svg{display:block;width:100%;height:100%;object-fit:cover;}
.article-body{font-size:17px;color:var(--encre);line-height:1.9;}
.article-body p{margin-bottom:28px;}
.article-body h2{font-family:'Playfair Display',serif;font-size:27px;color:var(--vert);line-height:1.3;margin:44px 0 18px;}
.article-body strong{color:var(--vert);font-weight:600;}
.article-body em{font-style:italic;}
.article-body blockquote{border-left:3px solid var(--vert-mid);padding:18px 28px;background:var(--vert-pale);border-radius:0 8px 8px 0;margin:32px 0;font-family:'Playfair Display',serif;font-size:20px;font-style:italic;color:var(--vert);line-height:1.6;}
.article-body img{max-width:100%;border-radius:10px;margin:24px 0;display:block;}
.article-body a{color:var(--vert-clair);text-decoration:underline;}
.article-body ul,.article-body ol{margin:0 0 28px 24px;}
.article-body li{margin-bottom:8px;}
.article-body sup a{font-family:'Inter',sans-serif;font-size:10px;text-decoration:none;background:var(--vert-pale);color:var(--vert);padding:1px 5px;border-radius:4px;margin-left:2px;}

/* SOURCES + AUTEUR BOX */
.sources{margin-top:16px;padding:24px 28px;background:var(--gris-pale);border:1px solid var(--border);border-radius:12px;}
.sources h3{font-family:'Inter',sans-serif;font-size:11px;font-weight:500;letter-spacing:.14em;text-transform:uppercase;color:var(--vert);margin-bottom:12px;}
.sources ol{margin-left:20px;font-size:13.5px;color:var(--gris);line-height:1.65;}
.sources li{margin-bottom:8px;}
.sources em{color:var(--encre);}
.auteur-box{display:flex;gap:20px;align-items:flex-start;margin-top:32px;padding:28px;border:1px solid var(--border);border-radius:14px;background:var(--blanc);box-shadow:0 2px 16px rgba(27,77,62,.06);}
.auteur-box .label{font-family:'Inter',sans-serif;font-size:10px;letter-spacing:.14em;text-transform:uppercase;color:var(--vert-mid);display:block;margin-bottom:4px;}
.auteur-box h3{font-family:'Playfair Display',serif;font-size:22px;color:var(--encre);}
.auteur-box .role{font-size:13px;color:var(--gris);margin-bottom:10px;}
.auteur-box p{font-size:14.5px;color:var(--gris);line-height:1.7;}
.auteur-box .liens{display:flex;gap:16px;flex-wrap:wrap;margin-top:12px;font-size:13px;}
.auteur-box .liens a{color:var(--vert);font-weight:600;text-decoration:none;cursor:pointer;}
.auteur-box .liens a:hover{text-decoration:underline;}

/* LIKES */
.likes-bar{display:flex;align-items:center;flex-wrap:wrap;gap:12px;padding:28px 0;border-top:1px solid var(--border);margin-top:40px;}
.like-big{display:inline-flex;align-items:center;gap:8px;background:var(--vert-pale);border:1px solid var(--border);padding:10px 22px;border-radius:100px;font-size:14px;font-weight:500;color:var(--vert);cursor:pointer;transition:all .2s;font-family:'Inter',sans-serif;text-decoration:none;}
.like-big:hover,.like-big.liked{background:var(--vert);color:var(--blanc);border-color:var(--vert);}
.like-count{font-family:'Inter',sans-serif;font-size:12px;color:var(--gris);}

/* À LIRE ENSUITE */
.suite{background:var(--gris-pale);border-top:1px solid var(--border);}

/* COMMENTAIRES */
.comments-wrap{max-width:760px;margin:0 auto;padding:0 40px 80px;}
.comments-hr{border:none;border-top:1px solid var(--border);margin-bottom:40px;}
.comments-heading{font-family:'Playfair Display',serif;font-size:22px;font-weight:600;color:var(--encre);margin-bottom:24px;}
.comment-form{background:var(--gris-pale);border-radius:12px;padding:24px;margin-bottom:40px;}
.comment-input{width:100%;padding:11px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:14px;outline:none;background:var(--blanc);color:var(--encre);margin-bottom:10px;transition:border-color .2s;}
.comment-input:focus{border-color:var(--vert-mid);}
.comment-textarea{width:100%;padding:11px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:14px;outline:none;background:var(--blanc);color:var(--encre);resize:vertical;min-height:100px;transition:border-color .2s;margin-bottom:10px;}
.comment-textarea:focus{border-color:var(--vert-mid);}
.comment-btn{background:var(--vert);color:var(--blanc);border:none;padding:10px 26px;border-radius:100px;font-family:'Inter',sans-serif;font-size:13px;font-weight:600;cursor:pointer;transition:background .2s;}
.comment-btn:hover{background:var(--vert-clair);}
.comment-ok{font-size:12px;color:var(--vert-clair);margin-left:12px;font-weight:500;}
.comment-item{padding:20px 0;border-bottom:1px solid var(--border);}
.comment-author{font-weight:600;font-size:14px;color:var(--encre);margin-bottom:3px;}
.comment-date{font-family:'Inter',sans-serif;font-size:10px;color:var(--gris);margin-bottom:10px;}
.comment-text{font-size:14px;color:var(--gris);line-height:1.7;}

/* NOS AUTEURS */
.auteurs-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;}
.auteur-card{display:flex;flex-direction:column;align-items:center;text-align:center;gap:10px;padding:32px 24px;background:var(--blanc);border:1px solid var(--border);border-radius:14px;cursor:pointer;text-decoration:none;color:inherit;transition:transform .25s,box-shadow .25s;}
.auteur-card:hover{transform:translateY(-4px);box-shadow:0 12px 32px rgba(27,77,62,.12);}
.auteur-card h3{font-family:'Playfair Display',serif;font-size:20px;}
.auteur-card .role{font-size:13px;color:var(--gris);}
.auteur-card .nb{font-family:'Inter',sans-serif;font-size:10px;letter-spacing:.1em;text-transform:uppercase;color:var(--vert-mid);}
.auteur-card.inviter{background:var(--vert-pale);border-style:dashed;justify-content:center;}
.auteur-card.inviter .plus{width:72px;height:72px;border-radius:50%;border:1.5px dashed var(--vert-mid);display:grid;place-items:center;font-size:28px;color:var(--vert);}
.auteur-tete{background:var(--vert-pale);padding:72px 48px 56px;text-align:center;}
.auteur-tete h1{font-family:'Playfair Display',serif;font-size:clamp(30px,4vw,44px);color:var(--vert);margin:18px 0 6px;}
.auteur-tete .role{color:var(--gris);font-size:15px;margin-bottom:16px;}
.auteur-tete p.bio{max-width:600px;margin:0 auto;color:var(--encre);opacity:.85;line-height:1.8;}
.auteur-tete .avatar{margin:0 auto;}

/* ÉCRIRE AVEC NOUS */
.bande-ecrire{background:var(--vert);color:var(--blanc);padding:72px 48px;}
.bande-ecrire-in{max-width:1100px;margin:0 auto;display:grid;grid-template-columns:1.1fr 1fr;gap:48px;align-items:center;}
.bande-ecrire .eyebrow{font-family:'Inter',sans-serif;font-size:10px;letter-spacing:.18em;text-transform:uppercase;color:var(--vert-mid);display:block;margin-bottom:14px;}
.bande-ecrire h2{font-family:'Playfair Display',serif;font-size:clamp(28px,3.4vw,40px);line-height:1.2;margin-bottom:14px;}
.bande-ecrire p{color:rgba(255,255,255,.78);line-height:1.8;margin-bottom:24px;}
.bande-ecrire .btn-blanc{display:inline-flex;align-items:center;gap:8px;background:var(--blanc);color:var(--vert);border:none;padding:12px 26px;border-radius:100px;font-family:'Inter',sans-serif;font-size:14px;font-weight:600;cursor:pointer;text-decoration:none;}
.bande-ecrire ul{list-style:none;display:grid;gap:0;border:1px solid rgba(255,255,255,.18);border-radius:14px;overflow:hidden;}
.bande-ecrire li{padding:18px 22px;border-bottom:1px solid rgba(255,255,255,.12);font-size:14.5px;color:rgba(255,255,255,.85);}
.bande-ecrire li:last-child{border-bottom:none;}
.bande-ecrire li b{display:block;color:var(--blanc);font-weight:600;}
.etapes{display:grid;grid-template-columns:repeat(4,1fr);gap:20px;counter-reset:etape;margin:40px 0 56px;}
.etape{background:var(--blanc);border:1px solid var(--border);border-radius:12px;padding:24px;}
.etape::before{counter-increment:etape;content:counter(etape);display:grid;place-items:center;width:32px;height:32px;border-radius:50%;background:var(--vert);color:var(--blanc);font-family:'Inter',sans-serif;font-size:13px;margin-bottom:14px;}
.etape h3{font-family:'Playfair Display',serif;font-size:18px;margin-bottom:6px;}
.etape p{font-size:13.5px;color:var(--gris);line-height:1.65;}
.ecrire-grid{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:start;}
.charte h3{font-family:'Playfair Display',serif;font-size:22px;color:var(--vert);margin-bottom:14px;}
.charte ul{margin-left:20px;color:var(--gris);font-size:14.5px;line-height:1.8;}
.charte li{margin-bottom:6px;}

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
.social-plat{font-family:'Inter',sans-serif;font-size:9px;letter-spacing:.1em;text-transform:uppercase;color:var(--gris);display:block;margin-bottom:2px;}
.social-handle{font-size:13px;font-weight:500;color:var(--encre);overflow-wrap:anywhere;}

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
.contact-ok{margin-top:16px;font-size:13px;color:var(--vert-clair);font-weight:500;min-height:1.2em;}

/* FOOTER */
footer{background:var(--vert);padding:48px;text-align:center;}
.footer-logo{display:inline-flex;align-items:center;gap:8px;font-family:'Inter',sans-serif;font-size:18px;font-weight:700;color:var(--blanc);margin-bottom:12px;}
.footer-logo-dot{width:8px;height:8px;border-radius:50%;background:var(--vert-mid);}
.footer-liens{display:flex;gap:24px;justify-content:center;flex-wrap:wrap;margin-bottom:16px;font-size:13px;}
.footer-liens a{color:rgba(255,255,255,.7);text-decoration:none;cursor:pointer;}
.footer-liens a:hover{color:var(--blanc);}
.footer-copy{font-family:'Inter',sans-serif;font-size:11px;color:rgba(255,255,255,.4);letter-spacing:.06em;}

/* BLOG CATEGORIES */
.cat-section{margin-bottom:56px;}
.cat-title{font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--vert);margin-bottom:20px;padding-bottom:12px;border-bottom:2px solid var(--vert-pale);display:flex;align-items:center;gap:10px;}
.cat-count{font-family:'Inter',sans-serif;font-size:11px;color:var(--gris);font-weight:400;}
.cat-filter{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:32px;}
.cat-btn{background:var(--gris-pale);border:1px solid var(--border);color:var(--gris);padding:6px 16px;border-radius:100px;font-size:12px;font-weight:500;cursor:pointer;transition:all .2s;font-family:'Inter',sans-serif;}
.cat-btn:hover,.cat-btn.active{background:var(--vert);color:var(--blanc);border-color:var(--vert);}

/* FEATURED HOME */
.featured-label{font-family:'Inter',sans-serif;font-size:10px;letter-spacing:.18em;text-transform:uppercase;color:var(--vert-mid);margin-bottom:16px;display:block;}
.voir-plus{display:inline-flex;align-items:center;gap:8px;margin-top:40px;background:transparent;border:1px solid var(--vert);color:var(--vert);padding:10px 24px;border-radius:100px;font-family:'Inter',sans-serif;font-size:13px;font-weight:500;cursor:pointer;transition:all .2s;text-decoration:none;}
.voir-plus:hover{background:var(--vert);color:var(--blanc);}

/* ÉDITEUR */
.editor-overlay{position:fixed;inset:0;background:rgba(0,0,0,.75);z-index:9999;overflow-y:auto;padding:24px;}
.editor-box{background:var(--blanc);max-width:820px;margin:0 auto;border-radius:16px;overflow:hidden;}
.editor-head{background:var(--vert);padding:20px 28px;display:flex;align-items:center;justify-content:space-between;}
.editor-head-title{font-family:'Playfair Display',serif;font-size:20px;font-weight:400;font-style:italic;color:var(--blanc);}
.editor-head-close{background:rgba(255,255,255,.15);border:none;color:var(--blanc);padding:7px 16px;border-radius:100px;cursor:pointer;font-size:13px;font-family:'Inter',sans-serif;transition:background .2s;}
.editor-head-close:hover{background:rgba(255,255,255,.25);}
.editor-body{padding:32px;}
.ed-label{display:block;font-family:'Inter',sans-serif;font-size:10px;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--gris);margin-bottom:8px;}
.ed-input{width:100%;padding:12px 16px;border:1px solid var(--border);border-radius:8px;font-family:'Inter',sans-serif;font-size:15px;outline:none;color:var(--encre);transition:border-color .2s;margin-bottom:20px;background:var(--blanc);}
.ed-input:focus{border-color:var(--vert-mid);}
textarea.ed-input{resize:vertical;min-height:80px;}
.ed-toolbar{display:flex;gap:6px;flex-wrap:wrap;padding:12px 14px;background:var(--gris-pale);border:1px solid var(--border);border-bottom:none;border-radius:8px 8px 0 0;}
.tool{background:var(--blanc);border:1px solid var(--border);color:var(--encre);padding:6px 12px;border-radius:6px;cursor:pointer;font-size:13px;font-family:'Inter',sans-serif;transition:all .2s;}
.tool:hover{background:var(--vert);color:var(--blanc);border-color:var(--vert);}
.tool-div{width:1px;background:var(--border);margin:0 4px;align-self:stretch;}
.ed-insert{display:flex;gap:8px;flex-wrap:wrap;padding:10px 14px;background:var(--gris-pale);border:1px solid var(--border);border-bottom:none;}
.ed-insert .ed-input{flex:1 1 200px;margin-bottom:0;width:auto;}
.ed-content{width:100%;min-height:300px;padding:20px;border:1px solid var(--border);border-radius:0 0 8px 8px;font-family:'Inter',sans-serif;font-size:16px;line-height:1.8;outline:none;color:var(--encre);margin-bottom:20px;}
.ed-content:empty::before{content:'Commence à écrire ton article ici...';color:#aaa;font-style:italic;}
.ed-content blockquote{border-left:3px solid var(--vert-mid);padding:12px 20px;background:var(--vert-pale);margin:16px 0;font-style:italic;color:var(--vert);border-radius:0 6px 6px 0;}
.ed-content img{max-width:100%;border-radius:8px;margin:12px 0;}
.ed-content a{color:var(--vert-clair);text-decoration:underline;}
.ed-aide{font-size:12px;color:var(--gris);margin:-12px 0 20px;}
.ed-actions{display:flex;align-items:center;flex-wrap:wrap;gap:12px;padding-top:20px;border-top:1px solid var(--border);}
.ed-publish{background:var(--vert);color:var(--blanc);border:none;padding:12px 32px;border-radius:100px;font-family:'Inter',sans-serif;font-size:14px;font-weight:600;cursor:pointer;transition:background .2s;}
.ed-publish:hover{background:var(--vert-clair);}
.ed-cancel{background:transparent;color:var(--gris);border:1px solid var(--border);padding:12px 24px;border-radius:100px;font-family:'Inter',sans-serif;font-size:14px;cursor:pointer;}
.ed-msg{font-size:13px;color:var(--vert-clair);font-weight:600;}
.ed-erreur{font-size:13px;color:#B3261E;font-weight:600;}
.ed-tags-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:20px;}
.ed-tag-check{display:flex;align-items:center;gap:8px;font-size:13px;color:var(--encre);padding:8px 12px;border:1px solid var(--border);border-radius:8px;cursor:pointer;transition:all .2s;background:var(--blanc);}
.ed-tag-check:hover{border-color:var(--vert-mid);background:var(--vert-pale);}
.ed-tag-check input[type="checkbox"]{accent-color:var(--vert);width:14px;height:14px;cursor:pointer;}
.ed-tag-check:has(input:checked){border-color:var(--vert);background:var(--vert-pale);}

/* SCROLL TOP */
.scroll-top{position:fixed;bottom:24px;right:24px;width:40px;height:40px;border-radius:50%;background:var(--vert);border:none;color:var(--blanc);cursor:pointer;font-size:16px;display:flex;align-items:center;justify-content:center;box-shadow:0 4px 12px rgba(27,77,62,.3);transition:background .2s;z-index:100;}
.scroll-top:hover{background:var(--vert-clair);}

@media(max-width:900px){
  .une{grid-template-columns:1fr;}
  .une .cover{min-height:0;aspect-ratio:16/9;}
  .une-corps{padding:28px;}
  .auteurs-grid{grid-template-columns:repeat(2,1fr);}
  .bande-ecrire-in,.ecrire-grid{grid-template-columns:1fr;}
  .etapes{grid-template-columns:repeat(2,1fr);}
  .nav-links{gap:22px;}
}
@media(max-width:768px){
  nav{padding:0 20px;}
  .nav-links{display:none;}
  .hamburger{display:flex;}
  .hero{padding:60px 20px 48px;}
  .articles-wrap{padding:48px 20px;}
  .articles-grid,.auteurs-grid,.etapes{grid-template-columns:1fr;}
  .article-full,.comments-wrap{padding-left:20px;padding-right:20px;}
  .about-wrap,.contact-wrap{padding:48px 20px;}
  .about-card{padding:36px 22px;}
  .about-socials{grid-template-columns:1fr;}
  .contact-card{padding:28px 20px;}
  .bande-ecrire,.auteur-tete{padding:56px 20px;}
  .auteur-box{flex-direction:column;padding:22px;}
  footer{padding:32px 20px;}
  .editor-overlay{padding:0;}
  .editor-box{border-radius:0;min-height:100vh;}
  .ed-tags-grid{grid-template-columns:repeat(2,1fr);}
}

/* ══ ACCUEIL 2026 ══ */
.sr-only{position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0 0 0 0);white-space:nowrap;}
.h2026{position:relative;overflow:hidden;background:var(--vert);color:var(--blanc);min-height:min(640px,86vh);display:flex;align-items:center;padding:72px 48px;}
.aurora{position:absolute;inset:-20%;filter:blur(70px);opacity:.9;pointer-events:none;}
.aurora span{position:absolute;border-radius:50%;}
.aurora .a1{width:46%;height:56%;left:-6%;top:8%;background:#2D7A5F;animation:flotte 18s ease-in-out infinite alternate;}
.aurora .a2{width:40%;height:50%;right:4%;top:-6%;background:#4FA882;opacity:.55;animation:flotte 22s ease-in-out infinite alternate-reverse;}
.aurora .a3{width:36%;height:44%;left:38%;bottom:-14%;background:#123A2F;animation:flotte 26s ease-in-out infinite alternate;}
@keyframes flotte{to{transform:translate(8%,6%) scale(1.12);}}
.orbites{position:absolute;right:-4%;top:50%;transform:translateY(-50%);width:min(620px,58vw);height:auto;pointer-events:none;}
.tourne{transform-origin:300px 300px;animation:orbite linear infinite;}
.tourne.lent{animation-duration:40s;}.tourne.moyen{animation-duration:26s;animation-direction:reverse;}.tourne.vite{animation-duration:14s;}
@keyframes orbite{to{transform:rotate(360deg);}}
.h-contenu{position:relative;max-width:1100px;width:100%;margin:0 auto;}
.h-eyebrow{display:inline-flex;align-items:center;gap:10px;font-family:'Inter',sans-serif;font-size:11px;letter-spacing:.18em;text-transform:uppercase;color:#BFE3D2;padding:8px 14px;border:1px solid rgba(232,244,239,.25);border-radius:100px;background:rgba(255,255,255,.06);backdrop-filter:blur(6px);}
.h2026 h1{font-family:'Playfair Display',serif;font-weight:700;font-size:clamp(40px,6.6vw,84px);line-height:1.04;letter-spacing:-.025em;max-width:13ch;margin:26px 0 36px;}
.h2026 h1 em{font-style:italic;font-weight:400;color:#BFE3D2;}
.recherche-hero{display:flex;align-items:center;gap:10px;max-width:620px;padding:8px 8px 8px 20px;border-radius:100px;background:rgba(255,255,255,.12);border:1px solid rgba(232,244,239,.28);backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);box-shadow:0 20px 50px rgba(0,0,0,.18);}
.recherche-hero svg{width:20px;height:20px;color:#BFE3D2;flex:none;}
.recherche-hero input{flex:1;min-width:0;background:transparent;border:none;outline:none;color:var(--blanc);font-family:'Inter',sans-serif;font-size:16px;padding:10px 4px;}
.recherche-hero input::placeholder{color:rgba(232,244,239,.6);}
.recherche-hero button{flex:none;background:var(--blanc);color:var(--vert);border:none;border-radius:100px;padding:12px 22px;font-family:'Inter',sans-serif;font-weight:600;font-size:14px;cursor:pointer;transition:background .2s;}
.recherche-hero button:hover{background:var(--vert-pale);}
.recherche-hero:focus-within{border-color:#BFE3D2;}
.h-raccourcis{display:flex;flex-wrap:wrap;gap:8px;margin-top:18px;}
.h-raccourcis a{font-size:13px;color:rgba(232,244,239,.85);text-decoration:none;padding:7px 14px;border-radius:100px;border:1px solid rgba(232,244,239,.2);transition:background .2s,color .2s;}
.h-raccourcis a:hover{background:rgba(232,244,239,.14);color:var(--blanc);}

.bento-wrap{padding:72px 48px 88px;background:var(--gris-pale);}
.bento{max-width:1100px;margin:0 auto;display:grid;grid-template-columns:repeat(12,1fr);grid-auto-rows:minmax(170px,auto);gap:16px;}
.tuile{position:relative;overflow:hidden;border-radius:22px;text-decoration:none;color:inherit;background:var(--blanc);border:1px solid var(--border);transition:transform .3s,box-shadow .3s;display:flex;flex-direction:column;justify-content:flex-end;padding:22px;}
a.tuile:hover{transform:translateY(-4px);box-shadow:0 18px 40px rgba(27,77,62,.14);}
.tuile .t-label{font-family:'Inter',sans-serif;font-size:10px;letter-spacing:.16em;text-transform:uppercase;color:var(--vert-mid);}
.t-une{grid-column:span 7;grid-row:span 3;padding:0;border:none;color:var(--blanc);}
.t-une .cover{position:absolute;inset:0;aspect-ratio:auto;height:100%;}
.t-une .t-voile{position:absolute;inset:0;background:linear-gradient(180deg,rgba(17,26,20,0) 35%,rgba(17,26,20,.78) 100%);}
.t-une .t-texte{position:relative;padding:30px;display:grid;gap:10px;}
.t-une .t-label{color:#BFE3D2;}
.t-une h2{font-family:'Playfair Display',serif;font-size:clamp(24px,2.6vw,34px);line-height:1.15;}
.t-une .t-meta{font-family:'Inter',sans-serif;font-size:11px;color:rgba(255,255,255,.75);}
.t-une:hover .cover svg,.t-une:hover .cover img{transform:scale(1.05);}
.t-citation{grid-column:span 5;grid-row:span 2;background:var(--vert-pale);border:none;justify-content:space-between;}
.t-citation .guillemet{font-family:'Playfair Display',serif;font-size:90px;line-height:.6;color:var(--vert-mid);}
.t-citation blockquote{font-family:'Playfair Display',serif;font-style:italic;font-size:clamp(20px,2vw,26px);line-height:1.35;color:var(--vert);}
.t-citation .t-source{font-size:12.5px;color:var(--gris);}
.t-theme{grid-column:span 4;}
.t-theme.petit{grid-column:span 5;grid-row:span 1;}
.t-theme .t-ill{position:absolute;right:-18px;top:-18px;width:150px;height:150px;color:var(--vert-pale);transition:transform .4s,color .3s;}
.t-theme .t-ill svg{width:100%;height:100%;}
a.t-theme:hover .t-ill{transform:rotate(-8deg) scale(1.08);color:#CFE8DC;}
.t-theme b{position:relative;font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--encre);}
.t-theme .t-nb{position:relative;font-family:'Inter',sans-serif;font-size:11px;color:var(--gris);margin-top:4px;}
.t-theme.fonce{background:var(--vert);border-color:var(--vert);}
.t-theme.fonce b{color:var(--blanc);}
.t-theme.fonce .t-nb{color:rgba(255,255,255,.65);}
.t-theme.fonce .t-ill{color:rgba(232,244,239,.12);}
a.t-theme.fonce:hover .t-ill{color:rgba(232,244,239,.2);}
.t-tout{grid-column:span 4;background:var(--encre);border:none;color:var(--blanc);}
.t-tout b{font-family:'Playfair Display',serif;font-size:22px;}
.t-tout .fleche{position:absolute;right:22px;top:22px;width:46px;height:46px;border-radius:50%;background:var(--vert-mid);display:grid;place-items:center;font-size:20px;transition:transform .3s;}
a.t-tout:hover .fleche{transform:rotate(-45deg);}
.t-tout .t-nb{font-family:'Inter',sans-serif;font-size:11px;color:rgba(255,255,255,.6);margin-top:4px;}
.t-reseaux{grid-column:span 12;grid-row:span 1;flex-direction:row;align-items:center;justify-content:space-between;gap:20px;flex-wrap:wrap;background:var(--blanc);}
.t-reseaux b{font-family:'Playfair Display',serif;font-size:22px;}
.t-reseaux .liens-r{display:flex;gap:10px;flex-wrap:wrap;}
.t-reseaux .liens-r a{display:inline-flex;align-items:center;gap:8px;padding:10px 18px;border-radius:100px;border:1px solid var(--border);text-decoration:none;color:var(--encre);font-size:14px;font-weight:500;transition:all .2s;}
.t-reseaux .liens-r a:hover{background:var(--vert);border-color:var(--vert);color:var(--blanc);}
.t-reseaux svg{width:18px;height:18px;}
.recherche-blog{display:block;width:100%;max-width:420px;margin:0 auto 28px;padding:12px 20px;border:1px solid var(--border);border-radius:100px;font-family:'Inter',sans-serif;font-size:15px;outline:none;background:var(--gris-pale);color:var(--encre);}
.recherche-blog:focus{border-color:var(--vert-mid);background:var(--blanc);}
.contact-note{background:var(--vert-pale);border-radius:10px;padding:12px 16px;margin-top:-16px;color:var(--vert)!important;font-size:13px!important;}
.mention{font-family:'Inter',sans-serif;font-size:11px;color:var(--vert-clair);}
@media(max-width:900px){
  .bento{grid-template-columns:repeat(6,1fr);grid-auto-rows:minmax(150px,auto);}
  .t-une{grid-column:span 6;grid-row:span 3;}
  .t-citation{grid-column:span 6;grid-row:span 2;}
  .t-theme,.t-theme.petit,.t-tout{grid-column:span 3;grid-row:span 1;}
  .t-reseaux{grid-column:span 6;grid-row:auto;}
  .orbites{opacity:.5;}
}
@media(max-width:768px){
  .h2026{padding:64px 20px 56px;min-height:0;}
  .orbites{width:120vw;right:-50%;opacity:.35;}
  .recherche-hero{padding-left:14px;}
  .recherche-hero button{padding:11px 16px;}
  .bento-wrap{padding:40px 20px 56px;}
  .bento{grid-template-columns:repeat(2,1fr);grid-auto-rows:minmax(140px,auto);gap:12px;}
  .t-une{grid-column:span 2;grid-row:span 3;}
  .t-citation{grid-column:span 2;grid-row:span 2;}
  .t-theme,.t-theme.petit,.t-tout{grid-column:span 1;}
  .t-theme b,.t-tout b{font-size:18px;}
  .t-theme .t-ill{width:110px;height:110px;}
  .t-reseaux{grid-column:span 2;}
  .t-tout .fleche{width:34px;height:34px;right:14px;top:14px;font-size:16px;}
}
@media(prefers-reduced-motion:reduce){.aurora span,.tourne{animation:none!important;}}

/* ══ ACCUEIL v6 ══ */
.t-label{font-family:'Inter',sans-serif;font-size:11px;letter-spacing:.16em;text-transform:uppercase;color:var(--vert-mid);}
.accueil-hero{max-width:1200px;margin:0 auto;padding:72px 48px 56px;display:grid;grid-template-columns:1.05fr 1fr;gap:56px;align-items:center;}
.accueil-hero .h-eyebrow{color:var(--vert-mid);border-color:var(--border);background:var(--blanc);backdrop-filter:none;}
.accueil-hero h1{font-family:'Playfair Display',serif;font-weight:700;font-size:clamp(40px,5.4vw,72px);line-height:1.05;letter-spacing:-.02em;color:var(--vert);margin:24px 0 20px;}
.accueil-hero h1 em{font-style:italic;font-weight:400;color:var(--vert-mid);}
.accueil-hero p{font-size:17px;line-height:1.7;color:var(--gris);max-width:44ch;}
.ah-boutons{display:flex;gap:12px;flex-wrap:wrap;margin-top:30px;}
.btn-plein,.btn-ligne{display:inline-flex;align-items:center;padding:14px 26px;border-radius:100px;font-family:'Inter',sans-serif;font-weight:600;font-size:14.5px;text-decoration:none;transition:all .2s;}
.btn-plein{background:var(--vert);color:var(--blanc);}
.btn-plein:hover{background:var(--vert-mid);}
.btn-ligne{border:1.5px solid var(--border);color:var(--vert);}
.btn-ligne:hover{border-color:var(--vert);}
.ah-photo{aspect-ratio:4/5;max-height:560px;border-radius:28px;overflow:hidden;position:relative;background:var(--vert-pale);}
.ah-photo img{width:100%;height:100%;object-fit:cover;display:block;}
.photo-vide{position:absolute;inset:14px;border:2px dashed #B9D7C8;border-radius:20px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:10px;text-align:center;padding:24px;color:var(--vert-mid);}
.photo-vide b{font-family:'Playfair Display',serif;font-size:22px;color:var(--vert);}
.photo-vide small{font-size:13px;color:var(--gris);max-width:26ch;line-height:1.5;}
.bloc{max-width:1200px;margin:0 auto;padding:56px 48px;}
.bloc-pale{max-width:none;background:var(--gris-pale);}
.bloc-pale > *{max-width:1104px;margin-left:auto;margin-right:auto;}
.bloc-tete{margin-bottom:26px;}
.bloc-tete h2{font-family:'Playfair Display',serif;font-size:clamp(26px,3vw,36px);color:var(--encre);margin:8px 0 6px;}
.bloc-tete p{color:var(--gris);font-size:15px;}
.une-duo{display:grid;grid-template-columns:7fr 5fr;gap:16px;}
.une-duo .t-une,.une-duo .t-citation{grid-column:auto;grid-row:auto;min-height:420px;}
.une-duo .t-citation{gap:20px;}
.biblio{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;}
.ressource{display:flex;flex-direction:column;background:var(--blanc);border:1px solid var(--border);border-radius:18px;overflow:hidden;text-decoration:none;color:inherit;transition:transform .3s,box-shadow .3s;}
.ressource:hover{transform:translateY(-4px);box-shadow:0 16px 36px rgba(27,77,62,.12);}
.r-visuel{position:relative;aspect-ratio:16/10;background:var(--vert-pale);display:grid;place-items:center;color:var(--vert-mid);overflow:hidden;}
.r-visuel img{width:100%;height:100%;object-fit:cover;}
.r-video .r-visuel{background:var(--vert);color:#BFE3D2;}
.r-cours .r-visuel{background:#D8ECE2;}
.r-nextpath .r-visuel{background:var(--encre);color:var(--vert-clair);}
.r-visuel .exemple{position:absolute;top:10px;right:10px;}
.r-play{position:absolute;width:50px;height:50px;border-radius:50%;background:rgba(17,26,20,.7);color:#fff;display:grid;place-items:center;font-size:16px;}
.r-corps{padding:18px;display:flex;flex-direction:column;gap:8px;flex:1;}
.r-type{display:inline-flex;align-items:center;gap:6px;font-family:'Inter',sans-serif;font-size:10.5px;letter-spacing:.08em;text-transform:uppercase;color:var(--vert-mid);}
.r-corps b{font-family:'Playfair Display',serif;font-size:18px;line-height:1.25;color:var(--encre);}
.r-corps p{font-size:13.5px;line-height:1.55;color:var(--gris);flex:1;}
.r-lien{font-size:13px;font-weight:600;color:var(--vert);}
.avis{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px;}
.avis-carte{background:var(--blanc);border:1px solid var(--border);border-radius:18px;padding:26px;display:flex;flex-direction:column;gap:12px;margin:0;}
.avis-carte .guillemet{font-family:'Playfair Display',serif;font-size:60px;line-height:.5;color:var(--vert-clair);}
.avis-carte blockquote{font-family:'Playfair Display',serif;font-style:italic;font-size:18px;line-height:1.45;color:var(--vert);}
.avis-carte figcaption{font-size:13px;color:var(--gris);}
.avis-appel{background:var(--vert-pale);border:none;align-items:flex-start;}
.avis-appel b{font-family:'Playfair Display',serif;font-size:22px;color:var(--vert);}
.avis-appel p{color:var(--gris);font-size:14.5px;}
.bloc-fin{padding-bottom:80px;}
.suivre{display:flex;align-items:center;justify-content:space-between;gap:20px;flex-wrap:wrap;border:1px solid var(--border);border-radius:22px;padding:26px 28px;}
.suivre b{display:block;font-family:'Playfair Display',serif;font-size:22px;margin-top:6px;}
.suivre .liens-r{display:flex;gap:10px;flex-wrap:wrap;}
.suivre .liens-r a{display:inline-flex;align-items:center;gap:8px;padding:10px 18px;border-radius:100px;border:1px solid var(--border);text-decoration:none;color:var(--encre);font-size:14px;font-weight:500;transition:all .2s;}
.suivre .liens-r a:hover{background:var(--vert);border-color:var(--vert);color:var(--blanc);}
.suivre svg{width:18px;height:18px;}
@media(max-width:1000px){.biblio{grid-template-columns:repeat(2,1fr);}}
@media(max-width:820px){
  .accueil-hero{grid-template-columns:1fr;gap:32px;padding:40px 20px 24px;}
  .ah-photo{aspect-ratio:4/3;}
  .bloc{padding:36px 20px;}
  .une-duo{grid-template-columns:1fr;}
  .une-duo .t-une{min-height:360px;}
  .une-duo .t-citation{min-height:0;}
}
@media(max-width:520px){.biblio{grid-template-columns:none;grid-auto-flow:column;grid-auto-columns:80%;overflow-x:auto;scroll-snap-type:x mandatory;padding-bottom:8px;}.ressource{scroll-snap-align:start;}}

@media(prefers-reduced-motion:reduce){*{transition:none!important;scroll-behavior:auto!important;}}

/* ══ v7 : moins « effet IA » ══ */
.t-label,.tuile .t-label,.r-type,.cover-cat,.exemple,.card-tag,.card-cta,.sources h3,.auteur-box .label,.ed-label,.featured-label{letter-spacing:.04em;font-weight:600;}
.t-label{font-size:13px;text-transform:none;color:var(--vert-mid);}
.r-type{text-transform:none;font-size:12px;}
.card-meta,.signature-meta,.t-une .t-meta,.comment-date,.cat-count,.footer-copy{font-size:12.5px;letter-spacing:0;}
.accueil-hero h1{margin-top:0;}
.accueil-hero h1 em{font-style:normal;font-weight:700;color:var(--vert-mid);}
.t-citation blockquote,.avis-carte blockquote{font-style:normal;font-family:'Inter',sans-serif;font-weight:500;line-height:1.5;}
.t-citation blockquote{font-size:clamp(19px,1.8vw,23px);}
.avis-carte blockquote{font-size:16px;}
.bloc-tete-ligne{display:flex;align-items:flex-end;justify-content:space-between;gap:20px;flex-wrap:wrap;}
.biblio-page{padding-top:64px;}
.biblio-page h1{font-family:'Playfair Display',serif;font-size:clamp(32px,4.4vw,54px);line-height:1.1;color:var(--vert);margin:10px 0 12px;}
.biblio-page .cat-filter{margin-bottom:28px;}
.biblio:not(.biblio-grand){grid-template-columns:repeat(3,1fr);}
.biblio-grand{grid-template-columns:repeat(3,1fr);gap:22px;}
.biblio-grand .r-corps b{font-size:21px;}
@media(max-width:1000px){.biblio:not(.biblio-grand),.biblio-grand{grid-template-columns:repeat(2,1fr);}}
@media(max-width:520px){.biblio-grand{grid-template-columns:1fr;grid-auto-flow:row;overflow:visible;}}
@media(max-width:520px){.biblio:not(.biblio-grand){grid-template-columns:none;}}

/* ══ COUPS DE CŒUR (page colorée) ══ */
#page-bibliotheque{--corail:#FF6B57;--soleil:#FFC93C;--violet:#7C5CFF;--ciel:#2FA4FF;background:#FFFBF4;}
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

.ah-photo[hidden]{display:none;}
.accueil-hero.sans-photo{grid-template-columns:1fr;padding-bottom:24px;}
.accueil-hero.sans-photo h1{font-size:clamp(44px,6.6vw,88px);max-width:16ch;}
</style>
</head>
<body>

<nav>
  <a class="nav-logo" href="#accueil">
    <div class="nav-logo-dot"></div>
    <span><span class="nav-logo-np">NextPath</span> <span class="nav-logo-blog">Blog</span></span>
  </a>
  <ul class="nav-links">
    <li><a href="#accueil" data-page="home">Accueil</a></li>
    <li><a href="#blog" data-page="blog">Blog</a></li>
    <li><a href="#coups-de-coeur" data-page="bibliotheque">Coups de cœur</a></li>
    <li><a href="#a-propos" data-page="about">À propos</a></li>
    <li><a href="#contact" data-page="contact">Contact</a></li>
  </ul>
  <button class="hamburger" id="hamburger" aria-label="Ouvrir le menu" aria-expanded="false"><span></span><span></span><span></span></button>
</nav>

<div class="mobile-menu" id="mobile-menu">
  <a href="#accueil">Accueil</a>
  <a href="#blog">Blog</a>
  <a href="#coups-de-coeur">Coups de cœur</a>
  <a href="#a-propos">À propos</a>
  <a href="#contact">Contact</a>
</div>

<div class="progression" id="progression"></div>

<!-- ACCUEIL -->
<div class="page" id="page-home">
  <section class="accueil-hero">
    <div class="ah-texte">
      <h1>L'endroit où les idées deviennent <em>des actions.</em></h1>
      <p>Des articles sourcés et relus, et une sélection de ressources pour apprendre et avancer.</p>
      <div class="ah-boutons"><a class="btn-plein" href="#blog">Lire les articles</a><a class="btn-ligne" href="#coups-de-coeur">Nos coups de cœur</a></div>
    </div>
    <div class="ah-photo" id="ah-photo"></div>
  </section>

  <section class="bloc">
    <div class="bloc-tete"><span class="t-label">À la une</span></div>
    <div class="une-duo" id="une-duo"></div>
  </section>

  <section class="bloc bloc-pale">
    <div class="bloc-tete bloc-tete-ligne"><div><span class="t-label">Nos coups de cœur</span><h2>Ce que nous vous conseillons de voir</h2><p>Nos derniers coups de cœur : vidéos, articles et cours.</p></div><a class="btn-plein" href="#coups-de-coeur">Tous nos coups de cœur →</a></div>
    <div class="biblio" id="biblio"></div>
  </section>

  <section class="bloc" id="avis">
    <div class="bloc-tete"><span class="t-label">Témoignages et avis</span><h2>Ce qu'en disent les lecteurs</h2></div>
    <div class="avis" id="liste-avis"></div>
  </section>

  <section class="bloc bloc-fin">
    <div class="suivre" id="suivre"></div>
  </section>
</div>

<!-- BIBLIOTHÈQUE -->
<div class="page" id="page-bibliotheque">
  <section class="cdc-hero">
    <span class="bulle b1"></span><span class="bulle b2"></span><span class="bulle b3"></span><span class="bulle b4"></span>
    <div class="cdc-hero-in">
      <span class="cdc-coeur" aria-hidden="true">♥</span>
      <h1>Nos coups <span>de cœur</span></h1>
      <p>Ce que nous apprenons, nous le partageons. Des vidéos, des articles, des cours et des livres qui nous ont aidés, choisis pour vous.</p>
      <div class="cdc-filtres" id="biblio-filtres"></div>
    </div>
  </section>
  <section class="cdc-grille" id="biblio-tout"></section>
</div>

<!-- BLOG -->
<div class="page" id="page-blog">
  <div class="articles-wrap">
    <div class="articles-header">
      <div class="articles-title">Tous les articles</div>
    </div>
    <label class="sr-only" for="q-blog">Rechercher un article</label>
    <input class="recherche-blog" id="q-blog" type="search" placeholder="Rechercher un article…">
    <div id="blog-categories"></div>
  </div>
</div>

<!-- ARTICLE -->
<div class="page" id="page-article">
  <div class="article-full" id="article-full-content"></div>
  <div class="comments-wrap" id="comments-wrap"></div>
  <div class="suite">
    <div class="articles-wrap">
      <div class="articles-header"><span class="featured-label">Continuer la lecture</span><div class="articles-title">À lire ensuite</div></div>
      <div class="articles-grid" id="suite"></div>
    </div>
  </div>
</div>

<!-- À PROPOS -->
<div class="page" id="page-about">
  <div class="about-wrap">
    <div class="about-card">
      <div class="about-icon">🧭</div>
      <h2>À propos de nous</h2>
      <p>NextPath System est une plateforme qui aide chacun à savoir dans quoi se lancer, à identifier sa voie, et à avoir les outils pour y arriver. Les articles sont rédigés et relus par l'équipe NextPath, avec des sources citées.</p>
      <div class="about-divider"></div>
      <div class="about-socials-title">Rejoignez notre communauté</div>
      <div class="about-socials">
        <a href="https://instagram.com/nextpath.system" target="_blank" rel="noopener" class="social-link">
          <div class="social-icon">📸</div>
          <div><span class="social-plat">Instagram</span><span class="social-handle">@nextpath.system</span></div>
        </a>
        <a href="https://www.youtube.com/@NextPathSystem" target="_blank" rel="noopener" class="social-link">
          <div class="social-icon">▶️</div>
          <div><span class="social-plat">YouTube</span><span class="social-handle">@NextPathSystem</span></div>
        </a>
        <a href="https://tiktok.com/@nextpath.system" target="_blank" rel="noopener" class="social-link">
          <div class="social-icon">🎵</div>
          <div><span class="social-plat">TikTok</span><span class="social-handle">@nextpath.system</span></div>
        </a>
        <div class="social-link">
          <div class="social-icon">✉️</div>
          <div><span class="social-plat">Email</span><span class="social-handle">nextpathsystem@gmail.com</span></div>
        </div>
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
      <p class="contact-note">Vous avez un sujet intéressant et souhaitez qu'il soit publié ? Choisissez « Proposer un article » dans l'objet.</p>
      <form id="contact-form" novalidate>
        <label class="contact-label" for="c-nom">Nom complet</label>
        <input type="text" id="c-nom" name="nom" class="contact-input" placeholder="Ex: Koffi Mensah" required>
        <label class="contact-label" for="c-email">Adresse Email</label>
        <input type="email" id="c-email" name="email" class="contact-input" placeholder="Ex: koffi.mensah@example.com" required>
        <label class="contact-label" for="c-objet">Objet</label>
        <select id="c-objet" name="objet" class="contact-input"><option>Question</option><option>Suggestion</option><option>Proposer un article</option><option>Avis / témoignage</option><option>Partenariat</option><option>Autre</option></select>
        <label class="contact-label" for="c-message">Message</label>
        <textarea id="c-message" name="message" class="contact-textarea" placeholder="Décrivez votre besoin ou votre question en détails..." required></textarea>
        <button type="submit" class="contact-submit">Envoyer le message ✈</button>
        <div class="contact-ok" id="contact-ok" role="status"></div>
      </form>
    </div>
  </div>
</div>

<footer>
  <div class="footer-logo"><div class="footer-logo-dot"></div>NextPath Blog</div>
  <div class="footer-liens"><a href="#blog">Articles</a><a href="#coups-de-coeur">Coups de cœur</a><a href="#a-propos">À propos</a><a href="#contact">Contact</a></div>
  <div class="footer-copy">© 2026 NextPath Blog</div>
</footer>

<button class="scroll-top" id="scroll-top" aria-label="Revenir en haut">↑</button>

<!-- ÉDITEUR ADMIN (taper NPADMIN) -->
<div class="editor-overlay" id="editor-overlay" hidden>
  <div class="editor-box">
    <div class="editor-head">
      <div class="editor-head-title">Rédiger un article</div>
      <button class="editor-head-close" id="ed-fermer" type="button">✕ Fermer</button>
    </div>
    <div class="editor-body">
      <label class="ed-label" for="ed-titre">Titre de l'article *</label>
      <input type="text" class="ed-input" id="ed-titre" placeholder="Ex : La discipline, ce que personne ne t'a dit">

      <label class="ed-label" for="ed-chapo">Chapô (2 phrases qui donnent envie de lire)</label>
      <textarea class="ed-input" id="ed-chapo"></textarea>

      <label class="ed-label" for="ed-auteur">Auteur *</label>
      <select class="ed-input" id="ed-auteur"></select>
      <p class="ed-aide">« Grace Kabundo » quand c'est toi qui écris, « Équipe NextPath » quand c'est l'équipe.</p>

      <span class="ed-label">Catégories * (choisis une ou plusieurs)</span>
      <div class="ed-tags-grid" id="ed-tags-grid"></div>

      <label class="ed-label" for="ed-img">URL d'image de couverture (optionnel)</label>
      <input type="text" class="ed-input" id="ed-img" placeholder="https://... (lien d'une image en ligne)">

      <span class="ed-label">Contenu *</span>
      <div class="ed-toolbar" id="ed-toolbar">
        <button class="tool" type="button" data-cmd="bold"><b>G</b></button>
        <button class="tool" type="button" data-cmd="italic"><i>I</i></button>
        <button class="tool" type="button" data-cmd="underline"><u>S</u></button>
        <div class="tool-div"></div>
        <button class="tool" type="button" data-cmd="h2">Intertitre</button>
        <button class="tool" type="button" data-cmd="quote">❝ Citation</button>
        <button class="tool" type="button" data-cmd="lien">🔗 Lien</button>
        <button class="tool" type="button" data-cmd="image">🖼 Image</button>
        <div class="tool-div"></div>
        <button class="tool" type="button" data-cmd="insertUnorderedList">• Liste</button>
        <button class="tool" type="button" data-cmd="insertOrderedList">1. Liste num.</button>
      </div>
      <div class="ed-insert" id="ed-insert" hidden>
        <input class="ed-input" id="ed-insert-url" placeholder="Colle le lien ici">
        <input class="ed-input" id="ed-insert-texte" placeholder="Texte du lien">
        <button class="tool" type="button" id="ed-insert-ok">Insérer</button>
      </div>
      <div class="ed-content" id="ed-content" contenteditable="true"></div>

      <label class="ed-label" for="ed-sources">Sources (une par ligne)</label>
      <textarea class="ed-input" id="ed-sources" placeholder="Auteur (année). Titre. Revue ou site."></textarea>
      <p class="ed-aide">Dans le texte, écris [1], [2]… pour renvoyer vers la source correspondante.</p>

      <label class="ed-label" for="ed-relu">Relu par (optionnel)</label>
      <input type="text" class="ed-input" id="ed-relu" placeholder="Ex : Grace">

      <div class="ed-actions">
        <button class="ed-publish" id="ed-publier" type="button">Publier l'article</button>
        <button class="ed-cancel" id="ed-annuler" type="button">Annuler</button>
        <button class="ed-cancel" id="ed-exporter" type="button" title="Télécharge un fichier avec tous tes articles">Exporter mes articles</button>
        <span class="ed-msg" id="ed-msg" role="status"></span>
      </div>
    </div>
  </div>
</div>

<script>
// ══ AUTEURS ══
// Tout est signé « Équipe NextPath » par défaut. Pour un auteur invité ponctuel : copie le bloc, change l'identifiant, change l'identifiant (sans espace ni accent) et remplis les champs.
// photo : lien d'une image carrée (optionnel). liens : réseaux ou site de l'auteur (optionnel).
var AUTEURS = {
  'grace': {
    nom:'Grace Kabundo', role:'Fondatrice de NextPath',
    bio:"Grace a créé NextPath pour partager des idées utiles, vérifiées et faciles à mettre en pratique.",
    photo:'', liens:[['Instagram','https://instagram.com/nextpath.system'],['YouTube','https://youtube.com/@NextPathSystem']]
  },
  'equipe': {
    nom:'Équipe NextPath', role:'',
    bio:"Les articles de l'équipe sont écrits et relus à plusieurs. Chaque affirmation importante renvoie à une source que vous pouvez vérifier.",
    photo:'', liens:[['Instagram','https://instagram.com/nextpath.system'],['YouTube','https://youtube.com/@NextPathSystem']]
  }
};

// ══ PHOTOS ══
// Mets ici le lien de tes propres images (ton hébergement, un lien d'image public…).
// Pour un article, l'image se met dans l'éditeur (champ « URL d'image de couverture »).
var PHOTOS = {
  accueil: ''   // grande photo à droite du titre sur l'accueil
};

// ══ NOS COUPS DE CŒUR ══
// Une ligne par ressource. Ajoute les nouvelles EN HAUT de la liste : l'accueil montre les 3 premières.
// type : 'Vidéo', 'Article', 'Cours', 'Livre' ou 'NextPath' (un de nos articles).
// Pour une vidéo YouTube, colle le lien de la vidéo : la miniature s'affiche toute seule.
// image : lien d'une image (optionnel, pour les ressources qui ne sont pas des vidéos).
var BIBLIOTHEQUE = [
  {type:'Vidéo', sujet:'Science', titre:'ScienceEtonnante', pourquoi:"Pour comprendre des grandes idées scientifiques, expliquées simplement.", lien:'https://www.youtube.com/@ScienceEtonnante', image:''},
  {type:'Cours', sujet:'Apprendre', titre:'Learning How to Learn (Coursera, gratuit)', pourquoi:"Pour apprendre à apprendre : mémoire, concentration, procrastination.", lien:'https://www.coursera.org/learn/learning-how-to-learn', image:''},
  {type:'Article', sujet:'Actualité scientifique', titre:'The Conversation France', pourquoi:"Des chercheurs qui expliquent eux-mêmes leurs travaux.", lien:'https://theconversation.com/fr', image:''},
];

// ══ TÉMOIGNAGES ET AVIS ══
// Ajoute les avis reçus (avec l'accord de la personne). Exemple :
// {texte:"Cet article m'a aidée à préparer mes examens.", nom:'Sarah', contexte:'Étudiante'},
var AVIS = [];

var CATEGORIES = ['Éducation','Science','Orientation','Développement personnel','Foi','NextPath','Jeunesse','Afrique','Carrière','Santé'];

// ══ ARTICLES D'EXEMPLE ══
// Ils montrent le rendu. À supprimer quand tes vrais articles seront en ligne.
var EXEMPLES = []; // les articles d'exemple ont été retirés de la version en ligne

// ══ ARTICLES EN LIGNE (visibles par tous les visiteurs) ══
// Colle ici le contenu du fichier « nextpath-articles.json » (bouton « Exporter mes articles » dans l'éditeur).
var ARTICLES_EN_LIGNE = [];

// ══ PERSISTANCE ══
// Attention : localStorage garde les articles dans le navigateur de celui qui écrit.
// Les visiteurs ne les voient pas tant que le site n'a pas un vrai hébergement des articles.
function lire(cle, defaut){ try { var v = localStorage.getItem(cle); return v ? JSON.parse(v) : defaut; } catch(e){ return defaut; } }
function sauvegarder(){
  try {
    localStorage.setItem('np_articles', JSON.stringify(articles));
    localStorage.setItem('np_comments', JSON.stringify(comments));
    localStorage.setItem('np_liked', JSON.stringify(liked));
  } catch(e){}
}
var articles = lire('np_articles', []);
var comments = lire('np_comments', {});
var liked = lire('np_liked', {});
function tous(){
  var vus = {}, liste = articles.concat(ARTICLES_EN_LIGNE).map(normaliser).filter(function(a){ if (vus[a.id]) return false; vus[a.id] = 1; return true; });
  return liste.concat(EXEMPLES).sort(function(a,b){ return (b.date || '').localeCompare(a.date || ''); });
}
// Rend compatibles les articles écrits avec l'ancienne version du site.
function normaliser(a){
  if (!a.id) a.id = 'article-' + Date.now();
  a.id = String(a.id);
  if (!a.tags) a.tags = a.tag ? [a.tag] : [];
  if (!AUTEURS[a.auteur]) a.auteur = 'equipe';
  if (!a.sources) a.sources = [];
  if (a.date && !/^\d{4}-/.test(a.date)) { a.dateTexte = a.date; }
  return a;
}

// ══ OUTILS ══
function $(id){ return document.getElementById(id); }
function esc(s){ return String(s == null ? '' : s).replace(/[&<>"']/g, function(c){ return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]; }); }
function dateFr(a, champ){
  var v = a[champ || 'date'];
  if (!v) return '';
  if (!/^\d{4}-/.test(v)) return v;
  return new Date(v + 'T12:00:00').toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'});
}
function slugify(t){ return t.toLowerCase().normalize('NFD').replace(/[̀-ͯ]/g,'').replace(/[^a-z0-9]+/g,'-').replace(/^-+|-+$/g,'').slice(0,70) || ('article-' + Date.now()); }
function hash(s){ s = String(s); var h = 2166136261; for (var i = 0; i < s.length; i++){ h ^= s.charCodeAt(i); h = Math.imul(h, 16777619) >>> 0; } h ^= h >>> 13; h = Math.imul(h, 0x5bd1e995) >>> 0; return (h ^ (h >>> 15)) >>> 0; }
function auteurDe(a){ return AUTEURS[a.auteur] || {nom:a.auteur || 'NextPath', role:'', bio:'', liens:[]}; }
function initiales(n){ return n.split(/\s+/).filter(Boolean).map(function(m){ return m[0]; }).join('').slice(0,2).toUpperCase(); }
function avatar(au, taille){ return '<span class="avatar' + (taille ? ' ' + taille : '') + '">' + (au.photo ? '<img src="' + esc(au.photo) + '" alt="">' : esc(initiales(au.nom))) + '</span>'; }

// Couverture illustrée quand l'article n'a pas de photo : un paysage de chemins aux couleurs NextPath, unique par article.
function couverture(a){
  if (a.img) return '<img src="' + esc(a.img) + '" alt="" loading="lazy">';
  var h = hash(a.id), W = 800, H = 450;
  function r(k){ return ((h >>> k) & 255) / 255; }
  var fonds = [['#1B4D3E','#2D7A5F'],['#2D7A5F','#4FA882'],['#1B4D3E','#4FA882'],['#24604D','#7FC3A4']];
  var f = fonds[h % fonds.length];
  var id = 'g' + (h % 100000);
  var sx = 160 + r(3) * 480, sy = 110 + r(11) * 80;
  function colline(base, amp, ph){
    var d = 'M0 ' + base;
    for (var x = 0; x <= W; x += 100){
      var y = base - Math.sin(x / 140 + ph) * amp - Math.cos(x / 70 + ph * 2) * amp * .3;
      d += ' L' + x + ' ' + y.toFixed(1);
    }
    return d + ' L' + W + ' ' + H + ' L0 ' + H + 'Z';
  }
  var chemin = 'M' + (W * .52).toFixed(0) + ' ' + H + ' C ' + (W * .5) + ' 380, ' + (W * (.3 + r(5) * .3)).toFixed(0) + ' 340, ' + (W * (.45 + r(7) * .2)).toFixed(0) + ' 300';
  return '<svg viewBox="0 0 ' + W + ' ' + H + '" preserveAspectRatio="xMidYMid slice" aria-hidden="true">'
    + '<defs><linearGradient id="' + id + '" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="' + f[0] + '"/><stop offset="1" stop-color="' + f[1] + '"/></linearGradient></defs>'
    + '<rect width="' + W + '" height="' + H + '" fill="url(#' + id + ')"/>'
    + '<circle cx="' + sx.toFixed(0) + '" cy="' + sy.toFixed(0) + '" r="120" fill="#E8F4EF" opacity=".08"/>'
    + '<circle cx="' + sx.toFixed(0) + '" cy="' + sy.toFixed(0) + '" r="54" fill="#E8F4EF" opacity=".9"/>'
    + '<path d="' + colline(300, 34, r(2) * 6) + '" fill="#4FA882" opacity=".45"/>'
    + '<path d="' + colline(340, 26, r(9) * 6) + '" fill="#2D7A5F" opacity=".85"/>'
    + '<path d="' + colline(390, 18, r(13) * 6) + '" fill="#1B4D3E"/>'
    + '<path d="' + chemin + '" fill="none" stroke="#E8F4EF" stroke-width="5" stroke-dasharray="2 14" stroke-linecap="round" opacity=".9"/>'
    + '</svg>';
}
function coverHtml(a){
  return '<div class="cover">' + couverture(a) + '<span class="cover-cat">' + esc(a.tags[0] || 'NextPath') + '</span>' + (a.exemple ? '<span class="exemple">Exemple</span>' : '') + '</div>';
}
function auteurMini(a){
  var au = auteurDe(a);
  return '<div class="auteur-mini">' + avatar(au) + '<div style="min-width:0"><b>' + esc(au.nom) + '</b><small>' + esc(au.role) + '</small></div></div>';
}

// ══ CARTE ARTICLE ══
function buildCard(a){
  var tags = a.tags.map(function(t){ return '<span class="card-tag">' + esc(t) + '</span>'; }).join('');
  return '<a class="article-card" href="#' + esc(a.id) + '">'
    + coverHtml(a)
    + '<div class="card-body">'
    + '<div class="card-tags">' + tags + '</div>'
    + '<div class="card-meta"><span>' + dateFr(a) + '</span><span>' + esc(a.lecture) + ' de lecture</span>' + (a.sources.length ? '<span>' + a.sources.length + ' source' + (a.sources.length > 1 ? 's' : '') + '</span>' : '') + '</div>'
    + '<div class="card-title">' + esc(a.titre) + '</div>'
    + '<div class="card-excerpt">' + esc(a.chapo || a.extrait) + '</div>'
    + '<div class="card-pied">' + auteurMini(a) + '<span class="card-cta">Lire</span></div>'
    + '</div></a>';
}
// ══ RENDU ACCUEIL ══
var RESEAUX = [
  ['Instagram','https://instagram.com/nextpath.system','<rect x="3" y="3" width="18" height="18" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor"/>'],
  ['TikTok','https://www.tiktok.com/@nextpath.system','<path d="M14 3v11.5a3.5 3.5 0 1 1-3.5-3.5"/><path d="M14 3c.5 2.8 2.4 4.6 5 5"/>'],
  ['YouTube','https://youtube.com/@NextPathSystem','<rect x="2" y="5" width="20" height="14" rx="4"/><path d="m10 9 5 3-5 3z" fill="currentColor"/>']
];
var PICTO = {
  'Vidéo':'<rect x="2" y="5" width="20" height="14" rx="4"/><path d="m10 9 5 3-5 3z" fill="currentColor"/>',
  'Article':'<path d="M6 3h9l4 4v14H6z"/><path d="M14 3v5h5M9 13h7M9 17h7"/>',
  'Cours':'<path d="M2 9l10-5 10 5-10 5z"/><path d="M6 11v5c3 2 9 2 12 0v-5"/>',
  'Livre':'<path d="M4 4h6a3 3 0 0 1 3 3v13a2 2 0 0 0-2-2H4z"/><path d="M20 4h-6a3 3 0 0 0-3 3"/><path d="M20 4v14h-7"/>',
  'NextPath':'<circle cx="12" cy="12" r="9"/><path d="m15 9-2 4-4 2 2-4z" fill="currentColor"/>'
};
function svgPicto(t, taille){ return '<svg viewBox="0 0 24 24" width="' + taille + '" height="' + taille + '" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">' + (PICTO[t] || PICTO['Article']) + '</svg>'; }
function idYoutube(u){ var m = String(u).match(/(?:youtu\.be\/|[?&]v=|\/shorts\/|\/embed\/)([\w-]{11})/); return m ? m[1] : ''; }
function carteRessource(r){
  var yt = idYoutube(r.lien), img = r.image || (yt ? 'https://i.ytimg.com/vi/' + yt + '/hqdefault.jpg' : '');
  var interne = r.lien.charAt(0) === '#';
  var visuel = img ? '<img src="' + esc(img) + '" alt="" loading="lazy">' : '<span class="r-picto">' + svgPicto(r.type, 44) + '</span>';
  return '<a class="ressource r-' + esc(plat(r.type)) + '" href="' + esc(r.lien) + '"' + (interne ? '' : ' target="_blank" rel="noopener"') + '>'
    + '<div class="r-visuel">' + visuel + (yt ? '<span class="r-play">▶</span>' : '') + (r.exemple ? '<span class="exemple">Exemple</span>' : '') + '</div>'
    + '<div class="r-corps"><span class="r-type">' + svgPicto(r.type, 14) + esc(r.type === 'NextPath' ? 'Sur NextPath' : r.type) + ' · ' + esc(r.sujet) + '</span>'
    + '<b>' + esc(r.titre) + '</b><p>' + esc(r.pourquoi) + '</p><span class="r-lien">' + (interne ? 'Lire l\'article →' : 'Voir ↗') + '</span></div></a>';
}
function carteCoeur(r, i){
  var yt = idYoutube(r.lien), img = r.image || (yt ? 'https://i.ytimg.com/vi/' + yt + '/hqdefault.jpg' : '');
  var interne = r.lien.charAt(0) === '#', t = plat(r.type);
  var visuel = img ? '<img src="' + esc(img) + '" alt="" loading="lazy">'
    : '<span class="cc-forme f1"></span><span class="cc-forme f2"></span><span class="cc-picto">' + svgPicto(r.type, 64) + '</span>';
  return '<a class="cc c-' + esc(t) + (i % 5 === 0 ? ' large' : '') + '" style="--r:' + ((i % 3) - 1) * 1.2 + 'deg" href="' + esc(r.lien) + '"' + (interne ? '' : ' target="_blank" rel="noopener"') + '>'
    + '<div class="cc-visuel">' + visuel + (yt ? '<span class="r-play">▶</span>' : '') + '</div>'
    + '<span class="cc-sticker">' + svgPicto(r.type, 14) + esc(r.type === 'NextPath' ? 'Sur NextPath' : r.type) + '</span>'
    + (r.exemple ? '<span class="cc-exemple">Exemple</span>' : '')
    + '<div class="cc-corps"><span class="cc-sujet">' + esc(r.sujet) + '</span><b>' + esc(r.titre) + '</b>'
    + '<p class="cc-note">« ' + esc(r.pourquoi) + ' »</p>'
    + '<span class="cc-lien">' + (interne ? 'Lire l\'article' : 'J\'y vais') + ' →</span></div></a>';
}
var typeBiblio = 'Tout';
var TYPES_BIBLIO = [['Tout','Tout'],['Vidéo','Vidéos'],['Article','Articles'],['Cours','Cours'],['Livre','Livres'],['NextPath','Sur NextPath']];
function renderBibliotheque(){
  var presents = TYPES_BIBLIO.filter(function(t){ return t[0] === 'Tout' || BIBLIOTHEQUE.some(function(r){ return r.type === t[0]; }); });
  $('biblio-filtres').innerHTML = presents.map(function(t){ return '<button class="cdc-filtre c-' + esc(plat(t[0])) + (t[0] === typeBiblio ? ' active' : '') + '" type="button" data-type="' + esc(t[0]) + '">' + (t[0] === 'Tout' ? '' : svgPicto(t[0], 16)) + esc(t[1]) + '</button>'; }).join('');
  var liste = typeBiblio === 'Tout' ? BIBLIOTHEQUE : BIBLIOTHEQUE.filter(function(r){ return r.type === typeBiblio; });
  $('biblio-tout').innerHTML = liste.length ? liste.map(carteCoeur).join('') : '<div class="empty-state"><div class="empty-title">Bientôt ici.</div></div>';
}
function parQui(a){ return a.auteur === 'equipe' ? 'l\'équipe NextPath' : auteurDe(a).nom; }
function renderHome(){
  var arts = tous();
  $('ah-photo').hidden = !PHOTOS.accueil;
  document.querySelector('.accueil-hero').classList.toggle('sans-photo', !PHOTOS.accueil);
  $('ah-photo').innerHTML = PHOTOS.accueil
    ? '<img src="' + esc(PHOTOS.accueil) + '" alt="">'
    : '<div class="photo-vide"><svg viewBox="0 0 24 24" width="40" height="40" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="3" y="5" width="18" height="15" rx="3"/><circle cx="9" cy="11" r="2"/><path d="m21 17-5-5-9 8"/></svg><b>Ta photo ici</b><small>Une image qui te ressemble : toi qui écris, tes livres, ton espace de travail…</small></div>';
  if (arts.length){
    var une = arts[0], cit = arts[1] || arts[0];
    $('une-duo').innerHTML =
      '<a class="tuile t-une" href="#' + esc(une.id) + '">' + coverHtml(une) + '<span class="t-voile"></span><div class="t-texte"><h2>' + esc(une.titre) + '</h2><span class="t-meta">Par ' + esc(parQui(une)) + ' · ' + esc(une.lecture) + ' de lecture</span></div></a>'
      + '<a class="tuile t-citation" href="#' + esc(cit.id) + '"><span class="guillemet">“</span><blockquote>' + esc(cit.chapo || cit.extrait) + '</blockquote><span class="t-source">Extrait · ' + esc(cit.titre) + ' →</span></a>';
  } else $('une-duo').innerHTML = '<div class="empty-state"><div class="empty-title">Le premier article arrive bientôt.</div></div>';
  $('biblio').innerHTML = BIBLIOTHEQUE.slice(0,3).map(carteRessource).join('');
  $('liste-avis').innerHTML = AVIS.map(function(v){
    return '<figure class="avis-carte"><span class="guillemet">“</span><blockquote>' + esc(v.texte) + '</blockquote><figcaption><b>' + esc(v.nom) + '</b>' + (v.contexte ? ' · ' + esc(v.contexte) : '') + '</figcaption></figure>';
  }).join('') + '<div class="avis-carte avis-appel"><b>' + (AVIS.length ? 'Et vous ?' : 'Les premiers avis arrivent bientôt.') + '</b><p>Un article vous a aidé ou fait réfléchir ? Racontez-le-nous en quelques mots.</p><a class="btn-plein" href="#contact" data-objet="Avis / témoignage">Donner mon avis</a></div>';
  $('suivre').innerHTML = '<div><span class="t-label">Suivre NextPath</span><b>Une idée par jour, en vidéo et en image.</b></div><div class="liens-r">'
    + RESEAUX.map(function(r){ return '<a href="' + r[1] + '" target="_blank" rel="noopener"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">' + r[2] + '</svg>' + r[0] + '</a>'; }).join('') + '</div>';
}

// ══ RENDU BLOG ══
var activeCat = 'Tous', recherche = '';
function plat(s){ return String(s || '').toLowerCase().normalize('NFD').replace(/[\u0300-\u036f]/g,''); }
function renderBlog(){
  var c = $('blog-categories'), arts = tous();
  if (!arts.length){ c.innerHTML = '<div class="empty-state"><div class="empty-icon">✍️</div><div class="empty-title">Aucun article pour l\'instant.</div><div class="empty-desc">Reviens très vite.</div></div>'; return; }
  var cats = ['Tous'];
  arts.forEach(function(a){ var t = a.tags[0]; if (t && cats.indexOf(t) === -1) cats.push(t); });
  var html = '<div class="cat-filter">' + cats.map(function(cat){ return '<button class="cat-btn' + (cat === activeCat ? ' active' : '') + '" type="button" data-cat="' + esc(cat) + '">' + esc(cat) + '</button>'; }).join('') + '</div>';
  var filtres = activeCat === 'Tous' ? arts : arts.filter(function(a){ return a.tags.indexOf(activeCat) !== -1; });
  var q = plat(recherche).trim();
  if (q) filtres = filtres.filter(function(a){ return plat(a.titre + ' ' + (a.chapo || a.extrait) + ' ' + a.tags.join(' ')).indexOf(q) !== -1; });
  if (!filtres.length){ c.innerHTML = html + '<div class="empty-state"><div class="empty-icon">🔎</div><div class="empty-title">Rien trouvé pour « ' + esc(recherche) + ' ».</div><div class="empty-desc">Essaie un autre mot, ou propose-nous ce sujet depuis la page Contact.</div></div>'; return; }
  var groupes = {};
  if (activeCat === 'Tous' && !q) filtres.forEach(function(a){ var k = a.tags[0] || 'Autre'; (groupes[k] = groupes[k] || []).push(a); });
  else groupes[q ? 'Résultats' : activeCat] = filtres;
  Object.keys(groupes).forEach(function(cat){
    var g = groupes[cat];
    html += '<div class="cat-section"><div class="cat-title">' + esc(cat) + ' <span class="cat-count">' + g.length + ' article' + (g.length > 1 ? 's' : '') + '</span></div><div class="articles-grid">' + g.map(buildCard).join('') + '</div></div>';
  });
  c.innerHTML = html;
}

// ══ ARTICLE ══
function openArticle(a){
  var au = auteurDe(a);
  var lien = location.href.split('#')[0] + '#' + a.id;
  var corps = (a.corps || '').replace(/\[(\d+)\]/g, function(m, k){ return '<sup><a href="#" data-cible="source-' + k + '">' + k + '</a></sup>'; });
  var maj = a.maj && a.maj !== a.date ? '<span>Mis à jour le ' + dateFr(a, 'maj') + '</span>' : '';
  $('article-full-content').innerHTML =
    '<a class="article-full-back" href="#blog">← Tous les articles</a>'
    + '<div class="article-full-tags">' + a.tags.map(function(t){ return '<span class="card-tag">' + esc(t) + '</span>'; }).join('') + '</div>'
    + '<h1>' + esc(a.titre) + '</h1>'
    + (a.chapo ? '<p class="chapo">' + esc(a.chapo) + '</p>' : '')
    + '<div class="signature"><div class="auteur-mini">' + avatar(au, 'moyen') + '<div><b>Par ' + (a.auteur === 'equipe' ? 'l\'équipe NextPath' : esc(au.nom)) + '</b><small>' + esc(au.role) + '</small></div></div>'
    + '<div class="signature-meta"><span>Publié le ' + dateFr(a) + '</span>' + maj + '<span>' + esc(a.lecture) + ' de lecture</span>'
    + (a.relu ? '<span class="relu"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Relu par ' + esc(a.relu) + '</span>' : '') + '</div></div>'
    + '<div class="article-full-img">' + couverture(a) + '</div>'
    + '<div class="article-body">' + corps + '</div>'
    + (a.sources.length ? '<div class="sources"><h3>Sources</h3><ol>' + a.sources.map(function(s, i){ return '<li id="source-' + (i + 1) + '">' + s + '</li>'; }).join('') + '</ol></div>' : '')
    + '<div class="likes-bar">'
    + '<button class="like-big' + (liked[a.id] ? ' liked' : '') + '" type="button" id="btn-like">' + (liked[a.id] ? '♥ Tu as aimé' : '♡ J\'aime cet article') + '</button>'
    + '<a class="like-big" href="https://wa.me/?text=' + encodeURIComponent(a.titre + ' ' + lien) + '" target="_blank" rel="noopener">Partager sur WhatsApp</a>'
    + '<button class="like-big" type="button" id="btn-lien">Copier le lien</button>'
    + '<span class="like-count" id="note-lien" role="status"></span>'
    + '</div>'
    + '<div class="auteur-box">' + avatar(au, 'grand') + '<div><span class="label">Qui écrit ici</span><h3>' + esc(au.nom) + '</h3><div class="role">' + esc(au.role) + '</div><p>' + esc(au.bio) + '</p>'
    + '<div class="liens"><a href="#a-propos">Notre démarche →</a>' + (au.liens || []).map(function(l){ return '<a href="' + esc(l[1]) + '" target="_blank" rel="noopener">' + esc(l[0]) + '</a>'; }).join('') + '</div></div></div>';

  $('btn-like').onclick = function(){
    liked[a.id] = !liked[a.id]; sauvegarder();
    this.className = 'like-big' + (liked[a.id] ? ' liked' : '');
    this.textContent = liked[a.id] ? '♥ Tu as aimé' : '♡ J\'aime cet article';
  };
  $('btn-lien').onclick = function(){
    var note = $('note-lien');
    try { navigator.clipboard.writeText(lien).then(function(){ note.textContent = 'Lien copié'; }, function(){ note.textContent = lien; }); } catch(e){ note.textContent = lien; }
  };
  renderComments(a.id);
  var autres = tous().filter(function(x){ return x.id !== a.id; }).sort(function(x, y){
    function sc(z){ return z.tags.filter(function(t){ return a.tags.indexOf(t) !== -1; }).length + (z.auteur === a.auteur ? .5 : 0); }
    return sc(y) - sc(x);
  });
  $('suite').innerHTML = autres.slice(0,2).map(buildCard).join('');
  document.title = a.titre + ' · NextPath Blog';
}

function renderComments(id){
  var comms = comments[id] || [];
  $('comments-wrap').innerHTML = '<hr class="comments-hr"><div class="comments-heading">Commentaires (' + comms.length + ')</div>'
    + '<form class="comment-form" id="form-com" novalidate>'
    + '<label class="sr" for="cm-prenom" style="position:absolute;left:-9999px">Ton prénom</label><input type="text" class="comment-input" id="cm-prenom" placeholder="Ton prénom">'
    + '<label for="cm-texte" style="position:absolute;left:-9999px">Ton commentaire</label><textarea class="comment-textarea" id="cm-texte" placeholder="Ton commentaire..."></textarea>'
    + '<button class="comment-btn" type="submit">Publier</button><span class="comment-ok" id="cm-ok" role="status"></span></form>'
    + comms.map(function(c){ return '<div class="comment-item"><div class="comment-author">' + esc(c.prenom) + '</div><div class="comment-date">' + esc(c.date) + '</div><div class="comment-text">' + esc(c.texte) + '</div></div>'; }).join('');
  $('form-com').onsubmit = function(e){
    e.preventDefault();
    var p = $('cm-prenom').value.trim(), t = $('cm-texte').value.trim();
    if (!p || !t){ $('cm-ok').textContent = 'Merci de remplir tous les champs.'; return; }
    (comments[id] = comments[id] || []).unshift({prenom:p, texte:t, date:new Date().toLocaleDateString('fr-FR',{day:'2-digit',month:'long',year:'numeric'})});
    sauvegarder(); renderComments(id);
  };
}

// ══ NAVIGATION (une adresse par page, par article et par auteur) ══
var PAGES = {'accueil':'home','blog':'blog','coups-de-coeur':'bibliotheque','a-propos':'about','contact':'contact'};
function router(){
  var cle = decodeURIComponent((location.hash || '#accueil').slice(1)) || 'accueil';
  var a = tous().find(function(x){ return x.id === cle; });
  if (a){ go('article'); openArticle(a); return; }
  go(PAGES[cle] || 'home');
}
function go(p){
  document.querySelectorAll('.page').forEach(function(x){ x.classList.toggle('active', x.id === 'page-' + p); });
  document.querySelectorAll('.nav-links a[data-page]').forEach(function(x){
    x.classList.toggle('active', x.dataset.page === p || (p === 'article' && x.dataset.page === 'blog'));
  });
  window.scrollTo(0,0);
  $('mobile-menu').classList.remove('open'); $('hamburger').setAttribute('aria-expanded','false');
  $('progression').style.width = '0';
  if (p === 'home'){ renderHome(); document.title = 'NextPath Blog'; }
  if (p === 'bibliotheque'){ renderBibliotheque(); document.title = 'Nos coups de cœur · NextPath Blog'; }
  if (p === 'blog'){ renderBlog(); document.title = 'Articles · NextPath Blog'; }
}
window.addEventListener('hashchange', router);
$('hamburger').onclick = function(){ var o = $('mobile-menu').classList.toggle('open'); this.setAttribute('aria-expanded', o); };
document.addEventListener('click', function(e){
  var c = e.target.closest('[data-cible]');
  if (c){ e.preventDefault(); var el = $(c.dataset.cible); if (el) el.scrollIntoView({behavior:'smooth', block:'center'}); return; }
  var ty = e.target.closest('[data-type]');
  if (ty){ typeBiblio = ty.dataset.type; renderBibliotheque(); return; }
  var o = e.target.closest('[data-objet]');
  if (o) $('c-objet').value = o.dataset.objet;
  var b = e.target.closest('[data-cat]');
  if (b){ activeCat = b.dataset.cat; recherche = ''; $('q-blog').value = ''; renderBlog(); }
  var menu = $('mobile-menu');
  if (menu.classList.contains('open') && !menu.contains(e.target) && !$('hamburger').contains(e.target)) menu.classList.remove('open');
});
window.addEventListener('scroll', function(){
  if (!$('page-article').classList.contains('active')) return;
  var t = $('article-full-content'), fin = t.offsetTop + t.offsetHeight - window.innerHeight;
  $('progression').style.width = Math.max(0, Math.min(100, window.scrollY / Math.max(1, fin) * 100)) + '%';
}, {passive:true});
$('scroll-top').onclick = function(){ window.scrollTo({top:0, behavior:'smooth'}); };

// ══ FORMULAIRES (Formspree) ══
function brancher(formId, okId, sujet, okTexte){
  $(formId).onsubmit = function(e){
    e.preventDefault();
    var form = this, ok = $(okId);
    if (!form.checkValidity()){ ok.textContent = 'Merci de remplir les champs obligatoires avec une adresse email valide.'; return; }
    var data = new FormData(form); data.append('_subject', sujet);
    ok.textContent = 'Envoi en cours…';
    fetch('https://formspree.io/f/xdaqgdyw', {method:'POST', body:data, headers:{'Accept':'application/json'}})
      .then(function(r){ if (r.ok){ form.reset(); ok.textContent = okTexte; } else ok.textContent = 'Une erreur est survenue. Réessaie ou écris directement à nextpathsystem@gmail.com'; })
      .catch(function(){ ok.textContent = 'Une erreur est survenue. Réessaie ou écris directement à nextpathsystem@gmail.com'; });
  };
}
brancher('contact-form','contact-ok','Contact NextPath Blog','✔ Message envoyé — nous vous répondrons bientôt !');

// ══ RECHERCHE ══
$('q-blog').oninput = function(){ recherche = this.value; renderBlog(); };

// ══ ÉDITEUR (taper NPADMIN) ══
$('ed-auteur').innerHTML = Object.keys(AUTEURS).map(function(id){ return '<option value="' + esc(id) + '">' + esc(AUTEURS[id].nom) + '</option>'; }).join('');
$('ed-tags-grid').innerHTML = CATEGORIES.map(function(c, i){ return '<label class="ed-tag-check"><input type="checkbox" id="ed-cat-' + i + '" value="' + esc(c) + '"> ' + esc(c) + '</label>'; }).join('');
function openEditor(){ $('ed-msg').textContent = ''; $('editor-overlay').hidden = false; document.body.style.overflow = 'hidden'; }
function closeEditor(){ $('editor-overlay').hidden = true; document.body.style.overflow = ''; }
$('ed-fermer').onclick = closeEditor; $('ed-annuler').onclick = closeEditor;
var modeInsert = null;
$('ed-toolbar').addEventListener('click', function(e){
  var b = e.target.closest('button'); if (!b) return;
  var cmd = b.dataset.cmd; $('ed-content').focus();
  if (cmd === 'quote') document.execCommand('formatBlock', false, 'blockquote');
  else if (cmd === 'h2') document.execCommand('formatBlock', false, 'h2');
  else if (cmd === 'lien' || cmd === 'image'){ modeInsert = cmd; $('ed-insert').hidden = false; $('ed-insert-texte').hidden = cmd === 'image'; $('ed-insert-url').focus(); }
  else document.execCommand(cmd, false, null);
});
$('ed-insert-ok').onclick = function(){
  var url = $('ed-insert-url').value.trim(); if (!/^https?:\/\//.test(url)) return;
  var txt = $('ed-insert-texte').value.trim() || url;
  $('ed-content').focus();
  document.execCommand('insertHTML', false, modeInsert === 'image' ? '<img src="' + esc(url) + '" alt="">' : '<a href="' + esc(url) + '" target="_blank" rel="noopener">' + esc(txt) + '</a>');
  $('ed-insert').hidden = true; $('ed-insert-url').value = ''; $('ed-insert-texte').value = '';
};
$('ed-publier').onclick = function(){
  var titre = $('ed-titre').value.trim(), corps = $('ed-content').innerHTML.trim(), texte = $('ed-content').innerText || '';
  var tags = Array.from(document.querySelectorAll('#ed-tags-grid input:checked')).map(function(cb){ return cb.value; });
  if (!titre || !texte.trim()){ $('ed-msg').textContent = 'Le titre et le contenu sont obligatoires.'; return; }
  if (!tags.length){ $('ed-msg').textContent = 'Choisis au moins une catégorie.'; return; }
  var id = slugify(titre);
  if (tous().some(function(a){ return a.id === id; })) id += '-' + Date.now().toString(36);
  var auj = new Date().toISOString().slice(0,10);
  articles.unshift({
    id:id, titre:titre, tags:tags, tag:tags[0], auteur:$('ed-auteur').value, relu:$('ed-relu').value.trim(),
    img:$('ed-img').value.trim(), chapo:$('ed-chapo').value.trim(),
    extrait:texte.substring(0,160).trim() + (texte.length > 160 ? '...' : ''),
    corps:corps, date:auj, maj:auj, lecture:Math.max(1, Math.round(texte.split(/\s+/).length / 200)) + ' min', likes:0,
    sources:$('ed-sources').value.split('\n').map(function(l){ return l.trim(); }).filter(Boolean).map(esc)
  });
  sauvegarder();
  ['ed-titre','ed-chapo','ed-img','ed-sources','ed-relu'].forEach(function(k){ $(k).value = ''; });
  $('ed-content').innerHTML = '';
  document.querySelectorAll('#ed-tags-grid input').forEach(function(cb){ cb.checked = false; });
  $('ed-msg').textContent = '✔ Article publié !';
  setTimeout(function(){ closeEditor(); location.hash = id; }, 900);
};
$('ed-exporter').onclick = function(){
  var data = JSON.stringify(articles, null, 2);
  var a = document.createElement('a');
  a.href = URL.createObjectURL(new Blob([data], {type:'application/json'}));
  a.download = 'nextpath-articles.json';
  document.body.appendChild(a); a.click(); a.remove();
  $('ed-msg').textContent = articles.length + ' article' + (articles.length > 1 ? 's' : '') + ' exporté' + (articles.length > 1 ? 's' : '') + '.';
};
var kbuf = '';
document.addEventListener('keydown', function(e){
  if (e.target.closest && e.target.closest('input,textarea,select,[contenteditable]')) return;
  kbuf = (kbuf + (e.key || '')).toUpperCase().slice(-7);
  if (kbuf === 'NPADMIN'){ openEditor(); kbuf = ''; }
});

router();
</script>
</body>
</html>
