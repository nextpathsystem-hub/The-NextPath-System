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
.nav-logo{display:flex;align-items:center;gap:10px;text-decoration:none;flex-shrink:0;}
.nav-logo img{height:36px;width:auto;}
.nav-logo span{font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--navy);}
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
.mobile-menu a{font-size:13px;font-weight:500;letter-spacing:.06em;text-transform:uppercase;color:var(--dark);text-decoration:none;padding:12px 0;border-bottom:1px solid var(--border);display:block;}
.mobile-menu a:last-of-type{border-bottom:none;}
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
.btn{display:inline-flex;align-items:center;justify-content:center;gap:8px;font-size:11px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;padding:14px 28px;border-radius:2px;text-decoration:none;transition:all .25s;border:2px solid transparent;}
.btn-navy{background:var(--navy);color:#fff;border-color:var(--navy);}
.btn-navy:hover{background:var(--gold);border-color:var(--gold);color:var(--navy);}
.btn-outline{border-color:var(--navy);color:var(--navy);}
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
.stat-col:last-child{text-align:center;}
.stat-num{font-family:'Playfair Display',serif;font-size:48px;font-weight:900;color:var(--gold);display:block;line-height:1;}
.stat-lbl{font-size:11px;color:rgba(245,240,232,0.6);letter-spacing:.08em;text-transform:uppercase;margin-top:8px;display:block;}
.section{padding:96px 80px;}
.section-alt{background:var(--light);}
.container{max-width:1140px;margin:0 auto;}
.stag{display:inline-flex;align-items:center;gap:10px;font-size:11px;font-weight:600;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);margin-bottom:16px;}
.stag::before{content:'';display:block;width:24px;height:1.5px;background:var(--gold);}
.stag-center{justify-content:center;}
.stag-center::before{display:none;}
h2.stitle{font-family:'Playfair Display',serif;font-size:clamp(26px,3.5vw,44px);font-weight:700;color:var(--navy);line-height:1.15;margin-bottom:20px;}
h2.stitle em{color:var(--gold);font-style:italic;}
h2.stitle.light{color:var(--cream);}
.sbody{font-size:15px;color:var(--mid);line-height:1.85;max-width:580px;}
.divider{width:48px;height:2px;background:var(--gold);margin:24px 0;opacity:.7;}
.pillars-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;margin-top:48px;}
.pillar-card{background:#fff;border:1px solid var(--border);border-radius:4px;padding:40px 32px;transition:all .3s;border-top:3px solid transparent;}
.pillar-card:hover{border-top-color:var(--gold);box-shadow:0 8px 32px rgba(13,27,62,.08);transform:translateY(-4px);}
.pnum{font-family:'Playfair Display',serif;font-size:52px;font-weight:900;color:var(--gold);line-height:1;margin-bottom:16px;}
.ptitle{font-family:'Playfair Display',serif;font-size:20px;font-weight:700;color:var(--navy);margin-bottom:12px;text-transform:uppercase;letter-spacing:.04em;}
.ptext{font-size:14px;color:var(--mid);line-height:1.8;}
.yt-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px;margin-top:40px;}
.yt-card{border:1px solid var(--border);border-radius:4px;overflow:hidden;transition:all .25s;text-decoration:none;display:block;background:#fff;cursor:pointer;}
.yt-card:hover{border-color:var(--gold);box-shadow:0 8px 24px rgba(13,27,62,.1);transform:translateY(-3px);}
.yt-thumb{position:relative;aspect-ratio:16/9;overflow:hidden;background:var(--navy);display:flex;align-items:center;justify-content:center;}
.yt-play{width:48px;height:48px;border-radius:50%;background:rgba(201,168,76,0.9);display:flex;align-items:center;justify-content:center;transition:transform .2s;}
.yt-card:hover .yt-play{transform:scale(1.1);}
.yt-play::after{content:'';border-style:solid;border-width:8px 0 8px 16px;border-color:transparent transparent transparent var(--navy);margin-left:3px;}
.yt-info{padding:16px;}
.yt-title{font-size:13px;font-weight:600;color:var(--dark);line-height:1.5;margin-bottom:6px;}
.yt-meta{font-size:11px;color:var(--light-text);}
.prog-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px;margin-top:40px;}
.prog-card{border:1px solid var(--border);border-radius:4px;padding:36px;transition:all .25s;position:relative;overflow:hidden;}
.prog-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:var(--gold);transform:scaleX(0);transition:transform .3s;}
.prog-card:hover{border-color:var(--gold);box-shadow:0 8px 24px rgba(13,27,62,.08);}
.prog-card:hover::before{transform:scaleX(1);}
.prog-icon{font-size:32px;margin-bottom:16px;display:block;}
.prog-name{font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--navy);margin-bottom:10px;}
.prog-desc{font-size:13px;color:var(--mid);line-height:1.7;margin-bottom:20px;}
.prog-badge{display:inline-block;font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;padding:4px 10px;border-radius:20px;background:var(--gold-bg);color:var(--gold);margin-bottom:14px;}
.module-list{display:flex;flex-direction:column;gap:16px;}
.module-item{display:flex;gap:20px;align-items:flex-start;padding:20px 24px;border:1px solid var(--border);border-radius:4px;transition:all .25s;}
.module-item:hover{border-color:var(--gold);background:var(--gold-bg);}
.mweek{font-size:10px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--gold);background:var(--gold-bg);padding:4px 10px;border-radius:20px;white-space:nowrap;flex-shrink:0;margin-top:3px;}
.module-item h4{font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:6px;}
.module-item p{font-size:13px;color:var(--mid);line-height:1.7;}
.irow{display:flex;justify-content:space-between;align-items:center;padding:14px 0;border-bottom:1px solid var(--border);font-size:14px;}
.irow:last-child{border-bottom:none;}
.irow span:first-child{color:var(--light-text);font-size:11px;letter-spacing:.08em;text-transform:uppercase;}
.irow span:last-child{color:var(--dark);font-weight:500;}
.bitem{display:flex;gap:12px;align-items:flex-start;font-size:14px;color:var(--mid);line-height:1.6;margin-bottom:10px;}
.bdot{width:20px;height:20px;border-radius:50%;background:var(--gold-bg);border:1px solid var(--gold);display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:2px;font-size:10px;color:var(--gold);}
.prog-cta{margin-top:40px;padding:32px;background:var(--navy);border-radius:4px;text-align:center;}
.prog-cta h3{font-family:'Playfair Display',serif;font-size:22px;color:var(--gold);margin-bottom:10px;}
.prog-cta p{font-size:14px;color:rgba(245,240,232,.7);margin-bottom:22px;line-height:1.7;}
.gbadge{display:inline-block;background:var(--gold);color:var(--navy);font-size:11px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;padding:4px 12px;border-radius:20px;margin-bottom:14px;}
.profiles-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;margin:48px 0;}
.profile-card{padding:28px 20px;border:1px solid var(--border);border-radius:4px;text-align:center;transition:all .25s;}
.profile-card:hover{border-color:var(--gold);background:var(--gold-bg);}
.picon{font-size:28px;margin-bottom:12px;display:block;}
.pname{font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;}
.pdesc{font-size:12px;color:var(--light-text);line-height:1.7;}
.pdf-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px;margin-top:40px;} .pdf-grid a[style*="grid-column"]{grid-column:1/-1;}
.pdf-card{border:1px solid var(--border);border-radius:4px;padding:28px 24px;display:flex;flex-direction:column;gap:12px;transition:all .25s;text-decoration:none;background:#fff;}
.pdf-card.available:hover{border-color:var(--gold);box-shadow:0 6px 20px rgba(13,27,62,.08);transform:translateY(-2px);}
.pdf-card.soon{opacity:.6;cursor:default;}
.pdf-icon{width:44px;height:44px;border-radius:8px;background:var(--navy);display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0;}
.pdf-title{font-size:14px;font-weight:600;color:var(--dark);line-height:1.4;}
.pdf-desc{font-size:12px;color:var(--light-text);line-height:1.6;}
.pdf-dl{display:inline-flex;align-items:center;gap:6px;font-size:11px;font-weight:600;letter-spacing:.08em;text-transform:uppercase;color:var(--gold);margin-top:4px;}
.avis-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;margin-bottom:56px;}
.avis-card{background:#fff;border:1px solid var(--border);border-radius:4px;padding:32px;border-top:3px solid var(--gold);}
.stars{color:var(--gold);font-size:14px;margin-bottom:14px;}
.avis-text{font-size:14px;color:var(--mid);line-height:1.8;margin-bottom:18px;font-style:italic;}
.avis-author{display:flex;align-items:center;gap:12px;}
.avis-avatar{width:38px;height:38px;border-radius:50%;background:var(--navy);display:flex;align-items:center;justify-content:center;font-family:'Playfair Display',serif;font-weight:700;color:var(--gold);font-size:13px;flex-shrink:0;}
.avis-name{font-size:13px;font-weight:600;color:var(--navy);}
.avis-loc{font-size:11px;color:var(--light-text);letter-spacing:.06em;text-transform:uppercase;}
.grace-grid{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:start;}
.grace-photo{position:relative;border-radius:4px;overflow:hidden;aspect-ratio:4/5;box-shadow:0 20px 60px rgba(13,27,62,.15);}
.grace-photo img{width:100%;height:100%;object-fit:cover;object-position:center top;}
.grace-photo::after{content:'';position:absolute;inset:0;border:3px solid var(--gold);border-radius:4px;pointer-events:none;opacity:.4;}
.quote-box{margin-top:28px;padding:22px 26px;border-left:3px solid var(--gold);background:var(--light);}
.quote-box p{font-family:'Playfair Display',serif;font-size:16px;font-style:italic;color:var(--navy);line-height:1.65;}
.slink{display:flex;align-items:center;gap:16px;padding:14px 18px;border:1px solid var(--border);border-radius:4px;text-decoration:none;transition:all .2s;color:var(--dark);margin-bottom:10px;}
.slink:hover{border-color:var(--navy);background:rgba(13,27,62,.04);}
.splat{font-size:10px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--gold);min-width:70px;}
.shandle{font-size:14px;font-weight:500;color:var(--dark);}
footer{background:var(--navy);padding:40px 80px;display:flex;justify-content:space-between;align-items:center;border-top:3px solid var(--gold);flex-wrap:wrap;gap:16px;}
.flogo{font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--gold);}
.flinks{display:flex;gap:20px;flex-wrap:wrap;}
.flinks a{font-size:11px;color:rgba(245,240,232,.5);text-decoration:none;letter-spacing:.06em;transition:color .2s;}
.flinks a:hover{color:var(--gold);}
.fcopy{font-size:11px;color:rgba(245,240,232,.3);letter-spacing:.06em;}
@media(max-width:768px){
  nav{padding:0 20px;}
  .nav-links{display:none;}
  .hamburger{display:flex;}
  .hero{grid-template-columns:1fr;min-height:auto;}
  .hero-left{padding:40px 24px;}
  .hero-right{min-height:200px;padding:40px 24px;}
  .hero-right-content h2{font-size:20px;}
  .stats-strip{padding:40px 24px;}
  .stats-inner{flex-direction:column;gap:28px;padding:0;}
  .stat-col{border-right:none;border-bottom:1px solid rgba(201,168,76,.2);padding:0 0 24px;text-align:center;}
  .stat-col:last-child{border-bottom:none;padding-bottom:0;}
  .section{padding:56px 24px;}
  .pillars-grid,.prog-grid,.yt-grid,.pdf-grid,.avis-grid{grid-template-columns:1fr;}
  .profiles-grid{grid-template-columns:1fr 1fr;}
  .grace-grid{grid-template-columns:1fr;gap:32px;}
  footer{padding:32px 24px;flex-direction:column;text-align:center;}
  .flinks{justify-content:center;}
  .hero-actions{flex-direction:column;}
  .btn{width:100%;justify-content:center;}
}

