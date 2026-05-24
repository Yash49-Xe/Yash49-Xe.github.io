<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Yash Raj — Data Science Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Instrument+Sans:wght@400;500;600&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0d0f12;
      --bg2: #13161b;
      --bg3: #1a1e25;
      --border: rgba(255,255,255,0.07);
      --border2: rgba(255,255,255,0.12);
      --text: #e8eaf0;
      --muted: #7a8090;
      --accent: #5ee7c0;
      --accent2: #a78bfa;
      --accent3: #f9a66c;
      --serif: 'DM Serif Display', serif;
      --sans: 'Instrument Sans', sans-serif;
      --mono: 'DM Mono', monospace;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--sans);
      font-size: 16px;
      line-height: 1.7;
      overflow-x: hidden;
    }

    /* ─── NOISE TEXTURE OVERLAY ─── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
    }

    /* ─── NAV ─── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.2rem 4rem;
      background: rgba(13,15,18,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: var(--serif);
      font-size: 1.15rem;
      color: var(--text);
      text-decoration: none;
      letter-spacing: 0.01em;
    }

    .nav-links {
      display: flex;
      gap: 2.5rem;
      list-style: none;
    }

    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 0.85rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--text); }

    /* ─── HERO ─── */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 8rem 4rem 5rem;
      position: relative;
    }

    .hero-grid-bg {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(94,231,192,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(94,231,192,0.03) 1px, transparent 1px);
      background-size: 60px 60px;
      mask-image: radial-gradient(ellipse 70% 60% at 50% 50%, black 30%, transparent 100%);
    }

    .hero-glow {
      position: absolute;
      top: 20%;
      left: -10%;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(94,231,192,0.06) 0%, transparent 70%);
      pointer-events: none;
    }

    .hero-glow-2 {
      position: absolute;
      top: 40%;
      right: -5%;
      width: 400px;
      height: 400px;
      background: radial-gradient(circle, rgba(167,139,250,0.05) 0%, transparent 70%);
      pointer-events: none;
    }

    .hero-content {
      position: relative;
      max-width: 820px;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-size: 0.78rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--accent);
      border: 1px solid rgba(94,231,192,0.2);
      padding: 0.35rem 0.9rem;
      border-radius: 100px;
      margin-bottom: 2rem;
    }

    .hero-tag::before {
      content: '';
      width: 6px; height: 6px;
      border-radius: 50%;
      background: var(--accent);
      animation: pulse 2s ease-in-out infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.3; }
    }

    h1.display {
      font-family: var(--serif);
      font-size: clamp(3rem, 7vw, 5.5rem);
      line-height: 1.05;
      letter-spacing: -0.02em;
      color: var(--text);
      margin-bottom: 1.5rem;
    }

    h1.display em {
      font-style: italic;
      color: var(--accent);
    }

    .hero-sub {
      font-size: 1.1rem;
      color: var(--muted);
      max-width: 560px;
      line-height: 1.8;
      margin-bottom: 2.5rem;
    }

    .hero-cta {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.8rem 1.8rem;
      border-radius: 6px;
      font-family: var(--sans);
      font-size: 0.9rem;
      font-weight: 500;
      text-decoration: none;
      transition: all 0.2s;
      cursor: pointer;
      border: none;
    }

    .btn-primary {
      background: var(--accent);
      color: #0d1a14;
    }

    .btn-primary:hover { background: #7af0d2; transform: translateY(-1px); }

    .btn-ghost {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border2);
    }

    .btn-ghost:hover { border-color: rgba(255,255,255,0.25); background: var(--bg3); }

    /* ─── SECTIONS ─── */
    section {
      padding: 6rem 4rem;
      position: relative;
    }

    .section-label {
      font-size: 0.75rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 0.75rem;
      font-weight: 500;
    }

    h2.section-title {
      font-family: var(--serif);
      font-size: clamp(2rem, 4vw, 3rem);
      line-height: 1.15;
      color: var(--text);
      margin-bottom: 3rem;
    }

    /* ─── ABOUT ─── */
    #about {
      border-top: 1px solid var(--border);
      max-width: 1200px;
      margin: 0 auto;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }

    .about-text p {
      color: var(--muted);
      margin-bottom: 1.2rem;
      font-size: 1.05rem;
      line-height: 1.85;
    }

    .about-text p strong {
      color: var(--text);
      font-weight: 500;
    }

    .stat-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
    }

    .stat-cell {
      background: var(--bg2);
      padding: 2rem;
    }

    .stat-num {
      font-family: var(--mono);
      font-size: 2rem;
      color: var(--text);
      display: block;
      margin-bottom: 0.25rem;
    }

    .stat-num span { color: var(--accent); }

    .stat-label {
      font-size: 0.82rem;
      color: var(--muted);
      letter-spacing: 0.05em;
    }

    /* ─── SKILLS ─── */
    #skills {
      border-top: 1px solid var(--border);
      max-width: 1200px;
      margin: 0 auto;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }

    .skill-card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 1.75rem;
      transition: border-color 0.2s, transform 0.2s;
    }

    .skill-card:hover {
      border-color: var(--border2);
      transform: translateY(-3px);
    }

    .skill-icon {
      width: 40px; height: 40px;
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      margin-bottom: 1.2rem;
      font-size: 1.1rem;
      font-family: var(--mono);
      font-weight: 500;
    }

    .skill-icon.teal { background: rgba(94,231,192,0.1); color: var(--accent); }
    .skill-icon.purple { background: rgba(167,139,250,0.1); color: var(--accent2); }
    .skill-icon.amber { background: rgba(249,166,108,0.1); color: var(--accent3); }

    .skill-card h3 {
      font-size: 0.95rem;
      font-weight: 600;
      color: var(--text);
      margin-bottom: 1rem;
    }

    .tag-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .tag {
      font-size: 0.75rem;
      font-family: var(--mono);
      padding: 0.3rem 0.65rem;
      border-radius: 4px;
      background: var(--bg3);
      color: var(--muted);
      border: 1px solid var(--border);
    }

    /* ─── PROJECTS ─── */
    #projects {
      border-top: 1px solid var(--border);
      max-width: 1200px;
      margin: 0 auto;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1.5rem;
    }

    .project-card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 2rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      transition: border-color 0.2s, transform 0.2s;
      text-decoration: none;
      color: inherit;
    }

    .project-card:hover {
      border-color: rgba(94,231,192,0.25);
      transform: translateY(-3px);
    }

    .project-num {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--muted);
      letter-spacing: 0.1em;
    }

    .project-card h3 {
      font-family: var(--serif);
      font-size: 1.35rem;
      color: var(--text);
      line-height: 1.3;
    }

    .project-card p {
      font-size: 0.92rem;
      color: var(--muted);
      line-height: 1.75;
      flex: 1;
    }

    .project-insight {
      background: rgba(94,231,192,0.05);
      border-left: 2px solid var(--accent);
      padding: 0.75rem 1rem;
      border-radius: 0 6px 6px 0;
      font-size: 0.85rem;
      color: rgba(94,231,192,0.8);
      font-style: italic;
    }

    .project-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: auto;
      padding-top: 1rem;
      border-top: 1px solid var(--border);
    }

    .project-link {
      font-size: 0.82rem;
      color: var(--accent);
      display: flex;
      align-items: center;
      gap: 0.35rem;
      font-weight: 500;
    }

    .project-link svg { width: 14px; height: 14px; }

    /* ─── LEARNING ─── */
    #learning {
      border-top: 1px solid var(--border);
      max-width: 1200px;
      margin: 0 auto;
    }

    .learning-list {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
    }

    .learning-item {
      display: flex;
      gap: 1rem;
      align-items: flex-start;
      padding: 1.25rem 1.5rem;
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 10px;
    }

    .learning-dot {
      width: 8px; height: 8px;
      border-radius: 50%;
      background: var(--accent2);
      flex-shrink: 0;
      margin-top: 0.55rem;
    }

    .learning-item strong {
      display: block;
      color: var(--text);
      font-size: 0.95rem;
      margin-bottom: 0.25rem;
    }

    .learning-item p {
      font-size: 0.85rem;
      color: var(--muted);
      line-height: 1.6;
    }

    /* ─── CONTACT ─── */
    #contact {
      border-top: 1px solid var(--border);
      max-width: 1200px;
      margin: 0 auto;
      text-align: center;
    }

    #contact h2.section-title { margin-bottom: 1rem; }

    .contact-sub {
      color: var(--muted);
      font-size: 1.05rem;
      max-width: 480px;
      margin: 0 auto 2.5rem;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
      margin-bottom: 3rem;
    }

    /* ─── FOOTER ─── */
    footer {
      border-top: 1px solid var(--border);
      padding: 2rem 4rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      max-width: 1200px;
      margin: 0 auto;
    }

    footer p {
      font-size: 0.82rem;
      color: var(--muted);
    }

    footer a { color: var(--muted); text-decoration: none; }
    footer a:hover { color: var(--text); }

    /* ─── GITHUB STATS ─── */
    .stats-row {
      display: flex;
      gap: 1rem;
      justify-content: center;
      flex-wrap: wrap;
      margin-top: 2rem;
    }

    .stats-row img {
      border-radius: 8px;
      border: 1px solid var(--border);
      height: 140px;
    }

    /* ─── DIVIDER ─── */
    .divider {
      width: 40px;
      height: 2px;
      background: var(--accent);
      margin: 1.5rem 0 2.5rem;
    }

    /* ─── MOBILE ─── */
    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      #hero, section { padding: 5rem 1.5rem 3rem; }
      .about-grid, .skills-grid, .projects-grid, .learning-list {
        grid-template-columns: 1fr;
      }
      footer { flex-direction: column; gap: 0.5rem; padding: 2rem 1.5rem; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a href="#hero" class="nav-logo">Yash Raj</a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <div class="hero-grid-bg"></div>
    <div class="hero-glow"></div>
    <div class="hero-glow-2"></div>

    <div class="hero-content">
      <div class="hero-tag">Available for opportunities</div>

      <h1 class="display">
        Turning <em>mathematics</em><br>
        into insight.
      </h1>

      <p class="hero-sub">
        B.Tech in Mathematics &amp; Scientific Computing. I build data pipelines, REST APIs, and statistical models that extract signal from real-world data.
      </p>

      <div class="hero-cta">
        <a href="#projects" class="btn btn-primary">View Projects</a>
        <a href="mailto:yashraj4009.xe@gmail.com" class="btn btn-ghost">Get in Touch</a>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="section-label">Background</div>
    <div class="about-grid">
      <div class="about-text">
        <h2 class="section-title">The person<br>behind the data.</h2>
        <p>
          I'm a <strong>Mathematics &amp; Scientific Computing</strong> student with a deep interest in data science and backend engineering. My mathematical foundation isn't just academic — it shapes how I approach model design, data quality, and performance trade-offs in production systems.
        </p>
        <p>
          I work on building <strong>end-to-end data pipelines</strong>, designing REST APIs, and applying statistical methods to extract actionable insight from complex datasets. I'm currently moving from descriptive analysis toward building systems that <strong>forecast and classify</strong>.
        </p>
        <p>
          When I'm not coding, I'm grinding competitive programming problems to sharpen my algorithmic thinking.
        </p>
      </div>

      <div class="stat-grid">
        <div class="stat-cell">
          <span class="stat-num">100<span>k+</span></span>
          <span class="stat-label">Transactions processed in RFM project</span>
        </div>
        <div class="stat-cell">
          <span class="stat-num">2</span>
          <span class="stat-label">End-to-end project pipelines built</span>
        </div>
        <div class="stat-cell">
          <span class="stat-num">4</span>
          <span class="stat-label">Core languages &amp; frameworks</span>
        </div>
        <div class="stat-cell">
          <span class="stat-num">∞</span>
          <span class="stat-label">Mathematical curiosity</span>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills">
    <div class="section-label">Technical Stack</div>
    <h2 class="section-title">Skills &amp; Tools</h2>

    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-icon teal">∑</div>
        <h3>Data Science &amp; Analytics</h3>
        <div class="tag-list">
          <span class="tag">Python</span>
          <span class="tag">Pandas</span>
          <span class="tag">NumPy</span>
          <span class="tag">Matplotlib</span>
          <span class="tag">Seaborn</span>
          <span class="tag">Jupyter</span>
          <span class="tag">RFM Analysis</span>
          <span class="tag">Statistical Modeling</span>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-icon purple">⚡</div>
        <h3>Backend &amp; APIs</h3>
        <div class="tag-list">
          <span class="tag">FastAPI</span>
          <span class="tag">Python</span>
          <span class="tag">Java</span>
          <span class="tag">Uvicorn</span>
          <span class="tag">REST APIs</span>
          <span class="tag">Pipeline Design</span>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-icon amber">λ</div>
        <h3>CS Fundamentals</h3>
        <div class="tag-list">
          <span class="tag">C++</span>
          <span class="tag">Data Structures</span>
          <span class="tag">Algorithms</span>
          <span class="tag">Competitive Programming</span>
          <span class="tag">LeetCode</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="section-label">Work</div>
    <h2 class="section-title">Selected Projects</h2>

    <div class="projects-grid">

      <a href="https://github.com/Yash49-Xe" class="project-card">
        <span class="project-num">01 / Data Science</span>
        <h3>E-Commerce Customer RFM Segmentation API</h3>
        <p>
          An end-to-end data science pipeline and REST API for customer segmentation. Processes real-world e-commerce transactions to compute Recency, Frequency, and Monetary scores and classify customers into actionable business segments in real time.
        </p>
        <div class="project-insight">
          Key finding: 95%+ of customers had made only a single purchase — requiring custom scoring functions outside standard quantile methods to isolate high-value segments.
        </div>
        <div class="project-footer">
          <div class="tag-list">
            <span class="tag">Python</span>
            <span class="tag">FastAPI</span>
            <span class="tag">Pandas</span>
            <span class="tag">Seaborn</span>
          </div>
          <span class="project-link">
            View
            <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
              <path d="M3 8h10M9 4l4 4-4 4"/>
            </svg>
          </span>
        </div>
      </a>

      <a href="https://github.com/Yash49-Xe" class="project-card">
        <span class="project-num">02 / Full-Stack AI</span>
        <h3>Sustainable Shopping Assistant</h3>
        <p>
          A full-stack mobile application delivering AI-powered sustainability insights at the point of purchase. Integrates a Flutter frontend with a Python/FastAPI backend and Groq AI to provide real-time, data-driven recommendations for eco-conscious decision-making.
        </p>
        <div class="project-insight">
          AI at purchase-time: bridging behavioral data with sustainability metrics via real-time LLM inference.
        </div>
        <div class="project-footer">
          <div class="tag-list">
            <span class="tag">Flutter</span>
            <span class="tag">FastAPI</span>
            <span class="tag">Groq AI</span>
            <span class="tag">Dart</span>
          </div>
          <span class="project-link">
            View
            <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
              <path d="M3 8h10M9 4l4 4-4 4"/>
            </svg>
          </span>
        </div>
      </a>

    </div>
  </section>

  <!-- CURRENTLY LEARNING -->
  <section id="learning">
    <div class="section-label">Growth</div>
    <h2 class="section-title">Currently Learning</h2>

    <div class="learning-list">
      <div class="learning-item">
        <div class="learning-dot"></div>
        <div>
          <strong>SQL &amp; Query Optimization</strong>
          <p>Working with large-scale structured datasets, query planning, and indexing strategies for analytical workloads.</p>
        </div>
      </div>
      <div class="learning-item">
        <div class="learning-dot"></div>
        <div>
          <strong>Scikit-Learn Pipelines</strong>
          <p>Supervised and unsupervised learning — building reproducible, production-ready ML workflows.</p>
        </div>
      </div>
      <div class="learning-item">
        <div class="learning-dot"></div>
        <div>
          <strong>Machine Learning Fundamentals</strong>
          <p>Regression, classification, and clustering with emphasis on the underlying mathematics, not just the APIs.</p>
        </div>
      </div>
      <div class="learning-item">
        <div class="learning-dot"></div>
        <div>
          <strong>Pipeline Optimization</strong>
          <p>Applying scientific computing principles to improve data processing efficiency and reduce latency at scale.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="section-label">Let's connect</div>
    <h2 class="section-title">Get in Touch</h2>
    <p class="contact-sub">Open to data science internships, collaborations, and interesting problems. Reach out anytime.</p>

    <div class="contact-links">
      <a href="mailto:yashraj4009.xe@gmail.com" class="btn btn-primary">
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
          <rect x="1" y="3" width="14" height="10" rx="1.5"/><path d="M1 4.5l7 5 7-5"/>
        </svg>
        yashraj4009.xe@gmail.com
      </a>
      <a href="https://www.linkedin.com/in/yash-raj-49xe" class="btn btn-ghost" target="_blank" rel="noopener">
        LinkedIn
      </a>
      <a href="https://leetcode.com/u/Yash_xe--49" class="btn btn-ghost" target="_blank" rel="noopener">
        LeetCode
      </a>
      <a href="https://github.com/Yash49-Xe" class="btn btn-ghost" target="_blank" rel="noopener">
        GitHub
      </a>
    </div>

    <div class="stats-row">
      <img
        src="https://github-readme-stats.vercel.app/api?username=Yash49-Xe&show_icons=true&theme=transparent&hide_border=true&count_private=true&text_color=7a8090&title_color=5ee7c0&icon_color=5ee7c0"
        alt="Yash's GitHub stats"
      />
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs/?username=Yash49-Xe&layout=compact&theme=transparent&hide_border=true&text_color=7a8090&title_color=5ee7c0"
        alt="Top languages"
      />
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>© 2025 Yash Raj — Mathematics &amp; Scientific Computing</p>
    <p>Built with HTML &amp; CSS · Hosted on <a href="https://pages.github.com" target="_blank" rel="noopener">GitHub Pages</a></p>
  </footer>

</body>
</html>
