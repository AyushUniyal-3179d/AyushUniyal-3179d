<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ayush Uniyal — Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600;700&family=JetBrains+Mono:wght@300;400;700&display=swap" rel="stylesheet"/>
<style>
:root {
  --c1: #0ff;
  --c2: #a855f7;
  --c3: #f0f;
  --bg: #020008;
  --card: rgba(10,0,30,0.85);
  --glow1: 0 0 20px #0ff8, 0 0 60px #0ff3;
  --glow2: 0 0 20px #a855f788, 0 0 60px #a855f733;
}

*{margin:0;padding:0;box-sizing:border-box;}

html,body{
  width:100%;height:100%;
  background:var(--bg);
  color:#e0f7ff;
  font-family:'Rajdhani',sans-serif;
  overflow-x:hidden;
  cursor:none;
}

/* ── Custom cursor ── */
#cursor{
  position:fixed;width:14px;height:14px;
  border-radius:50%;background:var(--c1);
  pointer-events:none;z-index:9999;
  transform:translate(-50%,-50%);
  transition:transform .08s,width .2s,height .2s,background .2s;
  box-shadow:var(--glow1);
  mix-blend-mode:screen;
}
#cursor-ring{
  position:fixed;width:38px;height:38px;
  border-radius:50%;border:1.5px solid var(--c1);
  pointer-events:none;z-index:9998;
  transform:translate(-50%,-50%);
  transition:transform .18s ease,width .3s,height .3s,border-color .3s;
  opacity:.7;
}
body:has(a:hover) #cursor,body:has(button:hover) #cursor{
  width:22px;height:22px;background:var(--c2);
  box-shadow:var(--glow2);
}
body:has(a:hover) #cursor-ring,body:has(button:hover) #cursor-ring{
  width:56px;height:56px;border-color:var(--c2);opacity:1;
}

/* ── Canvas bg ── */
#bg-canvas{
  position:fixed;inset:0;z-index:0;
  pointer-events:none;
}

/* ── Scan lines overlay ── */
body::before{
  content:'';position:fixed;inset:0;z-index:1;pointer-events:none;
  background:repeating-linear-gradient(
    0deg,
    transparent,transparent 2px,
    rgba(0,255,255,.015) 2px,rgba(0,255,255,.015) 4px
  );
}

/* ── Main wrapper ── */
.wrapper{
  position:relative;z-index:2;
  max-width:1100px;margin:0 auto;
  padding:0 24px 80px;
}

/* ══════════════════════════════
   HERO
══════════════════════════════ */
.hero{
  min-height:100vh;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  text-align:center;
  padding:60px 0 40px;
  position:relative;
}

/* Rotating 3-D ring */
.ring-scene{
  width:240px;height:240px;
  margin:0 auto 40px;
  perspective:800px;
  position:relative;
}
.ring-3d{
  width:100%;height:100%;
  position:relative;
  transform-style:preserve-3d;
  animation:ringRotate 12s linear infinite;
}
@keyframes ringRotate{
  from{transform:rotateY(0deg) rotateX(20deg);}
  to  {transform:rotateY(360deg) rotateX(20deg);}
}
.ring-face{
  position:absolute;inset:0;
  border-radius:50%;
  border:2px solid transparent;
}
.rf1{border-color:var(--c1);box-shadow:0 0 18px var(--c1),inset 0 0 18px var(--c1)4d;animation:rfPulse1 3s ease-in-out infinite alternate;}
.rf2{border-color:var(--c2);transform:rotateY(60deg);box-shadow:0 0 18px var(--c2);animation:rfPulse2 4s ease-in-out infinite alternate;}
.rf3{border-color:var(--c3);transform:rotateX(60deg);box-shadow:0 0 18px var(--c3);animation:rfPulse3 5s ease-in-out infinite alternate;}
@keyframes rfPulse1{from{opacity:.6}to{opacity:1}}
@keyframes rfPulse2{from{opacity:.4}to{opacity:.9}}
@keyframes rfPulse3{from{opacity:.5}to{opacity:1}}

