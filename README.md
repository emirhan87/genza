<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GENZA e.V. — 2026 Projelerimiz</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --navy: #0D2B5E;
  --teal: #1AACAA;
  --teal-light: #4ECDC4;
  --gold: #F5A623;
  --gold-light: #FFD166;
  --cream: #F7F5F0;
  --dark: #111827;
  --mid: #4B5563;
  --light: #9CA3AF;
  --white: #FFFFFF;
  --violet: #6C63FF;
  --rose: #E85D75;
  --green: #2ECC71;
}

* { margin:0; padding:0; box-sizing:border-box; }

body {
  font-family: 'DM Sans', sans-serif;
  background: #080808;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 20px;
}

#slideshow {
  width: 100%;
  max-width: 1280px;
  position: relative;
  aspect-ratio: 16/9;
}

.slide {
  /* All slides stacked, visibility toggled — never display:none so scale is stable */
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  display: flex;
  opacity: 0;
  visibility: hidden;
  pointer-events: none;
  border-radius: 14px;
  overflow: hidden;
  box-shadow: 0 40px 100px rgba(0,0,0,0.7);
  transition: opacity 0.4s ease;
}
.slide.active {
  opacity: 1;
  visibility: visible;
  pointer-events: auto;
}

/* ── FULLSCREEN: slide fills the entire screen ── */
:fullscreen, :-webkit-full-screen {
  background: #080808;
}
:fullscreen body, :-webkit-full-screen body {
  padding: 0;
  width: 100vw;
  height: 100vh;
  justify-content: center;
  align-items: center;
}
:fullscreen #slideshow-wrapper, :-webkit-full-screen #slideshow-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}
:fullscreen #slideshow, :-webkit-full-screen #slideshow {
  width: 1280px !important;
  height: 720px !important;
  max-width: none !important;
  aspect-ratio: unset !important;
}
:fullscreen .slide, :-webkit-full-screen .slide {
  border-radius: 0;
}
:fullscreen #controls, :-webkit-full-screen #controls,
:fullscreen #slide-indicator, :-webkit-full-screen #slide-indicator,
:fullscreen #hint, :-webkit-full-screen #hint {
  display: none;
}
:fullscreen #fsBtn, :-webkit-full-screen #fsBtn {
  display: flex;
}

@keyframes fadeIn {
  from { opacity:0; transform:translateY(10px); }
  to   { opacity:1; transform:translateY(0); }
}

/* ── FULLSCREEN BUTTON ── */
#fsBtn {
  position: fixed; top:16px; right:16px;
  background: rgba(255,255,255,0.08);
  border: 1px solid rgba(255,255,255,0.15);
  color: white; width:42px; height:42px;
  border-radius:8px; font-size:18px; cursor:pointer;
  z-index:999; display:flex; align-items:center; justify-content:center;
  transition:all .2s;
}
#fsBtn:hover { background:rgba(255,255,255,0.2); }

/* ── CONTROLS ── */
#controls { display:flex; align-items:center; gap:20px; margin-top:22px; }
.ctrl-btn {
  background:rgba(255,255,255,0.08);
  border:1px solid rgba(255,255,255,0.15);
  color:white; width:50px; height:50px; border-radius:50%;
  font-size:20px; cursor:pointer; transition:all .2s;
  display:flex; align-items:center; justify-content:center;
}
.ctrl-btn:hover { background:rgba(255,255,255,0.18); }
.ctrl-btn:disabled { opacity:.2; cursor:not-allowed; }
#dots { display:flex; gap:8px; flex-wrap:wrap; justify-content:center; }
.dot {
  width:9px; height:9px; border-radius:50%;
  background:rgba(255,255,255,0.2); cursor:pointer; transition:all .3s;
}
.dot.active { background:var(--teal-light); transform:scale(1.5); }
#slide-indicator { color:rgba(255,255,255,0.35); font-size:13px; letter-spacing:2px; min-width:70px; text-align:center; }
#hint { color:rgba(255,255,255,0.18); font-size:11px; letter-spacing:2px; margin-top:6px; text-transform:uppercase; }