/* ADMIN PANEL */
#admin-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.85);z-index:9999;overflow-y:auto;}
#admin-panel{background:#fff;max-width:760px;margin:40px auto;border-radius:8px;padding:40px;}
#admin-panel h2{font-family:Georgia,serif;font-size:24px;color:#0D1B3E;margin-bottom:8px;}
#admin-panel p{font-size:13px;color:#666;margin-bottom:24px;}
.admin-section{background:#f8f8f8;border-radius:6px;padding:20px;margin-bottom:20px;border-left:4px solid #C9A84C;}
.admin-section h3{font-size:14px;font-weight:700;color:#0D1B3E;margin-bottom:12px;text-transform:uppercase;letter-spacing:.05em;}
.admin-row{display:flex;align-items:center;gap:10px;margin-bottom:10px;}
.admin-row label{font-size:12px;font-weight:600;color:#555;min-width:120px;}
.admin-row input{flex:1;padding:8px 12px;border:1px solid #ddd;border-radius:4px;font-size:13px;font-family:inherit;}
.admin-btn{background:#0D1B3E;color:#fff;border:none;padding:10px 24px;border-radius:4px;font-size:12px;font-weight:600;letter-spacing:.08em;text-transform:uppercase;cursor:pointer;margin-top:8px;}
.admin-btn:hover{background:#C9A84C;color:#0D1B3E;}
.admin-close{background:#eee;color:#333;border:none;padding:8px 18px;border-radius:4px;font-size:12px;cursor:pointer;float:right;margin-bottom:16px;}
</style>
</head>
<body>

<nav>
  <a href="#" class="nav-logo" onclick="go('home')">
    <img src="data:image/png;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gHYSUNDX1BST0ZJTEUAAQEAAAHIAAAAAAQwAABtbnRyUkdCIFhZWiAH4AABAAEAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAACRyWFlaAAABFAAAABRnWFlaAAABKAAAABRiWFlaAAABPAAAABR3dHB0AAABUAAAABRyVFJDAAABZAAAAChnVFJDAAABZAAAAChiVFJDAAABZAAAAChjcHJ0AAABjAAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAAgAAAAcAHMAUgBHAEJYWVogAAAAAAAAb6IAADj1AAADkFhZWiAAAAAAAABimQAAt4UAABjaWFlaIAAAAAAAACSgAAAPhAAAts9YWVogAAAAAAAA9tYAAQAAAADTLXBhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABtbHVjAAAAAAAAAAEAAAAMZW5VUwAAACAAAAAcAEcAbwBvAGcAbABlACAASQBuAGMALgAgADIAMAAxADb/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAQABAADASIAAhEBAxEB/8QAHQABAAICAwEBAAAAAAAAAAAAAAEIBgcCBQkDBP/EAGEQAQABAwMBBQIHBw8FCwsFAQABAgMEBQYRBwgSITFBUWETFCJxgZHRMkJSYpOhsRUWIzNVcnWCkpSisrPB0hckN0PwGCc2RVNWY3N0hMImNDU4RlRllaPT4QklREdkg//EABoBAQEAAwEBAAAAAAAAAAAAAAABAgMEBQb/xAA9EQEAAgECAQkFBgUEAQUAAAAAAQIDBBESBRMhMUFRU2GRFCIycYEVQqHB0eEzQ1Kx8CNUYnLCBiQ0NYL/2gAMAwEAAhEDEQA/ALlgCAAAAAAAAAAAAgAAAAAAAAAKACAAAAAAAAAAAAAAAAoAAAIAAACgAAAgAKAAAAAAACAAoAAAAAAAAAAAAAAAAAIACgAAAAAgAAAKAAACAAAAAAoAAAIACgAgAKAAACAAoAAAAAAAAAAAIAAACgAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKACAAAAAAoAAAIACgAAAAAAAAAAAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKACAAoAAAIAAAAAAAAAAAAAAAAAAAAAAACgAAAAAAAgAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAIAAAAAAAAACgAAAAAAAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKAAACAAoAAAIAAAAACgAAAgAAAAAAAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAAAIAAAAAAAAAAAAAAAAACgAgAAAAAAAAAAAAAAAAAAAAAAAKAAACAAoAIAAACgAgAAAAAKACAAoAIAAAAAAACgAgAAAAAKAAACAAoAIAAAAAAAAAAAAAAAAAAAAAAAAAAACgAAAAAgAAAAAAAKACAAAAAAAAoAIACgAgAAAAAAAAAAAAAAAAAAAAAKAAAAAAACAAAAAAAAAAAAqEgAAAAAABIAAAAAAAAAgAKAAAAAAAAAAACAAAAoAAAAAIAAACgAAAAAgAAAAAAAAAAAAAKEgAAAAIAAAAAAACgAAAAAAAgAAAAAKACAAAAAAAAAAAAoAAAAAAAIAAAAAAAAAAAAAChAABAAAIAAACgAgAAAAAKAAAAAAB6gAAAAgAAAAAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACgAgAAAKACAAAAAAAAAAAAAAAAoAAAAAIAAACgAgAAAAAKj0SAAAAAITwAbgAbgAAAgAAAAAKACAAoAIAAAAAAAAAAAAAAAAAAAAACgAAAgAAAAAAAAAAAAAAAKACAAAAAAAAAAAAAAAAoAIAAACgAgAAAAAAAAAAAAAAAKACAAAAAAoAIAAAAAAAAACoSIFSAIACAAoAAAIAAAAAAACgAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKAAAAAAAAACAAAAAAAAAAAAAAoAAAIAAACgAAAgAAAAAKAAiUgAAAAAAAAIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACgAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKACAAAAoAAAIAAAAAAAAAAAAACgAAAAAAAAAAAgAKACAAoABIAAAAAgAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAAAIAAAAAAAAAAAAAAACgAAAAAgAAAAAAAAAAAAAKACAAAAoHqAACAAAAAAAAAAAAAAoAIACgAAAAAgAKACAAAAoAAAAAIAAACgAgAAAAAAAAAAAAAKAAAAACAAAAAAoAIAAAAAAAAAAAAAAAAAAAAACgAgAAAKAAAAACAAAAAAAAAAAAoAIAAACgAAAgAAAAAAAAAAAAAKAAACAAoAIAAAAAAAAACgAgAKAAAAAAACAAAAoAIACgAgAAAKAAAAACAAAAoAIACgAgAAAAAAAKACAAAAoAIAAACgAgAKAAAAAAACAAAAoAIAAAAAAACgAgAB6gCgAgAAAAAAAAAAAKAAAAACAAAAoAAAIAAAAAAAAAcCgAAAAAgAAAAAKACAAAAAAoAAAKAAACAAAAAAgAKACAAoAIAAAAAAAAAAAAACgAAcgbAAAAAAgAAAAAAAKACAAAAAAAAAAAAAAoAIAAAAAAAAAAACgAgAAAAAAAKACAAAAoAIACgAgAKACAAAAAAAAAAAAAAoAAAAAAAAAAAAAAAAAAAIAAACgAgAAAAAAAAAKACAAAAqEgAAAAAAIAAAAAAAAAAAAAAAAACgAgAKAAACAAAAAAAAAAAAoAAAAAAAIAAAAACgAgAAAKACAAAAAAAAAAAAAAAAoAAAAAAAAAAAAAAABAAoAIAAAAAAACAAAAAAAAAAAAAAAAAAAAoAIAAAAAAAAACgAgAAAAAKA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AAAAAAAAAAAAoAIAAACgAAAgAAAAAAAAAAAKAAAAACAAAAAAAAAAAAAAoAAAAAAAAAAAAAAAAAIAAAAAAACgAbAAAAoAAAIAAAAACAAAAAAoAIAAAAAAAAAAAAAAAAAAAAACgAgAAAAAAAAAAAAAAAAAKAAACAAAAAAAAAAAAoAAAIAAAAAAAAAAAAACgAgAAAKACAAAAAAAAAAAAAAAAAAAAAAoAAAAAAAIAAAAAAAAAAACgAgAAAAAAAAAAAKACAAAAAAAAoAIAAAAAAAAAAAAAAACgAAAAAgAAAAAAAAAAAAAAAKACAAAIkVIiEgACAAoAIACgAAAAAAAgAAAAAAAAAAAAAAAAAAAAAKACAAAAoAIAAAAAAAAAAAAAAAAAAAAAAACgAgAAAAAAAAAAAAAAAAAAAAAAAAAKAAAAACAAAAAAAAAAAAoAIAAAAAAACkAAACAAAAoAAAAAIACgAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKAAACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAIACgAAAgAAAAAAAAAAAAAAAAAAAAAAAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAAAIAAAAAAAAAAAAAAAAACgAgAAAAAAAAAAAAAAAKACAAoAAAIAAAAAAAAAAAAAAACgAAAgAKAAACAAAAoAAAIAAACgAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAIACgAAAAAgAKACAAAAAAAAAAAAoAIAAAAAAAAACgAAAgAAAAAAAAAAAAAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACgAAAAAgAAAAAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAAAIAAAAAAAAAAAAAAAAAAAAACgAAAAAAAgAAAAAAAAAAAAAAAAAAAAAAAAAKACAAoAAAAAAAAAIACgAgAAAAAAAKACAAAAAAAAAAAAAAAAoAIAAAAAAAAAAAAAAAAACgAAAAAAAAAgAKAAAAAAAAAAAAACAAoAAAAAAAIACgAAAAAgAAAKACAAAAAAAAAAoAIAAACgAgAKACAAoAAAIAAAAAAAAAAAAAAAAAAAAAAAAAAACgAgAAAAAKACAAAAAAAAoAIAAACgAgAAAAAAAAAAAKAAAAACAAoAIAAACgAgAAAAAAAAAAAAAAAAAAAAAAAAAAAKACAAoAAAIACgAAAAAgAKACAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoAIAAAAAAAAACgAgAAAAAAAKAAACAAoAIAAACgAAAAAAAgAAAAAAAAAAAAAAAAAAAKAAACAAAAAAAAAAAAAAAAoAIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACgAgAAAKAAAAACAAoAAAIAAAAAAAAAAAAAAACgAAAAAAAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAKAAAAAAAAAAACAAoAAAIACgAAAAAAAAAAAAAAAAAAAgAAAKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAoAD//2Q==" alt="NextPath System">
    <span>NextPath System</span>
  </a>
  <ul class="nav-links">
    <li><a href="#" onclick="go('home')">Accueil</a></li>
    <li><a href="#" onclick="go('mission')">Notre mission</a></li>
    <li><a href="#" onclick="go('programmes')">Devenir membre</a></li>
    <li><a href="#" onclick="go('ressources')">Nos ressources</a></li>
    <li><a href="#" onclick="go('avis')">Avis</a></li>
    <li><a href="#" onclick="go('opportunites')">Opportunit&#233;s</a></li>
    <li><a href="#" onclick="go('grace')">&#192; propos</a></li>
    <li><a href="#" onclick="go('contact')">Contact</a></li>
    <li><a href="https://tally.so/r/81Jey5" target="_blank" class="nav-cta">Rejoindre</a></li>
    <li><div class="lang-switcher"><button class="lang-btn active" id="btn-fr" onclick="setLang('fr')">FR</button><button class="lang-btn" id="btn-en" onclick="setLang('en')">EN</button></div></li>
  </ul>
  <button class="hamburger" onclick="toggleMenu()"><span></span><span></span><span></span></button>
</nav>

<div class="mobile-menu" id="mobile-menu">
  <a href="#" onclick="go('home');toggleMenu()">Accueil</a>
  <a href="#" onclick="go('mission');toggleMenu()">Notre mission</a>
  <a href="#" onclick="go('programmes');toggleMenu()">Devenir membre</a>
  <a href="#" onclick="go('ressources');toggleMenu()">Nos ressources</a>
  <a href="#" onclick="go('avis');toggleMenu()">Avis</a>
  <a href="#" onclick="go('opportunites');toggleMenu()">Opportunit&#233;s</a>
  <a href="#" onclick="go('grace');toggleMenu()">À propos</a>
  <a href="#" onclick="go('contact');toggleMenu()">Contact</a>
  <a href="https://tally.so/r/81Jey5" target="_blank" style="color:var(--gold);font-weight:700;">Rejoindre</a>
  <div style="display:flex;gap:8px;padding:12px 0;"><button class="lang-btn active" onclick="setLang('fr')">FR</button><button class="lang-btn" onclick="setLang('en')">EN</button></div>
</div>

<!-- ══ ACCUEIL ══ -->
<div class="page active" id="page-home">
  <div class="hero">
    <div class="hero-left">
      <div class="hero-tag">NextPath System · POUR LA Jeunesse Africaine</div>
      <h1 id="h1-hero">Tu as plus de valeur<br>que tu ne <em>le crois.</em></h1>
      <p class="hero-sub" id="p-hero">Une plateforme dédiée à la jeunesse africaine — 15 à 30 ans — pour se connaître, explorer son potentiel et construire un chemin qui lui ressemble vraiment.</p>
      <div class="hero-actions">
        <a href="https://tally.so/r/ZjGJQB" target="_blank" class="btn btn-navy" id="btn-hero1">Rejoindre The Grace Effect</a>
        <a href="#" onclick="go('programmes')" class="btn btn-outline" id="btn-hero2">Devenir membre</a>
      </div>
      <div class="hero-quote">
        <p id="quote-hero">"Un jeune qui se connaît ne se perd jamais."</p>
        <cite>— Grace Kabondo, Fondatrice</cite>
      </div>
    </div>
    <div class="hero-right">
      <div class="hero-right-content">
        <div class="line"></div>
        <h2 id="h2-hero-right">Devenir la référence<br>de la jeunesse africaine</h2>
        <div class="line"></div>
      </div>
    </div>
  </div>

  <div class="stats-strip">
    <div class="stats-inner">
      <div class="stat-col">
        <span class="stat-num">300+</span>
        <span class="stat-lbl" id="stat1">Jeunes dans la communaut&eacute;</span>
      </div>
      <div class="stat-col">
        <span class="stat-num">15&ndash;30</span>
        <span class="stat-lbl" id="stat2">tranche d&rsquo;âge prioritaire</span>
      </div>
      <div class="stat-col">
        <span class="stat-num">2</span>
        <span class="stat-lbl" id="stat3">programmes en cours de cr&eacuteation;</span>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="container">
      <div style="text-align:center;margin-bottom:56px;">
        <div class="stag stag-center" id="tag-cycle">Notre approche</div>
        <h2 class="stitle" style="text-align:center;" id="h2-cycle">Le Cycle NextPath</h2>
        <p class="sbody" style="margin:0 auto;text-align:center;" id="p-cycle">Trois étapes concrètes pour transformer la découverte de soi en chemin d&rsquo;action.</p>
      </div>
      <div class="pillars-grid">
        <div class="pillar-card"><div class="pnum">01</div><div class="ptitle" id="p1-title">Connais-toi</div><p class="ptext" id="p1-text">Découvre ta personnalité, tes forces naturelles et tes valeurs profondes. Ce que tu es naturellement — pas ce qu&rsquo;on t&rsquo;a dit d&rsquo;être.</p></div>
        <div class="pillar-card"><div class="pnum">02</div><div class="ptitle" id="p2-title">Libère-toi</div><p class="ptext" id="p2-text">Identifie ce qui te bloque — pression familiale, peur du jugement, croyances limitantes. Comprendre le frein, c&rsquo;est déjà commencer à le dépasser.</p></div>
        <div class="pillar-card"><div class="pnum">03</div><div class="ptitle" id="p3-title">Construis-toi</div><p class="ptext" id="p3-text">Passe à l&rsquo;action avec des outils concrets et une communauté qui avance avec toi. Pas juste de l&rsquo;inspiration — des résultats réels.</p></div>
      </div>
      <div style="text-align:center;margin-top:48px;"><a href="#" onclick="go('mission')" class="btn btn-outline" id="btn-mission">En savoir plus sur notre mission</a></div>
    </div>
  </div>

</div>

<!-- ══ MISSION ══ -->
<div class="page" id="page-mission">
  <div class="section" style="padding-top:80px;">
    <div class="container">

      <div class="stag" id="tag-mission">Notre mission</div>
      <h2 class="stitle" id="h2-mission">NextPath System est n&eacute; d&rsquo;une <em>observation.</em></h2>
      <div class="divider"></div>

      <div style="max-width:760px;margin:0 auto;">

        <p style="font-size:17px;color:var(--dark);line-height:1.9;margin-bottom:24px;">
          J&rsquo;ai longtemps regard&eacute; la jeunesse &mdash; ma g&eacute;n&eacute;ration &mdash; se perdre dans ce que j&rsquo;appelle la <strong>m&eacute;diocrit&eacute;</strong>.
        </p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">
          Le terme est cru. Mais laisse-moi t&rsquo;expliquer.
        </p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">
          On observe une jeunesse qui crie partout son droit d&rsquo;exister, son droit d&rsquo;&ecirc;tre entendue, son droit qu&rsquo;on lui donne une chance. Mais en observant de plus pr&egrave;s, je me suis pos&eacute; une question fondamentale&nbsp;:
        </p>

        <div style="background:var(--navy);border-left:4px solid var(--gold);padding:28px 32px;border-radius:4px;margin:32px 0;">
          <p style="font-family:Georgia,serif;font-size:20px;color:var(--gold);font-style:italic;line-height:1.7;margin:0;" id="p-mission">
            &laquo;&nbsp;Qu&rsquo;est-ce qu&rsquo;elle a r&eacute;ellement &agrave; offrir&nbsp;?&nbsp;&raquo;
          </p>
        </div>

        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">
          J&rsquo;ai interrog&eacute; des dizaines de jeunes &mdash; parfois informellement, avec des questions simples comme <em>&laquo;&nbsp;Comment tu te vois dans quelques ann&eacute;es&nbsp;?&nbsp;&raquo;</em>, <em>&laquo;&nbsp;Tu crois qu&rsquo;en tant qu&rsquo;Africain tu peux cr&eacute;er et innover&nbsp;?&nbsp;&raquo;</em>
        </p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">
          Les r&eacute;ponses m&rsquo;ont beaucoup appris. Et pour beaucoup, &ecirc;tre Africain &eacute;tait per&ccedil;u comme un frein &agrave; l&rsquo;impact mondial.
        </p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:32px;">
          Sans chercher &agrave; critiquer, j&rsquo;en suis arriv&eacute;e &agrave; une conclusion claire&nbsp;: <strong style="color:var(--dark);">le probl&egrave;me de la jeunesse africaine n&rsquo;est pas seulement le manque de ressources. C&rsquo;est le manque de connaissance de ce qu&rsquo;elle poss&egrave;de d&eacute;j&agrave; &agrave; l&rsquo;int&eacute;rieur d&rsquo;elle-m&ecirc;me.</strong>
        </p>

        <div style="border-top:1px solid var(--border);margin:32px 0;"></div>

        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">
          Moi-m&ecirc;me, je suis pass&eacute;e par des moments de doute profond. Des moments o&ugrave; je me sentais d&eacute;favoris&eacute;e. Pas assez l&eacute;gitime. Pas &agrave; la hauteur des d&eacute;fis qui se pr&eacute;sentaient &agrave; moi.
        </p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:20px;">
          Il a fallu que mon syst&egrave;me de pens&eacute;e change compl&egrave;tement pour que je commence &agrave; croire que je pouvais <strong style="color:var(--dark);">&ecirc;tre celle qu&rsquo;il fallait.</strong>
        </p>
        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:32px;">
          Et apr&egrave;s avoir travers&eacute; ce blocage, j&rsquo;ai voulu en sortir les autres. Parce qu&rsquo;au fond &mdash;
        </p>

        <div style="background:var(--light);border-left:4px solid var(--gold);padding:24px 28px;border-radius:4px;margin:0 0 40px;">
          <p style="font-family:Georgia,serif;font-size:18px;color:var(--navy);font-style:italic;line-height:1.7;margin:0;">
            &laquo;&nbsp;L&rsquo;aide de l&rsquo;Homme, c&rsquo;est l&rsquo;Homme.&nbsp;&raquo;
          </p>
        </div>

        <p style="font-size:15px;color:var(--mid);line-height:1.9;margin-bottom:40px;">
          C&rsquo;est de l&agrave; qu&rsquo;est n&eacute; <strong style="color:var(--dark);">Le Syst&egrave;me NextPath</strong> &mdash; un syst&egrave;me de pens&eacute;e con&ccedil;u pour te repositionner et te rappeler que tu vaux infiniment plus que ce que tu crois.
        </p>

      </div>

      <div style="max-width:760px;margin:0 auto 56px;">
        <p style="font-size:13px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--gold);text-align:center;margin-bottom:28px;">En acceptant de traverser ces 3 &eacute;tapes</p>
        <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:20px;">
          <div style="padding:32px 24px;background:var(--navy);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
            <div style="font-size:28px;font-weight:700;color:var(--gold);font-family:Georgia,serif;margin-bottom:8px;">01</div>
            <div style="font-size:16px;font-weight:700;color:white;margin-bottom:10px;" id="m1-title">Connais-toi</div>
            <p style="font-size:13px;color:rgba(245,240,232,.7);line-height:1.7;margin:0;" id="m1-text">D&eacute;couvre ta personnalit&eacute;, tes forces naturelles et tes valeurs profondes.</p>
          </div>
          <div style="padding:32px 24px;background:var(--gold);border-radius:4px;border-top:3px solid var(--navy);text-align:center;">
            <div style="font-size:28px;font-weight:700;color:var(--navy);font-family:Georgia,serif;margin-bottom:8px;">02</div>
            <div style="font-size:16px;font-weight:700;color:var(--navy);margin-bottom:10px;" id="m2-title">Lib&egrave;re-toi</div>
            <p style="font-size:13px;color:var(--navy);line-height:1.7;margin:0;opacity:.8;" id="m2-text">Identifie ce qui te bloque &mdash; croyances limitantes, peur du regard, pression ext&eacute;rieure.</p>
          </div>
          <div style="padding:32px 24px;background:var(--navy);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
            <div style="font-size:28px;font-weight:700;color:var(--gold);font-family:Georgia,serif;margin-bottom:8px;">03</div>
            <div style="font-size:16px;font-weight:700;color:white;margin-bottom:10px;" id="m3-title">Construis-toi</div>
            <p style="font-size:13px;color:rgba(245,240,232,.7);line-height:1.7;margin:0;" id="m3-text">Passe &agrave; l&rsquo;action avec des outils concrets et une communaut&eacute; qui avance avec toi.</p>
          </div>
        </div>
      </div>

      <div style="text-align:center;max-width:600px;margin:0 auto;">
        <p style="font-size:17px;font-family:Georgia,serif;color:var(--navy);line-height:1.8;margin-bottom:8px;">
          Tu d&eacute;bloques le potentiel qui est d&eacute;j&agrave; en toi &mdash; celui qui te permettra de devenir celui ou celle qu&rsquo;il faut.
        </p>
        <p style="font-size:15px;color:var(--mid);margin-bottom:32px;">
          Cette jeunesse &mdash; nous avons d&eacute;cid&eacute; de la construire ensemble. Et nous y arriverons.
        </p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold">Rejoindre le syst&egrave;me</a>
      </div>

    </div>
  </div>
</div>

<!-- ══ PROGRAMMES ══ -->
<div class="page" id="page-programmes">
  <div class="section" style="padding-top:80px;">
    <div class="container">

      <div class="stag" id="tag-prog">Rejoins le mouvement</div>
      <h2 class="stitle" id="h2-prog">Devenir <em>membre</em> de la communauté</h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:56px;" id="p-prog">NextPath System c’est plus qu’une page Instagram. C’est une communauté de jeunes africains de 15 à 30 ans qui avancent ensemble. Rejoins-nous — c’est gratuit.</p>

      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:20px;margin-bottom:56px;">
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">&#127897;&#65039;</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;" id="av1-title">Lives & webinaires</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;" id="av1-text">Accès aux sessions exclusives et événements en ligne de la communauté NextPath.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">&#128172;</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;" id="av2-title">Groupe WhatsApp</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;" id="av2-text">Intègre le groupe privé NextPath pour échanger avec Grace et les autres membres.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">&#128218;</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;" id="av3-title">Ressources NextPath</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;" id="av3-text">Accès en priorité aux guides, outils et contenus exclusifs de NextPath System.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">&#127919;</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;" id="av4-title">Opportunités</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;" id="av4-text">Accès aux offres de stages, missions et mentorats via NextPath Opportunities.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">&#127775;</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;" id="av5-title">Priorité aux programmes</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;" id="av5-text">Tu seras prioritaire pour rejoindre les prochains programmes d’accompagnement NextPath.</p>
        </div>
        <div style="padding:32px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);text-align:center;">
          <div style="font-size:32px;margin-bottom:14px;">&#127758;</div>
          <div style="font-family:Georgia,serif;font-size:16px;font-weight:700;color:var(--navy);margin-bottom:8px;" id="av6-title">Communauté RDC & diaspora</div>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;" id="av6-text">Rejoins des jeunes africains engagés qui partagent les mêmes ambitions que toi.</p>
        </div>
      </div>

      <div style="background:var(--navy);border-radius:4px;padding:64px;text-align:center;margin-bottom:56px;">
        <div style="font-size:40px;margin-bottom:16px;">&#127757;</div>
        <h3 style="font-family:Georgia,serif;font-size:30px;color:var(--gold);margin-bottom:12px;" id="h3-membre-cta">Rejoins la communauté NextPath</h3>
        <p style="font-size:15px;color:rgba(245,240,232,0.7);max-width:520px;margin:0 auto 32px;line-height:1.8;" id="p-membre-cta">Tu t’inscris en 2 minutes. Tu seras contact&eacute;(e) sur WhatsApp pour &ecirc;tre accueilli(e) personnellement.</p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold" style="font-size:13px;padding:16px 48px;" id="btn-membre-cta">Devenir membre — Gratuit</a>
        <p style="font-size:11px;color:rgba(245,240,232,0.4);margin-top:16px;" id="p-gratuit-cta">100% gratuit · Sans engagement · Accessible depuis la RDC et la diaspora</p>
      </div>

      <div style="background:var(--light-bg);border-radius:4px;padding:48px;display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:center;">
        <div>
          <div class="stag" id="tag-test">Outil</div>
          <h3 class="stitle" style="font-size:30px;" id="h3-test">Le <em>NextPath Test</em></h3>
          <div class="divider"></div>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:24px;" id="p-test">13 questions. 5 minutes. Un portrait complet de qui tu es — ta personnalité, tes forces naturelles et les directions qui te correspondent vraiment.</p>
          <div class="bitem"><div class="bdot">&#x2726;</div><span id="tb1">Profil de personnalité parmi 4 types NextPath</span></div>
          <div class="bitem"><div class="bdot">&#x2726;</div><span id="tb2">Tes forces naturelles identifiées</span></div>
          <div class="bitem"><div class="bdot">&#x2726;</div><span id="tb3">Les directions qui te correspondent</span></div>
          <div class="bitem"><div class="bdot">&#x2726;</div><span id="tb4">Gratuit · Sans inscription</span></div>
        </div>
        <div style="background:#fff;border-radius:4px;padding:40px;text-align:center;border:1px solid var(--border);">
          <div class="profiles-grid" style="margin:0 0 28px;">
            <div class="profile-card"><span class="picon">&#129504;</span><div class="pname" style="font-size:13px;">L’Éclaireur</div></div>
            <div class="profile-card"><span class="picon">&#127760;</span><div class="pname" style="font-size:13px;">Le Connecteur</div></div>
            <div class="profile-card"><span class="picon">&#127959;&#65039;</span><div class="pname" style="font-size:13px;">Le Bâtisseur</div></div>
            <div class="profile-card"><span class="picon">&#127807;</span><div class="pname" style="font-size:13px;">Le Semeur</div></div>
          </div>
          <a href="https://docs.google.com/forms/d/e/1FAIpQLSdvA440a9h65ZcFT4XXJUoPJBelQbqrmUgU27X1pDnX6I-XkQ/viewform?usp=header" target="_blank" class="btn btn-navy" style="width:100%;justify-content:center;" id="btn-test-cta">Passer le NextPath Test — Gratuit</a>
        </div>
      </div>

    </div>
  </div>
</div>

<!-- ══ NOS RESSOURCES ══ -->
<div class="page" id="page-ressources">
  <div class="section" style="padding-top:80px;">
    <div class="container">

      <!-- TITRE -->
      <div class="stag" id="tag-res">Nos ressources</div>
      <h2 class="stitle" id="h2-res">Vidéos &amp; <em>guides</em></h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:56px;" id="p-res">Retrouve ici toutes nos vidéos YouTube et nos guides PDF — des contenus concrets pour te connaître, te libérer et construire ton chemin.</p>

      <!-- SECTION GUIDES PDF -->
      <div style="margin-bottom:64px;">
        <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:8px;flex-wrap:wrap;gap:12px;">
          <h3 style="font-family:Georgia,serif;font-size:26px;font-weight:700;color:var(--navy);" id="h3-pdf">Guides &amp; outils PDF</h3>
          <span style="font-size:12px;color:var(--gold);font-weight:600;">T&eacute;l&eacute;chargement direct</span>
        </div>
        <p style="font-size:13px;color:var(--light-text);margin-bottom:28px;">S&eacute;rie 1 &mdash; &Eacute;veil &amp; D&eacute;couverte de soi</p>
        <div class="pdf-grid" id="pdf-grid">

          <a href="https://drive.google.com/uc?export=download&id=VOTRE_ID_MODULE0" target="_blank" class="pdf-card available" style="text-decoration:none;">
            <div class="pdf-icon">&#128218;</div>
            <div>
              <div style="font-size:9px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:#C9A84C;margin-bottom:4px;">Guide de d&eacute;marrage</div>
              <div class="pdf-title">Bienvenue dans NextPath</div>
              <div class="pdf-desc">Comprends le parcours, pose les bases et &eacute;cris ta lettre de d&eacute;part.</div>
              <div class="pdf-dl">&#11015;&#65039; T&eacute;l&eacute;charger</div>
            </div>
          </a>

          <a href="https://drive.google.com/uc?export=download&id=VOTRE_ID_MODULE1" target="_blank" class="pdf-card available" style="text-decoration:none;">
            <div class="pdf-icon">&#129504;</div>
            <div>
              <div style="font-size:9px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:#C9A84C;margin-bottom:4px;">Module 1</div>
              <div class="pdf-title">Connais-toi</div>
              <div class="pdf-desc">Profil de personnalit&eacute;, forces naturelles, valeurs fondamentales. Exercices &eacute;crits complets.</div>
              <div class="pdf-dl">&#11015;&#65039; T&eacute;l&eacute;charger</div>
            </div>
          </a>

          <a href="https://drive.google.com/uc?export=download&id=VOTRE_ID_MODULE2" target="_blank" class="pdf-card available" style="text-decoration:none;">
            <div class="pdf-icon">&#128275;</div>
            <div>
              <div style="font-size:9px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:#C9A84C;margin-bottom:4px;">Module 2</div>
              <div class="pdf-title">Lib&egrave;re-toi</div>
              <div class="pdf-desc">Les 5 blocages les plus courants, lettre &agrave; ton blocage, plan de lib&eacute;ration concret.</div>
              <div class="pdf-dl">&#11015;&#65039; T&eacute;l&eacute;charger</div>
            </div>
          </a>

          <a href="https://drive.google.com/uc?export=download&id=VOTRE_ID_MODULE3" target="_blank" class="pdf-card available" style="text-decoration:none;">
            <div class="pdf-icon">&#127959;&#65039;</div>
            <div>
              <div style="font-size:9px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:#C9A84C;margin-bottom:4px;">Module 3</div>
              <div class="pdf-title">Construis-toi</div>
              <div class="pdf-desc">M&eacute;thode des 3 cercles, tes 3 chemins possibles, orientation post-dipl&ocirc;me, plan 90 jours.</div>
              <div class="pdf-dl">&#11015;&#65039; T&eacute;l&eacute;charger</div>
            </div>
          </a>

        </div>
      </div>

      <!-- SEPARATEUR -->
      <div style="border-top:1px solid var(--border);margin-bottom:64px;"></div>

      <!-- SECTION VIDÉOS -->
      <div style="margin-bottom:64px;">
        <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:28px;flex-wrap:wrap;gap:12px;">
          <h3 style="font-family:Georgia,serif;font-size:26px;font-weight:700;color:var(--navy);" id="h3-vid">Derni&egrave;res vid&eacute;os</h3>
          <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="btn btn-outline" style="font-size:11px;padding:10px 20px;" id="btn-yt">Voir toutes les vid&eacute;os &uarr;</a>
        </div>
        <div class="yt-grid" id="yt-grid">

          <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="yt-card">
            <div class="yt-thumb" style="background:linear-gradient(135deg,#0D1B3E 0%,#1a2d5a 100%);">
              <div class="yt-play"></div>
            </div>
            <div class="yt-info">
              <div class="yt-title">Ton dipl&ocirc;me d&rsquo;&Eacute;tat peut te rendre utile si tu sais l&rsquo;utiliser</div>
              <div class="yt-meta">The Waken Series &middot; NextPath System</div>
            </div>
          </a>

          <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="yt-card">
            <div class="yt-thumb" style="background:linear-gradient(135deg,#0D1B3E 0%,#1a2d5a 100%);">
              <div class="yt-play"></div>
            </div>
            <div class="yt-info">
              <div class="yt-title">On nous a tout appris sauf &agrave; construire notre avenir</div>
              <div class="yt-meta">The Waken Series &middot; NextPath System</div>
            </div>
          </a>

          <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="yt-card">
            <div class="yt-thumb" style="background:linear-gradient(135deg,#0D1B3E 0%,#1a2d5a 100%);">
              <div class="yt-play"></div>
            </div>
            <div class="yt-info">
              <div class="yt-title">Comment construire son identit&eacute; et augmenter sa valeur ?</div>
              <div class="yt-meta">The Waken Series &middot; NextPath System</div>
            </div>
          </a>

        </div>
      </div>

      <!-- CTA REJOINDRE -->
      <div style="margin-top:56px;background:var(--navy);border-radius:4px;padding:48px;text-align:center;">
        <div style="font-size:32px;margin-bottom:14px;">📬</div>
        <h3 style="font-family:Georgia,serif;font-size:24px;color:var(--gold);margin-bottom:10px;" id="h3-notif">Prêt(e) à commencer ton parcours ?</h3>
        <p style="font-size:14px;color:rgba(245,240,232,.7);max-width:480px;margin:0 auto 28px;line-height:1.7;" id="p-notif">Les 4 guides NextPath System sont disponibles maintenant. Télécharge-les et commence ton parcours aujourd'hui.</p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold" id="btn-notif">Obtenir les guides — 10 USD</a>
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
      <p style="font-size:15px;color:rgba(245,240,232,.65);line-height:1.7;max-width:440px;margin-bottom:28px;">Fondatrice · NextPath System </p>
      <div style="display:flex;gap:8px;flex-wrap:wrap;">
        <span style="font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;padding:6px 14px;border:1px solid rgba(201,168,76,.4);border-radius:2px;color:var(--gold);">Master Sciences du Médicament</span>
        <span style="font-size:10px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;padding:6px 14px;border:1px solid rgba(201,168,76,.4);border-radius:2px;color:var(--gold);">Nantes Université</span>
      </div>
    </div>
    <div style="position:relative;height:380px;overflow:hidden;border-radius:4px 4px 0 0;">
      <img src="data:image/jpeg;base64,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" alt="Grace Kabondo" style="width:100%;height:100%;object-fit:cover;object-position:center top;">
      <div style="position:absolute;inset:0;background:linear-gradient(to top,rgba(13,27,62,.3) 0%,transparent 60%);"></div>
    </div>
  </div>
  <div class="section">
    <div class="container">
      <div class="grace-grid">
        <div>
          <div class="stag" id="tag-grace">Mon histoire</div>
          <h2 class="stitle" style="font-size:34px;" id="h2-grace">Je suis passée<br>par là, <em>moi aussi.</em></h2>
          <div class="divider"></div>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:18px;" id="g-p1">J&rsquo;ai fait mon école secondaire à Lubumbashi, en RDC — au cœur du système, de la pression, des choix imposés et des questions sans réponses.</p>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:18px;" id="g-p2">Puis j&rsquo;ai poursuivi mes études supérieures en France, où j&rsquo;ai obtenu une Licence en Chimie-Biologie à Nantes Université, avant de poursuivre un Master en Sciences du Médicament.</p>
          <p style="font-size:15px;color:var(--mid);line-height:1.85;margin-bottom:28px;" id="g-p3">Ce parcours entre deux mondes m&rsquo;a révélé une vérité : personne ne m&rsquo;avait appris à me connaître. À transformer ce que j&rsquo;avais en quelque chose de concret.</p>
          <div class="quote-box"><p id="g-quote">"NextPath System c&rsquo;est ce que j&rsquo;aurais voulu avoir à 17 ans. C&rsquo;est ce que je construis aujourd&rsquo;hui — pour toi."</p></div>
        </div>
        <div>
          <div style="display:flex;flex-direction:column;gap:0;border:1px solid var(--border);border-radius:4px;overflow:hidden;">
            <div style="display:flex;gap:14px;padding:14px 18px;border-bottom:1px solid var(--border);"><span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);min-width:80px;margin-top:2px;">Formation</span><span style="font-size:14px;color:var(--dark);line-height:1.6;">Licence Chimie-Biologie &middot; France<br>Master Sciences du M&eacute;dicament &middot; France</span></div>
            <div style="display:flex;gap:14px;padding:14px 18px;border-bottom:1px solid var(--border);"><span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);min-width:80px;margin-top:2px;">R&ocirc;le</span><span style="font-size:14px;color:var(--dark);">Fondatrice &middot; NextPath System</span></div>
            <div style="display:flex;gap:14px;padding:14px 18px;"><span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);min-width:80px;margin-top:2px;">Contact</span><span style="font-size:14px;color:var(--dark);">nextpathsystem@gmail.com</span></div>
          </div>
          <div style="margin-top:24px;background:var(--navy);border-radius:4px;padding:40px;text-align:center;">
            <p style="font-family:Georgia,serif;font-size:18px;font-style:italic;color:var(--cream);line-height:1.65;margin-bottom:16px;" id="g-cite">"Un jeune qui se connaît ne se perd jamais."</p>
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
          <div class="stag" id="tag-contact">Nous contacter</div>
          <h2 class="stitle" id="h2-contact">Ensemble,<br>on <em>construit</em><br>une génération.</h2>
          <div class="divider"></div>
          <a href="https://instagram.com/nextpath.system" target="_blank" class="slink"><span class="splat">Instagram</span><span class="shandle">@nextpath.system</span></a>
          <a href="https://www.youtube.com/@NextPathSystem" target="_blank" class="slink"><span class="splat">YouTube</span><span class="shandle">The NextPath System</span></a>
          <a href="https://tiktok.com/@nextpath.system" target="_blank" class="slink"><span class="splat">TikTok</span><span class="shandle">@nextpath.system</span></a>
          <a href="https://wa.me/33766131603" target="_blank" class="slink"><span class="splat">WhatsApp</span><span class="shandle">+33 7 66 13 16 03</span></a>
          <a href="mailto:nextpathsystem@gmail.com" class="slink"><span class="splat">Email</span><span class="shandle">nextpathsystem@gmail.com</span></a>
        </div>
        <div style="background:var(--light);border-radius:4px;padding:40px;">
          <h3 style="font-family:Georgia,serif;font-size:22px;color:var(--navy);margin-bottom:8px;" id="h3-contact">Rejoins The Grace Effect</h3>
          <p style="font-size:14px;color:var(--mid);margin-bottom:24px;line-height:1.7;" id="p-contact">15 places. Totalement gratuit. Tu recevras une r&eacute;ponse sous 48h.</p>
          <a href="https://tally.so/r/ZjGJQB" target="_blank" class="btn btn-navy" style="width:100%;margin-bottom:14px;" id="btn-contact1">Rejoindre The Grace Effect</a>
          <div style="text-align:center;margin:12px 0;font-size:12px;color:var(--light-text);" id="ou-text">ou</div>
          <a href="#" onclick="go('ressources')" class="btn btn-outline" style="width:100%;" id="btn-contact2">Devenir membre de la communauté</a>
        </div>
      </div>
    </div>
  </div>
</div>


<!-- ══ PAGE AVIS ══ -->
<div class="page" id="page-avis">
  <div class="section" style="padding-top:80px;">
    <div class="container" style="max-width:720px;">

      <div class="stag">Témoignages</div>
      <h2 class="stitle">Ce qu’ils disent de <em>NextPath</em></h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:40px;">Des retours réels de la communauté. Chaque témoignage compte.</p>

      <!-- FLUX AVIS -->
      <div id="avis-feed" style="margin-bottom:48px;"></div>

      <!-- FORMULAIRE COMPACT -->
      <div style="background:var(--light-bg);border-radius:4px;padding:28px;border:1px solid var(--border);">
        <h3 style="font-family:Georgia,serif;font-size:17px;font-weight:700;color:var(--navy);margin-bottom:4px;">Laisse ton avis</h3>
        <p style="font-size:13px;color:var(--mid);margin-bottom:18px;">Ton témoignage peut changer la trajectoire d’un autre jeune.</p>
        <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px;">
          <div><label style="display:block;font-size:10px;font-weight:700;letter-spacing:.07em;text-transform:uppercase;color:var(--mid);margin-bottom:4px;">Prénom *</label><input type="text" id="a-prenom" placeholder="Ex : Grace" style="width:100%;padding:8px 11px;border:1px solid var(--border);border-radius:2px;font-family:inherit;font-size:13px;outline:none;"></div>
          <div><label style="display:block;font-size:10px;font-weight:700;letter-spacing:.07em;text-transform:uppercase;color:var(--mid);margin-bottom:4px;">Ville & Pays *</label><input type="text" id="a-ville" placeholder="Ex : Kinshasa, RDC" style="width:100%;padding:8px 11px;border:1px solid var(--border);border-radius:2px;font-family:inherit;font-size:13px;outline:none;"></div>
        </div>
        <div style="margin-bottom:10px;">
          <label style="display:block;font-size:10px;font-weight:700;letter-spacing:.07em;text-transform:uppercase;color:var(--mid);margin-bottom:4px;">Note *</label>
          <div id="star-rating" style="display:flex;gap:3px;">
            <span onclick="setRating(1)" data-star="1" style="font-size:20px;cursor:pointer;color:#ddd;">&#9733;</span>
            <span onclick="setRating(2)" data-star="2" style="font-size:20px;cursor:pointer;color:#ddd;">&#9733;</span>
            <span onclick="setRating(3)" data-star="3" style="font-size:20px;cursor:pointer;color:#ddd;">&#9733;</span>
            <span onclick="setRating(4)" data-star="4" style="font-size:20px;cursor:pointer;color:#ddd;">&#9733;</span>
            <span onclick="setRating(5)" data-star="5" style="font-size:20px;cursor:pointer;color:#ddd;">&#9733;</span>
          </div>
        </div>
        <div style="margin-bottom:14px;"><label style="display:block;font-size:10px;font-weight:700;letter-spacing:.07em;text-transform:uppercase;color:var(--mid);margin-bottom:4px;">Témoignage *</label><textarea id="a-texte" rows="3" placeholder="Partage ton expérience avec NextPath System..." style="width:100%;padding:8px 11px;border:1px solid var(--border);border-radius:2px;font-family:inherit;font-size:13px;outline:none;resize:vertical;"></textarea></div>
        <div style="display:flex;align-items:center;gap:14px;">
          <button onclick="soumettreAvis()" class="btn btn-navy" style="padding:9px 24px;font-size:11px;">Envoyer</button>
          <span id="avis-ok" style="display:none;font-size:13px;color:var(--gold);font-weight:500;">&#10004; Merci ! Ton avis sera lu personnellement.</span>
        </div>
      </div>

    </div>
  </div>
</div>

<!-- ══ PAGE OPPORTUNITÉS ══ -->
<div class="page" id="page-opportunites">
  <div class="section" style="padding-top:80px;">
    <div class="container">

      <div class="stag" id="tag-opp">NextPath Opportunities</div>
      <h2 class="stitle" id="h2-opp">Des opportunit&eacute;s <em>s&eacute;lectionn&eacute;es</em><br>pour toi.</h2>
      <div class="divider"></div>
      <p class="sbody" style="margin-bottom:16px;" id="p-opp">Grace s&eacute;lectionne et publie r&eacute;guli&egrave;rement des opportunit&eacute;s concr&egrave;tes pour les jeunes africains &mdash; bourses, formations, programmes, concours, stages. Pour chaque opportunit&eacute;, tu trouveras aussi les comp&eacute;tences &agrave; d&eacute;velopper et les ressources pour y arriver.</p>
      <p style="font-size:13px;color:var(--light-text);margin-bottom:48px;">Mise &agrave; jour r&eacute;guli&egrave;re &middot; V&eacute;rifi&eacute;es et s&eacute;lectionn&eacute;es &middot; Accessibles depuis la RDC et la diaspora</p>

      <!-- TYPES D'OPPORTUNITÉS -->
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-bottom:56px;">
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">&#127891;</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Bourses &amp; financements</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Bourses d&rsquo;&eacute;tudes, programmes de financement, aides &agrave; la formation.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">&#127979;</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Formations &amp; certifications</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Cours en ligne gratuits ou certifi&eacute;s pour d&eacute;velopper des comp&eacute;tences cl&eacute;s.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">&#127942;</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Concours &amp; challenges</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Comp&eacute;titions, hackathons, prix pour les jeunes africains.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">&#127759;</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Programmes internationaux</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Programmes d&rsquo;&eacute;changes, leadership et d&eacute;veloppement pour jeunes africains.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">&#127919;</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Stages &amp; exp&eacute;riences</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Premi&egrave;res exp&eacute;riences professionnelles pour construire ton parcours.</div>
        </div>
        <div style="padding:20px;border:1px solid var(--border);border-radius:4px;border-top:3px solid var(--gold);">
          <div style="font-size:22px;margin-bottom:8px;">&#128104;&#8205;&#128187;</div>
          <div style="font-family:Georgia,serif;font-size:14px;font-weight:700;color:var(--navy);margin-bottom:4px;">Comp&eacute;tences du futur</div>
          <div style="font-size:12px;color:var(--mid);line-height:1.6;">Digital, IA, entrepreneuriat, communication &mdash; les comp&eacute;tences essentielles aujourd&rsquo;hui.</div>
        </div>
      </div>

      <!-- OPPORTUNITÉS ACTUELLES -->
      <h3 style="font-family:Georgia,serif;font-size:22px;font-weight:700;color:var(--navy);margin-bottom:24px;">Opportunit&eacute;s disponibles</h3>

      <!-- CARTE OPPORTUNITÉ EXEMPLE -->
      <div style="display:flex;flex-direction:column;gap:20px;margin-bottom:56px;">

        <div style="border:1px solid var(--border);border-radius:4px;padding:28px;border-left:4px solid var(--gold);background:#fff;">
          <div style="display:flex;align-items:flex-start;justify-content:space-between;flex-wrap:wrap;gap:12px;margin-bottom:14px;">
            <div>
              <span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);margin-right:10px;">Bourse</span>
              <span style="font-size:10px;color:var(--light-text);letter-spacing:.06em;">Mise &agrave; jour r&eacute;guli&egrave;re</span>
            </div>
            <span style="font-size:11px;font-weight:600;color:var(--navy);background:var(--light);padding:4px 12px;border-radius:20px;">Ouvert &agrave; tous</span>
          </div>
          <h4 style="font-family:Georgia,serif;font-size:18px;font-weight:700;color:var(--navy);margin-bottom:8px;">Cette section est en cours de construction</h4>
          <p style="font-size:13px;color:var(--mid);line-height:1.7;margin-bottom:16px;">Les premi&egrave;res opportunit&eacute;s sont en cours de s&eacute;lection les premi&egrave;res opportunit&eacute;s pour toi. Rejoins la communaut&eacute; pour &ecirc;tre notifi&eacute;(e) d&egrave;s leur publication.</p>
          <div style="background:var(--light);border-radius:4px;padding:14px 18px;margin-bottom:16px;">
            <div style="font-size:11px;font-weight:700;color:var(--navy);margin-bottom:6px;">&#127891; Comp&eacute;tences recommand&eacute;es</div>
            <div style="font-size:12px;color:var(--mid);">Communication &middot; Anglais &middot; Prise de d&eacute;cision &middot; Leadership</div>
          </div>
          <div style="background:var(--light);border-radius:4px;padding:14px 18px;">
            <div style="font-size:11px;font-weight:700;color:var(--navy);margin-bottom:6px;">&#128218; Ressources pour se pr&eacute;parer</div>
            <div style="font-size:12px;color:var(--mid);">Module 1 NextPath &mdash; Connais-toi &middot; Module 3 &mdash; Construis-toi</div>
          </div>
        </div>

      </div>

      <!-- CTA COMMUNAUTÉ -->
      <div style="background:var(--navy);border-radius:4px;padding:56px;text-align:center;">
        <div style="font-size:36px;margin-bottom:16px;">&#128276;</div>
        <h3 style="font-family:Georgia,serif;font-size:26px;color:var(--gold);margin-bottom:12px;">Sois notifi&eacute;(e) en premier</h3>
        <p style="font-size:14px;color:rgba(245,240,232,0.7);max-width:520px;margin:0 auto 28px;line-height:1.8;">Chaque nouvelle opportunit&eacute; est partag&eacute;e en priorit&eacute; dans la communaut&eacute; WhatsApp NextPath. Rejoins-nous pour ne rien manquer.</p>
        <a href="https://tally.so/r/81Jey5" target="_blank" class="btn btn-gold">Rejoindre la communaut&eacute;</a>
      </div>

    </div>
  </div>
</div>

<footer>
  <div class="flogo">NextPath System</div>
  <div class="flinks">
    <a href="#" onclick="go('home')">Accueil</a>
    <a href="#" onclick="go('mission')">Mission</a>
    <a href="#" onclick="go('programmes')">Devenir membre</a>
    <a href="#" onclick="go('ressources')">Ressources</a>
    <a href="#" onclick="go('avis')">Avis</a>
    <a href="#" onclick="go('opportunites')">Opportunit&#233;s</a>
    <a href="#" onclick="go('grace')">&Agrave; propos</a>
    <a href="#" onclick="go('contact')">Contact</a>
  </div>
  <div class="fcopy" style="display:flex;align-items:center;justify-content:space-between;width:100%;">
    <span>&copy; 2026 NextPath System</span>
    <span onclick="openAdmin()" title="" style="width:8px;height:8px;border-radius:50%;background:rgba(201,168,76,0.25);cursor:pointer;display:inline-block;transition:background .3s;" onmouseover="this.style.background='rgba(201,168,76,0.7)'" onmouseout="this.style.background='rgba(201,168,76,0.25)'"></span>
  </div>
</footer>

<script>
// ── NAVIGATION ──
function go(p){document.querySelectorAll('.page').forEach(function(x){x.classList.remove('active');});var t=document.getElementById('page-'+p);if(t){t.classList.add('active');window.scrollTo(0,0);}document.getElementById('mobile-menu').classList.remove('open');}
function toggleMenu(){document.getElementById('mobile-menu').classList.toggle('open');}

// ── AVIS ──
var rating=0;
function setRating(n){
  rating=n;
  document.querySelectorAll('#star-rating span').forEach(function(s){
    s.style.color=parseInt(s.dataset.star)<=n?'var(--gold)':'#ddd';
  });
}
function soumettreAvis(){
  var p=document.getElementById('a-prenom').value.trim();
  var v=document.getElementById('a-ville').value.trim();
  var t=document.getElementById('a-texte').value.trim();
  if(!p||!v||!t||rating===0){alert('Merci de remplir tous les champs et de donner une note.');return;}
  var ini=p.charAt(0).toUpperCase();
  var stars='';for(var i=0;i<rating;i++)stars+='★';
  var now=new Date();
  var date=now.toLocaleDateString('fr-FR',{day:'2-digit',month:'2-digit',year:'numeric'});
  var item=document.createElement('div');
  item.style.cssText='display:flex;gap:12px;align-items:flex-start;padding:14px 0;border-bottom:1px solid var(--border);';
  item.innerHTML='<div style="width:34px;height:34px;border-radius:50%;background:var(--navy);display:flex;align-items:center;justify-content:center;font-family:Georgia,serif;font-weight:700;color:var(--gold);font-size:12px;flex-shrink:0;margin-top:2px;">'+ini+'</div>'
    +'<div style="flex:1;min-width:0;">'
    +'<div style="display:flex;align-items:center;flex-wrap:wrap;gap:8px;margin-bottom:3px;">'
    +'<span style="font-size:13px;font-weight:600;color:var(--navy);">'+p+'</span>'
    +'<span style="font-size:10px;color:var(--light-text);letter-spacing:.05em;text-transform:uppercase;">'+v+'</span>'
    +'<span style="font-size:12px;color:var(--gold);">'+stars+'</span>'
    +'<span style="font-size:11px;color:var(--light-text);margin-left:auto;">'+date+'</span>'
    +'</div>'
    +'<p style="font-size:13px;color:var(--mid);line-height:1.65;margin:0;">“'+t+'”</p>'
    +'</div>';
  var feed=document.getElementById('avis-feed');
  if(feed){feed.insertBefore(item,feed.firstChild);}
  document.getElementById('avis-ok').style.display='inline';
  document.getElementById('a-prenom').value='';
  document.getElementById('a-ville').value='';
  document.getElementById('a-texte').value='';
  rating=0;
  document.querySelectorAll('#star-rating span').forEach(function(s){s.style.color='#ddd';});
}

// ── LANGUE ──
var lang='fr';
var T={
  'h1-hero':['Tu as plus de valeur<br>que tu ne <em>le crois.</em>','You are worth more<br>than you <em>believe.</em>'],
  'p-hero':['Une plateforme dédiée à la jeunesse africaine — 15 à 30 ans — pour se connaître, explorer son potentiel et construire un chemin qui lui ressemble vraiment.','A platform dedicated to African youth — 15 to 25 years old — to know themselves, explore their potential and build a path that truly fits them.'],
  'btn-hero1':['Rejoindre The Grace Effect','Join The Grace Effect'],
  'btn-hero2':['Devenir membre','Become a member'],
  'quote-hero':['"Un jeune qui se connaît ne se perd jamais."','"A young person who knows themselves never gets lost."'],
  'h2-hero-right':['Devenir la référence<br>de la jeunesse africaine','Becoming the reference<br>for African youth'],
  'stat1':['Jeunes visés d’ici 2028','Youth targeted by 2028'],
  'stat2':['tranche d’âge prioritaire','priority age range'],
  'stat3':['2 programmes en cours','2 programs underway'],
  'tag-cycle':['Notre approche','Our approach'],
  'h2-cycle':['Le Cycle NextPath','The NextPath Cycle'],
  'p-cycle':['Trois étapes concrètes pour transformer la découverte de soi en chemin d’action.','Three concrete steps to transform self-discovery into a path of action.'],
  'p1-title':['Connais-toi','Know yourself'],
  'p1-text':['Découvre ta personnalité, tes forces naturelles et tes valeurs profondes. Ce que tu es naturellement — pas ce qu’on t’a dit d’être.','Discover your personality, natural strengths and deep values. What you truly are — not what you’ve been told to be.'],
  'p2-title':['Libère-toi','Free yourself'],
  'p2-text':['Identifie ce qui te bloque — pression familiale, peur du jugement, croyances limitantes. Comprendre le frein, c’est déjà commencer à le dépasser.','Identify what holds you back — family pressure, fear of judgment, limiting beliefs. Understanding the block is already the beginning of overcoming it.'],
  'p3-title':['Construis-toi','Build yourself'],
  'p3-text':['Passe à l’action avec des outils concrets et une communauté qui avance avec toi. Pas juste de l’inspiration — des résultats réels.','Take action with concrete tools and a community moving forward with you. Not just inspiration — real results.'],
  'btn-mission':['En savoir plus sur notre mission','Learn more about our mission'],
  'tag-avis':['Témoignages','Testimonials'],
  'h2-avis':['Ce qu’ils disent de <em>NextPath</em>','What they say about <em>NextPath</em>'],
  'h3-avis':['Laisse ton avis','Leave your review'],
  'p-avis':['Ton témoignage peut changer la trajectoire d’un autre jeune.','Your testimonial can change another young person’s path.'],
  'btn-avis':['Envoyer mon témoignage','Send my testimonial'],
  'p-avis-ok':['🎉 Merci ! Grace lira ton témoignage personnellement.','🎉 Thank you! Grace will read your testimonial personally.'],
  'tag-mission':['Notre mission','Our mission'],
  'h2-mission':['Éveiller. Orienter. <em>Transformer.</em>','Awaken. Guide. <em>Transform.</em>'],
  'p-mission':['La jeunesse africaine a un potentiel immense. Mais personne ne lui a appris à le voir, à le nommer, à le construire. NextPath System comble ce vide — avec du contenu, des outils concrets et un accompagnement réel.','African youth has immense potential. But no one has taught them to see it, name it, build it. NextPath System fills this gap — with content, concrete tools and real support.'],
  'm1-title':['Éveiller','Awaken'],
  'm1-text':['Faire prendre conscience à chaque jeune de sa valeur et de son potentiel — avant même de parler de carrière ou d’orientation.','Making every young person aware of their value and potential — before even talking about career.'],
  'm2-title':['Orienter','Guide'],
  'm2-text':['Donner des outils concrets pour identifier ses forces, ses valeurs et les directions qui correspondent vraiment à qui on est.','Providing concrete tools to identify strengths and directions that truly match who one is.'],
  'm3-title':['Transformer','Transform'],
  'm3-text':['Accompagner la mise en action — avec un plan clair, une communauté engagée, et un suivi qui crée des résultats mesurables.','Supporting action — with a clear plan, engaged community and follow-up that creates real results.'],
  'tag-prog':['Rejoins le mouvement','Join the movement'],
  'h2-prog':['Devenir <em>membre</em> de la communauté','Become a <em>member</em> of the community'],
  'p-prog':['NextPath System c\u2019est plus qu\u2019une page Instagram. C\u2019est une communauté de jeunes africains de 15 à 30 ans qui avancent ensemble. Rejoins-nous — c\u2019est gratuit.','NextPath System is more than an Instagram page. It\u2019s a community of African youth aged 15 to 25 moving forward together. Join us — it\u2019s free.'],
  'av1-title':['Lives & webinaires','Lives & webinars'],
  'av1-text':['Accès aux sessions exclusives et événements en ligne de la communauté NextPath.','Access to exclusive sessions and online events of the NextPath community.'],
  'av2-title':['Groupe WhatsApp','WhatsApp Group'],
  'av2-text':['Intègre le groupe privé NextPath pour échanger avec Grace et les autres membres.','Join the private NextPath group to connect with Grace and other members.'],
  'av3-title':['Ressources NextPath','NextPath Resources'],
  'av3-text':['Accès en priorité aux guides, outils et contenus exclusifs de NextPath System.','Priority access to guides, tools and exclusive NextPath System content.'],
  'av4-title':['Opportunités','Opportunities'],
  'av4-text':['Accès aux offres de stages, missions et mentorats via NextPath Opportunities.','Access to internships, missions and mentoring offers via NextPath Opportunities.'],
  'av5-title':['Priorité aux cohortes','Priority for cohorts'],
  'av5-text':['Tu seras prioritaire pour rejoindre les prochains programmes d\u2019accompagnement NextPath.','You will have priority to join upcoming NextPath coaching programs.'],
  'av6-title':['Communauté RDC & diaspora','DRC & diaspora community'],
  'av6-text':['Rejoins des jeunes africains engagés qui partagent les mêmes ambitions que toi.','Join committed African youth who share the same ambitions as you.'],
  'h3-membre-cta':['Rejoins la communauté NextPath','Join the NextPath community'],
  'p-membre-cta':['Tu t\u2019inscris en 2 minutes. Grace te contacte sur WhatsApp pour t\u2019accueillir personnellement.','You register in 2 minutes. Grace contacts you on WhatsApp to welcome you personally.'],
  'btn-membre-cta':['Devenir membre — Gratuit','Become a member — Free'],
  'p-gratuit-cta':['100% gratuit · Sans engagement · Accessible depuis la RDC et la diaspora','100% free · No commitment · Accessible from DRC and diaspora'],
  'tag-test':['Outil gratuit','Free tool'],
  'h3-test':['Le <em>NextPath Test</em>','The <em>NextPath Test</em>'],
  'p-test':['13 questions. 5 minutes. Un portrait complet de qui tu es.','13 questions. 5 minutes. A complete portrait of who you are.'],
  'tb1':['Profil de personnalité parmi 4 types NextPath','Personality profile among 4 NextPath types'],
  'tb2':['Tes forces naturelles identifiées','Your natural strengths identified'],
  'tb3':['Les directions qui te correspondent','The directions that suit you'],
  'tb4':['Gratuit · Sans inscription','Free · No registration'],
  'btn-test-cta':['Passer le NextPath Test — Gratuit','Take the NextPath Test — Free'],
  'h2-prog':['Deux outils pour <em>te révéler.</em>','Two tools to <em>reveal you.</em>'],
  'badge-ge':['Programme · 4 semaines','Program · 4 weeks'],
  'desc-ge':['4 semaines pour te connaître, comprendre ce qui te bloque et construire ton chemin. En ligne, en groupe, avec Grace. Première cohorte totalement gratuite.','4 weeks to know yourself, understand what holds you back and build your path. Online, in a group, with Grace. First cohort completely free.'],
  'btn-ge':['Réserver ma place gratuite','Reserve my free spot'],
  'badge-test':['Outil gratuit · 10 min','Free tool · 10 min'],
  'desc-test':['20 questions pour révéler ton profil de personnalité, tes forces naturelles, tes blocages et les directions qui te correspondent. Gratuit, sans inscription.','20 questions to reveal your personality profile, natural strengths, blocks and directions that suit you. Free, no registration.'],
  'btn-test':['Passer le test','Take the test'],
  'h3-ge':['The Grace Effect — Détail du programme','The Grace Effect — Program details'],
  's1':['Semaine 1','Week 1'],'s2':['Semaine 2','Week 2'],'s3':['Semaine 3','Week 3'],'s4':['Semaine 4','Week 4'],
  'm-s1':['Qui es-tu vraiment ?','Who are you really?'],
  'mp-s1':['Profil NextPath, forces naturelles, valeurs fondamentales.','NextPath profile, natural strengths, core values.'],
  'm-s2':['Qu’est-ce qui te bloque ?','What’s holding you back?'],
  'mp-s2':['Identification des blocages et outils pour s’en libérer.','Identifying blocks and tools to overcome them.'],
  'm-s3':['Comment construire ton chemin ?','How to build your path?'],
  'mp-s3':['Méthode NextPath pour connecter tes forces à un chemin concret.','NextPath method to connect your strengths to a concrete path.'],
  'm-s4':['Ton plan pour avancer','Your plan to move forward'],
  'mp-s4':['Premières actions concrètes ancrées dans qui tu es.','First concrete actions rooted in who you are.'],
  'if1':['Format','Format'],'if2':['Durée','Duration'],'if3':['Places','Spots'],'if4':['Âge','Age'],
  'iv1':['100% en ligne · Sessions de groupe','100% online · Group sessions'],
  'iv2':['4 semaines · 90 min / session','4 weeks · 90 min / session'],
  'h3-cta':['Rejoins The Grace Effect','Join The Grace Effect'],
  'p-cta':['15 places disponibles. Ne laisse pas ta place à quelqu’un d’autre.','15 spots available. Don’t let someone else take your spot.'],
  'btn-cta':['Réserver ma place','Reserve my spot'],
  'h3-test-detail':['NextPath Test — Les 4 profils','NextPath Test — The 4 profiles'],
  'pr1-name':['L’Éclaireur','The Enlightener'],'pr1-desc':['Sciences, recherche, enseignement, droit.','Sciences, research, teaching, law.'],
  'pr2-name':['Le Connecteur','The Connector'],'pr2-desc':['Médias, diplomatie, entrepreneuriat social.','Media, diplomacy, social entrepreneurship.'],
  'pr3-name':['Le Bâtisseur','The Builder'],'pr3-desc':['Entrepreneuriat, management, commerce.','Entrepreneurship, management, business.'],
  'pr4-name':['Le Semeur','The Sower'],'pr4-desc':['Éducation, santé, social, arts.','Education, health, social, arts.'],
  'btn-test2':['Passer le NextPath Test — Gratuit','Take the NextPath Test — Free'],
  'tag-membre':['Communauté','Community'],
  'h3-membre':['Devenir <em>membre</em>','Become a <em>member</em>'],
  'p-membre':['Rejoins la communauté NextPath System. Accède aux ressources, aux événements en ligne et aux échanges. C’est gratuit.','Join the NextPath System community. Access resources, online events and discussions. It’s free.'],
  'b1':['Accès aux lives et webinaires exclusifs','Access to exclusive lives and webinars'],
  'b2':['Groupe WhatsApp de la communauté','Community WhatsApp group'],
  'b3':['Ressources et outils NextPath gratuits','Free NextPath resources and tools'],
  'b4':['Priorité pour les prochaines cohortes','Priority for upcoming cohorts'],
  'h4-membre':['Rejoins le mouvement','Join the movement'],
  'p-membre2':['Fais partie des premiers membres de la communauté NextPath System.','Be among the first members of the NextPath System community.'],
  'btn-membre':['Devenir membre — Gratuit','Become a member — Free'],
  'p-gratuit':['100% gratuit · Sans engagement','100% free · No commitment'],
  
  'h2-videos':['Contenu pour <em>t’éveiller.</em>','Content to <em>awaken you.</em>'],
  
  'btn-yt':['Voir toutes les vidéos sur YouTube ↗','See all videos on YouTube ↗'],
  'tag-res':['Ressources gratuites','Free resources'],
  'h2-res':['Guides & <em>outils</em>','Guides & <em>tools</em>'],
  'p-res':['Des ressources concrètes pour avancer — guides PDF, outils d’orientation, exercices pratiques. Télécharge gratuitement.','Concrete resources to move forward — PDF guides, orientation tools, practical exercises. Download for free.'],
  'h3-notif':['Sois le premier à recevoir les guides','Be the first to receive the guides'],
  'p-notif':['Les ressources sont en cours de création. Rejoins la communauté pour les recevoir dès leur sortie.','Resources are being created. Join the community to receive them as soon as they’re released.'],
  'btn-notif':['Rejoindre la communauté','Join the community'],
  'tag-grace':['Mon histoire','My story'],
  'h2-grace':['Je suis passée<br>par là, <em>moi aussi.</em>','I’ve been there,<br><em>too.</em>'],
  'g-p1':['J’ai fait mon école secondaire à Lubumbashi, en RDC — au cœur du système, de la pression, des choix imposés et des questions sans réponses.','I did my secondary school in Lubumbashi, DRC — at the heart of the system, pressure, imposed choices and unanswered questions.'],
  'g-p2':['Puis j’ai poursuivi mes études supérieures en France, où j’ai obtenu une Licence en Chimie-Biologie à Nantes Université, avant de poursuivre un Master en Sciences du Médicament.','Then I pursued higher education in France, where I obtained a Bachelor’s in Chemistry-Biology at Nantes University, before pursuing a Master’s in Drug Sciences.'],
  'g-p3':['Ce parcours entre deux mondes m’a révélé une vérité : personne ne m’avait appris à me connaître. À transformer ce que j’avais en quelque chose de concret.','This journey between two worlds revealed a truth: no one had taught me to know myself. To transform what I had into something concrete.'],
  'g-quote':['"NextPath System c’est ce que j’aurais voulu avoir à 17 ans. C’est ce que je construis aujourd’hui — pour toi."','"NextPath System is what I wish I had at 17. It’s what I’m building today — for you."'],
  'gl1':['Origine','Origin'],'gv1':['Lubumbashi, RDC','Lubumbashi, DRC'],
  'gl2':['Basée','Based'],'gv2':['France','France'],
  'gl3':['Formation','Education'],'gv3':['Licence Chimie-Biologie · France<br>Master Sciences du Médicament · France','Bachelor Chemistry-Biology · France<br>MSc Drug Sciences · France'],
  'gl4':['Rôle','Role'],'gv4':['Fondatrice · NextPath System','Founder · NextPath System'],
  'gl5':['Contact','Contact'],
  'g-cite':['"Un jeune qui se connaît ne se perd jamais."','"A young person who knows themselves never gets lost."'],
  'tag-contact':['Nous contacter','Contact us'],
  'h2-contact':['Ensemble,<br>on <em>construit</em><br>une génération.','Together,<br>we <em>build</em><br>a generation.'],
  'h3-contact':['Rejoins The Grace Effect','Join The Grace Effect'],
  'p-contact':['15 places. Totalement gratuit. Tu recevras une r&eacute;ponse sous 48h.','15 spots. Completely free. Grace will contact you within 48h.'],
  'btn-contact1':['Rejoindre The Grace Effect','Join The Grace Effect'],
  'ou-text':['ou','or'],
  'btn-contact2':['Devenir membre de la communauté','Become a community member'],
  'tag-opp':['NextPath Opportunities','NextPath Opportunities'],
  'h2-opp':['Le pont entre toi et ceux qui ont des <em>opportunités.</em>','The bridge between you and those who have <em>opportunities.</em>'],
  'p-opp':['Des stages, missions, projets et mentorats proposés par des professionnels partenaires.','Internships, missions, projects and mentoring offered by partner professionals.'],
  'btn-proposer':['Proposer une opportunité','Propose an opportunity'],
  'btn-postuler':['Postuler à une opportunité','Apply for an opportunity'],
  'h3-types':['Types d\u2019opportunités disponibles','Available opportunity types'],
  'h3-coming':['Premières opportunités bientôt disponibles','First opportunities coming soon'],
  'p-coming':['NextPath Opportunities est en cours de lancement. Rejoins la communauté pour être notifié(e) en premier.','NextPath Opportunities is launching soon. Join the community to be notified first.'],
  'btn-notif-opp':['Rejoindre la communauté','Join the community'],
  'tag-partners':['Devenir partenaire','Become a partner'],
  'h3-partners':['Tu as une opportunité à offrir à la <em>jeunesse ?</em>','Do you have an opportunity to offer <em>youth?</em>'],
  'p-partners':['Il y a des centaines de jeunes en RDC et dans la diaspora qui ont le feu en eux. Sois le pont.','There are hundreds of young people in DRC and the diaspora with fire in them. Be the bridge.'],
  'h4-partner':['Propose une opportunité','Propose an opportunity'],
  'p-partner2':['Gratuit. Simple. Chaque proposition est examin&eacute;e sous 48h.','Free. Simple. Grace reviews each proposal within 48h.'],
  'btn-partner-cta':['Je propose une opportunité','I propose an opportunity'],
  'p-charte':['En proposant vous acceptez la Charte NextPath Partners','By proposing you accept the NextPath Partners Charter'],
  'pack-label':['Pack complet — 4 modules','Complete pack — 4 modules'],
  'pack-title':['Les guides NextPath System','NextPath System guides'],
  'pack-desc':['Les 4 guides PDF complets — Bienvenue, Connais-toi, Libère-toi, Construis-toi — pour te connaître, identifier tes blocages et construire ton chemin concret.','The 4 complete PDF guides — Welcome, Know Yourself, Free Yourself, Build Yourself — to know yourself, identify your blocks and build your concrete path.'],
  'btn-acheter':['Acheter les guides →','Buy the guides →'],
  'm1-tag':['Module 1','Module 1'],'m1-pdf-title':['Connais-toi','Know Yourself'],
  'm1-pdf-desc':['Profil de personnalité, forces naturelles, valeurs fondamentales. 3 exercices écrits + portrait NextPath complet.','Personality profile, natural strengths, core values. 3 written exercises + complete NextPath portrait.'],
  'm1-dl':['Inclus dans le pack','Included in the pack'],
  'm2-tag':['Module 2','Module 2'],'m2-pdf-title':['Libère-toi','Free Yourself'],
  'm2-pdf-desc':['Les 5 blocages les plus courants, lettre à ton blocage, plan de libération concret.','The 5 most common blocks, letter to your block, concrete liberation plan.'],
  'm2-dl':['Inclus dans le pack','Included in the pack'],
  'm3-tag':['Module 3','Module 3'],'m3-pdf-title':['Construis-toi','Build Yourself'],
  'm3-pdf-desc':['Méthode des 3 cercles, tes 3 chemins possibles, orientation post-diplôme, plan d\u2019action 90 jours.','3-circle method, your 3 possible paths, post-diploma orientation, 90-day action plan.'],
  'm3-dl':['Inclus dans le pack','Included in the pack'],
  'h3-notif':['Prêt(e) à commencer ton parcours ?','Ready to start your journey?'],
  'p-notif':['Les 4 guides NextPath System sont disponibles maintenant. Télécharge-les et commence ton parcours aujourd\'hui.','The 4 NextPath System guides are available now. Download them and start your journey today.'],
  'tag-gratuit':['10 USD le pack complet','10 USD complete pack']
};

function setLang(l){
  lang=l;
  document.getElementById('btn-fr').classList.toggle('active',l==='fr');
  document.getElementById('btn-en').classList.toggle('active',l==='en');
  var i=l==='fr'?0:1;
  for(var id in T){
    var el=document.getElementById(id);
    if(el)el.innerHTML=T[id][i];
  }
}

// ── ADMIN ──
var adminOpen = false;
function openAdmin(){
  document.getElementById('admin-overlay').style.display='block';
  adminOpen = true;
}
function closeAdmin(){
  document.getElementById('admin-overlay').style.display='none';
  adminOpen = false;
}

function appliquerPDF(){
  var ids = ['lien-m0','lien-m1','lien-m2','lien-m3'];
  var cards = document.querySelectorAll('#pdf-grid a.pdf-card');
  ids.forEach(function(id,i){
    var val = document.getElementById(id).value.trim();
    if(val && cards[i]) cards[i].href = val;
  });
  document.getElementById('msg-pdf').style.display='block';
  setTimeout(function(){document.getElementById('msg-pdf').style.display='none';},3000);
}

function appliquerVideos(){
  var yt = document.querySelectorAll('#yt-grid .yt-card');
  var data = [
    {titre: document.getElementById('yt1-titre').value, lien: document.getElementById('yt1-lien').value},
    {titre: document.getElementById('yt2-titre').value, lien: document.getElementById('yt2-lien').value},
    {titre: document.getElementById('yt3-titre').value, lien: document.getElementById('yt3-lien').value},
  ];
  data.forEach(function(d,i){
    if(d.lien && yt[i]){
      yt[i].href = d.lien;
      if(d.titre) yt[i].querySelector('.yt-title').textContent = d.titre;
    }
  });
  document.getElementById('msg-yt').style.display='block';
  setTimeout(function(){document.getElementById('msg-yt').style.display='none';},3000);
}

function ajouterOpp(){
  var type = document.getElementById('opp-type').value.trim();
  var titre = document.getElementById('opp-titre').value.trim();
  var desc = document.getElementById('opp-desc').value.trim();
  var skills = document.getElementById('opp-skills').value.trim();
  var lien = document.getElementById('opp-lien').value.trim();
  var date = document.getElementById('opp-date').value.trim();
  if(!titre || !lien) return alert('Titre et lien sont obligatoires.');
  var container = document.querySelector('#page-opportunites .section .container');
  var listEl = container.querySelector('.opp-list');
  if(!listEl){
    listEl = document.createElement('div');
    listEl.className = 'opp-list';
    listEl.style.cssText = 'display:flex;flex-direction:column;gap:20px;margin-bottom:56px;';
    var h3 = container.querySelector('h3');
    h3.after(listEl);
  }
  var card = document.createElement('div');
  card.style.cssText = 'border:1px solid var(--border);border-radius:4px;padding:28px;border-left:4px solid var(--gold);background:#fff;';
  card.innerHTML = '<div style="display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:10px;margin-bottom:12px;">'
    + '<div><span style="font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);">' + (type||'Opportunité') + '</span>'
    + (date ? '<span style="font-size:10px;color:var(--light-text);margin-left:10px;">Limite : ' + date + '</span>' : '') + '</div>'
    + '<a href="' + lien + '" target="_blank" style="font-size:11px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;background:var(--gold);color:var(--navy);padding:8px 18px;border-radius:2px;text-decoration:none;">Voir l’opportunité &rarr;</a>'
    + '</div>'
    + '<h4 style="font-family:Georgia,serif;font-size:17px;font-weight:700;color:var(--navy);margin-bottom:8px;">' + titre + '</h4>'
    + (desc ? '<p style="font-size:13px;color:var(--mid);line-height:1.7;margin-bottom:14px;">' + desc + '</p>' : '')
    + (skills ? '<div style="background:var(--light);border-radius:4px;padding:12px 16px;"><div style="font-size:11px;font-weight:700;color:var(--navy);margin-bottom:4px;">&#127891; Compétences recommandées</div><div style="font-size:12px;color:var(--mid);">' + skills + '</div></div>' : '');
  listEl.prepend(card);
  // Vider les champs
  ['opp-type','opp-titre','opp-desc','opp-skills','opp-lien','opp-date'].forEach(function(id){document.getElementById(id).value='';});
  document.getElementById('msg-opp').style.display='block';
  setTimeout(function(){document.getElementById('msg-opp').style.display='none';},3000);
  closeAdmin();
}

</script>

<!-- ADMIN PANEL — INVISIBLE AU PUBLIC -->
<div id="admin-overlay">
  <div id="admin-panel">
    <button class="admin-close" onclick="closeAdmin()">&#10005; Fermer</button>
    <h2>&#9881;&#65039; Panneau NextPath System</h2>
    <p>Mets &agrave; jour tes ressources sans toucher au code. Colle tes liens Google Drive et tes liens YouTube, puis clique sur Appliquer.</p>

    <div class="admin-section">
      <h3>&#128218; Guides PDF &mdash; S&eacute;rie 1 : &Eacute;veil &amp; D&eacute;couverte de soi</h3>
      <div class="admin-row"><label>Module 0 &mdash; Bienvenue</label><input type="text" id="lien-m0" placeholder="Lien Google Drive (export download)"></div>
      <div class="admin-row"><label>Module 1 &mdash; Connais-toi</label><input type="text" id="lien-m1" placeholder="Lien Google Drive (export download)"></div>
      <div class="admin-row"><label>Module 2 &mdash; Lib&egrave;re-toi</label><input type="text" id="lien-m2" placeholder="Lien Google Drive (export download)"></div>
      <div class="admin-row"><label>Module 3 &mdash; Construis-toi</label><input type="text" id="lien-m3" placeholder="Lien Google Drive (export download)"></div>
      <p style="font-size:11px;color:#999;margin-top:8px;">Format du lien : https://drive.google.com/uc?export=download&amp;id=TON_ID</p>
      <button class="admin-btn" onclick="appliquerPDF()">Appliquer les liens PDF</button>
      <div id="msg-pdf" style="font-size:12px;color:green;margin-top:8px;display:none;">&#10004; Liens PDF mis &agrave; jour !</div>
    </div>

    <div class="admin-section">
      <h3>&#127909; Vid&eacute;os YouTube</h3>
      <div class="admin-row"><label>Vid&eacute;o 1 &mdash; Titre</label><input type="text" id="yt1-titre" placeholder="Titre de la vid&eacute;o"></div>
      <div class="admin-row"><label>Vid&eacute;o 1 &mdash; Lien</label><input type="text" id="yt1-lien" placeholder="https://youtube.com/watch?v=..."></div>
      <div class="admin-row"><label>Vid&eacute;o 2 &mdash; Titre</label><input type="text" id="yt2-titre" placeholder="Titre de la vid&eacute;o"></div>
      <div class="admin-row"><label>Vid&eacute;o 2 &mdash; Lien</label><input type="text" id="yt2-lien" placeholder="https://youtube.com/watch?v=..."></div>
      <div class="admin-row"><label>Vid&eacute;o 3 &mdash; Titre</label><input type="text" id="yt3-titre" placeholder="Titre de la vid&eacute;o"></div>
      <div class="admin-row"><label>Vid&eacute;o 3 &mdash; Lien</label><input type="text" id="yt3-lien" placeholder="https://youtube.com/watch?v=..."></div>
      <button class="admin-btn" onclick="appliquerVideos()">Appliquer les vid&eacute;os</button>
      <div id="msg-yt" style="font-size:12px;color:green;margin-top:8px;display:none;">&#10004; Vid&eacute;os mises &agrave; jour !</div>
    </div>

    <div class="admin-section">
      <h3>&#128203; Ajouter une opportunit&eacute;</h3>
      <div class="admin-row"><label>Type</label><input type="text" id="opp-type" placeholder="Ex : Bourse, Stage, Formation..."></div>
      <div class="admin-row"><label>Titre</label><input type="text" id="opp-titre" placeholder="Titre de l'opportunit&eacute;"></div>
      <div class="admin-row"><label>Description</label><input type="text" id="opp-desc" placeholder="Description courte"></div>
      <div class="admin-row"><label>Comp&eacute;tences</label><input type="text" id="opp-skills" placeholder="Ex : Communication &middot; Anglais &middot; Excel"></div>
      <div class="admin-row"><label>Lien</label><input type="text" id="opp-lien" placeholder="https://..."></div>
      <div class="admin-row"><label>Date limite</label><input type="text" id="opp-date" placeholder="Ex : 30 juin 2026"></div>
      <button class="admin-btn" onclick="ajouterOpp()">Ajouter cette opportunit&eacute;</button>
      <div id="msg-opp" style="font-size:12px;color:green;margin-top:8px;display:none;">&#10004; Opportunit&eacute; ajout&eacute;e !</div>
    </div>

  </div>
</div>
</body>
</html>
