<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Gautam Keshri — Data Scientist</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Playfair+Display:ital,wght@0,700;1,400&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#03060f;
  --bg2:#070d1a;
  --glass:rgba(255,255,255,0.05);
  --glass-b:rgba(255,255,255,0.10);
  --blue:#4f8ef7;
  --cyan:#22d3ee;
  --purple:#a78bfa;
  --gold:#fbbf24;
  --green:#34d399;
  --text:#e8edf5;
  --text2:#8899bb;
  --text3:#4a5a7a;
  --font:'Space Grotesk',sans-serif;
  --mono:'Space Mono',monospace;
  --serif:'Playfair Display',Georgia,serif;
}
html{scroll-behavior:smooth}
body{
  font-family:var(--font);
  background:var(--bg);
  color:var(--text);
  overflow-x:hidden;
  line-height:1.6;
}

/* ── CANVAS ── */
#bg-canvas{
  position:fixed;top:0;left:0;width:100%;height:100%;
  z-index:0;pointer-events:none;
}

/* ── LAYOUT ── */
.page{position:relative;z-index:1}

/* ── HERO ── */
.hero{
  min-height:100vh;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  text-align:center;
  padding:60px 24px;
  position:relative;
}
.hero-orb{
  position:absolute;
  border-radius:50%;
  filter:blur(80px);
  pointer-events:none;
  animation:orbFloat 8s ease-in-out infinite;
}
.hero-orb-1{
  width:500px;height:500px;
  background:radial-gradient(circle,rgba(79,142,247,0.18),transparent 70%);
  top:-100px;left:-150px;
  animation-delay:0s;
}
.hero-orb-2{
  width:400px;height:400px;
  background:radial-gradient(circle,rgba(167,139,250,0.15),transparent 70%);
  bottom:-80px;right:-100px;
  animation-delay:-3s;
}
.hero-orb-3{
  width:300px;height:300px;
  background:radial-gradient(circle,rgba(34,211,238,0.12),transparent 70%);
  top:50%;left:50%;transform:translate(-50%,-50%);
  animation-delay:-6s;
}
@keyframes orbFloat{
  0%,100%{transform:translateY(0) scale(1);}
  50%{transform:translateY(-30px) scale(1.05);}
}
.hero-badge{
  display:inline-flex;align-items:center;gap:8px;
  background:rgba(79,142,247,0.12);
  border:1px solid rgba(79,142,247,0.3);
  color:#93c5fd;
  font-size:11px;font-family:var(--mono);
  letter-spacing:0.12em;text-transform:uppercase;
  padding:7px 18px;border-radius:100px;
  margin-bottom:36px;
}
.live-dot{
  width:7px;height:7px;border-radius:50%;
  background:#4ade80;
  box-shadow:0 0 8px #4ade80;
  animation:livePulse 2s infinite;
}
@keyframes livePulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:0.5;transform:scale(0.8);}}