/* ════════════════════════════════
   SLIDE 1 — COVER
════════════════════════════════ */
.s-cover {
  background: linear-gradient(140deg, #061630 0%, #0D2B5E 50%, #0a2040 100%);
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  gap: 2%;
}
.s-cover::before {
  content:'';
  position:absolute; inset:0;
  background:
    radial-gradient(ellipse 70% 60% at 75% 25%, rgba(26,172,170,0.22) 0%, transparent 65%),
    radial-gradient(ellipse 50% 50% at 25% 75%, rgba(245,166,35,0.18) 0%, transparent 65%);
}
.s-cover .cover-logo {
  height: clamp(60px, 8vw, 110px);
  position:relative; z-index:2;
  filter: drop-shadow(0 6px 24px rgba(26,172,170,0.45));
  animation: float 3.5s ease-in-out infinite;
}
@keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-10px)} }
.s-cover h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(32px, 5.5vw, 76px);
  font-weight: 900;
  color: white;
  line-height: 1.05;
  position:relative; z-index:2;
  letter-spacing: -1px;
}
.s-cover h1 span {
  background: linear-gradient(90deg, var(--teal-light), var(--gold-light));
  -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
}
.s-cover .cover-sub {
  font-size: clamp(13px, 1.8vw, 24px);
  color: rgba(255,255,255,0.45);
  letter-spacing: 5px;
  text-transform: uppercase;
  font-weight: 300;
  position:relative; z-index:2;
}
.s-cover .cover-date {
  font-size: clamp(11px, 1.3vw, 17px);
  color: var(--teal-light);
  letter-spacing: 4px;
  text-transform: uppercase;
  position:relative; z-index:2;
}
.s-cover .bg-year {
  position:absolute; bottom:-20px; right:3%;
  font-family:'Playfair Display',serif;
  font-size: clamp(100px, 18vw, 260px);
  font-weight:900; color:rgba(255,255,255,0.03);
  pointer-events:none; line-height:1;
}

/* ════════════════════════════════
   SLIDE 2 — PROJECTS OVERVIEW
════════════════════════════════ */
.s-overview {
  background: var(--cream);
  flex-direction: column;
  padding: 5% 6%;
  gap: 4%;
}
.slide-topbar {
  display:flex; justify-content:space-between; align-items:flex-start;
}
.slide-topbar .logo-img { height: clamp(36px, 4.5vw, 62px); object-fit:contain; }
.eyebrow {
  font-size: clamp(10px, 1.1vw, 15px);
  letter-spacing:4px; text-transform:uppercase;
  color:var(--teal); font-weight:700; margin-bottom:4px;
}
.slide-title {
  font-family:'Playfair Display',serif;
  font-size: clamp(24px, 3.5vw, 50px);
  color: var(--navy); font-weight:900; line-height:1.0;
}
.overview-grid {
  display:grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 2.5%;
  flex:1;
}
.ov-card {
  background:white;
  border-radius:12px;
  padding: 6% 5%;
  display:flex; flex-direction:column; gap:6px;
  border-top: 4px solid;
  box-shadow: 0 3px 20px rgba(0,0,0,0.07);
  position:relative; overflow:hidden;
}
.ov-card:nth-child(1){border-color:var(--teal);}
.ov-card:nth-child(2){border-color:var(--gold);}
.ov-card:nth-child(3){border-color:var(--violet);}
.ov-card:nth-child(4){border-color:var(--rose);}
.ov-card:nth-child(5){border-color:var(--green);}
.ov-card .ov-num {
  font-size: clamp(28px, 4vw, 58px);
  font-family:'Playfair Display',serif; font-weight:900;
  line-height:1; opacity:0.12; margin-bottom:2px;
}
.ov-card:nth-child(1) .ov-num{color:var(--teal);}
.ov-card:nth-child(2) .ov-num{color:var(--gold);}
.ov-card:nth-child(3) .ov-num{color:var(--violet);}
.ov-card:nth-child(4) .ov-num{color:var(--rose);}
.ov-card:nth-child(5) .ov-num{color:var(--green);}
.ov-card h3 {
  font-family:'Playfair Display',serif;
  font-size: clamp(12px, 1.3vw, 17px);
  color:var(--navy); font-weight:700; line-height:1.2;
}
.ov-card .ov-name {
  font-size: clamp(9px, 0.85vw, 12px);
  color:var(--light); font-weight:500; margin-top:auto; padding-top:6px;
}

