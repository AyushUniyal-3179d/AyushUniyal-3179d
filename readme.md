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

<!-- Custom cursor -->
<div id="cursor"></div>
<div id="cursor-ring"></div>

<!-- Particle canvas -->
<canvas id="bg-canvas"></canvas>

<div class="wrapper">

  <!-- ══════════ HERO ══════════ -->
  <section class="hero">

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
