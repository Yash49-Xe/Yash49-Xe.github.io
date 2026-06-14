<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Yash Raj — Data Scientist</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'Inter', sans-serif;
      background: #f8f7f4;
      color: #1a1a1a;
      line-height: 1.6;
      min-height: 100vh;
    }

    a { color: inherit; text-decoration: none; }

    .portfolio {
      max-width: 860px;
      margin: 0 auto;
      padding: 2.5rem 1.5rem 4rem;
    }

    .section-title {
      font-size: 11px;
      font-weight: 600;
      color: #999;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      margin: 2.5rem 0 1rem;
    }

    /* ── Hero ── */
    .hero {
      background: #ffffff;
      border: 0.5px solid #e0ddd5;
      border-radius: 16px;
      padding: 2.5rem 2rem;
      display: flex;
      gap: 2rem;
      align-items: center;
    }

    .avatar {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: #eeedfe;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 26px;
      font-weight: 600;
      color: #534ab7;
      flex-shrink: 0;
      box-shadow: 0 0 0 1px #c4c0f0;
    }

    .hero-text h1 { font-size: 24px; font-weight: 600; color: #1a1a1a; margin-bottom: 4px; }
    .hero-text .role { font-size: 13px; color: #534ab7; font-weight: 500; margin-bottom: 12px; }
    .hero-text .bio { font-size: 14px; color: #555; line-height: 1.65; max-width: 520px; margin-bottom: 16px; }

    .links { display: flex; gap: 8px; flex-wrap: wrap; }

    .link-badge {
      font-size: 12px;
      font-weight: 500;
      padding: 5px 14px;
      border: 0.5px solid #c4c0f0;
      border-radius: 20px;
      color: #534ab7;
      background: #eeedfe;
      transition: background 0.15s;
    }
    .link-badge:hover { background: #dddaf8; }
    .link-badge.email { background: #faece7; border-color: #f0b09a; color: #993c1d; }
    .link-badge.email:hover { background: #f5d0c0; }

    /* ── About ── */
    .about-card {
      background: #ffffff;
      border: 0.5px solid #e0ddd5;
      border-radius: 14px;
      padding: 1.5rem 1.75rem;
    }
    .about-card p { font-size: 14px; color: #555; line-height: 1.7; margin-bottom: 12px; }
    .about-card p:last-child { margin-bottom: 0; }

    /* ── Skills ── */
    .skills-section { display: flex; flex-direction: column; gap: 12px; }

    .skill-group {
      background: #ffffff;
      border: 0.5px solid #e0ddd5;
      border-radius: 12px;
      padding: 1rem 1.25rem;
    }

    .skill-group-label {
      font-size: 11px;
      font-weight: 600;
      color: #999;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      margin-bottom: 10px;
    }

    .skill-pills { display: flex; flex-wrap: wrap; gap: 7px; }

    .skill {
      font-size: 12px;
      font-weight: 500;
      padding: 4px 12px;
      border-radius: 20px;
    }
    .sk-ds    { background: #eeedfe; color: #534ab7; }
    .sk-be    { background: #e1f5ee; color: #0f6e56; }
    .sk-dsa   { background: #faeeda; color: #854f0b; }

    /* ── Projects ── */
    .proj-card {
      background: #ffffff;
      border: 0.5px solid #e0ddd5;
      border-radius: 14px;
      padding: 1.5rem 1.75rem;
      margin-bottom: 12px;
      transition: border-color 0.15s;
    }
    .proj-card:hover { border-color: #b0aee0; }

    .proj-header {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      gap: 1rem;
      margin-bottom: 10px;
    }

    .proj-card h3 { font-size: 16px; font-weight: 600; color: #1a1a1a; }

    .proj-link-btn {
      font-size: 12px;
      font-weight: 500;
      padding: 4px 12px;
      border: 0.5px solid #c4c0f0;
      border-radius: 20px;
      color: #534ab7;
      background: #eeedfe;
      white-space: nowrap;
      flex-shrink: 0;
      transition: background 0.15s;
    }
    .proj-link-btn:hover { background: #dddaf8; }

    .proj-card p { font-size: 13px; color: #666; line-height: 1.65; margin-bottom: 14px; }

    .proj-insight {
      background: #f8f7f4;
      border-left: 2px solid #c4c0f0;
      border-radius: 0 8px 8px 0;
      padding: 10px 14px;
      font-size: 12px;
      color: #666;
      line-height: 1.6;
      margin-bottom: 14px;
    }
    .proj-insight strong { color: #534ab7; font-weight: 600; }

    .proj-tags { display: flex; gap: 6px; flex-wrap: wrap; }
    .proj-tag {
      font-size: 11px;
      font-weight: 500;
      padding: 3px 10px;
      border-radius: 12px;
      background: #f1efe8;
      color: #5f5e5a;
    }

    /* ── Currently Learning ── */
    .learning-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }

    .learning-item {
      background: #ffffff;
      border: 0.5px solid #e0ddd5;
      border-radius: 12px;
      padding: 1rem 1.25rem;
    }

    .learning-item h4 { font-size: 14px; font-weight: 600; color: #1a1a1a; margin-bottom: 4px; }
    .learning-item p { font-size: 12px; color: #888; line-height: 1.5; }

    .learning-dot {
      display: inline-block;
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #1d9e75;
      margin-right: 8px;
      margin-bottom: 10px;
    }

    /* ── Contact ── */
    .contact-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }

    .contact-card {
      background: #ffffff;
      border: 0.5px solid #e0ddd5;
      border-radius: 12px;
      padding: 1.2rem;
      text-align: center;
      transition: border-color 0.15s;
    }
    .contact-card:hover { border-color: #b0aee0; }
    .contact-card .icon { font-size: 20px; margin-bottom: 6px; }
    .contact-card .label { font-size: 11px; font-weight: 600; color: #999; text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 4px; }
    .contact-card p { font-size: 12px; color: #534ab7; font-weight: 500; word-break: break-all; }

    /* ── Footer ── */
    footer {
      text-align: center;
      font-size: 12px;
      color: #bbb;
      margin-top: 3rem;
      padding-top: 1.5rem;
      border-top: 0.5px solid #e0ddd5;
    }

    /* ── Responsive ── */
    @media (max-width: 600px) {
      .hero { flex-direction: column; text-align: center; }
      .links { justify-content: center; }
      .learning-grid { grid-template-columns: 1fr; }
      .contact-row { grid-template-columns: 1fr; }
      .proj-header { flex-direction: column; }
    }
  </style>
</head>
<body>

<main class="portfolio">

  <!-- ── Hero ── -->
  <section class="hero">
    <div class="avatar"><img src="my_photo.png" alt="YR"></div>
    <div class="hero-text">
      <h1>Yash Raj</h1>
      <div class="role">B.Tech · Mathematics &amp; Scientific Computing</div>
      <p class="bio">
        Mathematics &amp; Scientific Computing student with a focus on data science and backend engineering.
        Building data pipelines, designing REST APIs, and applying statistical methods to extract insight
        from real-world datasets.
      </p>
      <div class="links">
        <a class="link-badge" href="https://www.linkedin.com/in/yash-raj-49xe" target="_blank" rel="noopener">LinkedIn</a>
        <a class="link-badge" href="https://leetcode.com/u/Yash_xe--49" target="_blank" rel="noopener">LeetCode</a>
        <a class="link-badge" href="https://github.com/Yash49-Xe" target="_blank" rel="noopener">GitHub</a>
        <a class="link-badge email" href="mailto:yashraj4009.xe@gmail.com">Email</a>
      </div>
    </div>
  </section>

  <!-- ── About ── -->
  <p class="section-title">About</p>
  <div class="about-card">
    <p>
      My mathematical background shapes how I approach model design, data quality, and performance trade-offs.
      I work on building data pipelines, designing REST APIs, and applying statistical methods to extract
      insight from real-world datasets.
    </p>
    <p>
      Currently deepening my work in predictive analytics and machine learning — moving from descriptive
      analysis toward building systems that forecast and classify.
    </p>
  </div>

  <!-- ── Skills ── -->
  <p class="section-title">Technical skills</p>
  <div class="skills-section">

    <div class="skill-group">
      <div class="skill-group-label">Data Science &amp; Analytics</div>
      <div class="skill-pills">
        <span class="skill sk-ds">Python</span>
        <span class="skill sk-ds">Pandas</span>
        <span class="skill sk-ds">NumPy</span>
        <span class="skill sk-ds">SciPy</span>
        <span class="skill sk-ds">Matplotlib</span>
        <span class="skill sk-ds">Seaborn</span>
        <span class="skill sk-ds">Jupyter</span>
      </div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">Backend &amp; APIs</div>
      <div class="skill-pills">
        <span class="skill sk-be">FastAPI</span>
        <span class="skill sk-be">SQLite</span>
        <span class="skill sk-be">PyArrow</span>
        <span class="skill sk-be">Java</span>
        <span class="skill sk-be">Uvicorn</span>
      </div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">Data Structures &amp; Algorithms</div>
      <div class="skill-pills">
        <span class="skill sk-dsa">C++</span>
        <span class="skill sk-dsa">LeetCode</span>
      </div>
    </div>

  </div>

  <!-- ── Projects ── -->
  <p class="section-title">Projects</p>

  <div class="proj-card">
    <div class="proj-header">
      <h3>Automated Wealth &amp; Portfolio Optimization API</h3>
      <a class="proj-link-btn" href="https://github.com/Yash49-Xe/portfolio-optimization-api" target="_blank" rel="noopener">View repo →</a>
    </div>
    <p>
      An asynchronous backend microservice that ingests real-time EOD price data and US Treasury rates from
      the Financial Modeling Prep API and computes the mathematically optimal capital allocation across a
      multi-asset portfolio. A 24-hour background sync worker decouples data ingestion from the API layer,
      keeping response times low regardless of external API latency.
    </p>
    <div class="proj-insight">
      <strong>Optimization approach:</strong> Maximizes the Sharpe Ratio — excess return over the live
      risk-free rate, divided by portfolio standard deviation — subject to full capital allocation and no
      short selling, using SLSQP constrained optimization on the Efficient Frontier.
    </div>
    <div class="proj-tags">
      <span class="proj-tag">Python</span>
      <span class="proj-tag">FastAPI</span>
      <span class="proj-tag">SciPy</span>
      <span class="proj-tag">Pandas</span>
      <span class="proj-tag">NumPy</span>
      <span class="proj-tag">SQLite</span>
      <span class="proj-tag">httpx</span>
    </div>
  </div>

  <div class="proj-card">
    <div class="proj-header">
      <h3>Dynamic Pricing Optimization Engine</h3>
      <a class="proj-link-btn" href="https://github.com/Yash49-Xe/dynamic-pricing-engine" target="_blank" rel="noopener">View repo →</a>
    </div>
    <p>
      A high-performance microservice that computes the mathematically optimal price for products to maximize
      profit. Uses constrained minimization to locate the exact peak of a profit function by balancing base
      costs, dynamic demand multipliers, and competitor pricing. PyArrow loads a compressed Parquet database
      directly into RAM on boot, enabling Pandas Boolean indexing across 100,000+ synthetic products in
      milliseconds.
    </p>
    <div class="proj-tags">
      <span class="proj-tag">Python</span>
      <span class="proj-tag">FastAPI</span>
      <span class="proj-tag">SciPy</span>
      <span class="proj-tag">Pandas</span>
      <span class="proj-tag">PyArrow</span>
      <span class="proj-tag">NumPy</span>
    </div>
  </div>

  <div class="proj-card">
    <div class="proj-header">
      <h3>E-Commerce Customer RFM Segmentation API</h3>
      <a class="proj-link-btn" href="https://github.com/Yash49-Xe/ecommerce-rfm-api" target="_blank" rel="noopener">View repo →</a>
    </div>
    <p>
      An end-to-end data science pipeline and REST API for customer segmentation. Processes 100,000+ real-world
      e-commerce transactions to compute Recency, Frequency, and Monetary scores and classify customers into
      actionable business segments in real time.
    </p>
    <div class="proj-insight">
      <strong>Key finding:</strong> Over 95% of customers had made only a single purchase — this required designing
      custom scoring functions outside standard quantile methods to meaningfully isolate high-value segments
      from the broader one-time buyer pool.
    </div>
    <div class="proj-tags">
      <span class="proj-tag">Python</span>
      <span class="proj-tag">FastAPI</span>
      <span class="proj-tag">Pandas</span>
      <span class="proj-tag">Seaborn</span>
      <span class="proj-tag">RFM Analysis</span>
    </div>
  </div>

  <!-- ── Currently Learning ── -->
  <p class="section-title">Currently learning</p>
  <div class="learning-grid">
    <div class="learning-item">
      <span class="learning-dot"></span>
      <h4>SQL</h4>
      <p>Query optimization and working with large-scale structured datasets.</p>
    </div>
    <div class="learning-item">
      <span class="learning-dot"></span>
      <h4>Scikit-learn</h4>
      <p>Supervised and unsupervised learning pipelines.</p>
    </div>
    <div class="learning-item">
      <span class="learning-dot"></span>
      <h4>Machine Learning Fundamentals</h4>
      <p>Regression, classification, and clustering with emphasis on the underlying mathematics.</p>
    </div>
    <div class="learning-item">
      <span class="learning-dot"></span>
      <h4>Pipeline Optimization</h4>
      <p>Applying scientific computing principles to improve data processing efficiency.</p>
    </div>
  </div>

  <!-- ── Contact ── -->
  <p class="section-title">Contact</p>
  <div class="contact-row">
    <a class="contact-card" href="mailto:yashraj4009.xe@gmail.com">
      <div class="icon">✉️</div>
      <div class="label">Email</div>
      <p>yashraj4009.xe@gmail.com</p>
    </a>
    <a class="contact-card" href="https://www.linkedin.com/in/yash-raj-49xe" target="_blank" rel="noopener">
      <div class="icon">🔗</div>
      <div class="label">LinkedIn</div>
      <p>linkedin.com/in/yash-raj-49xe</p>
    </a>
    <a class="contact-card" href="https://leetcode.com/u/Yash_xe--49" target="_blank" rel="noopener">
      <div class="icon">💻</div>
      <div class="label">LeetCode</div>
      <p>leetcode.com/u/Yash_xe--49</p>
    </a>
  </div>

  <footer>
    Built with GitHub Pages &nbsp;·&nbsp; 2025 &nbsp;·&nbsp; Yash Raj
  </footer>

</main>

</body>
</html>
