[index.html](https://github.com/user-attachments/files/26486757/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sai Kumar Gummadavelly — A Story of Code, Curiosity & Clarity</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=DM+Sans:wght@300;400;500&family=Cinzel:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #0d0d0d;
    --cream: #f5f0e8;
    --gold: #c9933a;
    --gold-light: #e8b96a;
    --rust: #8b3a2a;
    --cloud: #ddd8cc;
    --muted: #6b6255;
    --white: #fefcf8;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--ink);
    color: var(--cream);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ─── CURSOR ─── */
  body { cursor: none; }
  #cursor {
    position: fixed; width: 12px; height: 12px;
    background: var(--gold); border-radius: 50%;
    pointer-events: none; z-index: 9999;
    transform: translate(-50%,-50%);
    transition: transform 0.1s, background 0.3s;
    mix-blend-mode: difference;
  }

  /* ─── NOISE OVERLAY ─── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 1000; opacity: 0.35;
  }

  /* ─── NAV ─── */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 500;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.5rem 4rem;
    background: linear-gradient(to bottom, rgba(13,13,13,0.95), transparent);
    backdrop-filter: blur(8px);
  }
  .nav-logo {
    font-family: 'Cinzel', serif;
    font-size: 1.1rem; letter-spacing: 0.2em;
    color: var(--gold); text-decoration: none;
  }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    color: var(--cloud); text-decoration: none;
    font-size: 0.8rem; letter-spacing: 0.15em; text-transform: uppercase;
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--gold); }

  /* ─── HERO ─── */
  #hero {
    min-height: 100vh;
    position: relative;
    display: flex; align-items: center; justify-content: center;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background: url('https://images.unsplash.com/photo-1519681393784-d120267933ba?w=1600') center/cover no-repeat;
    filter: brightness(0.25) saturate(0.6);
  }
  .hero-gradient {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(13,13,13,0.7) 0%, rgba(201,147,58,0.08) 50%, rgba(13,13,13,0.9) 100%);
  }
  .hero-content {
    position: relative; z-index: 2;
    text-align: center; padding: 2rem;
    max-width: 900px;
  }
  .hero-eyebrow {
    font-family: 'Cinzel', serif;
    font-size: 0.75rem; letter-spacing: 0.4em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 1.5rem;
    animation: fadeUp 1s ease 0.2s both;
  }
  .hero-name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1rem, 4vw, 4rem);
    font-weight: 900; line-height: 0.95;
    color: var(--white);
    animation: fadeUp 1s ease 0.4s both;
  }
  .hero-name em {
    font-style: italic; color: var(--gold);
    display: block;
  }
  .hero-tagline {
    margin-top: 2rem;
    font-size: 1.1rem; font-weight: 300;
    color: var(--cloud); line-height: 1.8;
    max-width: 600px; margin-left: auto; margin-right: auto;
    animation: fadeUp 1s ease 0.6s both;
  }
  .hero-scroll {
    margin-top: 4rem;
    display: flex; flex-direction: column; align-items: center; gap: 0.5rem;
    animation: fadeUp 1s ease 0.9s both;
  }
  .hero-scroll span {
    font-size: 0.7rem; letter-spacing: 0.3em; text-transform: uppercase;
    color: var(--muted);
  }
  .scroll-line {
    width: 1px; height: 60px;
    background: linear-gradient(to bottom, var(--gold), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }

  /* ─── CONNECT STRIP ─── */
  .connect-strip {
    background: rgba(201,147,58,0.08);
    border-top: 1px solid rgba(201,147,58,0.2);
    border-bottom: 1px solid rgba(201,147,58,0.2);
    padding: 1.2rem 4rem;
    display: flex; gap: 2.5rem; align-items: center; justify-content: center;
    flex-wrap: wrap;
  }
  .connect-link {
    display: flex; align-items: center; gap: 0.6rem;
    color: var(--cloud); text-decoration: none;
    font-size: 0.78rem; letter-spacing: 0.08em;
    transition: color 0.3s, transform 0.3s;
  }
  .connect-link:hover { color: var(--gold); transform: translateY(-2px); }
  .connect-link img {
    width: 22px; height: 22px; object-fit: contain;
    border-radius: 4px;
    filter: brightness(0.9);
  }

  /* ─── CHAPTER SYSTEM ─── */
  .chapter {
    max-width: 1100px; margin: 0 auto;
    padding: 8rem 4rem;
    position: relative;
  }
  .chapter-number {
    font-family: 'Playfair Display', serif;
    font-size: 8rem; font-weight: 900;
    color: rgba(201,147,58,0.06);
    position: absolute; top: 4rem; left: 2rem;
    line-height: 1; pointer-events: none;
    user-select: none;
  }
  .chapter-label {
    font-family: 'Cinzel', serif;
    font-size: 0.7rem; letter-spacing: 0.4em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 1rem;
    display: flex; align-items: center; gap: 1rem;
  }
  .chapter-label::before {
    content: ''; display: block;
    width: 40px; height: 1px; background: var(--gold);
  }
  .chapter-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3.5rem);
    font-weight: 700; line-height: 1.15;
    color: var(--white); margin-bottom: 2.5rem;
  }
  .chapter-title em { font-style: italic; color: var(--gold); }
  .chapter-body {
    font-size: 1.05rem; line-height: 1.95;
    color: var(--cloud); max-width: 720px;
  }
  .chapter-body p { margin-bottom: 1.5rem; }

  .divider {
    width: 100%; height: 1px;
    background: linear-gradient(to right, transparent, rgba(201,147,58,0.3), transparent);
    margin: 0 auto;
  }

  /* ─── EDUCATION TIMELINE ─── */
  .timeline {
    position: relative;
    padding-left: 3rem;
    margin-top: 3rem;
  }
  .timeline::before {
    content: ''; position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, var(--gold), rgba(201,147,58,0.1));
  }
  .timeline-item {
    position: relative;
    margin-bottom: 3.5rem;
    opacity: 0; transform: translateX(-20px);
    transition: all 0.7s ease;
  }
  .timeline-item.visible { opacity: 1; transform: translateX(0); }
  .timeline-dot {
    position: absolute; left: -3rem;
    top: 0.3rem;
    width: 10px; height: 10px;
    border-radius: 50%;
    background: var(--gold);
    transform: translateX(-4.5px);
    box-shadow: 0 0 15px rgba(201,147,58,0.5);
  }
  .timeline-year {
    font-family: 'Cinzel', serif;
    font-size: 0.72rem; letter-spacing: 0.2em; color: var(--gold);
    margin-bottom: 0.4rem;
  }
  .timeline-place {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-weight: 700; color: var(--white);
    margin-bottom: 0.3rem;
  }
  .timeline-degree {
    font-size: 0.9rem; color: var(--muted);
    margin-bottom: 0.8rem;
  }
  .timeline-desc {
    font-size: 0.95rem; line-height: 1.7; color: var(--cloud);
  }

  /* ─── EXPERIENCE CARDS ─── */
  .exp-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 2rem; margin-top: 3rem;
  }
  .exp-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(201,147,58,0.15);
    border-radius: 2px;
    padding: 2.5rem;
    transition: border-color 0.3s, transform 0.3s;
    opacity: 0; transform: translateY(20px);
    transition: all 0.6s ease;
  }
  .exp-card.visible { opacity: 1; transform: translateY(0); }
  .exp-card:hover {
    border-color: rgba(201,147,58,0.5);
    transform: translateY(-4px);
  }
  .exp-icon {
    font-size: 2rem; margin-bottom: 1rem;
  }
  .exp-role {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem; font-weight: 700; color: var(--white);
    margin-bottom: 0.5rem;
  }
  .exp-desc {
    font-size: 0.9rem; line-height: 1.7; color: var(--muted);
  }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 2rem; margin-top: 3rem;
  }
  .project-card {
    position: relative; overflow: hidden;
    border: 1px solid rgba(201,147,58,0.1);
    padding: 2.5rem;
    background: rgba(255,255,255,0.02);
    cursor: default;
    opacity: 0; transform: translateY(30px);
    transition: all 0.7s ease;
  }
  .project-card.visible { opacity: 1; transform: translateY(0); }
  .project-card::before {
    content: ''; position: absolute;
    top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(to right, var(--gold), transparent);
  }
  .project-card:hover {
    background: rgba(201,147,58,0.04);
    border-color: rgba(201,147,58,0.3);
  }
  .project-tag {
    display: inline-block;
    font-size: 0.65rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--gold); border: 1px solid rgba(201,147,58,0.4);
    padding: 0.25rem 0.75rem; margin-bottom: 1rem;
  }
  .project-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem; font-weight: 700; color: var(--white);
    margin-bottom: 1rem; line-height: 1.4;
  }
  .project-desc {
    font-size: 0.88rem; line-height: 1.75; color: var(--muted);
  }

  /* ─── SKILLS ─── */
  .skills-section { margin-top: 3rem; }
  .skill-group { margin-bottom: 2.5rem; }
  .skill-group-title {
    font-family: 'Cinzel', serif;
    font-size: 0.7rem; letter-spacing: 0.3em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 1rem;
  }
  .skill-tags {
    display: flex; flex-wrap: wrap; gap: 0.6rem;
  }
  .skill-tag {
    font-size: 0.8rem;
    padding: 0.4rem 1rem;
    border: 1px solid rgba(201,147,58,0.2);
    color: var(--cloud);
    transition: all 0.3s;
    cursor: default;
  }
  .skill-tag:hover {
    background: rgba(201,147,58,0.1);
    border-color: var(--gold);
    color: var(--gold);
  }

  /* ─── PERSONAL / STORY SECTIONS ─── */
  .story-block {
    background: rgba(255,255,255,0.02);
    border-left: 3px solid var(--gold);
    padding: 2.5rem 3rem;
    margin: 2rem 0;
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: 1.1rem; line-height: 1.9;
    color: var(--cloud);
    opacity: 0; transform: translateX(-20px);
    transition: all 0.8s ease;
  }
  .story-block.visible { opacity: 1; transform: translateX(0); }

  .insight-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 1.5rem; margin-top: 2.5rem;
  }
  .insight-card {
    padding: 1.8rem;
    border: 1px solid rgba(255,255,255,0.06);
    background: rgba(255,255,255,0.02);
    opacity: 0; transform: scale(0.95);
    transition: all 0.6s ease;
  }
  .insight-card.visible { opacity: 1; transform: scale(1); }
  .insight-card:hover {
    border-color: rgba(201,147,58,0.3);
    background: rgba(201,147,58,0.04);
  }
  .insight-person {
    font-family: 'Playfair Display', serif;
    font-size: 1rem; font-weight: 700; color: var(--white);
    margin-bottom: 0.5rem;
  }
  .insight-lesson {
    font-size: 0.85rem; line-height: 1.6; color: var(--muted);
  }

  /* ─── TRAVEL HERO ─── */
  .travel-visual {
    position: relative; height: 500px;
    margin: 3rem 0; overflow: hidden;
    border: 1px solid rgba(201,147,58,0.15);
  }
  .travel-visual img {
    width: 100%; height: 100%; object-fit: cover;
    filter: brightness(0.5) saturate(0.7);
  }
  .travel-overlay {
    position: absolute; inset: 0;
    display: flex; flex-direction: column;
    justify-content: flex-end; padding: 3rem;
    background: linear-gradient(to top, rgba(13,13,13,0.9) 0%, transparent 60%);
  }
  .travel-quote {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.5rem, 3vw, 2.5rem);
    font-style: italic; color: var(--white);
    max-width: 600px; line-height: 1.4;
  }
  .travel-quote span { color: var(--gold); }

  /* ─── BLOG SECTION ─── */
  .blog-card {
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(201,147,58,0.1);
    padding: 2rem; margin-top: 2rem;
    display: flex; align-items: center; gap: 2rem;
    transition: all 0.3s;
    text-decoration: none;
  }
  .blog-card:hover {
    border-color: rgba(201,147,58,0.4);
    background: rgba(201,147,58,0.04);
    transform: translateX(8px);
  }
  .blog-icon {
    font-size: 2.5rem; flex-shrink: 0;
  }
  .blog-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-weight: 700; color: var(--white);
    margin-bottom: 0.4rem;
  }
  .blog-sub {
    font-size: 0.85rem; color: var(--muted);
  }
  .blog-arrow {
    margin-left: auto; color: var(--gold); font-size: 1.5rem;
    flex-shrink: 0;
  }

  /* ─── FOOTER ─── */
  footer {
    border-top: 1px solid rgba(201,147,58,0.15);
    padding: 4rem;
    text-align: center;
  }
  .footer-name {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem; font-style: italic;
    color: var(--gold); margin-bottom: 0.5rem;
  }
  .footer-sub {
    font-size: 0.8rem; letter-spacing: 0.2em;
    text-transform: uppercase; color: var(--muted);
    margin-bottom: 2rem;
  }
  .footer-links {
    display: flex; justify-content: center; gap: 2rem; flex-wrap: wrap;
  }
  .footer-links a {
    color: var(--muted); text-decoration: none;
    font-size: 0.8rem; letter-spacing: 0.1em;
    transition: color 0.3s;
  }
  .footer-links a:hover { color: var(--gold); }
  .footer-copy {
    margin-top: 3rem;
    font-size: 0.72rem; color: rgba(107,98,85,0.5);
    letter-spacing: 0.1em;
  }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes scrollPulse {
    0%, 100% { opacity: 0.4; transform: scaleY(1); }
    50%       { opacity: 1;   transform: scaleY(1.3); }
  }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 768px) {
    nav { padding: 1.2rem 1.5rem; }
    .nav-links { display: none; }
    .chapter { padding: 5rem 1.5rem; }
    .exp-grid, .projects-grid { grid-template-columns: 1fr; }
    .connect-strip { padding: 1rem 1.5rem; gap: 1.2rem; }
    .travel-visual { height: 320px; }
    footer { padding: 3rem 1.5rem; }
  }