/* Avatar inside ring */
.avatar-wrap{
  position:absolute;inset:24px;
  border-radius:50%;overflow:hidden;
  border:2px solid rgba(0,255,255,.4);
  box-shadow:0 0 40px rgba(0,255,255,.25),inset 0 0 30px rgba(0,0,0,.6);
  background:linear-gradient(135deg,#0d0030,#001830);
  display:flex;align-items:center;justify-content:center;
}
.avatar-initials{
  font-family:'Orbitron',sans-serif;
  font-size:52px;font-weight:900;
  background:linear-gradient(135deg,var(--c1),var(--c2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
  text-shadow:none;
  letter-spacing:-2px;
  animation:initPulse 3s ease-in-out infinite alternate;
}
@keyframes initPulse{
  from{filter:brightness(1);}
  to  {filter:brightness(1.4) drop-shadow(0 0 12px #0ff);}
}

/* glitch name */
.glitch-wrap{margin-bottom:12px;}
.glitch{
  font-family:'Orbitron',sans-serif;
  font-size:clamp(2rem,6vw,4.2rem);
  font-weight:900;
  color:#fff;
  letter-spacing:4px;
  position:relative;
  display:inline-block;
  text-shadow:0 0 30px var(--c1), 0 0 60px rgba(0,255,255,.3);
  animation:glitchAnim 6s infinite;
}
.glitch::before,.glitch::after{
  content:attr(data-text);
  position:absolute;inset:0;
  font-family:inherit;font-size:inherit;font-weight:inherit;letter-spacing:inherit;
  clip-path:polygon(0 0,100% 0,100% 35%,0 35%);
}
.glitch::before{
  color:var(--c1);
  animation:glitchTop 6s infinite;
  text-shadow:2px 0 var(--c3);
}
.glitch::after{
  color:var(--c2);
  clip-path:polygon(0 65%,100% 65%,100% 100%,0 100%);
  animation:glitchBot 6s infinite;
  text-shadow:-2px 0 var(--c1);
}
@keyframes glitchAnim{
  0%,90%,100%{transform:translate(0);}
  92%{transform:translate(-3px,1px);}
  94%{transform:translate(3px,-1px);}
  96%{transform:translate(-2px,2px);}
}
@keyframes glitchTop{
  0%,90%,100%{transform:translate(0);opacity:0;}
  92%{transform:translate(4px,-2px);opacity:.8;}
  95%{transform:translate(-4px,2px);opacity:.6;}
}
@keyframes glitchBot{
  0%,90%,100%{transform:translate(0);opacity:0;}
  93%{transform:translate(-4px,2px);opacity:.7;}
  96%{transform:translate(4px,-2px);opacity:.5;}
}

/* Typing role */
.role-line{
  font-family:'JetBrains Mono',monospace;
  font-size:1.05rem;color:var(--c1);
  letter-spacing:2px;margin-bottom:20px;
  min-height:1.6em;
}
.cursor-blink{animation:blink .7s step-end infinite;}
@keyframes blink{50%{opacity:0;}}

/* Bio */
.bio{
  max-width:520px;
  font-size:1.05rem;line-height:1.7;
  color:#a0c8e0;margin:0 auto 32px;
  font-weight:300;
  animation:fadeUp 1s ease .8s both;
}
@keyframes fadeUp{from{opacity:0;transform:translateY(20px);}to{opacity:1;transform:translateY(0);}}

/* Status pill */
.status{
  display:inline-flex;align-items:center;gap:8px;
  background:rgba(0,255,100,.08);
  border:1px solid rgba(0,255,100,.3);
  border-radius:99px;padding:6px 18px;
  font-family:'JetBrains Mono',monospace;
  font-size:.8rem;color:#4ade80;
  margin-bottom:36px;
  animation:fadeUp 1s ease 1s both;
}
.pulse-green{
  width:8px;height:8px;border-radius:50%;background:#4ade80;
  animation:pulseG 2s ease-in-out infinite;
}
@keyframes pulseG{0%,100%{box-shadow:0 0 0 0 rgba(74,222,128,.7);}50%{box-shadow:0 0 0 7px rgba(74,222,128,0);}}

/* CTA buttons */
.cta-row{
  display:flex;gap:14px;flex-wrap:wrap;justify-content:center;
  animation:fadeUp 1s ease 1.2s both;
}
.btn{
  font-family:'Orbitron',sans-serif;font-size:.75rem;font-weight:700;
  letter-spacing:2px;text-transform:uppercase;
  padding:13px 28px;border-radius:4px;
  text-decoration:none;cursor:pointer;
  border:none;outline:none;
  transition:transform .2s,box-shadow .2s;
  position:relative;overflow:hidden;
}
.btn::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,.15),transparent);
  transform:translateX(-100%);
  transition:transform .4s;
}
.btn:hover::before{transform:translateX(100%);}
.btn:hover{transform:translateY(-3px);}
.btn-primary{
  background:linear-gradient(135deg,var(--c1),var(--c2));
  color:#000;
  box-shadow:0 0 20px rgba(0,255,255,.4),0 4px 20px rgba(168,85,247,.4);
}
.btn-primary:hover{box-shadow:0 0 40px rgba(0,255,255,.6),0 8px 30px rgba(168,85,247,.5);}
.btn-ghost{
  background:transparent;
  color:var(--c1);
  border:1.5px solid var(--c1);
  box-shadow:0 0 12px rgba(0,255,255,.2);
}
.btn-ghost:hover{background:rgba(0,255,255,.08);box-shadow:0 0 25px rgba(0,255,255,.4);}

/* Scroll indicator */
.scroll-hint{
  position:absolute;bottom:28px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:6px;
  font-family:'JetBrains Mono',monospace;font-size:.7rem;
  color:rgba(0,255,255,.4);letter-spacing:2px;
  animation:fadeUp 1s ease 1.6s both;
}
.scroll-line{
  width:1.5px;height:40px;
  background:linear-gradient(to bottom,var(--c1),transparent);
  animation:scrollDrop 2s ease-in-out infinite;
}
@keyframes scrollDrop{0%{transform:scaleY(0);transform-origin:top;}50%{transform:scaleY(1);transform-origin:top;}51%{transform-origin:bottom;}100%{transform:scaleY(0);transform-origin:bottom;}}

/* ══════════════════════════════
   SECTION COMMON
══════════════════════════════ */
.section{
  padding:80px 0 40px;
}
.section-header{
  display:flex;align-items:center;gap:16px;
  margin-bottom:48px;
}
.section-num{
  font-family:'Orbitron',sans-serif;font-size:.7rem;
  color:var(--c1);letter-spacing:3px;
  border:1px solid var(--c1);padding:4px 10px;border-radius:2px;
}
.section-title{
  font-family:'Orbitron',sans-serif;font-size:1.8rem;font-weight:700;
  color:#fff;letter-spacing:2px;
  text-shadow:0 0 20px rgba(0,255,255,.3);
}
.section-line{
  flex:1;height:1px;
  background:linear-gradient(90deg,rgba(0,255,255,.4),transparent);
}

/* ══════════════════════════════
   STATS ROW
══════════════════════════════ */
.stats-grid{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));
  gap:16px;margin-bottom:60px;
}
.stat-card{
  background:var(--card);
  border:1px solid rgba(0,255,255,.15);
  border-radius:8px;padding:28px 20px;text-align:center;
  position:relative;overflow:hidden;
  transition:transform .3s,box-shadow .3s;
}
.stat-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--c1),transparent);
}
.stat-card:hover{transform:translateY(-6px);box-shadow:0 20px 40px rgba(0,255,255,.15);}
.stat-num{
  font-family:'Orbitron',sans-serif;font-size:2.4rem;font-weight:900;
  background:linear-gradient(135deg,var(--c1),var(--c2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  display:block;
}
.stat-lbl{font-size:.85rem;color:#6b9bb8;letter-spacing:1px;font-family:'JetBrains Mono',monospace;}

/* ══════════════════════════════
   3D SKILL CARDS
══════════════════════════════ */
.skills-grid{
  display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));
  gap:16px;margin-bottom:20px;
}
.skill-flip{
  height:140px;perspective:800px;
}
.skill-flip-inner{
  position:relative;width:100%;height:100%;
  transform-style:preserve-3d;
  transition:transform .6s cubic-bezier(.4,0,.2,1);
}
.skill-flip:hover .skill-flip-inner{transform:rotateY(180deg);}
.skill-front,.skill-back{
  position:absolute;inset:0;
  backface-visibility:hidden;
  border-radius:8px;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;gap:8px;
  padding:16px;
}
.skill-front{
  background:var(--card);
  border:1px solid rgba(255,255,255,.08);
}
.skill-back{
  background:linear-gradient(135deg,rgba(0,255,255,.1),rgba(168,85,247,.1));
  border:1px solid var(--c1);
  transform:rotateY(180deg);
}
.skill-icon{font-size:2rem;line-height:1;}
.skill-name{
  font-family:'JetBrains Mono',monospace;
  font-size:.8rem;font-weight:700;
  color:#e0f7ff;letter-spacing:1px;
}
.skill-level{
  font-family:'Orbitron',sans-serif;
  font-size:1.4rem;font-weight:900;
  background:linear-gradient(90deg,var(--c1),var(--c2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.skill-bar-wrap{
  width:100%;height:4px;
  background:rgba(255,255,255,.1);border-radius:99px;overflow:hidden;
}
.skill-bar-fill{
  height:100%;border-radius:99px;
  background:linear-gradient(90deg,var(--c1),var(--c2));
  box-shadow:0 0 8px var(--c1);
  transform:scaleX(0);transform-origin:left;
  transition:transform 1.2s cubic-bezier(.4,0,.2,1);
}
.skill-bar-fill.animated{transform:scaleX(1);}

/* ══════════════════════════════
   PROJECT CARDS
══════════════════════════════ */
.projects-grid{
  display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));
  gap:24px;
}
.proj-card{
  background:var(--card);
  border:1px solid rgba(255,255,255,.07);
  border-radius:12px;padding:28px;
  position:relative;overflow:hidden;
  transition:transform .35s,border-color .35s,box-shadow .35s;
  cursor:default;
}
.proj-card::after{
  content:'';position:absolute;inset:0;
  background:radial-gradient(circle at var(--mx,50%) var(--my,50%),rgba(0,255,255,.07),transparent 60%);
  opacity:0;transition:opacity .3s;
  pointer-events:none;
}
.proj-card:hover::after{opacity:1;}
.proj-card:hover{
  transform:translateY(-8px) scale(1.01);
  border-color:rgba(0,255,255,.35);
  box-shadow:0 24px 60px rgba(0,255,255,.12),0 0 0 1px rgba(0,255,255,.1);
}
.proj-tag-row{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px;}
.proj-tag{
  font-family:'JetBrains Mono',monospace;font-size:.7rem;
  padding:3px 10px;border-radius:99px;letter-spacing:1px;font-weight:700;
}
.tag-live{background:rgba(74,222,128,.12);color:#4ade80;border:1px solid rgba(74,222,128,.3);}
.tag-wip {background:rgba(251,191,36,.12);color:#fbbf24;border:1px solid rgba(251,191,36,.3);}
.tag-oss {background:rgba(99,102,241,.15);color:#818cf8;border:1px solid rgba(99,102,241,.3);}
.proj-title{
  font-family:'Orbitron',sans-serif;font-size:1.1rem;font-weight:700;
  color:#fff;margin-bottom:8px;
}
.proj-desc{font-size:.9rem;color:#7ba8c0;line-height:1.6;margin-bottom:20px;font-weight:300;}
.proj-stack{display:flex;gap:8px;flex-wrap:wrap;}
.proj-pill{
  font-family:'JetBrains Mono',monospace;font-size:.7rem;
  background:rgba(0,255,255,.06);
  border:1px solid rgba(0,255,255,.15);
  color:var(--c1);padding:3px 10px;border-radius:4px;
}
.proj-corner{
  position:absolute;top:0;right:0;
  width:60px;height:60px;overflow:hidden;
}
.proj-corner::before{
  content:'';position:absolute;top:-30px;right:-30px;
  width:60px;height:60px;
  background:var(--c1);opacity:.05;
  transform:rotate(45deg);
}

/* ══════════════════════════════
   GITHUB STATS
══════════════════════════════ */
.gh-stats{
  display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:24px;
}
.gh-card{
  border-radius:10px;overflow:hidden;
  border:1px solid rgba(0,255,255,.12);
  transition:transform .3s,box-shadow .3s;
}
.gh-card:hover{transform:scale(1.02);box-shadow:0 12px 40px rgba(0,255,255,.15);}
.gh-card img{width:100%;display:block;}

/* ══════════════════════════════
   CONTACT
══════════════════════════════ */
.contact-grid{
  display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));
  gap:16px;
}
.contact-card{
  background:var(--card);
  border:1px solid rgba(255,255,255,.07);
  border-radius:10px;padding:22px 20px;
  display:flex;align-items:center;gap:14px;
  text-decoration:none;color:inherit;
  transition:transform .3s,border-color .3s,box-shadow .3s;
  position:relative;overflow:hidden;
}
.contact-card::before{
  content:'';position:absolute;bottom:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,var(--c2),var(--c1));
  transform:scaleX(0);transition:transform .3s;
}
.contact-card:hover::before{transform:scaleX(1);}
.contact-card:hover{
  transform:translateY(-4px);
  border-color:rgba(168,85,247,.4);
  box-shadow:0 16px 40px rgba(168,85,247,.15);
}
.contact-icon{
  width:42px;height:42px;border-radius:8px;
  display:flex;align-items:center;justify-content:center;
  font-size:1.4rem;flex-shrink:0;
}
.contact-label{
  font-family:'Orbitron',sans-serif;font-size:.75rem;
  font-weight:700;letter-spacing:1px;color:#fff;
  display:block;margin-bottom:2px;
}
.contact-val{
  font-family:'JetBrains Mono',monospace;font-size:.75rem;
  color:#6b9bb8;
}

/* ══════════════════════════════
   FOOTER
══════════════════════════════ */
.footer{
  text-align:center;padding:40px 0 20px;
  border-top:1px solid rgba(0,255,255,.08);
  margin-top:60px;
}
.footer-name{
  font-family:'Orbitron',sans-serif;font-size:.85rem;
  font-weight:700;letter-spacing:4px;
  background:linear-gradient(90deg,var(--c1),var(--c2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.footer-sub{
  font-family:'JetBrains Mono',monospace;font-size:.72rem;
  color:rgba(107,155,184,.5);letter-spacing:2px;margin-top:6px;
}

/* ══════════════════════════════
   REVEAL ANIMATION
══════════════════════════════ */
.reveal{
  opacity:0;transform:translateY(30px);
  transition:opacity .7s ease,transform .7s ease;
}
.reveal.visible{opacity:1;transform:translateY(0);}

/* scrollbar */
::-webkit-scrollbar{width:4px;}
::-webkit-scrollbar-track{background:var(--bg);}
::-webkit-scrollbar-thumb{background:var(--c2);border-radius:99px;}

@media(max-width:600px){
  .gh-stats{grid-template-columns:1fr;}
  .glitch{font-size:2rem;}
  .ring-scene{width:180px;height:180px;}
}
</style>
</head>
<body>

<!-- Custom cursor -->
<div id="cursor"></div>
<div id="cursor-ring"></div>

<!-- Particle canvas -->
<canvas id="bg-canvas"></canvas>

<div class="wrapper">

  <!-- ══════════ HERO ══════════ -->
  <section class="hero">

    <div class="ring-scene">
      <div class="ring-3d">
        <div class="ring-face rf1"></div>
        <div class="ring-face rf2"></div>
        <div class="ring-face rf3"></div>
        <div class="avatar-wrap">
          <span class="avatar-initials">AU</span>
        </div>
      </div>
    </div>

    <div class="glitch-wrap">
      <h1 class="glitch" data-text="AYUSH UNIYAL">AYUSH UNIYAL</h1>
    </div>

    <div class="role-line" id="role-line">
      <span id="typed-role"></span><span class="cursor-blink">█</span>
    </div>

    <p class="bio">
      Full-stack developer crafting immersive digital experiences from India 🇮🇳.
      Passionate about clean code, creative UIs, and pushing pixels to their limits.
    </p>

    <div class="status">
      <div class="pulse-green"></div>
      Available for work &amp; collaborations
    </div>

    <div class="cta-row">
      <a href="https://github.com/AyushUniyal-3179d" target="_blank" class="btn btn-primary">View GitHub</a>
      <a href="mailto:ayush@example.com" class="btn btn-ghost">Contact Me</a>
    </div>

    <div class="scroll-hint">
      <span>scroll</span>
      <div class="scroll-line"></div>
    </div>

  </section>

  <!-- ══════════ STATS ══════════ -->
  <section class="section reveal">
    <div class="section-header">
      <span class="section-num">01</span>
      <h2 class="section-title">At a Glance</h2>
      <div class="section-line"></div>
    </div>
    <div class="stats-grid">
      <div class="stat-card"><span class="stat-num" data-target="1">0</span><span class="stat-lbl">REPOSITORIES</span></div>
      <div class="stat-card"><span class="stat-num" data-target="2">0</span><span class="stat-lbl">COMMITS</span></div>
      <div class="stat-card"><span class="stat-num" data-target="0">0</span><span class="stat-lbl">FOLLOWERS</span></div>
      <div class="stat-card"><span class="stat-num" data-target="2026">0</span><span class="stat-lbl">JOINED YEAR</span></div>
    </div>
  </section>

  <!-- ══════════ SKILLS ══════════ -->
  <section class="section reveal">
    <div class="section-header">
      <span class="section-num">02</span>
      <h2 class="section-title">Skills</h2>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">⚛️</span><span class="skill-name">REACT</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".88"></div></div></div>
          <div class="skill-back"><span class="skill-level">88%</span><span class="skill-name">REACT</span></div>
        </div>
      </div>
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">🟢</span><span class="skill-name">NODE.JS</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".82"></div></div></div>
          <div class="skill-back"><span class="skill-level">82%</span><span class="skill-name">NODE.JS</span></div>
        </div>
      </div>
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">🐍</span><span class="skill-name">PYTHON</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".75"></div></div></div>
          <div class="skill-back"><span class="skill-level">75%</span><span class="skill-name">PYTHON</span></div>
        </div>
      </div>
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">🌐</span><span class="skill-name">HTML/CSS</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".92"></div></div></div>
          <div class="skill-back"><span class="skill-level">92%</span><span class="skill-name">HTML/CSS</span></div>
        </div>
      </div>
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">🐋</span><span class="skill-name">DOCKER</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".65"></div></div></div>
          <div class="skill-back"><span class="skill-level">65%</span><span class="skill-name">DOCKER</span></div>
        </div>
      </div>
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">🍃</span><span class="skill-name">MONGODB</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".78"></div></div></div>
          <div class="skill-back"><span class="skill-level">78%</span><span class="skill-name">MONGODB</span></div>
        </div>
      </div>
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">☁️</span><span class="skill-name">AWS</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".60"></div></div></div>
          <div class="skill-back"><span class="skill-level">60%</span><span class="skill-name">AWS</span></div>
        </div>
      </div>
      <div class="skill-flip">
        <div class="skill-flip-inner">
          <div class="skill-front"><span class="skill-icon">🐱</span><span class="skill-name">GIT</span><div class="skill-bar-wrap"><div class="skill-bar-fill" data-pct=".85"></div></div></div>
          <div class="skill-back"><span class="skill-level">85%</span><span class="skill-name">GIT</span></div>
        </div>
      </div>
    </div>
    <p style="font-family:'JetBrains Mono',monospace;font-size:.75rem;color:#4b6b7e;text-align:center;margin-top:12px;">
      hover cards to reveal proficiency
    </p>
  </section>

  <!-- ══════════ PROJECTS ══════════ -->
  <section class="section reveal">
    <div class="section-header">
      <span class="section-num">03</span>
      <h2 class="section-title">Projects</h2>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <div class="proj-card" onmousemove="cardMouse(this,event)">
        <div class="proj-corner"></div>
        <div class="proj-tag-row"><span class="proj-tag tag-live">LIVE</span></div>
        <div class="proj-title">NeuralChat</div>
        <p class="proj-desc">AI-powered real-time chat with sentiment analysis and smart reply suggestions.</p>
        <div class="proj-stack">
          <span class="proj-pill">React</span>
          <span class="proj-pill">Node.js</span>
          <span class="proj-pill">Socket.io</span>
          <span class="proj-pill">OpenAI</span>
        </div>
      </div>

      <div class="proj-card" onmousemove="cardMouse(this,event)">
        <div class="proj-corner"></div>
        <div class="proj-tag-row"><span class="proj-tag tag-wip">IN PROGRESS</span></div>
        <div class="proj-title">TrailMapper</div>
        <p class="proj-desc">Himalayan trek planning app with elevation maps, community trip reports & gear lists.</p>
        <div class="proj-stack">
          <span class="proj-pill">React</span>
          <span class="proj-pill">MapboxGL</span>
          <span class="proj-pill">Python</span>
        </div>
      </div>

      <div class="proj-card" onmousemove="cardMouse(this,event)">
        <div class="proj-corner"></div>
        <div class="proj-tag-row"><span class="proj-tag tag-oss">OPEN SOURCE</span></div>
        <div class="proj-title">DevShell</div>
        <p class="proj-desc">CLI productivity toolkit for full-stack developers — snippets, scaffolding & automation.</p>
        <div class="proj-stack">
          <span class="proj-pill">Python</span>
          <span class="proj-pill">Click</span>
          <span class="proj-pill">Docker</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ══════════ GITHUB STATS ══════════ -->
  <section class="section reveal">
    <div class="section-header">
      <span class="section-num">04</span>
      <h2 class="section-title">GitHub Activity</h2>
      <div class="section-line"></div>
    </div>
    <div class="gh-stats">
      <div class="gh-card">
        <img src="https://github-readme-stats.vercel.app/api?username=AyushUniyal-3179d&show_icons=true&theme=tokyonight&hide_border=true&bg_color=020008&title_color=00ffff&icon_color=a855f7&text_color=c0e8f0&ring_color=a855f7" alt="GitHub stats"/>
      </div>
      <div class="gh-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=AyushUniyal-3179d&layout=compact&theme=tokyonight&hide_border=true&bg_color=020008&title_color=00ffff&text_color=c0e8f0" alt="Top languages"/>
      </div>
    </div>
    <div class="gh-card" style="margin-bottom:16px;">
      <img src="https://github-readme-streak-stats.herokuapp.com?user=AyushUniyal-3179d&theme=tokyonight&hide_border=true&background=020008&ring=a855f7&fire=00ffff&currStreakLabel=00ffff&sideLabels=a855f7" alt="Streak" style="width:100%;display:block;"/>
    </div>
    <div class="gh-card">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=AyushUniyal-3179d&theme=tokyo-night&hide_border=true&bg_color=020008&color=a855f7&line=00ffff&point=ffffff&area=true" alt="Activity graph" style="width:100%;display:block;"/>
    </div>
  </section>

  <!-- ══════════ CONTACT ══════════ -->
  <section class="section reveal">
    <div class="section-header">
      <span class="section-num">05</span>
      <h2 class="section-title">Connect</h2>
      <div class="section-line"></div>
    </div>
    <div class="contact-grid">
      <a href="https://github.com/AyushUniyal-3179d" target="_blank" class="contact-card">
        <div class="contact-icon" style="background:rgba(255,255,255,.05);">🐱</div>
        <div><span class="contact-label">GITHUB</span><span class="contact-val">AyushUniyal-3179d</span></div>
      </a>
      <a href="mailto:ayush@example.com" class="contact-card">
        <div class="contact-icon" style="background:rgba(0,255,255,.06);">✉️</div>
        <div><span class="contact-label">EMAIL</span><span class="contact-val">ayush@example.com</span></div>
      </a>
      <a href="https://linkedin.com" target="_blank" class="contact-card">
        <div class="contact-icon" style="background:rgba(0,119,181,.1);">💼</div>
        <div><span class="contact-label">LINKEDIN</span><span class="contact-val">Add your link</span></div>
      </a>
      <a href="https://twitter.com" target="_blank" class="contact-card">
        <div class="contact-icon" style="background:rgba(29,161,242,.08);">🐦</div>
        <div><span class="contact-label">TWITTER</span><span class="contact-val">Add your handle</span></div>
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <div class="footer-name">AYUSH UNIYAL</div>
    <div class="footer-sub">// built with code &amp; caffeine · india 🇮🇳 · 2026</div>
  </footer>

</div><!-- /wrapper -->

<script>
/* ── cursor ── */
const cur=document.getElementById('cursor'),ring=document.getElementById('cursor-ring');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px';});
(function animRing(){rx+=(mx-rx)*.12;ry+=(my-ry)*.12;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(animRing);})();

/* ── particle field ── */
const canvas=document.getElementById('bg-canvas');
const ctx=canvas.getContext('2d');
let W,H,particles=[];
function resize(){W=canvas.width=window.innerWidth;H=canvas.height=window.innerHeight;}
resize();window.addEventListener('resize',resize);
class Particle{
  constructor(){this.reset();}
  reset(){
    this.x=Math.random()*W;
    this.y=Math.random()*H;
    this.vx=(Math.random()-.5)*.4;
    this.vy=(Math.random()-.5)*.4;
    this.r=Math.random()*1.5+.3;
    this.a=Math.random()*.6+.1;
    this.c=Math.random()>.5?'0,255,255':'168,85,247';
  }
  update(){
    this.x+=this.vx;this.y+=this.vy;
    if(this.x<0||this.x>W||this.y<0||this.y>H)this.reset();
  }
  draw(){
    ctx.beginPath();ctx.arc(this.x,this.y,this.r,0,Math.PI*2);
    ctx.fillStyle=`rgba(${this.c},${this.a})`;ctx.fill();
  }
}
for(let i=0;i<140;i++)particles.push(new Particle());
function drawLines(){
  for(let i=0;i<particles.length;i++){
    for(let j=i+1;j<particles.length;j++){
      const dx=particles[i].x-particles[j].x,dy=particles[i].y-particles[j].y;
      const d=Math.sqrt(dx*dx+dy*dy);
      if(d<110){
        ctx.beginPath();
        ctx.moveTo(particles[i].x,particles[i].y);
        ctx.lineTo(particles[j].x,particles[j].y);
        ctx.strokeStyle=`rgba(0,255,255,${.12*(1-d/110)})`;
        ctx.lineWidth=.5;ctx.stroke();
      }
    }
  }
}
function loop(){
  ctx.clearRect(0,0,W,H);
  particles.forEach(p=>{p.update();p.draw();});
  drawLines();requestAnimationFrame(loop);
}
loop();

/* ── typing effect ── */
const roles=['Full-Stack Developer','Creative Coder','UI/UX Enthusiast','Open Source Fan','Problem Solver'];
let ri=0,ci=0,del=false;
const el=document.getElementById('typed-role');
function typeLoop(){
  const r=roles[ri];
  if(!del){
    el.textContent=r.slice(0,++ci);
    if(ci===r.length){del=true;setTimeout(typeLoop,2200);return;}
  }else{
    el.textContent=r.slice(0,--ci);
    if(ci===0){del=false;ri=(ri+1)%roles.length;}
  }
  setTimeout(typeLoop,del?45:90);
}
typeLoop();

/* ── scroll reveal ── */
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('visible');});
},{threshold:.1});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));

