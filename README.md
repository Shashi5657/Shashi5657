<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Shashidhar Sangepu — Full Stack Developer</title>
  <meta name="description" content="Full Stack MERN Developer from Hyderabad. Building scalable web systems with React, Node.js, Next.js, and TypeScript." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #080c10;
      --bg2: #0d1117;
      --bg3: #111822;
      --surface: #161e2a;
      --border: #1e2d3d;
      --border-bright: #2a4060;
      --accent: #00e5ff;
      --accent2: #64ffda;
      --accent3: #ff6b6b;
      --text: #cdd9e5;
      --text-dim: #6b8394;
      --text-bright: #e6f0f8;
      --mono: 'Space Mono', monospace;
      --sans: 'Syne', sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--sans);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ── NOISE OVERLAY ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.035'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 9999;
      opacity: 0.4;
    }

    /* ── SCROLLBAR ── */
    ::-webkit-scrollbar { width: 4px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--border-bright); border-radius: 2px; }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.2rem 3rem;
      background: rgba(8,12,16,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }
    .nav-logo {
      font-family: var(--mono);
      font-size: 0.85rem;
      color: var(--accent);
      letter-spacing: 0.05em;
    }
    .nav-logo span { color: var(--text-dim); }
    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }
    .nav-links a {
      font-family: var(--mono);
      font-size: 0.78rem;
      color: var(--text-dim);
      text-decoration: none;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--accent); }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 8rem 3rem 4rem;
      position: relative;
      overflow: hidden;
    }

    .hero-grid {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,229,255,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,229,255,0.04) 1px, transparent 1px);
      background-size: 60px 60px;
      mask-image: radial-gradient(ellipse 80% 70% at 50% 50%, black 30%, transparent 100%);
    }

    .hero-glow {
      position: absolute;
      width: 600px; height: 600px;
      background: radial-gradient(circle, rgba(0,229,255,0.07) 0%, transparent 70%);
      top: 50%; left: 55%;
      transform: translate(-50%, -50%);
      pointer-events: none;
    }

    .hero-content { position: relative; max-width: 800px; }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--accent);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
    }
    .hero-tag::before {
      content: '';
      width: 24px; height: 1px;
      background: var(--accent);
    }

    h1 {
      font-family: var(--sans);
      font-weight: 800;
      font-size: clamp(3rem, 7vw, 5.5rem);
      line-height: 1.0;
      color: var(--text-bright);
      letter-spacing: -0.02em;
      margin-bottom: 0.3rem;
    }
    h1 .dim { color: var(--text-dim); }
    h1 .accent { color: var(--accent); }

    .hero-role {
      font-family: var(--mono);
      font-size: clamp(0.85rem, 2vw, 1rem);
      color: var(--text-dim);
      margin: 1.2rem 0 2rem;
      letter-spacing: 0.05em;
    }
    .hero-role em { color: var(--accent2); font-style: normal; }

    .hero-desc {
      font-size: 1.05rem;
      color: var(--text);
      max-width: 540px;
      margin-bottom: 2.5rem;
      line-height: 1.75;
    }

    .hero-btns {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.8rem 1.8rem;
      background: var(--accent);
      color: var(--bg);
      font-family: var(--mono);
      font-size: 0.8rem;
      font-weight: 700;
      text-decoration: none;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      transition: all 0.2s;
      clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 10px, 100% 100%, 10px 100%, 0 calc(100% - 10px));
    }
    .btn-primary:hover {
      background: var(--accent2);
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba(0,229,255,0.25);
    }

    .btn-ghost {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.8rem 1.8rem;
      border: 1px solid var(--border-bright);
      color: var(--text);
      font-family: var(--mono);
      font-size: 0.8rem;
      text-decoration: none;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      transition: all 0.2s;
      background: transparent;
      clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 10px, 100% 100%, 10px 100%, 0 calc(100% - 10px));
    }
    .btn-ghost:hover {
      border-color: var(--accent);
      color: var(--accent);
      background: rgba(0,229,255,0.04);
    }

    .hero-stats {
      display: flex;
      gap: 2.5rem;
      margin-top: 3.5rem;
      padding-top: 2rem;
      border-top: 1px solid var(--border);
    }
    .stat-num {
      font-family: var(--sans);
      font-weight: 800;
      font-size: 2rem;
      color: var(--accent);
      line-height: 1;
    }
    .stat-label {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--text-dim);
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-top: 0.3rem;
    }

    /* ── SECTIONS ── */
    section {
      padding: 6rem 3rem;
      max-width: 1100px;
      margin: 0 auto;
    }

    .section-label {
      display: flex;
      align-items: center;
      gap: 1rem;
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--accent);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 1rem;
    }
    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      max-width: 60px;
      background: var(--accent);
    }

    h2 {
      font-family: var(--sans);
      font-weight: 800;
      font-size: clamp(2rem, 4vw, 3rem);
      color: var(--text-bright);
      letter-spacing: -0.02em;
      margin-bottom: 3rem;
    }

    /* ── ABOUT ── */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }

    .about-text p {
      color: var(--text);
      font-size: 1rem;
      line-height: 1.8;
      margin-bottom: 1rem;
    }
    .about-text strong { color: var(--accent2); font-weight: 600; }

    .about-highlights {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      margin-top: 1.5rem;
    }
    .highlight-item {
      display: flex;
      align-items: flex-start;
      gap: 0.8rem;
      font-family: var(--mono);
      font-size: 0.8rem;
      color: var(--text-dim);
      line-height: 1.5;
    }
    .highlight-item::before {
      content: '▸';
      color: var(--accent);
      flex-shrink: 0;
    }
    .highlight-item em { color: var(--text); font-style: normal; }

    /* ── SKILLS ── */
    .skills-group { margin-bottom: 2.5rem; }
    .skills-group-title {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--text-dim);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 1rem;
    }
    .skills-chips {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
    }
    .chip {
      display: inline-block;
      padding: 0.35rem 0.9rem;
      border: 1px solid var(--border-bright);
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--text);
      letter-spacing: 0.04em;
      transition: all 0.2s;
      background: var(--surface);
    }
    .chip:hover {
      border-color: var(--accent);
      color: var(--accent);
      background: rgba(0,229,255,0.05);
    }
    .chip.highlight {
      border-color: rgba(0,229,255,0.4);
      color: var(--accent);
      background: rgba(0,229,255,0.07);
    }

    /* ── PROJECTS ── */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 1.5rem;
    }

    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 1.8rem;
      transition: all 0.25s;
      position: relative;
      overflow: hidden;
    }
    .project-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 3px; height: 0;
      background: var(--accent);
      transition: height 0.3s;
    }
    .project-card:hover::before { height: 100%; }
    .project-card:hover {
      border-color: var(--border-bright);
      transform: translateY(-4px);
      box-shadow: 0 12px 40px rgba(0,0,0,0.4);
    }

    .project-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 1rem;
    }
    .project-icon {
      font-size: 1.5rem;
    }
    .project-links {
      display: flex;
      gap: 0.8rem;
    }
    .project-link {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--text-dim);
      text-decoration: none;
      letter-spacing: 0.06em;
      transition: color 0.2s;
      text-transform: uppercase;
    }
    .project-link:hover { color: var(--accent); }
    .project-link.demo { color: var(--accent2); }

    .project-name {
      font-family: var(--sans);
      font-weight: 700;
      font-size: 1.1rem;
      color: var(--text-bright);
      margin-bottom: 0.6rem;
    }
    .project-desc {
      font-size: 0.88rem;
      color: var(--text-dim);
      line-height: 1.65;
      margin-bottom: 1.2rem;
    }
    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
    }
    .project-tag {
      font-family: var(--mono);
      font-size: 0.65rem;
      padding: 0.2rem 0.6rem;
      background: rgba(0,229,255,0.07);
      color: var(--accent);
      letter-spacing: 0.05em;
    }

    /* ── EXPERIENCE ── */
    .exp-timeline { position: relative; }
    .exp-timeline::before {
      content: '';
      position: absolute;
      left: 0; top: 8px; bottom: 0;
      width: 1px;
      background: linear-gradient(to bottom, var(--accent), transparent);
    }
    .exp-item {
      padding-left: 2.5rem;
      margin-bottom: 3rem;
      position: relative;
    }
    .exp-item::before {
      content: '';
      position: absolute;
      left: -4px; top: 8px;
      width: 9px; height: 9px;
      border: 1px solid var(--accent);
      background: var(--bg);
      transform: rotate(45deg);
    }
    .exp-period {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--accent);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 0.4rem;
    }
    .exp-role {
      font-family: var(--sans);
      font-weight: 700;
      font-size: 1.15rem;
      color: var(--text-bright);
      margin-bottom: 0.2rem;
    }
    .exp-company {
      font-family: var(--mono);
      font-size: 0.8rem;
      color: var(--text-dim);
      margin-bottom: 1rem;
    }
    .exp-points {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 0.5rem;
    }
    .exp-points li {
      font-size: 0.9rem;
      color: var(--text);
      padding-left: 1rem;
      position: relative;
      line-height: 1.6;
    }
    .exp-points li::before {
      content: '—';
      position: absolute;
      left: 0;
      color: var(--accent);
      font-size: 0.75rem;
    }

    /* ── CONTACT ── */
    #contact { text-align: center; }
    .contact-inner { max-width: 540px; margin: 0 auto; }
    .contact-inner p {
      color: var(--text-dim);
      font-size: 1rem;
      line-height: 1.75;
      margin-bottom: 2.5rem;
    }
    .contact-links {
      display: flex;
      justify-content: center;
      gap: 1.5rem;
      flex-wrap: wrap;
    }
    .contact-link {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.7rem 1.4rem;
      border: 1px solid var(--border-bright);
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--text);
      text-decoration: none;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      transition: all 0.2s;
      background: var(--surface);
    }
    .contact-link:hover {
      border-color: var(--accent);
      color: var(--accent);
      background: rgba(0,229,255,0.06);
    }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      padding: 2rem 3rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    footer p {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--text-dim);
      letter-spacing: 0.06em;
    }
    footer a { color: var(--accent); text-decoration: none; }

    /* ── TERMINAL BIO BOX ── */
    .terminal-box {
      background: var(--bg2);
      border: 1px solid var(--border);
      padding: 1.5rem;
      font-family: var(--mono);
      font-size: 0.8rem;
      line-height: 1.8;
      color: var(--text-dim);
    }
    .terminal-box .prompt { color: var(--accent); }
    .terminal-box .value { color: var(--accent2); }
    .terminal-box .key { color: var(--text); }
    .terminal-top {
      display: flex;
      align-items: center;
      gap: 0.4rem;
      margin-bottom: 1rem;
      padding-bottom: 0.7rem;
      border-bottom: 1px solid var(--border);
    }
    .dot { width: 10px; height: 10px; border-radius: 50%; }
    .dot.r { background: #ff5f57; }
    .dot.y { background: #febc2e; }
    .dot.g { background: #28c840; }
    .terminal-title {
      margin-left: auto;
      font-size: 0.65rem;
      color: var(--text-dim);
      letter-spacing: 0.06em;
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }

    .fade-up { opacity: 0; animation: fadeUp 0.7s ease forwards; }
    .delay-1 { animation-delay: 0.15s; }
    .delay-2 { animation-delay: 0.3s; }
    .delay-3 { animation-delay: 0.45s; }
    .delay-4 { animation-delay: 0.6s; }

    .cursor {
      display: inline-block;
      width: 2px; height: 1em;
      background: var(--accent);
      margin-left: 2px;
      vertical-align: text-bottom;
      animation: blink 1s step-end infinite;
    }

    /* ── ERRORS PANEL ── */
    .errors-section {
      background: var(--bg2);
      border: 1px solid #3a1a1a;
      border-left: 3px solid var(--accent3);
      padding: 2rem;
      margin-bottom: 2rem;
    }
    .errors-section h3 {
      font-family: var(--mono);
      font-size: 0.8rem;
      color: var(--accent3);
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 1.2rem;
    }
    .error-item {
      display: flex;
      gap: 1rem;
      align-items: flex-start;
      margin-bottom: 0.8rem;
      font-size: 0.88rem;
      line-height: 1.6;
      color: var(--text);
    }
    .error-badge {
      flex-shrink: 0;
      font-family: var(--mono);
      font-size: 0.65rem;
      padding: 0.15rem 0.5rem;
      letter-spacing: 0.05em;
      text-transform: uppercase;
    }
    .badge-warn { background: rgba(255,107,107,0.15); color: var(--accent3); border: 1px solid rgba(255,107,107,0.3); }
    .badge-info { background: rgba(0,229,255,0.1); color: var(--accent); border: 1px solid rgba(0,229,255,0.2); }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      #hero { padding: 7rem 1.5rem 3rem; }
      section { padding: 4rem 1.5rem; }
      .about-grid { grid-template-columns: 1fr; gap: 2rem; }
      .hero-stats { gap: 1.5rem; }
      footer { flex-direction: column; gap: 0.5rem; text-align: center; }
    }
  </style>
</head>
<body>

  <!-- ── NAV ── -->
  <nav>
    <div class="nav-logo"><span>~/</span>shashidhar.dev</div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- ── HERO ── -->
  <section id="hero" style="max-width:unset; padding-left:3rem; padding-right:3rem;">
    <div class="hero-grid"></div>
    <div class="hero-glow"></div>
    <div class="hero-content">
      <div class="hero-tag fade-up">Available for opportunities</div>
      <h1 class="fade-up delay-1">
        Shashidhar<br/>
        <span class="dim">Sang</span><span class="accent">epu</span><span class="cursor"></span>
      </h1>
      <p class="hero-role fade-up delay-2">
        Full Stack Developer &nbsp;/&nbsp; <em>MERN &amp; Next.js</em> &nbsp;/&nbsp; System Design
      </p>
      <p class="hero-desc fade-up delay-3">
        Building production-ready, scalable web systems from Hyderabad, India.
        Specialising in clean frontend architecture and high-performance APIs.
      </p>
      <div class="hero-btns fade-up delay-4">
        <a href="#projects" class="btn-primary">View Projects →</a>
        <a href="mailto:sangepushashidhar@gmail.com" class="btn-ghost">Get in Touch</a>
      </div>
      <div class="hero-stats fade-up delay-4">
        <div>
          <div class="stat-num">2+</div>
          <div class="stat-label">Years Exp.</div>
        </div>
        <div>
          <div class="stat-num">75</div>
          <div class="stat-label">GitHub Repos</div>
        </div>
        <div>
          <div class="stat-num">25%</div>
          <div class="stat-label">Bundle Reduction</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── ABOUT ── -->
  <section id="about">
    <div class="section-label">01 — About</div>
    <h2>Who I Am</h2>
    <div class="about-grid">
      <div class="about-text">
        <p>
          I'm a <strong>Certified Frontend Developer</strong> with a strong full-stack foundation in
          the <strong>MERN Stack</strong> (MongoDB, Express.js, React, Node.js) and Next.js.
          I care deeply about clean architecture, developer experience, and systems that scale.
        </p>
        <p>
          I've delivered measurable results — implementing <strong>Redux &amp; React Query</strong>
          to cut bundle size by <strong>25%</strong> and boost team productivity by <strong>15%</strong>.
          I approach every project with the discipline of a systems thinker, not just a feature builder.
        </p>
        <div class="about-highlights">
          <div class="highlight-item"><em>Frontend Architecture</em> with React, Next.js &amp; TypeScript</div>
          <div class="highlight-item"><em>Backend Engineering</em> with Node.js, Express &amp; REST APIs</div>
          <div class="highlight-item"><em>Database design</em> — MongoDB &amp; MySQL</div>
          <div class="highlight-item"><em>Containerisation</em> with Docker &amp; Git workflows</div>
          <div class="highlight-item">Passionate about <em>AI-assisted dev workflows</em></div>
        </div>
      </div>
      <div>
        <div class="terminal-box">
          <div class="terminal-top">
            <div class="dot r"></div>
            <div class="dot y"></div>
            <div class="dot g"></div>
            <span class="terminal-title">profile.json</span>
          </div>
          <div><span class="prompt">$ </span>cat profile.json</div>
          <br/>
          <div>{</div>
          <div>&nbsp;&nbsp;<span class="key">"name"</span>: <span class="value">"Shashidhar Sangepu"</span>,</div>
          <div>&nbsp;&nbsp;<span class="key">"role"</span>: <span class="value">"Full Stack Developer"</span>,</div>
          <div>&nbsp;&nbsp;<span class="key">"location"</span>: <span class="value">"Hyderabad, India"</span>,</div>
          <div>&nbsp;&nbsp;<span class="key">"experience"</span>: <span class="value">"2+ years"</span>,</div>
          <div>&nbsp;&nbsp;<span class="key">"stack"</span>: [</div>
          <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="value">"React"</span>, <span class="value">"Next.js"</span>, <span class="value">"Node"</span>,</div>
          <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="value">"TypeScript"</span>, <span class="value">"MongoDB"</span></div>
          <div>&nbsp;&nbsp;],</div>
          <div>&nbsp;&nbsp;<span class="key">"focus"</span>: <span class="value">"System Design &amp; AI"</span>,</div>
          <div>&nbsp;&nbsp;<span class="key">"available"</span>: <span style="color:#28c840">true</span></div>
          <div>}</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── SKILLS ── -->
  <section id="skills">
    <div class="section-label">02 — Skills</div>
    <h2>Tech Stack</h2>

    <div class="skills-group">
      <div class="skills-group-title">Frontend</div>
      <div class="skills-chips">
        <span class="chip highlight">React.js</span>
        <span class="chip highlight">Next.js</span>
        <span class="chip highlight">TypeScript</span>
        <span class="chip">JavaScript (ES2022+)</span>
        <span class="chip">Redux Toolkit</span>
        <span class="chip">React Query</span>
        <span class="chip">HTML5</span>
        <span class="chip">CSS3 / Sass</span>
        <span class="chip">Tailwind CSS</span>
      </div>
    </div>

    <div class="skills-group">
      <div class="skills-group-title">Backend &amp; Database</div>
      <div class="skills-chips">
        <span class="chip highlight">Node.js</span>
        <span class="chip highlight">Express.js</span>
        <span class="chip">MongoDB</span>
        <span class="chip">MySQL</span>
        <span class="chip">REST APIs</span>
        <span class="chip">JWT Auth</span>
      </div>
    </div>

    <div class="skills-group">
      <div class="skills-group-title">DevOps &amp; Tooling</div>
      <div class="skills-chips">
        <span class="chip">Docker</span>
        <span class="chip">Git &amp; GitHub</span>
        <span class="chip">Netlify / Vercel</span>
        <span class="chip">Postman</span>
        <span class="chip">VS Code</span>
      </div>
    </div>

    <div class="skills-group">
      <div class="skills-group-title">Interests &amp; Learning</div>
      <div class="skills-chips">
        <span class="chip">System Design</span>
        <span class="chip">AI Integrations</span>
        <span class="chip">LLM APIs</span>
        <span class="chip">Performance Optimisation</span>
        <span class="chip">Microservices</span>
      </div>
    </div>
  </section>

  <!-- ── PROJECTS ── -->
  <section id="projects">
    <div class="section-label">03 — Projects</div>
    <h2>Featured Work</h2>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-header">
          <div class="project-icon">🧠</div>
          <div class="project-links">
            <a href="https://github.com/Shashi5657/Nextjs-Master" class="project-link" target="_blank">GitHub</a>
          </div>
        </div>
        <div class="project-name">Next.js Master</div>
        <div class="project-desc">
          Comprehensive Next.js learning repository covering SSR, SSG, API routes, App Router, and production patterns. A structured reference for advanced Next.js development.
        </div>
        <div class="project-tags">
          <span class="project-tag">Next.js</span>
          <span class="project-tag">JavaScript</span>
          <span class="project-tag">App Router</span>
          <span class="project-tag">SSR/SSG</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div class="project-icon">📝</div>
          <div class="project-links">
            <a href="https://github.com/Shashi5657/notes-app-react" class="project-link" target="_blank">GitHub</a>
          </div>
        </div>
        <div class="project-name">Notes App</div>
        <div class="project-desc">
          A full-featured notes management application built with React. Supports creation, editing, deletion, and search — with clean state management patterns.
        </div>
        <div class="project-tags">
          <span class="project-tag">React.js</span>
          <span class="project-tag">State Management</span>
          <span class="project-tag">CRUD</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div class="project-icon">⏱️</div>
          <div class="project-links">
            <a href="https://github.com/Shashi5657/Pomodoro-Timer" class="project-link" target="_blank">GitHub</a>
          </div>
        </div>
        <div class="project-name">Pomodoro Timer</div>
        <div class="project-desc">
          A productivity-focused Pomodoro timer with work/break cycle management, custom intervals, and session tracking. Built for real daily use.
        </div>
        <div class="project-tags">
          <span class="project-tag">JavaScript</span>
          <span class="project-tag">React</span>
          <span class="project-tag">Productivity</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div class="project-icon">🎮</div>
          <div class="project-links">
            <a href="https://github.com/Shashi5657/tic-tac-toe" class="project-link" target="_blank">GitHub</a>
          </div>
        </div>
        <div class="project-name">Tic-Tac-Toe</div>
        <div class="project-desc">
          Classic two-player game with win detection, draw handling, and board reset. Demonstrates React component design, hooks, and event handling.
        </div>
        <div class="project-tags">
          <span class="project-tag">React.js</span>
          <span class="project-tag">Game Logic</span>
          <span class="project-tag">Hooks</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div class="project-icon">👤</div>
          <div class="project-links">
            <a href="https://github.com/Shashi5657/React-Portfolio" class="project-link" target="_blank">GitHub</a>
            <a href="https://shashis-portfolio.netlify.app" class="project-link demo" target="_blank">Live →</a>
          </div>
        </div>
        <div class="project-name">React Portfolio</div>
        <div class="project-desc">
          Personal developer portfolio showcasing projects, skills, and experience. Deployed on Netlify with a responsive design.
        </div>
        <div class="project-tags">
          <span class="project-tag">React.js</span>
          <span class="project-tag">Netlify</span>
          <span class="project-tag">Portfolio</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div class="project-icon">⚛️</div>
          <div class="project-links">
            <a href="https://github.com/Shashi5657/React_Master" class="project-link" target="_blank">GitHub</a>
          </div>
        </div>
        <div class="project-name">React Master</div>
        <div class="project-desc">
          Structured React learning repository covering core concepts, hooks, context, custom hooks, and architecture patterns from fundamentals to advanced.
        </div>
        <div class="project-tags">
          <span class="project-tag">React.js</span>
          <span class="project-tag">Hooks</span>
          <span class="project-tag">Context API</span>
          <span class="project-tag">Patterns</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ── EXPERIENCE ── -->
  <section id="experience">
    <div class="section-label">04 — Experience</div>
    <h2>Work History</h2>
    <div class="exp-timeline">

      <div class="exp-item">
        <div class="exp-period">2022 — Present</div>
        <div class="exp-role">Full Stack Developer</div>
        <div class="exp-company">MERN Stack · Hyderabad, India</div>
        <ul class="exp-points">
          <li>Architected scalable frontend systems using React.js, TypeScript, and Next.js with clean component boundaries and performance-first patterns.</li>
          <li>Implemented Redux Toolkit &amp; React Query for state management, reducing bundle size by 25% and improving team productivity by 15%.</li>
          <li>Built and consumed RESTful APIs with Node.js and Express.js, integrating MongoDB and MySQL databases.</li>
          <li>Containerised services using Docker for consistent development and deployment environments.</li>
          <li>Focused on authentication flows (JWT), performance optimisation, and DX improvements across the stack.</li>
        </ul>
      </div>

      <div class="exp-item">
        <div class="exp-period">Ongoing</div>
        <div class="exp-role">Open Source &amp; Personal Projects</div>
        <div class="exp-company">GitHub: Shashi5657 · 75+ Repositories</div>
        <ul class="exp-points">
          <li>Actively maintaining 75+ public repositories covering React, Next.js, and full-stack architectures.</li>
          <li>Continuously learning Advanced System Design, AI integrations, and LLM-powered developer workflows.</li>
        </ul>
      </div>

    </div>
  </section>

  <!-- ── CONTACT ── -->
  <section id="contact">
    <div class="section-label" style="justify-content:center">05 — Contact</div>
    <h2 style="text-align:center">Let's Build Together</h2>
    <div class="contact-inner">
      <p>
        I'm open to full-time roles, freelance projects, and interesting collaborations.
        If you're working on something challenging and want a developer who thinks in systems — let's talk.
      </p>
      <div class="contact-links">
        <a href="mailto:sangepushashidhar@gmail.com" class="contact-link">✉ Email</a>
        <a href="https://www.linkedin.com/in/shashidharsangepu/" class="contact-link" target="_blank">in LinkedIn</a>
        <a href="https://github.com/Shashi5657" class="contact-link" target="_blank">⌥ GitHub</a>
        <a href="https://wa.me/918639439876" class="contact-link" target="_blank">◎ WhatsApp</a>
      </div>
    </div>
  </section>

  <!-- ── FOOTER ── -->
  <footer>
    <p>© 2025 <a href="#">Shashidhar Sangepu</a> — Built with clean code &amp; intention.</p>
    <p><a href="https://shashis-portfolio.netlify.app" target="_blank">shashis-portfolio.netlify.app</a></p>
  </footer>

</body>
</html>