</style>
</head>
<body>

<div id="cursor"></div>

<!-- NAV -->
<nav>
  <a href="#hero" class="nav-logo">Profilo Personale & Professionale</a>
  <ul class="nav-links">
    <li><a href="#education">Education</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#life">Life</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-gradient"></div>
  <div class="hero-content">
    <p class="hero-eyebrow">PhD Researcher · Cloud Engineer · Thinker</p>
    <h1 class="hero-name">
      Sai Kumar
      <em>Gummadavelly</em>
    </h1>
    <p class="hero-tagline">
      From a curious student learning lines of code to a researcher reshaping the boundaries of cloud computing — this is not just a portfolio. <em>This is a story.</em>
    </p>
    <div class="hero-scroll">
      <span>Begin the journey</span>
      <div class="scroll-line"></div>
    </div>
  </div>
</section>

<!-- CONNECT STRIP -->
<div class="connect-strip" id="contact">
  <a href="https://linkedin.com/in/sai-kumar-gummadavelly-9a6736354" target="_blank" class="connect-link">
    <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" alt="LinkedIn"> LinkedIn
  </a>
  <a href="mailto:billiondreams.62@gmail.com" class="connect-link">
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/7e/Gmail_icon_%282020%29.svg" alt="Email"> billiondreams.62@gmail.com
  </a>
  <a href="https://www.researchgate.net/profile/Sai-Gummadavelly" target="_blank" class="connect-link">
    <img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/ResearchGate_icon_SVG.svg" alt="ResearchGate"> ResearchGate
  </a>
  
  <a href="https://chaostoclaritydiary.blogspot.com/" target="_blank" class="connect-link">
    ✍️ Blog: Chaos to Clarity
  </a>
  <a href="https://linktr.ee/billiondreams.62" target="_blank" class="connect-link">
    🌐 Linktree
  </a>