/* ════════════════════════════════
   PROJECT SLIDES — LEFT/RIGHT SPLIT
════════════════════════════════ */
.s-proj { flex-direction:row; }

.proj-left {
  width:36%; display:flex; flex-direction:column;
  padding:7% 6%; position:relative; overflow:hidden;
  justify-content:flex-end; gap:8px;
}
.proj-left::before {
  content:'';
  position:absolute; top:-30%; left:-20%;
  width:120%; height:120%;
  background:radial-gradient(ellipse at 30% 70%, rgba(255,255,255,0.1) 0%, transparent 60%);
  pointer-events:none;
}
.proj-big-num {
  position:absolute; top:-2%; left:-3%;
  font-family:'Playfair Display',serif;
  font-size: clamp(80px, 14vw, 200px);
  font-weight:900; color:rgba(255,255,255,0.07);
  line-height:1; pointer-events:none; letter-spacing:-4px;
}
.proj-eyebrow {
  font-size:clamp(9px, 1vw, 13px); letter-spacing:4px;
  text-transform:uppercase; color:rgba(255,255,255,0.5);
  font-weight:600; position:relative; z-index:2;
}
.proj-left h2 {
  font-family:'Playfair Display',serif;
  font-size: clamp(18px, 2.5vw, 36px);
  color:white; font-weight:700; line-height:1.15;
  position:relative; z-index:2;
}
.proj-presenter {
  font-size:clamp(10px, 1.1vw, 15px);
  color:rgba(255,255,255,0.55); font-weight:400;
  letter-spacing:2px; text-transform:uppercase;
  position:relative; z-index:2;
}
.proj-divider {
  width:36px; height:3px; border-radius:2px;
  background:rgba(255,255,255,0.35);
  position:relative; z-index:2;
}

.proj-right {
  width:64%; background:var(--cream);
  padding:5% 6%; display:flex; flex-direction:column; gap:4%;
}
.proj-right .logo-row {
  display:flex; justify-content:flex-end;
}
.proj-right .logo-img { height:clamp(32px, 4vw, 56px); object-fit:contain; }

/* Big statement text */
.big-statement {
  font-family:'Playfair Display',serif;
  font-size: clamp(16px, 2.2vw, 32px);
  color:var(--navy); font-weight:700;
  line-height:1.25; letter-spacing:-0.3px;
}
.big-statement em {
  font-style:italic; color:var(--teal);
}

/* Icon grid */
.icon-grid {
  display:grid; gap:3%;
  flex:1;
}
.icon-grid.cols-2 { grid-template-columns:1fr 1fr; }
.icon-grid.cols-3 { grid-template-columns:1fr 1fr 1fr; }
.icon-grid.cols-4 { grid-template-columns:1fr 1fr 1fr 1fr; }

.icon-card {
  background:white; border-radius:10px;
  padding:5% 5%; display:flex; flex-direction:column;
  gap:6px; box-shadow:0 2px 14px rgba(0,0,0,0.06);
}
.icon-card .ic-icon {
  font-size: clamp(18px, 2.5vw, 36px); line-height:1; margin-bottom:2px;
}
.icon-card .ic-title {
  font-weight:700; color:var(--navy);
  font-size:clamp(11px, 1.2vw, 17px); line-height:1.2;
}
.icon-card .ic-desc {
  font-size:clamp(9px, 0.9vw, 13px);
  color:var(--mid); line-height:1.4;
}

/* Pill tags */
.pill-row { display:flex; flex-wrap:wrap; gap:6px; margin-top:auto; }
.pill {
  font-size:clamp(9px, 0.9vw, 13px);
  padding:4px 14px; border-radius:20px; font-weight:600;
}

