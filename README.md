<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Tanaya Zore — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,400&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg-page: #0d1224;
    --bg-hero: linear-gradient(160deg, #0f1b3d 0%, #1a0a4a 50%, #0a2a5a 100%);
    --bg-card: rgba(255,255,255,0.04);
    --bg-card-border: rgba(255,255,255,0.08);
    --accent-blue: #36BCF7;
    --accent-purple: #7B68EE;
    --accent-teal: #20c997;
    --text-primary: #f0f4ff;
    --text-secondary: rgba(240,244,255,0.65);
    --text-muted: rgba(240,244,255,0.38);
  }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--bg-page);
    color: var(--text-primary);
    min-height: 100vh;
    line-height: 1.6;
  }

  /* ── HERO ── */
  .hero {
    background: var(--bg-hero);
    padding: 3rem 2rem 4rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse at 15% 60%, rgba(54,188,247,.18) 0%, transparent 55%),
      radial-gradient(ellipse at 85% 40%, rgba(106,90,205,.22) 0%, transparent 55%);
    pointer-events: none;
  }
  .hero-inner { position: relative; z-index: 1; max-width: 640px; margin: 0 auto; }

  .avatar {
    width: 88px; height: 88px; border-radius: 50%;
    background: linear-gradient(135deg, var(--accent-blue), var(--accent-purple));
    display: flex; align-items: center; justify-content: center;
    font-family: 'Space Mono', monospace; font-size: 24px; font-weight: 700; color: #fff;
    margin: 0 auto 1.25rem;
    box-shadow: 0 0 0 4px rgba(54,188,247,.25), 0 0 32px rgba(54,188,247,.15);
    animation: pulse 3s ease-in-out infinite;
  }
  @keyframes pulse {
    0%,100% { box-shadow: 0 0 0 4px rgba(54,188,247,.25), 0 0 32px rgba(54,188,247,.15); }
    50%      { box-shadow: 0 0 0 6px rgba(54,188,247,.35), 0 0 48px rgba(54,188,247,.25); }
  }

  .hero h1 {
    font-family: 'Space Mono', monospace;
    font-size: clamp(22px, 5vw, 32px); font-weight: 700;
    color: #fff; margin-bottom: .3rem; letter-spacing: -.5px;
  }
  .hero-title {
    font-size: 15px; color: var(--accent-blue); font-weight: 500; margin-bottom: .9rem;
  }
  .hero-desc {
    font-size: 13.5px; color: var(--text-secondary);
    max-width: 420px; margin: 0 auto 1.5rem; line-height: 1.7;
  }

  .badges {
    display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-bottom: 1.5rem;
  }
  .badge {
    font-size: 11.5px; padding: 4px 14px; border-radius: 20px; font-weight: 500;
    border: 1px solid rgba(54,188,247,.3);
    color: #a8d8f5; background: rgba(54,188,247,.07);
    animation: fadeUp .6s ease both;
  }
  .badge:nth-child(2) { animation-delay: .05s; }
  .badge:nth-child(3) { border-color: rgba(123,104,238,.4); color: #c4b8f5; background: rgba(123,104,238,.1); animation-delay: .1s; }
  .badge:nth-child(4) { animation-delay: .15s; }
  .badge:nth-child(5) { border-color: rgba(123,104,238,.4); color: #c4b8f5; background: rgba(123,104,238,.1); animation-delay: .2s; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(10px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .cta-row {
    display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; margin-bottom: .75rem;
  }
  .cta-btn {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 8px 20px; border-radius: 8px;
    border: 1px solid rgba(255,255,255,.18);
    color: rgba(255,255,255,.72); background: rgba(255,255,255,.05);
    font-size: 13px; font-weight: 500; text-decoration: none; cursor: pointer;
    transition: background .2s, border-color .2s, color .2s;
  }
  .cta-btn:hover { background: rgba(54,188,247,.15); border-color: rgba(54,188,247,.5); color: var(--accent-blue); }
  .cta-btn svg { width: 15px; height: 15px; flex-shrink: 0; }

  .profile-views {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 5px 16px; border-radius: 8px;
    border: 1px solid rgba(255,255,255,.12); color: var(--text-muted);
    font-size: 12px; background: rgba(255,255,255,.03); text-decoration: none;
    transition: color .2s, border-color .2s;
  }
  .profile-views:hover { color: var(--accent-blue); border-color: rgba(54,188,247,.35); }

  /* ── WAVE ── */
  .wave { display: block; width: 100%; line-height: 0; }
  .wave-hero { background: var(--bg-page); }
  .wave-hero svg path { fill: #0f1b3d; }

  /* ── BODY ── */
  .body { max-width: 820px; margin: 0 auto; padding: 2rem 1.25rem 3rem; }

  .section { margin-bottom: 2.5rem; }

  .section-header {
    display: flex; align-items: center; gap: 10px;
    font-size: 11px; font-weight: 600; letter-spacing: .12em; text-transform: uppercase;
    color: var(--text-muted); margin-bottom: 1rem;
  }
  .section-header::before {
    content: ''; width: 14px; height: 14px; border-radius: 3px;
    border: 1.5px solid var(--accent-blue); flex-shrink: 0;
  }
  .section-header::after {
    content: ''; flex: 1; height: .5px; background: rgba(255,255,255,.08);
  }

  /* ── ABOUT CARD ── */
  .about-card {
    background: var(--bg-card); border: 1px solid var(--bg-card-border);
    border-radius: 12px; padding: 1.25rem 1.5rem;
  }
  .about-item {
    display: flex; align-items: flex-start; gap: 12px;
    padding: 5px 0; font-size: 13.5px; color: var(--text-secondary); line-height: 1.55;
  }
  .dot {
    width: 7px; height: 7px; border-radius: 50%; margin-top: 6px; flex-shrink: 0;
    background: var(--accent-blue);
  }
  .about-item:nth-child(even) .dot { background: var(--accent-purple); }

  /* ── TECH STACK ── */
  .tech-card {
    background: var(--bg-card); border: 1px solid var(--bg-card-border);
    border-radius: 12px; padding: 1.25rem 1.5rem; display: flex; flex-direction: column; gap: 1.25rem;
  }
  .tech-group-title {
    font-size: 10.5px; font-weight: 600; letter-spacing: .1em; text-transform: uppercase;
    color: var(--text-muted); margin-bottom: .6rem;
  }
  .chips { display: flex; flex-wrap: wrap; gap: 7px; }
  .chip {
    font-size: 12.5px; padding: 4px 14px; border-radius: 6px; font-weight: 500; border: .5px solid;
  }
  .chip-fe   { background: rgba(54,188,247,.09); border-color: rgba(54,188,247,.28); color: #5fd1f9; }
  .chip-be   { background: rgba(123,104,238,.11); border-color: rgba(123,104,238,.32); color: #a894f7; }
  .chip-tool { background: rgba(32,201,151,.09); border-color: rgba(32,201,151,.28); color: #3dd9a6; }

  /* ── CURRENT WORK ── */
  .work-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  @media(max-width:540px) { .work-grid { grid-template-columns: 1fr; } }

  .work-card {
    background: var(--bg-card); border: 1px solid var(--bg-card-border);
    border-radius: 12px; padding: 1.25rem 1.35rem;
  }
  .work-card-head {
    display: flex; align-items: center; gap: 10px; margin-bottom: .85rem;
  }
  .work-icon {
    width: 34px; height: 34px; border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
  }
  .work-icon.blue { background: rgba(54,188,247,.12); }
  .work-icon.purple { background: rgba(123,104,238,.14); }
  .work-card-title { font-size: 14px; font-weight: 600; color: var(--text-primary); }
  .work-list { list-style: none; padding: 0; }
  .work-list li {
    font-size: 12.5px; color: var(--text-secondary);
    padding: 3.5px 0; display: flex; align-items: center; gap: 8px;
  }
  .work-list li::before {
    content: ''; width: 4px; height: 4px; border-radius: 50%;
    background: rgba(255,255,255,.2); flex-shrink: 0;
  }

  /* ── QUOTE ── */
  .quote-bar {
    background: var(--bg-card); border: 1px solid var(--bg-card-border);
    border-left: 3px solid var(--accent-blue);
    border-radius: 0 10px 10px 0;
    padding: 1rem 1.25rem;
    font-size: 13.5px; color: var(--text-secondary); font-style: italic; line-height: 1.7;
    margin-bottom: 2rem;
  }
  .quote-bar strong { color: var(--accent-blue); font-style: normal; font-weight: 600; }

  /* ── CONNECT ── */
  .connect-row { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; }
  .connect-btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 10px 22px; border-radius: 10px;
    border: 1px solid rgba(255,255,255,.14); background: rgba(255,255,255,.04);
    font-size: 13px; font-weight: 500; color: var(--text-secondary); text-decoration: none;
    transition: background .2s, border-color .2s, color .2s;
  }
  .connect-btn:hover { background: rgba(54,188,247,.12); border-color: rgba(54,188,247,.4); color: var(--accent-blue); }
  .connect-btn svg { width: 17px; height: 17px; }

  /* ── FOOTER WAVE ── */
  .footer-wave { line-height: 0; }
  .footer-wave svg path { fill: #0f1b3d; }
  .footer-bar {
    background: linear-gradient(160deg, #0f1b3d 0%, #1a0a4a 50%, #0a2a5a 100%);
    height: 60px;
  }
</style>
</head>
<body>

<!-- ═══════════════ HERO ═══════════════ -->
<header class="hero">
  <div class="hero-inner">
    <div class="avatar">TZ</div>
    <h1>Tanaya Zore</h1>
    <p class="hero-title">Full Stack Web &amp; Mobile App Developer</p>
    <p class="hero-desc">Building scalable web &amp; mobile applications using React.js, React Native, Node.js, TypeScript and SQL.</p>

    <div class="badges">
      <span class="badge">Full Stack Developer</span>
      <span class="badge">React · React Native · Node.js</span>
      <span class="badge">Real-Time Applications</span>
      <span class="badge">RFID &amp; GPS Tracking</span>
      <span class="badge">80+ Schools Platform</span>
    </div>

    <div class="cta-row">
      <a class="cta-btn" href="https://www.linkedin.com/in/tanaya-zore-381960228" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="cta-btn" href="mailto:tanayazore49@gmail.com">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="M22 7l-10 7L2 7"/></svg>
        Email
      </a>
    </div>
    <a class="profile-views" href="#">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" style="width:13px;height:13px"><rect x="3" y="3" width="7" height="7"/><rect x="14" y="3" width="7" height="7"/><rect x="3" y="14" width="7" height="7"/><rect x="14" y="14" width="7" height="7"/></svg>
      Profile views — TanayaZore
    </a>
  </div>
</header>

<div class="wave wave-hero">
  <svg viewBox="0 0 1200 40" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M0,40 L0,18 Q300,0 600,20 Q900,40 1200,10 L1200,40 Z"/>
  </svg>
</div>

<!-- ═══════════════ BODY ═══════════════ -->
<main class="body">

  <!-- ABOUT ME -->
  <section class="section">
    <div class="section-header">About me</div>
    <div class="about-card">
      <div class="about-item"><span class="dot"></span><span>Currently working on enterprise-level web &amp; mobile applications</span></div>
      <div class="about-item"><span class="dot"></span><span>Building real-time GPS tracking &amp; RFID systems</span></div>
      <div class="about-item"><span class="dot"></span><span>Developing reporting platforms used by 80+ schools</span></div>
      <div class="about-item"><span class="dot"></span><span>Improving performance using Redis caching &amp; API optimization</span></div>
      <div class="about-item"><span class="dot"></span><span>Working on both React.js &amp; React Native applications</span></div>
      <div class="about-item"><span class="dot"></span><span>Passionate about scalable systems &amp; clean UI development</span></div>
      <div class="about-item"><span class="dot"></span><span>Exploring advanced backend optimization &amp; system architecture</span></div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="section">
    <div class="section-header">Tech stack</div>
    <div class="tech-card">
      <div>
        <div class="tech-group-title">Frontend</div>
        <div class="chips">
          <span class="chip chip-fe">React</span>
          <span class="chip chip-fe">Redux</span>
          <span class="chip chip-fe">TypeScript</span>
          <span class="chip chip-fe">JavaScript</span>
          <span class="chip chip-fe">HTML</span>
          <span class="chip chip-fe">CSS</span>
          <span class="chip chip-fe">Tailwind CSS</span>
        </div>
      </div>
      <div>
        <div class="tech-group-title">Backend &amp; Database</div>
        <div class="chips">
          <span class="chip chip-be">Node.js</span>
          <span class="chip chip-be">Express</span>
          <span class="chip chip-be">MySQL</span>
          <span class="chip chip-be">Redis</span>
        </div>
      </div>
      <div>
        <div class="tech-group-title">Tools &amp; Platforms</div>
        <div class="chips">
          <span class="chip chip-tool">Git</span>
          <span class="chip chip-tool">GitHub</span>
          <span class="chip chip-tool">VS Code</span>
          <span class="chip chip-tool">Figma</span>
          <span class="chip chip-tool">Postman</span>
        </div>
      </div>
    </div>
  </section>

  <!-- CURRENT WORK -->
  <section class="section">
    <div class="section-header">Current work</div>
    <div class="work-grid">
      <div class="work-card">
        <div class="work-card-head">
          <div class="work-icon blue">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#36BCF7" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
          </div>
          <span class="work-card-title">Real-time systems</span>
        </div>
        <ul class="work-list">
          <li>GPS live tracking</li>
          <li>RFID attendance</li>
          <li>Fleet management</li>
          <li>Live monitoring dashboards</li>
        </ul>
      </div>
      <div class="work-card">
        <div class="work-card-head">
          <div class="work-icon purple">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#7B68EE" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/></svg>
          </div>
          <span class="work-card-title">Reporting platforms</span>
        </div>
        <ul class="work-list">
          <li>School analytics</li>
          <li>Performance reports</li>
          <li>Administrative dashboards</li>
          <li>Used by 80+ schools</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- QUOTE -->
  <div class="quote-bar">
    "Building real-world systems that <strong>solve practical problems.</strong>"
  </div>

  <!-- CONNECT -->
  <section class="section">
    <div class="section-header">Connect with me</div>
    <div class="connect-row">
      <a class="connect-btn" href="https://www.linkedin.com/in/tanaya-zore-381960228" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="connect-btn" href="mailto:tanayazore49@gmail.com">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="M22 7l-10 7L2 7"/></svg>
        tanayazore49@gmail.com
      </a>
    </div>
  </section>

</main>

<!-- FOOTER -->
<div class="footer-wave">
  <svg viewBox="0 0 1200 40" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" style="display:block;width:100%">
    <path d="M0,0 Q300,40 600,20 Q900,0 1200,30 L1200,40 L0,40 Z"/>
  </svg>
</div>
<div class="footer-bar"></div>

</body>
</html>