</div>


<!-- DIVIDER -->
<div class="divider"></div>

<!-- CHAPTER 1: EDUCATION -->
<section id="education">
  <div class="chapter">
    <div class="chapter-number">01</div>
    <p class="chapter-label">Chapter One</p>
    <h2 class="chapter-title">The Making of a <em>Mind</em></h2>
    <div class="chapter-body">
      <p>Every great story begins with a question. Mine began with one simple, burning question — <em>how do these systems actually work?</em> That question set me on a path I have never stepped off.</p>
    </div>
    <div class="timeline">
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-year">B.Tech — Foundation</div>
        <div class="timeline-place">Jayamukhi Institute of Technological Sciences</div>
        <div class="timeline-degree">B.Tech in Computer Science & Engineering · JNTUH</div>
        <div class="timeline-desc">Where curiosity became passion. I learned programming, data structures, and problem-solving fundamentals. This was not just education — it was the ignition of a lifelong obsession with technology.</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-year">M.Tech — Deepening</div>
        <div class="timeline-place">Vaagdevi College of Engineering</div>
        <div class="timeline-degree">M.Tech in Computer Science & Engineering · JNTUH</div>
        <div class="timeline-desc">Theory met reality. I worked on real-world problems, explored advanced concepts, and began to see technology not as subject matter but as a toolkit for solving the world's complex challenges.</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-year">PhD — Present · Ongoing</div>
        <div class="timeline-place">Shoolini University, Solan, Himachal Pradesh</div>
        <div class="timeline-degree">Doctor of Philosophy · Cloud Computing</div>
        <div class="timeline-desc">Nestled in the Himalayas, I am now pushing the frontier — researching modern cloud technologies, scalability, and digital infrastructure of tomorrow. Every experiment is a small revolution. Every paper, a step toward something meaningful.</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CHAPTER 2: EXPERIENCE -->