.hero-name{
  font-size:clamp(56px,9vw,120px);
  font-weight:700;
  letter-spacing:-0.04em;
  line-height:0.9;
  margin-bottom:8px;
  background:linear-gradient(135deg,#ffffff 0%,#c7d8ff 40%,#a78bfa 70%,#22d3ee 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
  animation:gradShift 6s ease-in-out infinite;
  background-size:200% 200%;
}
@keyframes gradShift{
  0%{background-position:0% 50%;}
  50%{background-position:100% 50%;}
  100%{background-position:0% 50%;}
}
.hero-sub{
  font-family:var(--serif);
  font-style:italic;
  font-size:clamp(18px,3vw,28px);
  color:var(--text2);
  margin:16px 0 48px;
}
.hero-chips{
  display:flex;flex-wrap:wrap;gap:12px;
  justify-content:center;margin-bottom:56px;
}
.chip{
  display:flex;align-items:center;gap:8px;
  background:var(--glass);
  border:1px solid var(--glass-b);
  backdrop-filter:blur(12px);
  padding:10px 20px;border-radius:100px;
  font-size:13px;color:var(--text2);
  transition:all 0.3s;
}
.chip:hover{background:rgba(255,255,255,0.1);color:var(--text);transform:translateY(-2px);}
.chip-icon{font-size:16px;}
.hero-cta{
  display:flex;gap:16px;flex-wrap:wrap;justify-content:center;
}
.btn-primary{
  padding:14px 36px;border-radius:100px;
  background:linear-gradient(135deg,#4f8ef7,#a78bfa);
  color:#fff;font-weight:600;font-size:14px;
  border:none;cursor:pointer;text-decoration:none;
  box-shadow:0 0 30px rgba(79,142,247,0.4);
  transition:all 0.3s;display:inline-block;
}
.btn-primary:hover{transform:translateY(-3px);box-shadow:0 0 50px rgba(79,142,247,0.6);}
.btn-outline{
  padding:14px 36px;border-radius:100px;
  background:transparent;
  color:var(--text);font-weight:600;font-size:14px;
  border:1px solid rgba(255,255,255,0.2);
  cursor:pointer;text-decoration:none;
  transition:all 0.3s;display:inline-block;
  backdrop-filter:blur(8px);
}
.btn-outline:hover{background:var(--glass);border-color:rgba(255,255,255,0.4);transform:translateY(-3px);}

/* ── SCROLL HINT ── */
.scroll-hint{
  position:absolute;bottom:36px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  color:var(--text3);font-size:11px;font-family:var(--mono);letter-spacing:0.1em;text-transform:uppercase;
  animation:fadeUpDown 2s ease-in-out infinite;
}
@keyframes fadeUpDown{0%,100%{opacity:0.4;transform:translateX(-50%) translateY(0);}50%{opacity:1;transform:translateX(-50%) translateY(-6px);}}
.scroll-line{width:1px;height:40px;background:linear-gradient(180deg,transparent,var(--blue));}

/* ── SECTION BASE ── */
.section{padding:100px 24px;max-width:1100px;margin:0 auto;}
.sec-label{
  font-family:var(--mono);font-size:11px;letter-spacing:0.18em;
  text-transform:uppercase;color:var(--blue);
  display:flex;align-items:center;gap:12px;margin-bottom:16px;
}
.sec-label::before{content:'';width:32px;height:1px;background:var(--blue);}
.sec-h{
  font-size:clamp(36px,5vw,60px);font-weight:700;
  letter-spacing:-0.03em;line-height:1.05;margin-bottom:60px;
}

/* ── STATS ROW ── */
.stats-row{
  display:grid;grid-template-columns:repeat(4,1fr);gap:2px;
  background:rgba(255,255,255,0.04);
  border:1px solid rgba(255,255,255,0.07);
  border-radius:20px;overflow:hidden;
  margin-bottom:100px;
}
.stat-cell{
  padding:40px 32px;
  background:var(--bg2);
  text-align:center;
  transition:background 0.3s;
  position:relative;
  overflow:hidden;
}
.stat-cell::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(79,142,247,0.06),transparent);
  opacity:0;transition:opacity 0.3s;
}
.stat-cell:hover::before{opacity:1;}
.stat-cell:hover{background:rgba(79,142,247,0.06);}
.stat-n{
  font-size:48px;font-weight:700;letter-spacing:-0.04em;
  line-height:1;margin-bottom:8px;
  background:linear-gradient(135deg,var(--blue),var(--cyan));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.stat-l{font-family:var(--mono);font-size:11px;letter-spacing:0.1em;text-transform:uppercase;color:var(--text3);}

/* ── 3D TILT CARDS (TECH) ── */
.tech-grid{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:20px;
}
.tilt-card{
  background:var(--glass);
  border:1px solid rgba(255,255,255,0.08);
  border-radius:20px;padding:32px 28px;
  backdrop-filter:blur(16px);
  transition:transform 0.1s ease,box-shadow 0.3s;
  cursor:default;
  transform-style:preserve-3d;
  will-change:transform;
}
.tilt-card:hover{box-shadow:0 20px 60px rgba(0,0,0,0.4),0 0 40px rgba(79,142,247,0.15);}
.tc-icon{font-size:28px;margin-bottom:16px;}
.tc-label{font-family:var(--mono);font-size:10px;letter-spacing:0.15em;text-transform:uppercase;color:var(--text3);margin-bottom:8px;}
.tc-title{font-size:17px;font-weight:600;color:var(--text);margin-bottom:20px;}
.pill-wrap{display:flex;flex-wrap:wrap;gap:8px;}
.p3d{
  font-family:var(--mono);font-size:11px;padding:5px 12px;
  border-radius:6px;border:1px solid;
  transition:all 0.25s;cursor:default;
}
.p3d:hover{transform:translateY(-2px) scale(1.05);}
.pb{background:rgba(79,142,247,0.12);color:#93c5fd;border-color:rgba(79,142,247,0.3);}
.pb:hover{background:rgba(79,142,247,0.25);}
.pp{background:rgba(167,139,250,0.12);color:#c4b5fd;border-color:rgba(167,139,250,0.3);}
.pp:hover{background:rgba(167,139,250,0.25);}
.pc{background:rgba(34,211,238,0.12);color:#67e8f9;border-color:rgba(34,211,238,0.3);}
.pc:hover{background:rgba(34,211,238,0.25);}
.pg{background:rgba(52,211,153,0.12);color:#6ee7b7;border-color:rgba(52,211,153,0.3);}
.pg:hover{background:rgba(52,211,153,0.25);}
.po{background:rgba(251,191,36,0.12);color:#fde68a;border-color:rgba(251,191,36,0.3);}
.po:hover{background:rgba(251,191,36,0.25);}

/* ── ABOUT SPLIT ── */
.about-split{
  display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:start;
}
.about-text{font-size:17px;line-height:1.8;color:var(--text2);}
.about-text strong{color:var(--text);font-weight:600;}
.about-text p{margin-bottom:20px;}
.code-window{
  background:#0d1117;border:1px solid rgba(255,255,255,0.08);
  border-radius:16px;overflow:hidden;
}
.cw-bar{
  background:#161b22;padding:14px 18px;
  display:flex;align-items:center;gap:8px;
  border-bottom:1px solid rgba(255,255,255,0.06);
}
.cw-dot{width:12px;height:12px;border-radius:50%;}
.cw-r{background:#ff5f57;}.cw-y{background:#febc2e;}.cw-g{background:#28c840;}
.cw-fn{font-family:var(--mono);font-size:12px;color:rgba(255,255,255,0.25);margin-left:10px;}
.cw-body{padding:24px 22px;}
pre.cw-pre{
  font-family:var(--mono);font-size:13px;line-height:2;
  color:#8b949e;white-space:pre-wrap;
}
.kw{color:#ff7b72;}.fn2{color:#79c0ff;}
.str{color:#a5d6ff;}.cm{color:#484f58;font-style:italic;}
.num{color:#ffa657;}

/* ── PROJECTS ── */
.proj-grid{display:flex;flex-direction:column;gap:20px;}
.proj-card{
  display:grid;grid-template-columns:auto 1fr auto;gap:32px;align-items:center;
  background:var(--glass);border:1px solid rgba(255,255,255,0.07);
  border-radius:20px;padding:32px 36px;
  backdrop-filter:blur(16px);
  transition:all 0.3s;position:relative;overflow:hidden;
  text-decoration:none;color:inherit;
}
.proj-card::before{
  content:'';position:absolute;left:0;top:0;bottom:0;width:3px;
  background:linear-gradient(180deg,var(--blue),var(--purple));
  border-radius:3px 0 0 3px;
  transform:scaleY(0);transition:transform 0.3s;
}
.proj-card:hover::before{transform:scaleY(1);}
.proj-card:hover{
  background:rgba(255,255,255,0.07);
  box-shadow:0 8px 40px rgba(0,0,0,0.3),0 0 0 1px rgba(79,142,247,0.2);
  transform:translateX(6px);
}
.proj-num{
  font-size:48px;font-weight:700;letter-spacing:-0.05em;
  color:rgba(255,255,255,0.05);font-family:var(--mono);
  transition:color 0.3s;
}
.proj-card:hover .proj-num{color:rgba(79,142,247,0.15);}
.proj-type{font-family:var(--mono);font-size:10px;letter-spacing:0.14em;text-transform:uppercase;color:var(--blue);margin-bottom:8px;}
.proj-name{font-size:20px;font-weight:600;color:var(--text);margin-bottom:10px;letter-spacing:-0.01em;}
.proj-desc{font-size:14px;color:var(--text2);line-height:1.6;margin-bottom:16px;}
.proj-tags-wrap{display:flex;flex-wrap:wrap;gap:6px;}
.proj-tag{font-family:var(--mono);font-size:11px;padding:3px 10px;background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.08);border-radius:4px;color:var(--text3);}
.proj-arrow{font-size:24px;color:var(--text3);transition:all 0.3s;flex-shrink:0;}
.proj-card:hover .proj-arrow{color:var(--blue);transform:translate(4px,-4px);}

/* ── WORKFLOW ── */
.flow-section{
  background:linear-gradient(180deg,transparent,rgba(79,142,247,0.04),transparent);
  border-top:1px solid rgba(255,255,255,0.05);
  border-bottom:1px solid rgba(255,255,255,0.05);
  padding:100px 24px;
}
.flow-inner{max-width:1100px;margin:0 auto;}
.flow-track{
  display:flex;align-items:flex-start;gap:0;
  position:relative;margin-top:20px;
}
.flow-track::before{
  content:'';position:absolute;
  top:36px;left:36px;right:36px;height:1px;
  background:linear-gradient(90deg,
    rgba(79,142,247,0.5),
    rgba(167,139,250,0.5),
    rgba(34,211,238,0.5),
    rgba(251,191,36,0.5),
    rgba(52,211,153,0.5),
    rgba(79,142,247,0.5)
  );
}
.flow-node{
  flex:1;display:flex;flex-direction:column;align-items:center;text-align:center;gap:16px;
}
.fn-circle{
  width:72px;height:72px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:20px;font-weight:700;font-family:var(--mono);
  position:relative;z-index:2;flex-shrink:0;
  transition:transform 0.3s;
}
.fn-circle:hover{transform:scale(1.15);}
.fnb{background:rgba(79,142,247,0.15);border:2px solid rgba(79,142,247,0.4);color:#93c5fd;box-shadow:0 0 20px rgba(79,142,247,0.2);}
.fnp{background:rgba(167,139,250,0.15);border:2px solid rgba(167,139,250,0.4);color:#c4b5fd;box-shadow:0 0 20px rgba(167,139,250,0.2);}
.fnc{background:rgba(34,211,238,0.15);border:2px solid rgba(34,211,238,0.4);color:#67e8f9;box-shadow:0 0 20px rgba(34,211,238,0.2);}
.fno{background:rgba(251,191,36,0.15);border:2px solid rgba(251,191,36,0.4);color:#fde68a;box-shadow:0 0 20px rgba(251,191,36,0.2);}
.fng{background:rgba(52,211,153,0.15);border:2px solid rgba(52,211,153,0.4);color:#6ee7b7;box-shadow:0 0 20px rgba(52,211,153,0.2);}
.fn-title{font-size:13px;font-weight:600;color:var(--text);}
.fn-sub{font-size:11px;color:var(--text3);font-family:var(--mono);line-height:1.5;}

/* ── GOALS ── */
.goals-split{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:start;}
.goal-item{
  display:flex;align-items:flex-start;gap:16px;
  padding:20px;border-radius:14px;
  border:1px solid rgba(255,255,255,0.06);
  background:var(--glass);backdrop-filter:blur(8px);
  margin-bottom:12px;
  transition:all 0.3s;
}
.goal-item:hover{background:rgba(255,255,255,0.07);border-color:rgba(79,142,247,0.3);transform:translateX(4px);}
.goal-icon{
  width:40px;height:40px;border-radius:10px;
  display:flex;align-items:center;justify-content:center;font-size:18px;
  flex-shrink:0;background:rgba(79,142,247,0.1);
}
.goal-t{font-size:15px;font-weight:600;color:var(--text);margin-bottom:4px;}
.goal-s{font-size:13px;color:var(--text3);line-height:1.5;}
.quote-card{
  background:linear-gradient(135deg,rgba(79,142,247,0.1),rgba(167,139,250,0.1));
  border:1px solid rgba(79,142,247,0.2);
  border-radius:20px;padding:40px 36px;
  backdrop-filter:blur(16px);
}
.q-mark{font-size:72px;font-family:var(--serif);color:rgba(79,142,247,0.3);line-height:0.8;margin-bottom:16px;}
.q-text{font-family:var(--serif);font-style:italic;font-size:22px;line-height:1.5;color:var(--text);margin-bottom:24px;}
.q-attr{font-family:var(--mono);font-size:12px;color:var(--text3);}
.roles-list{margin-top:28px;display:flex;flex-direction:column;gap:8px;}
.role-r{
  display:flex;align-items:center;justify-content:space-between;
  padding:14px 18px;
  background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.07);
  border-radius:10px;font-size:14px;color:var(--text2);
  transition:all 0.25s;
}
.role-r:hover{background:rgba(79,142,247,0.08);color:var(--text);border-color:rgba(79,142,247,0.25);}
.role-dot{width:8px;height:8px;border-radius:50%;background:#4ade80;box-shadow:0 0 8px #4ade80;}

/* ── CONNECT ── */
.connect-bg{
  background:linear-gradient(180deg,transparent,rgba(79,142,247,0.04));
  padding:100px 24px 0;
}
.connect-inner{max-width:1100px;margin:0 auto;}
.connect-grid{
  display:grid;grid-template-columns:repeat(2,1fr);gap:16px;margin-top:48px;
}
.connect-c{
  display:flex;align-items:center;gap:20px;
  padding:28px 28px;
  background:var(--glass);border:1px solid rgba(255,255,255,0.07);
  border-radius:18px;backdrop-filter:blur(16px);
  text-decoration:none;color:inherit;
  transition:all 0.3s;
  transform-style:preserve-3d;
}
.connect-c:hover{
  background:rgba(255,255,255,0.08);
  border-color:rgba(79,142,247,0.3);
  box-shadow:0 0 0 1px rgba(79,142,247,0.2),0 20px 40px rgba(0,0,0,0.3);
  transform:translateY(-4px);
}
.cc-icon{
  width:52px;height:52px;border-radius:14px;
  display:flex;align-items:center;justify-content:center;font-size:22px;
  background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.08);
  flex-shrink:0;transition:all 0.3s;
}
.connect-c:hover .cc-icon{background:rgba(79,142,247,0.15);border-color:rgba(79,142,247,0.3);}
.cc-plat{font-family:var(--mono);font-size:10px;letter-spacing:0.1em;text-transform:uppercase;color:var(--text3);margin-bottom:4px;}
.cc-handle{font-size:16px;font-weight:600;color:var(--text);}
.cc-arr{margin-left:auto;color:var(--text3);font-size:20px;transition:all 0.3s;}
.connect-c:hover .cc-arr{color:var(--blue);transform:translate(4px,-4px);}

/* ── FOOTER ── */
footer{
  max-width:1100px;margin:0 auto;
  padding:60px 24px 48px;
  display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:20px;
  border-top:1px solid rgba(255,255,255,0.06);margin-top:80px;
}
.footer-l .fn{font-size:22px;font-weight:700;background:linear-gradient(90deg,var(--blue),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.footer-l .fs{font-family:var(--mono);font-size:11px;color:var(--text3);margin-top:4px;letter-spacing:0.06em;}
.footer-copy{font-family:var(--mono);font-size:11px;color:var(--text3);}

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .stats-row{grid-template-columns:1fr 1fr;}
  .about-split,.goals-split{grid-template-columns:1fr;}
  .connect-grid{grid-template-columns:1fr;}
  .proj-card{grid-template-columns:1fr;gap:16px;}
  .proj-num,.proj-arrow{display:none;}
  .flow-track{flex-wrap:wrap;justify-content:center;gap:24px;}
  .flow-track::before{display:none;}
  .flow-node{min-width:100px;}
}
</style>
</head>
<body>

<canvas id="bg-canvas"></canvas>

<div class="page">

<!-- ── HERO ── -->
<section class="hero">
  <div class="hero-orb hero-orb-1"></div>
  <div class="hero-orb hero-orb-2"></div>
  <div class="hero-orb hero-orb-3"></div>

  <div class="hero-badge">
    <div class="live-dot"></div>
    Open to internships &amp; entry-level roles
  </div>

  <h1 class="hero-name">Gautam Keshri</h1>

  <p class="hero-sub">Data Scientist &amp; Machine Learning Enthusiast</p>

  <div class="hero-chips">
    <div class="chip"><span class="chip-icon">🏛️</span> IIT Guwahati</div>
    <div class="chip"><span class="chip-icon">📊</span> B.Sc. (Hons) DS &amp; AI</div>
    <div class="chip"><span class="chip-icon">📍</span> India</div>
    <div class="chip"><span class="chip-icon">🤖</span> ML Enthusiast</div>
  </div>

  <div class="hero-cta">
    <a href="#connect" class="btn-primary">Get in Touch</a>
    <a href="#projects" class="btn-outline">View Projects</a>
  </div>

  <div class="scroll-hint">
    <div class="scroll-line"></div>
    scroll
  </div>
</section>

<!-- ── STATS ── -->
<div style="max-width:1100px;margin:0 auto;padding:0 24px;">
  <div class="stats-row">
    <div class="stat-cell"><div class="stat-n">15+</div><div class="stat-l">Projects Shipped</div></div>
    <div class="stat-cell"><div class="stat-n">87%</div><div class="stat-l">Avg Accuracy</div></div>
    <div class="stat-cell"><div class="stat-n">5+</div><div class="stat-l">Tools Mastered</div></div>
    <div class="stat-cell"><div class="stat-n">∞</div><div class="stat-l">Curiosity</div></div>
  </div>
</div>

<!-- ── ABOUT ── -->
<section class="section">
  <div class="sec-label">01 — About me</div>
  <h2 class="sec-h">Turning data into<br><span style="background:linear-gradient(90deg,var(--blue),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">real decisions</span></h2>
  <div class="about-split">
    <div class="about-text">
      <p>I'm a data science student at <strong>IIT Guwahati</strong> who believes the most powerful thing you can do with numbers is tell a story that changes how people act.</p>
      <p>I obsess over the gap between raw data and <strong>real business impact</strong> — and I spend most of my time trying to close it with ML, visualization, and sharp analytical thinking.</p>
      <p>Passionate about <strong>data-driven decisions</strong>, I love working on problems where analysis meets storytelling and the output actually moves something in the real world.</p>
    </div>
    <div class="code-window">
      <div class="cw-bar">
        <div class="cw-dot cw-r"></div><div class="cw-dot cw-y"></div><div class="cw-dot cw-g"></div>
        <span class="cw-fn">gautam.py</span>
      </div>
      <div class="cw-body">
<pre class="cw-pre"><span class="kw">class</span> <span class="fn2">GautamKeshri</span>:
  <span class="kw">def</span> <span class="fn2">__init__</span>(self):
    self.name    = <span class="str">"Gautam Keshri"</span>
    self.role    = <span class="str">"Data Scientist"</span>
    self.edu     = <span class="str">"IIT Guwahati"</span>
    self.degree  = <span class="str">"B.Sc. DS & AI"</span>
    self.langs   = [<span class="str">"Python"</span>, <span class="str">"SQL"</span>]
    self.open    = <span class="num">True</span>

  <span class="kw">def</span> <span class="fn2">greet</span>(self) -> <span class="fn2">str</span>:
    <span class="cm"># Thanks for visiting!</span>
    <span class="kw">return</span> (
      <span class="str">"Let's turn data"</span>
      <span class="str">" into impact 🚀"</span>
    )

me = <span class="fn2">GautamKeshri</span>()
<span class="fn2">print</span>(me.greet())</pre>
      </div>
    </div>
  </div>
</section>

<!-- ── TECH ── -->
<section class="section" style="padding-top:0;">
  <div class="sec-label">02 — Stack</div>
  <h2 class="sec-h">My tool belt</h2>
  <div class="tech-grid" id="tilt-grid">
    <div class="tilt-card">
      <div class="tc-icon">🐍</div>
      <div class="tc-label">Core</div>
      <div class="tc-title">Languages &amp; Analysis</div>
      <div class="pill-wrap">
        <span class="p3d pb">Python</span>
        <span class="p3d pb">Pandas</span>
        <span class="p3d pb">NumPy</span>
        <span class="p3d pb">SQL</span>
        <span class="p3d pb">R</span>
      </div>
    </div>
    <div class="tilt-card">
      <div class="tc-icon">🤖</div>
      <div class="tc-label">AI / ML</div>
      <div class="tc-title">Machine Learning</div>
      <div class="pill-wrap">
        <span class="p3d pp">Scikit-Learn</span>
        <span class="p3d pp">TensorFlow</span>
        <span class="p3d pp">PyTorch</span>
        <span class="p3d pp">Keras</span>
        <span class="p3d pp">XGBoost</span>
      </div>
    </div>
    <div class="tilt-card">
      <div class="tc-icon">📊</div>
      <div class="tc-label">Viz &amp; BI</div>
      <div class="tc-title">Visualization</div>
      <div class="pill-wrap">
        <span class="p3d po">Power BI</span>
        <span class="p3d po">Tableau</span>
        <span class="p3d po">Matplotlib</span>
        <span class="p3d po">Seaborn</span>
        <span class="p3d po">Plotly</span>
      </div>
    </div>
    <div class="tilt-card">
      <div class="tc-icon">🗄️</div>
      <div class="tc-label">Data Layer</div>
      <div class="tc-title">Databases</div>
      <div class="pill-wrap">
        <span class="p3d pc">MySQL</span>
        <span class="p3d pc">PostgreSQL</span>
        <span class="p3d pc">MongoDB</span>
        <span class="p3d pc">SQL Server</span>
      </div>
    </div>
    <div class="tilt-card">
      <div class="tc-icon">⚙️</div>
      <div class="tc-label">DevOps</div>
      <div class="tc-title">Tools &amp; Platforms</div>
      <div class="pill-wrap">
        <span class="p3d pg">Git</span>
        <span class="p3d pg">Docker</span>
        <span class="p3d pg">AWS</span>
        <span class="p3d pg">Jupyter</span>
        <span class="p3d pg">Kaggle</span>
      </div>
    </div>
    <div class="tilt-card">
      <div class="tc-icon">🚀</div>
      <div class="tc-label">Learning now</div>
      <div class="tc-title">Leveling Up</div>
      <div class="pill-wrap">
        <span class="p3d pb">MLOps</span>
        <span class="p3d pp">LLMs</span>
        <span class="p3d pc">Azure</span>
        <span class="p3d pg">Deep Learning</span>
      </div>
    </div>
  </div>
</section>

<!-- ── PROJECTS ── -->
<section class="section" style="padding-top:0;" id="projects">
  <div class="sec-label">03 — Work</div>
  <h2 class="sec-h">Selected projects</h2>
  <div class="proj-grid">
    <div class="proj-card">
      <div class="proj-num">01</div>
      <div>
        <div class="proj-type">SQL · Analytics · Power BI</div>
        <div class="proj-name">Pizza Sales Analysis</div>
        <div class="proj-desc">End-to-end BI pipeline analysing order patterns, revenue trends, and peak-hour behaviour to drive operational decisions for a restaurant chain.</div>
        <div class="proj-tags-wrap">
          <span class="proj-tag">MySQL</span><span class="proj-tag">Power BI</span><span class="proj-tag">EDA</span><span class="proj-tag">Dashboarding</span>
        </div>
      </div>
      <div class="proj-arrow">↗</div>
    </div>
    <div class="proj-card">
      <div class="proj-num">02</div>
      <div>
        <div class="proj-type">Python · ML · Clustering</div>
        <div class="proj-name">Customer Shopping Behavior</div>
        <div class="proj-desc">Segmentation and predictive modelling of customer purchase intent, identifying high-value clusters and recommending personalised engagement strategies.</div>
        <div class="proj-tags-wrap">
          <span class="proj-tag">Pandas</span><span class="proj-tag">Scikit-Learn</span><span class="proj-tag">Seaborn</span><span class="proj-tag">K-Means</span>
        </div>
      </div>
      <div class="proj-arrow">↗</div>
    </div>
    <div class="proj-card">
      <div class="proj-num">03</div>
      <div>
        <div class="proj-type">Python · Automation · Database</div>
        <div class="proj-name">Hospital DB Migration &amp; Automation System</div>
        <div class="proj-desc">Full automated pipeline migrating fragmented hospital records across legacy systems — with validation, deduplication, and real-time dashboards. Reduced manual effort by 70%.</div>
        <div class="proj-tags-wrap">
          <span class="proj-tag">PostgreSQL</span><span class="proj-tag">ETL</span><span class="proj-tag">Python</span><span class="proj-tag">Data Quality</span><span class="proj-tag">Automation</span>
        </div>
      </div>
      <div class="proj-arrow">↗</div>
    </div>
  </div>
</section>

<!-- ── WORKFLOW ── -->
<section class="flow-section">
  <div class="flow-inner">
    <div class="sec-label">04 — Process</div>
    <h2 class="sec-h" style="margin-bottom:72px;">How I work</h2>
    <div class="flow-track">
      <div class="flow-node"><div class="fn-circle fnb">01</div><div class="fn-title">Collect</div><div class="fn-sub">Source &amp;<br>ingest</div></div>
      <div class="flow-node"><div class="fn-circle fnp">02</div><div class="fn-title">Clean</div><div class="fn-sub">Wrangle &amp;<br>validate</div></div>
      <div class="flow-node"><div class="fn-circle fnc">03</div><div class="fn-title">Explore</div><div class="fn-sub">EDA &amp;<br>hypothesis</div></div>
      <div class="flow-node"><div class="fn-circle fno">04</div><div class="fn-title">Model</div><div class="fn-sub">Build &amp;<br>tune</div></div>
      <div class="flow-node"><div class="fn-circle fng">05</div><div class="fn-title">Visualise</div><div class="fn-sub">Tell the<br>story</div></div>
      <div class="flow-node"><div class="fn-circle fnb">06</div><div class="fn-title">Impact</div><div class="fn-sub">Drive<br>decisions</div></div>
    </div>
  </div>
</section>

<!-- ── GOALS ── -->
<section class="section">
  <div class="sec-label">05 — Direction</div>
  <h2 class="sec-h">Where I'm headed</h2>
  <div class="goals-split">
    <div>
      <div class="goal-item"><div class="goal-icon">🧠</div><div><div class="goal-t">Advanced Machine Learning</div><div class="goal-s">Deep ensembles, gradient boosting, model interpretability.</div></div></div>
      <div class="goal-item"><div class="goal-icon">🔥</div><div><div class="goal-t">Deep Learning with PyTorch</div><div class="goal-s">CNNs, transformers, and NLP pipelines end-to-end.</div></div></div>
      <div class="goal-item"><div class="goal-icon">☁️</div><div><div class="goal-t">Cloud Computing (AWS / Azure)</div><div class="goal-s">Deploying scalable ML pipelines in production.</div></div></div>
      <div class="goal-item"><div class="goal-icon">🐳</div><div><div class="goal-t">MLOps &amp; Model Deployment</div><div class="goal-s">CI/CD for models, monitoring, drift detection.</div></div></div>
      <div class="goal-item"><div class="goal-icon">💻</div><div><div class="goal-t">Advanced SQL &amp; DB Design</div><div class="goal-s">Query optimization, indexing, warehouse modelling.</div></div></div>
    </div>
    <div>
      <div class="quote-card">
        <div class="q-mark">"</div>
        <div class="q-text">Data is only valuable when it drives action.</div>
        <div class="q-attr">— Gautam Keshri</div>
        <div class="roles-list">
          <div class="role-r"><span>Data Analyst Intern</span><div class="role-dot"></div></div>
          <div class="role-r"><span>Data Science Intern</span><div class="role-dot"></div></div>
          <div class="role-r"><span>Junior Data Scientist</span><div class="role-dot"></div></div>
          <div class="role-r"><span>BI Analyst</span><div class="role-dot"></div></div>
          <div class="role-r"><span>ML Engineer (Entry Level)</span><div class="role-dot"></div></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ── CONNECT ── -->
<section class="connect-bg" id="connect">
  <div class="connect-inner">
    <div class="sec-label">06 — Contact</div>
    <h2 class="sec-h">Let's build something<br><span style="background:linear-gradient(90deg,var(--cyan),var(--blue));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">meaningful together</span></h2>
    <div class="connect-grid">
      <a class="connect-c" href="https://www.linkedin.com/in/gautam-keshri" target="_blank">
        <div class="cc-icon">💼</div>
        <div><div class="cc-plat">LinkedIn</div><div class="cc-handle">gautam-keshri</div></div>
        <div class="cc-arr">↗</div>
      </a>
      <a class="connect-c" href="https://github.com/Gautam825406" target="_blank">
        <div class="cc-icon">🐙</div>
        <div><div class="cc-plat">GitHub</div><div class="cc-handle">Gautam825406</div></div>
        <div class="cc-arr">↗</div>
      </a>
      <a class="connect-c" href="mailto:gautam.keshri@example.com">
        <div class="cc-icon">📬</div>
        <div><div class="cc-plat">Email</div><div class="cc-handle">gautam.keshri</div></div>
        <div class="cc-arr">↗</div>
      </a>
      <a class="connect-c" href="https://www.kaggle.com/keshrigautam2000" target="_blank">
        <div class="cc-icon">📈</div>
        <div><div class="cc-plat">Kaggle</div><div class="cc-handle">keshrigautam2000</div></div>
        <div class="cc-arr">↗</div>
      </a>
    </div>
  </div>
</section>

<!-- ── FOOTER ── -->
<footer>
  <div class="footer-l">
    <div class="fn">Gautam Keshri</div>
    <div class="fs">Data Science · Machine Learning · IIT Guwahati</div>
  </div>
  <div class="live-dot" style="flex-shrink:0;"></div>
  <div class="footer-copy">Made with data &amp; curiosity · 2026</div>
</footer>

</div>

<script>
const canvas = document.getElementById('bg-canvas');
const ctx = canvas.getContext('2d');
let W, H, particles = [], mouse = {x:0,y:0};

function resize(){
  W = canvas.width = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
resize();
window.addEventListener('resize', resize);

function rand(a,b){return Math.random()*(b-a)+a;}

class Particle {
  constructor(){this.reset();}
  reset(){
    this.x = rand(0,W); this.y = rand(0,H);
    this.vx = rand(-0.2,0.2); this.vy = rand(-0.3,-0.05);
    this.r = rand(0.5,2.5);
    this.a = rand(0.1,0.6);
    this.life = rand(0,1);
    const cols = ['rgba(79,142,247,','rgba(167,139,250,','rgba(34,211,238,','rgba(52,211,153,'];
    this.col = cols[Math.floor(rand(0,cols.length))];
  }
  update(){
    this.x += this.vx; this.y += this.vy; this.life += 0.003;
    if(this.y < -10 || this.life > 1) this.reset();
  }
  draw(){
    const alpha = this.a * Math.sin(this.life * Math.PI);
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.r, 0, Math.PI*2);
    ctx.fillStyle = this.col + alpha + ')';
    ctx.fill();
  }
}

for(let i=0;i<120;i++) particles.push(new Particle());

function drawConnections(){
  for(let i=0;i<particles.length;i++){
    for(let j=i+1;j<particles.length;j++){
      const dx=particles[i].x-particles[j].x, dy=particles[i].y-particles[j].y;
      const dist=Math.sqrt(dx*dx+dy*dy);
      if(dist<100){
        ctx.beginPath();
        ctx.moveTo(particles[i].x,particles[i].y);
        ctx.lineTo(particles[j].x,particles[j].y);
        ctx.strokeStyle=`rgba(79,142,247,${0.06*(1-dist/100)})`;
        ctx.lineWidth=0.5;
        ctx.stroke();
      }
    }
  }
}

function loop(){
  ctx.clearRect(0,0,W,H);
  particles.forEach(p=>{p.update();p.draw();});
  drawConnections();
  requestAnimationFrame(loop);
}
loop();

document.addEventListener('mousemove',e=>{mouse.x=e.clientX;mouse.y=e.clientY;});

// 3D tilt cards
document.querySelectorAll('.tilt-card').forEach(card=>{
  card.addEventListener('mousemove',e=>{
    const r=card.getBoundingClientRect();
    const x=(e.clientX-r.left)/r.width-0.5;
    const y=(e.clientY-r.top)/r.height-0.5;
    card.style.transform=`perspective(600px) rotateY(${x*14}deg) rotateX(${-y*14}deg) scale(1.03)`;
  });
  card.addEventListener('mouseleave',()=>{
    card.style.transform='perspective(600px) rotateY(0) rotateX(0) scale(1)';
    card.style.transition='transform 0.5s ease';
  });
  card.addEventListener('mouseenter',()=>{card.style.transition='transform 0.1s ease';});
});
</script>
</body>
</html>