/* Themes */
.theme-teal .proj-left  { background:linear-gradient(150deg,#1AACAA 0%,#0a7070 100%); }
.theme-teal .big-statement em { color:var(--teal); }
.theme-teal .pill { background:rgba(26,172,170,0.12); color:#0a8080; }
.theme-teal .icon-card .ic-icon { color:var(--teal); }

.theme-gold .proj-left  { background:linear-gradient(150deg,#F5A623 0%,#b07010 100%); }
.theme-gold .big-statement em { color:var(--gold); }
.theme-gold .pill { background:rgba(245,166,35,0.12); color:#a06008; }
.theme-gold .icon-card .ic-icon { color:var(--gold); }

.theme-violet .proj-left { background:linear-gradient(150deg,#6C63FF 0%,#4035cc 100%); }
.theme-violet .big-statement em { color:var(--violet); }
.theme-violet .pill { background:rgba(108,99,255,0.12); color:var(--violet); }
.theme-violet .icon-card .ic-icon { color:var(--violet); }

.theme-rose .proj-left  { background:linear-gradient(150deg,#E85D75 0%,#a03050 100%); }
.theme-rose .big-statement em { color:var(--rose); }
.theme-rose .pill { background:rgba(232,93,117,0.12); color:var(--rose); }
.theme-rose .icon-card .ic-icon { color:var(--rose); }

.theme-green .proj-left { background:linear-gradient(150deg,#2ECC71 0%,#1a8045 100%); }
.theme-green .big-statement em { color:var(--green); }
.theme-green .pill { background:rgba(46,204,113,0.12); color:#1a8045; }
.theme-green .icon-card .ic-icon { color:var(--green); }

/* Timeline strip */
.timeline-strip {
  display:flex; align-items:stretch; gap:0;
  background:white; border-radius:10px;
  overflow:hidden; box-shadow:0 2px 14px rgba(0,0,0,0.06);
}
.tl-col {
  flex:1; padding:4% 4%; border-right:1px solid #eee;
  display:flex; flex-direction:column; gap:4px;
}
.tl-col:last-child { border-right:none; }
.tl-period {
  font-size:clamp(10px, 1.2vw, 17px);
  font-weight:700; color:var(--navy);
  margin-bottom:4px;
}
.tl-col ul { list-style:none; display:flex; flex-direction:column; gap:3px; }
.tl-col ul li {
  font-size:clamp(8px, 0.85vw, 12px); color:var(--mid);
  padding-left:10px; position:relative; line-height:1.4;
}
.tl-col ul li::before {
  content:'▸'; position:absolute; left:0;
  font-size:8px; top:2px;
}
.theme-gold .tl-col ul li::before { color:var(--gold); }
.theme-gold .tl-period { border-bottom:2px solid var(--gold); padding-bottom:4px; }

/* 4-week bar */
.week-bar {
  display:flex; gap:2%; background:white;
  border-radius:10px; padding:4% 5%;
  box-shadow:0 2px 14px rgba(0,0,0,0.06);
}
.week-item { flex:1; display:flex; flex-direction:column; align-items:center; gap:4px; }
.week-dot {
  width:clamp(28px,3.5vw,48px); height:clamp(28px,3.5vw,48px);
  border-radius:50%; display:flex; align-items:center; justify-content:center;
  font-weight:700; font-size:clamp(10px,1.2vw,16px); color:white;
}
.week-label {
  font-size:clamp(8px,0.85vw,12px); color:var(--mid);
  text-align:center; line-height:1.3;
}
.week-connector {
  flex:0.3; display:flex; align-items:center; padding-top:14px;
}
.week-connector::after { content:''; display:block; height:2px; width:100%; background:#e5e7eb; }

/* Module steps */
.module-steps {
  display:flex; flex-direction:column; gap:2.5%; flex:1;
}
.mod-row {
  display:flex; align-items:center; gap:3%;
  background:white; border-radius:8px;
  padding:3.5% 4%; box-shadow:0 1px 8px rgba(0,0,0,0.05);
  flex:1;
}
.mod-num {
  font-family:'Playfair Display',serif;
  font-size:clamp(18px,2.5vw,36px);
  font-weight:900; opacity:0.2; min-width:clamp(28px,3vw,44px);
  line-height:1;
}
.mod-content { flex:1; }
.mod-content .mod-title {
  font-weight:700; color:var(--navy);
  font-size:clamp(11px,1.2vw,17px); line-height:1.1;
}
.mod-content .mod-items {
  font-size:clamp(9px,0.9vw,12px); color:var(--mid);
  margin-top:2px; line-height:1.3;
}

/* FINAL SLIDE */
.s-final {
  background:linear-gradient(140deg,#061630 0%,#0D2B5E 60%,#061630 100%);
  flex-direction:column; align-items:center; justify-content:center;
  text-align:center; gap:3%;
}
.s-final::before {
  content:''; position:absolute; inset:0;
  background:radial-gradient(ellipse 60% 70% at 50% 50%, rgba(26,172,170,0.18) 0%,transparent 70%);
}
.s-final img { height:clamp(60px,8vw,110px); position:relative; z-index:2; animation:float 3.5s ease-in-out infinite; }
.s-final h2 {
  font-family:'Playfair Display',serif;
  font-size:clamp(28px,4.5vw,64px); color:white; font-weight:900;
  line-height:1.1; position:relative; z-index:2;
}
.s-final h2 span {
  background:linear-gradient(90deg,var(--teal-light),var(--gold-light));
  -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
}
.s-final .final-tagline {
  font-size:clamp(12px,1.5vw,21px);
  color:rgba(255,255,255,0.4); letter-spacing:3px;
  position:relative; z-index:2; font-weight:300;
}
.s-final .final-web {
  font-size:clamp(11px,1.2vw,17px);
  color:var(--teal-light); letter-spacing:4px;
  position:relative; z-index:2;
}
</style>
</head>
<body>

<button id="fsBtn" onclick="toggleFS()" title="Tam ekran (F)">⛶</button>

<div id="slideshow-wrapper"><div id="slideshow">

<!-- ═══════════════════════════════════════
     SLIDE 1 — COVER
═══════════════════════════════════════ -->
<div class="slide s-cover active">
  <img class="cover-logo" src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo-w.png" alt="GENZA e.V.">
  <div class="cover-sub"> </div>
  <h1><span>Geleceğimizi</span><br>birlikte inşa ediyoruz.</h1>
  <div class="bg-year">2026</div>
</div>

<!-- ═══════════════════════════════════════
     SLIDE 2 — OVERVIEW
═══════════════════════════════════════ -->
<div class="slide s-overview">
  <div class="slide-topbar">
    <div>
      <div class="eyebrow">2026 Projelerimiz</div>
      <div class="slide-title">5 Proje.<br>Bir Amaç.</div>
    </div>
    <img class="logo-img" src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo.png" alt="GENZA e.V.">
  </div>
  <div class="overview-grid">
    <div class="ov-card">
      <div class="ov-num">01</div>
      <h3>Yeni Gelenler için<br>Yol Haritası</h3>
      <div class="ov-name">Koray Çelebi</div>
    </div>
    <div class="ov-card">
      <div class="ov-num">02</div>
      <h3>Webinarlar</h3>
      <div class="ov-name">Emirhan Yasdıman</div>
    </div>
    <div class="ov-card">
      <div class="ov-num">03</div>
      <h3>Psikolojik<br>Dayanıklılık</h3>
      <div class="ov-name">Psk. Zeynep Demir</div>
    </div>
    <div class="ov-card">
      <div class="ov-num">04</div>
      <h3>İş Dünyasına<br>Entegrasyon</h3>
      <div class="ov-name">Umut Tekin</div>
    </div>
    <div class="ov-card">
      <div class="ov-num">05</div>
      <h3>Girişimci<br>Göçmenler</h3>
      <div class="ov-name">Alper Karanlık</div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════
     SLIDE 3 — PROJE 01: YOL HARİTASI
═══════════════════════════════════════ -->
<div class="slide s-proj theme-teal">
  <div class="proj-left">
    <div class="proj-big-num">01</div>
    <div class="proj-eyebrow">Proje 01</div>
    <div class="proj-divider"></div>
    <h2>Yeni Gelenler<br>için<br>Yol Haritası</h2>
    <div class="proj-presenter">Koray Çelebi</div>
  </div>
  <div class="proj-right">
    <div class="logo-row"><img class="logo-img" src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo.png" alt="GENZA e.V."></div>
    <div class="big-statement">
      <em>"Nereden başlamalıyım?"</em><br>sorusuna net bir yanıt.
    </div>
    <div class="icon-grid cols-4" style="flex:1">
      <div class="icon-card">
        <div class="ic-icon">🏠</div>
        <div class="ic-title">İkamet<br>& Kayıt</div>
        <div class="ic-desc">Anmeldung, belgeler, sık hatalar</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">💼</div>
        <div class="ic-title">Vergi<br>& Sigorta</div>
        <div class="ic-desc">Steuer-ID, Krankenversicherung</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">🏦</div>
        <div class="ic-title">Banka<br>& İş Hayatı</div>
        <div class="ic-desc">Hesap açma, iş sözleşmesi</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">🌱</div>
        <div class="ic-title">Uyum<br>& Gelecek</div>
        <div class="ic-desc">Kültürel adaptasyon, uzun vade</div>
      </div>
    </div>
    <div class="pill-row">
      <span class="pill">9 Konu Başlığı</span>
      <span class="pill">Tek Kaynak</span>
      <span class="pill">Sade & Güvenilir</span>
      <span class="pill">Doğru Sırayla</span>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════
     SLIDE 4 — PROJE 02: WEBİNARLAR
═══════════════════════════════════════ -->
<div class="slide s-proj theme-gold">
  <div class="proj-left">
    <div class="proj-big-num">02</div>
    <div class="proj-eyebrow">Proje 02</div>
    <div class="proj-divider"></div>
    <h2>Webinarlar</h2>
    <div class="proj-presenter">Emirhan Yasdıman</div>
  </div>
  <div class="proj-right">
    <div class="logo-row"><img class="logo-img" src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo.png" alt="GENZA e.V."></div>
    <div class="big-statement">
      Göç yolculuğunun <em>her aşamasında</em><br>uzman rehberliği.
    </div>
    <div class="timeline-strip">
      <div class="tl-col">
        <div class="tl-period">İlk 6 Ay</div>
        <ul>
          <li>Ev bulma</li>
          <li>Anmeldung & Steuer-ID</li>
          <li>Sağlık & banka</li>
          <li>Sosyal yaşam</li>
          <li>Ulaşım & internet</li>
          <li>Dil kursu</li>
          <li>Diploma denklik</li>
        </ul>
      </div>
      <div class="tl-col">
        <div class="tl-period">6 – 24 Ay</div>
        <ul>
          <li>Vergi beyannamesi</li>
          <li>Ehliyet & araba</li>
          <li>Süresiz oturum</li>
          <li>Sigortalar</li>
        </ul>
      </div>
      <div class="tl-col">
        <div class="tl-period">24+ Ay</div>
        <ul>
          <li>Ev alma</li>
          <li>Vatandaşlık</li>
          <li>Gayrimenkul yatırımı</li>
          <li>Hisse & fon</li>
          <li>Veraset yönetimi</li>
        </ul>
      </div>
    </div>
    <div class="pill-row">
      <span class="pill">Online</span>
      <span class="pill">Uzman Kadrosu</span>
      <span class="pill">Soru & Cevap</span>
      <span class="pill">Aşamalı Program</span>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════
     SLIDE 5 — PROJE 03: PSİKOLOJİK DAYANIKLILIK
═══════════════════════════════════════ -->
<div class="slide s-proj theme-violet">
  <div class="proj-left">
    <div class="proj-big-num">03</div>
    <div class="proj-eyebrow">Proje 03</div>
    <div class="proj-divider"></div>
    <h2>Psikolojik<br>Dayanıklılık</h2>
    <div class="proj-presenter">Psk. Zeynep Demir<br>Başlangıç: 7 Nisan 2026</div>
  </div>
  <div class="proj-right">
    <div class="logo-row"><img class="logo-img" src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo.png" alt="GENZA e.V."></div>
    <div class="big-statement">
      Göçün <em>duygusal yükünü</em><br>birlikte taşıyoruz.
    </div>
    <div class="icon-grid cols-3" style="flex:1">
      <div class="icon-card">
        <div class="ic-icon">🤝</div>
        <div class="ic-title">Destek Grubu</div>
        <div class="ic-desc">Online · 8–12 kişi<br>4 hafta · 90 dk/seans<br>Mayıs 2026</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">🎨</div>
        <div class="ic-title">Atölyeler</div>
        <div class="ic-desc">Kimlik & Uyum<br>Ebeveyn Olmak<br>İçsel Dayanıklılık<br>Ekim 2026</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">🌟</div>
        <div class="ic-title">Mentörlük</div>
        <div class="ic-desc">Deneyimli göçmenlerden yeni gelenlere destek<br>Ekim 2026</div>
      </div>
    </div>
    <div class="week-bar">
      <div class="week-item">
        <div class="week-dot" style="background:var(--violet)">H1</div>
        <div class="week-label">Göç deneyimini anlamak</div>
      </div>
      <div class="week-connector"></div>
      <div class="week-item">
        <div class="week-dot" style="background:var(--violet)">H2</div>
        <div class="week-label">Yabancılık & Aidiyet</div>
      </div>
      <div class="week-connector"></div>
      <div class="week-item">
        <div class="week-dot" style="background:var(--violet)">H3</div>
        <div class="week-label">Dayanıklılık & Kaynaklar</div>
      </div>
      <div class="week-connector"></div>
      <div class="week-item">
        <div class="week-dot" style="background:var(--violet)">H4</div>
        <div class="week-label">Geleceğe Bakmak</div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════
     SLIDE 6 — PROJE 04: ENTEGRASYON
═══════════════════════════════════════ -->
<div class="slide s-proj theme-rose">
  <div class="proj-left">
    <div class="proj-big-num">04</div>
    <div class="proj-eyebrow">Proje 04</div>
    <div class="proj-divider"></div>
    <h2>İş Dünyasına<br>Entegrasyon</h2>
    <div class="proj-presenter">Umut Tekin<br>Nisan 2026</div>
  </div>
  <div class="proj-right">
    <div class="logo-row"><img class="logo-img" src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo.png" alt="GENZA e.V."></div>
    <div class="big-statement">
      İlk başvurudan <em>kariyer gelişimine</em><br>5 adımda tam destek.
    </div>
    <div class="module-steps">
      <div class="mod-row">
        <div class="mod-num" style="color:var(--rose)">1</div>
        <div class="mod-content">
          <div class="mod-title">Mesleki Yeterlilik</div>
          <div class="mod-items">Diploma denklik · Çalışan hakları · Mentör eşleşmesi</div>
        </div>
      </div>
      <div class="mod-row">
        <div class="mod-num" style="color:var(--rose)">2</div>
        <div class="mod-content">
          <div class="mod-title">CV & İş Arama</div>
          <div class="mod-items">Almanca CV · İş başvurusu · Başvuru mektubu</div>
        </div>
      </div>
      <div class="mod-row">
        <div class="mod-num" style="color:var(--rose)">3</div>
        <div class="mod-content">
          <div class="mod-title">Mülakat & Başvuru</div>
          <div class="mod-items">İş başvuruları · Mülakat simülasyonları</div>
        </div>
      </div>
      <div class="mod-row">
        <div class="mod-num" style="color:var(--rose)">4</div>
        <div class="mod-content">
          <div class="mod-title">İş Kontratı & Entegrasyon</div>
          <div class="mod-items">Kontrat · On-boarding · İş yeri uyumu</div>
        </div>
      </div>
      <div class="mod-row">
        <div class="mod-num" style="color:var(--rose)">5</div>
        <div class="mod-content">
          <div class="mod-title">Kariyer Gelişimi</div>
          <div class="mod-items">Mesleki eğitimler · Meslek odaları · Terfi & maaş görüşmesi</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════
     SLIDE 7 — PROJE 05: GİRİŞİMCİLER
═══════════════════════════════════════ -->
<div class="slide s-proj theme-green">
  <div class="proj-left">
    <div class="proj-big-num">05</div>
    <div class="proj-eyebrow">Proje 05</div>
    <div class="proj-divider"></div>
    <h2>Girişimci<br>Göçmenler<br>Programı</h2>
    <div class="proj-presenter">Alper Karanlık<br>8 Ay · Sertifikalı</div>
  </div>
  <div class="proj-right">
    <div class="logo-row"><img class="logo-img" src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo.png" alt="GENZA e.V."></div>
    <div class="big-statement">
      8 aylık program ile fikrinizi<br><em>ölçeklenebilir bir iş modeline</em><br>dönüştürün ve somut çıktılarla mezun olun.
    </div>
    <div class="icon-grid cols-4" style="flex:1">
      <div class="icon-card">
        <div class="ic-icon">🏢</div>
        <div class="ic-title">Şirket<br>Kuruluşu</div>
        <div class="ic-desc">GmbH, UG, Einzelunternehmen</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">📊</div>
        <div class="ic-title">Finansal<br>Plan</div>
        <div class="ic-desc">12 ay cashflow + 36 ay projeksiyon</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">🚀</div>
        <div class="ic-title">Go-to-<br>Market</div>
        <div class="ic-desc">ICP · Satış hunisi · Pazarlama</div>
      </div>
      <div class="icon-card">
        <div class="ic-icon">🎤</div>
        <div class="ic-title">Demo<br>Day</div>
        <div class="ic-desc">Pitch deck + 3 dk sunum · Sertifika</div>
      </div>
    </div>
    <div class="pill-row">
      <span class="pill">8 Ay</span>
      <span class="pill">Ayda 2 Ders</span>
      <span class="pill">Workshop & Q&A</span>
      <span class="pill">Milestone Review</span>
      <span class="pill">Sertifika</span>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════
     SLIDE 8 — FINAL
═══════════════════════════════════════ -->
<div class="slide s-final">
  <img src="https://www.genza-ev.de/wp-content/uploads/2024/12/Genza-Logo-w.png" alt="GENZA e.V.">
  <h2>Birlikte daha güçlü,<br><span>birlikte daha ileri.</span></h2>
  <div class="final-tagline">Gemeinsam ein Netzwerk und eine Zukunft aufbauen.</div>
  <div class="final-web">genza-ev.de</div>
</div>

</div></div><!-- /slideshow-wrapper -->

<div id="controls">
  <button class="ctrl-btn" id="prevBtn" onclick="changeSlide(-1)" disabled>←</button>
  <div id="dots"></div>
  <button class="ctrl-btn" id="nextBtn" onclick="changeSlide(1)">→</button>
</div>
<div id="slide-indicator">1 / 8</div>
<div id="hint">← → gezin &nbsp;·&nbsp; F tam ekran</div>

<script>
let current = 0;
const slides = document.querySelectorAll('.slide');
const total = slides.length;

const dotsEl = document.getElementById('dots');
for (let i = 0; i < total; i++) {
  const d = document.createElement('div');
  d.className = 'dot' + (i===0?' active':'');
  d.onclick = () => goTo(i);
  dotsEl.appendChild(d);
}

function goTo(n) {
  slides[current].classList.remove('active');
  document.querySelectorAll('.dot')[current].classList.remove('active');
  current = n;
  slides[current].classList.add('active');
  document.querySelectorAll('.dot')[current].classList.add('active');
  document.getElementById('slide-indicator').textContent = (current+1)+' / '+total;
  document.getElementById('prevBtn').disabled = current===0;
  document.getElementById('nextBtn').disabled = current===total-1;
}
function changeSlide(d){ const n=current+d; if(n>=0&&n<total) goTo(n); }

document.addEventListener('keydown', e=>{
  if(e.key==='ArrowRight'||e.key==='ArrowDown') changeSlide(1);
  if(e.key==='ArrowLeft'||e.key==='ArrowUp') changeSlide(-1);
  if(e.key==='f'||e.key==='F') toggleFS();
});

function toggleFS(){
  if(!document.fullscreenElement) document.documentElement.requestFullscreen();
  else document.exitFullscreen();
}

function applyFSScale() {
  const sw = window.screen.width;
  const sh = window.screen.height;
  const scale = Math.min(sw / 1280, sh / 720);
  const ss = document.getElementById('slideshow');
  ss.style.transform = 'scale(' + scale + ')';
  ss.style.transformOrigin = 'center center';
}

function clearFSScale() {
  const ss = document.getElementById('slideshow');
  ss.style.transform = '';
  ss.style.transformOrigin = '';
}

document.addEventListener('fullscreenchange', () => {
  document.getElementById('fsBtn').textContent = document.fullscreenElement ? '✕' : '⛶';
  if (document.fullscreenElement) {
    applyFSScale();
  } else {
    clearFSScale();
  }
});
</script>
</body>
</html>