<section id="experience">
  <div class="chapter">
    <div class="chapter-number">02</div>
    <p class="chapter-label">Chapter Two</p>
    <h2 class="chapter-title">Where Theory <em>Meets Reality</em></h2>
    <div class="chapter-body">
      <p>The classroom gave me the language. The real world gave me the vocabulary. My career has been a bridge between the two — always learning, always building.</p>
    </div>
    <div class="exp-grid">
      <div class="exp-card">
        <div class="exp-icon">🔬</div>
        <div class="exp-role">Research & Teaching Assistant</div>
        <div class="exp-desc">I balance the weight of research and the responsibility of mentorship. Supporting cutting-edge cloud computing research while helping students transform confusion into clarity — teaching sharpened my own thinking in ways I never expected.</div>
      </div>
      <div class="exp-card">
        <div class="exp-icon">☁️</div>
        <div class="exp-role">Cloud & Network Engineer</div>
        <div class="exp-desc">From enterprise-scale cloud infrastructure to live network troubleshooting under pressure — I've designed scalable systems, ensured uptime when it mattered most, and solved problems that no textbook had prepared me for.</div>
      </div>
    </div>
    <div class="story-block">
      "Today, I stand at a point where research knowledge and industry experience come together — helping me grow as a skilled professional in cloud and network technologies. I have learned to adapt, solve problems, and continuously improve."
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CHAPTER 3: PROJECTS -->
<section id="projects">
  <div class="chapter">
    <div class="chapter-number">03</div>
    <p class="chapter-label">Chapter Three</p>
    <h2 class="chapter-title">Ideas I <em>Built</em></h2>
    <div class="chapter-body">
      <p>Every project is a problem I refused to leave unsolved. These are not just research papers — they are conversations with the future of technology.</p>
    </div>
    <div class="projects-grid">
      <div class="project-card">
        <span class="project-tag">Machine Learning · Finance</span>
        <div class="project-title">Predicting Stock Market Trends Using ML & Deep Learning: A Competitive Analysis</div>
        <div class="project-desc">A rigorous comparative analysis of ML and deep learning algorithms — from SVM and linear regression for continuous data, to LSTM and RNN networks for capturing temporal dependencies. Evaluating accuracy, precision, recall, and F1 score across models to determine the most effective approach for financial trend prediction.</div>
      </div>
      <div class="project-card">
        <span class="project-tag">Cloud Security · Cryptography</span>
        <div class="project-title">Expressive, Efficient & Revocable Data Access Control for Multi-Authority Cloud Storage</div>
        <div class="project-desc">Designed a CP-ABE based scheme that solves the attribute revocation problem in untrusted multi-authority cloud environments. The system achieves both forward and backward security — giving data owners true control, without compromising cloud scalability or efficiency.</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CHAPTER 4: SKILLS -->