/* ── counter animation ── */
const cObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      const nums=e.target.querySelectorAll('.stat-num[data-target]');
      nums.forEach(n=>{
        const t=+n.dataset.target,isYear=t>1000;
        const dur=isYear?1200:800,step=50;
        let cur=isYear?2020:0;
        const inc=Math.max(1,Math.ceil((t-cur)/(dur/step)));
        const iv=setInterval(()=>{
          cur=Math.min(cur+inc,t);
          n.textContent=cur;
          if(cur>=t)clearInterval(iv);
        },step);
      });
      cObs.unobserve(e.target);
    }
  });
},{threshold:.3});
document.querySelectorAll('.stats-grid').forEach(el=>cObs.observe(el));

/* ── skill bar animation ── */
const sbObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.querySelectorAll('.skill-bar-fill').forEach(b=>{
        b.style.transform=`scaleX(${b.dataset.pct})`;
        b.classList.add('animated');
      });
      sbObs.unobserve(e.target);
    }
  });
},{threshold:.2});
document.querySelectorAll('.skills-grid').forEach(el=>sbObs.observe(el));

/* ── project card mouse glow ── */
function cardMouse(card,e){
  const r=card.getBoundingClientRect();
  const x=((e.clientX-r.left)/r.width*100).toFixed(1);
  const y=((e.clientY-r.top)/r.height*100).toFixed(1);
  card.style.setProperty('--mx',x+'%');
  card.style.setProperty('--my',y+'%');
}
</script>
</body>
</html>