<section id="skills">
  <div class="chapter">
    <div class="chapter-number">04</div>
    <p class="chapter-label">Chapter Four</p>
    <h2 class="chapter-title">The <em>Arsenal</em></h2>
    <div class="chapter-body">
      <p>My skills are not just tools I learned — they are abilities I built through curiosity, practice, and real-world challenges. Each one tells its own small story of persistence.</p>
    </div>
    <div class="skills-section">
      <div class="skill-group">
        <div class="skill-group-title">Programming Languages</div>
        <div class="skill-tags">
          <span class="skill-tag">Python</span><span class="skill-tag">Java</span><span class="skill-tag">C</span><span class="skill-tag">C++</span><span class="skill-tag">C#</span><span class="skill-tag">JavaScript</span><span class="skill-tag">Shell Scripting</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Cloud & Infrastructure</div>
        <div class="skill-tags">
          <span class="skill-tag">Cloud Computing</span><span class="skill-tag">Network Engineering</span><span class="skill-tag">TCP/IP</span><span class="skill-tag">OSI Model</span><span class="skill-tag">Cisco Networking</span><span class="skill-tag">Routing & Switching</span><span class="skill-tag">Wireshark</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Cybersecurity</div>
        <div class="skill-tags">
          <span class="skill-tag">Threat Detection</span><span class="skill-tag">Network Vulnerabilities</span><span class="skill-tag">Endpoint Security</span><span class="skill-tag">Data Privacy</span><span class="skill-tag">Windows Security</span><span class="skill-tag">Unix/Linux Security</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Data & AI</div>
        <div class="skill-tags">
          <span class="skill-tag">Machine Learning</span><span class="skill-tag">Deep Learning</span><span class="skill-tag">NLP</span><span class="skill-tag">Data Analytics</span><span class="skill-tag">Data Visualization</span><span class="skill-tag">Tableau</span><span class="skill-tag">Microsoft Excel</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Databases & Web</div>
        <div class="skill-tags">
          <span class="skill-tag">SQL</span><span class="skill-tag">MySQL</span><span class="skill-tag">IBM Db2</span><span class="skill-tag">Oracle Database</span><span class="skill-tag">REST APIs</span><span class="skill-tag">HTML</span><span class="skill-tag">CSS</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Systems & Methodology</div>
        <div class="skill-tags">
          <span class="skill-tag">Linux</span><span class="skill-tag">Windows Server</span><span class="skill-tag">Active Directory</span><span class="skill-tag">Agile</span><span class="skill-tag">Scrum</span>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CHAPTER 5: PERSONAL LIFE -->
<section id="life">
  <div class="chapter">
    <div class="chapter-number">05</div>
    <p class="chapter-label">Chapter Five</p>
    <h2 class="chapter-title">Beyond the <em>Code</em></h2>
    <div class="chapter-body">
      <p>A person is more than their profession. Here is the side of me that does not fit on a resume — the side that makes me who I truly am.</p>
    </div>

    <!-- Books -->
    <div style="margin-top:3rem;">
      <p class="chapter-label" style="margin-bottom:1rem;">On Reading</p>
      <div class="story-block">
        I have a deep passion for reading books, especially those that explore philosophy, history, and human relationships. Works like The Fountainhead by Ayn Rand have shaped my thinking about individuality and self-belief, while Mein Kampf by Adolf Hitler helped me understand the importance of critical thinking and the impact of ideology. At the same time, novels like Half Girlfriend and 2 States: The Story of My Marriage by Chetan Bhagat have taught me valuable lessons about love, relationships, and cultural differences.
        Through reading, I have gained insights into life, developed a broader perspective, and learned to think more deeply about the world around me. Books are not just a hobby for me—they are a source of knowledge, growth, and personal transformation.
      </div>
    </div>

    <!-- Love & War -->
    <div style="margin-top:3rem;">
      <p class="chapter-label" style="margin-bottom:1rem;">Love, War & What They Taught Me</p>
      <div class="story-block">
I once believed that love is about feelings and war is about power. But over time, I learned that both are not always fair.
In relationships, you can care deeply and still get hurt. You can be honest and still be misunderstood. Love is not always equal, and sometimes even your best efforts are not enough. That’s where I started learning patience, understanding, and emotional strength.

At the same time, I explored history and global conflicts. From World War I and World War II to the long tension of the Cold War, I saw that wars are also not fair. Strong nations don’t always win easily, and small decisions can change everything. Events like the Cuban Missile Crisis showed how close the world came to disaster.
I also studied conflicts like the Vietnam War, Korean War, and Soviet-Afghan War, along with ongoing Middle East conflicts. These taught me that every side has its own reasons, and understanding those reasons is the key to diplomacy.


        "I once believed that love is about feelings and war is about power. But over time, I learned that both are not always fair... Both love and war taught me the same simple truth: <span style="color:var(--gold);font-style:normal;">understanding people matters more than trying to control situations.</span> Peace comes from understanding."
      </div>
    </div>

    <!-- Inspirations -->
    <div style="margin-top:3rem;">
      <p class="chapter-label" style="margin-bottom:1.5rem;">Different Paths, One Lesson</p>
      <div class="insight-grid">
        <div class="insight-card">
          <div class="insight-person">Thomas Edison</div>
          <div class="insight-lesson">Patience. Thousands of failures did not stop him. Success is often just persistence in disguise.</div>
        </div>
        <div class="insight-card">
          <div class="insight-person">Anne Frank (German Diarist)</div>
          <div class="insight-lesson"> I learned hope. Even in the darkest times, she believed in goodness. That kind of mindset is true strength (Died at age 15 in the Bergen-Belsen concentration camp).</div>
        </div>
        <div class="insight-card">
          <div class="insight-person">Chris Gardner</div>
          <div class="insight-lesson">Resilience. From homelessness to success — life can change if you refuse to give up.</div>
        </div>
        <div class="insight-card">
          <div class="insight-person">Adolf Hitler (World War-II)</div>
          <div class="insight-lesson">I learned something different — inspiration to follow, but a warning. Strong determination without humanity can lead to destruction. It reminded me that ambition must always be guided by ethics.</div>
        </div>
        <div class="insight-card">
          <div class="insight-person">Bob Marley</div>
          <div class="insight-lesson"> I learned to stay positive and spread peace, no matter how hard life becomes.</div>
        </div>
        <div class="insight-card">
          <div class="insight-person">Vladimir Putin</div>
          <div class="insight-lesson"> I saw how a person can rise step by step — from ordinary work (Cab Driver) to intelligence (KGB Spy) services, and then to the highest position of power(President). It taught me that discipline and strategy can change destiny.</div>
        </div>
      </div>
    </div>

    <!-- Solo Travel -->
    <div style="margin-top:4rem;">
      <p class="chapter-label" style="margin-bottom:1.5rem;">Alone, But Not Lonely</p>
      <div class="travel-visual">
        <img src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?w=1400" alt="Mountain solo travel">
        <div class="travel-overlay">
          <p class="travel-quote">
            "People think being alone is loneliness. But I've learned something different.
            <span>Being alone is freedom.</span>"
          </p>
        </div>
      </div>
      <div class="story-block">
        I started traveling alone not to escape the world, but to understand it — and maybe understand myself. No plans, no pressure. Just me, stray animals who don't judge, quiet nights, an open sky, and my own thoughts. 
        <span style="color:var(--gold);font-style:normal;">Somewhere between empty roads and cigarette smoke disappearing into darkness... </span>
        I found a version of myself I never knew existed.
      </div>
    </div>

    <!-- Atheism -->
    <div style="margin-top:3rem;">
      <p class="chapter-label" style="margin-bottom:1rem;">A Mind Driven by Logic & Curiosity-- My Athiesm,</p>
      <div class="story-block">
        <span style="color:var(--gold);font-style:normal;">Atheism,</span>
         for me, is not a rejection — it is a way of <em>thinking</em>. I see the world through logic, questions, and evidence. This mindset shaped my approach to research, engineering, and life itself. I believe meaning is not given — it is created through work, learning, and the way we treat others.
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- BLOG SECTION -->
<div style="max-width:1100px;margin:0 auto;padding:4rem 4rem;">
  <p class="chapter-label" style="margin-bottom:1.5rem;">Writing</p>
  <h2 style="font-family:'Playfair Display',serif;font-size:2rem;color:var(--white);margin-bottom:0.5rem;">Chaos to <em style="color:var(--gold);font-style:italic;">Clarity</em></h2>
  <p style="color:var(--muted);font-size:0.9rem;margin-bottom:1.5rem;">My personal blog — where scattered thoughts find structure.</p>
  <a href="https://chaostoclaritydiary.blogspot.com/" target="_blank" class="blog-card">
    <div class="blog-icon">✍️</div>
    <div>
      <div class="blog-title">Chaos to Clarity Diary</div>
      <div class="blog-sub">Reflections on technology, life, philosophy, and everything in between.</div>
    </div>
    <div class="blog-arrow">→</div>
  </a>
</div>

<div class="divider"></div>

<!-- FOOTER -->
<footer>
  <div class="footer-copy">Built with purpose, not just code.</div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top = e.clientY + 'px';
  });

  // Scroll animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, { threshold: 0.15 });

  document.querySelectorAll('.timeline-item, .exp-card, .project-card, .story-block, .insight-card').forEach(el => {
    observer.observe(el);
  });

  // Staggered delays for grids
  document.querySelectorAll('.exp-card').forEach((el, i) => el.style.transitionDelay = `${i * 0.15}s`);
  document.querySelectorAll('.project-card').forEach((el, i) => el.style.transitionDelay = `${i * 0.15}s`);
  document.querySelectorAll('.insight-card').forEach((el, i) => el.style.transitionDelay = `${i * 0.1}s`);
  document.querySelectorAll('.timeline-item').forEach((el, i) => el.style.transitionDelay = `${i * 0.2}s`);
</script>
</body>
</html>
