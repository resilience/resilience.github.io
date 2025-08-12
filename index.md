---
layout: null
---
<html>
<head>
  <style>
  :root {
    --bg-start: #0b0f17;
    --bg-end: #111827;
    --card-bg: rgba(255,255,255,0.06);
    --card-stroke: rgba(255,255,255,0.12);
    --text: #e5e7eb;
    --muted: #9ca3af;
    --brand: #60a5fa;   /* blue-400 */
    --brand-2: #a78bfa; /* violet-400 */
    --accent: #34d399;  /* teal/emerald */
  }

  @keyframes float {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-4px); }
    100% { transform: translateY(0px); }
  }

  html { box-sizing: border-box; }
  *, *:before, *:after { box-sizing: inherit; }

  body {
    margin: 0;
    font-family: "Inter", system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
    color: var(--text);
    background: radial-gradient(1200px 800px at 10% -10%, rgba(96,165,250,0.15), transparent),
                radial-gradient(1200px 800px at 90% 10%, rgba(167,139,250,0.12), transparent),
                linear-gradient(180deg, var(--bg-start), var(--bg-end));
    background-attachment: fixed;
  }

  .container {
    max-width: 980px;
    margin: 0 auto;
    padding: 48px 20px 80px;
  }

  .hero {
    position: relative;
    padding: 28px 24px;
    border-radius: 16px;
    background: linear-gradient(120deg, rgba(96,165,250,0.15), rgba(52,211,153,0.12) 60%, rgba(167,139,250,0.12));
    border: 1px solid var(--card-stroke);
    box-shadow: 0 10px 30px rgba(0,0,0,0.25);
    animation: float 9s ease-in-out infinite;
  }

  .intro-text {
    font-size: 18px;
    line-height: 1.8;
    margin-bottom: 28px;
  }

  h2 {
    font-family: "Space Grotesk", ui-sans-serif, system-ui;
    font-weight: 700;
    letter-spacing: 0.2px;
    font-size: 28px;
    margin: 26px 0 14px;
    background: linear-gradient(90deg, var(--brand), var(--brand-2));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }

  h3 {
    font-family: "Space Grotesk", ui-sans-serif, system-ui;
    font-weight: 600;
    margin: 18px 0 6px;
  }

  .card {
    background: backdrop-filter(blur(10px)) var(--card-bg);
    -webkit-backdrop-filter: blur(10px);
    border: 1px solid var(--card-stroke);
    border-radius: 14px;
    padding: 18px 18px 14px;
    margin: 14px 0 18px;
    box-shadow: 0 6px 18px rgba(0,0,0,0.2);
  }

  .articles-section {
    font-size: 18px;
    line-height: 1.9;
  }

  .articles-section a {
    color: var(--brand);
    text-decoration: none;
    border-bottom: 1px dashed rgba(96,165,250,0.4);
  }

  .articles-section a:hover {
    color: #93c5fd;
    border-bottom-color: rgba(96,165,250,0.7);
  }

  ul { padding-left: 20px; }
  li { margin: 6px 0; color: var(--text); }

  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.18), transparent);
    margin: 28px 0;
  }
  /* Theme overrides (orderedlist/minimal) */
  .wrapper { max-width: 1100px; padding: 0 24px; }
  .sidebar { display: none; }
  .page, .site { background: transparent !important; }

  /* Motion + reveal */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(8px);} to { opacity: 1; transform: translateY(0);} }
  .card { opacity: 0; animation: fadeUp .7s ease both; }
  .card:nth-of-type(2) { animation-delay: .06s; }
  .card:nth-of-type(3) { animation-delay: .12s; }
  .card:nth-of-type(4) { animation-delay: .18s; }
  .card:nth-of-type(5) { animation-delay: .24s; }

  /* Bullets */
  .articles-section ul { list-style: none; padding-left: 0; }
  .articles-section li { position: relative; padding-left: 22px; }
  .articles-section li::before { content: ""; position: absolute; left: 0; top: 9px; width: 8px; height: 8px; border-radius: 50%; background: radial-gradient(circle at 30% 30%, var(--brand), var(--brand-2)); box-shadow: 0 0 8px rgba(96,165,250,0.5); }

  /* Accessibility */
  @media (prefers-reduced-motion: reduce) {
    * { animation: none !important; transition: none !important; }
  }

  /* --- New UI: Header, Hero, Buttons, Badges, Footer --- */
  .skip-link {
    position: absolute; left: -999px; top: auto; width: 1px; height: 1px; overflow: hidden;
  }
  .skip-link:focus { left: 16px; top: 16px; width: auto; height: auto; padding: 8px 12px; background: #111827; color: #fff; border-radius: 8px; z-index: 1000; border: 1px solid var(--card-stroke); }

  header.site-header {
    position: sticky; top: 0; z-index: 50;
    backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px);
    background: linear-gradient(180deg, rgba(17,24,39,0.85), rgba(17,24,39,0.65));
    border-bottom: 1px solid var(--card-stroke);
  }
  .nav-wrap { max-width: 980px; margin: 0 auto; padding: 14px 20px; display: flex; align-items: center; justify-content: space-between; }
  .brand { font-family: "Space Grotesk", ui-sans-serif, system-ui; font-weight: 700; letter-spacing: 0.2px; font-size: 18px; background: linear-gradient(90deg, var(--brand), var(--brand-2)); -webkit-background-clip: text; background-clip: text; color: transparent; }
  nav a { color: var(--text); text-decoration: none; margin-left: 14px; font-size: 14px; opacity: 0.9; }
  nav a:hover { color: #fff; opacity: 1; }

  .hero { padding: 34px 28px; }
  .hero-grid { display: grid; grid-template-columns: 1.2fr 0.8fr; gap: 24px; align-items: center; }
  @media (max-width: 840px) { .hero-grid { grid-template-columns: 1fr; } }
  .eyebrow { color: var(--muted); font-weight: 600; text-transform: uppercase; font-size: 12px; letter-spacing: 1.1px; }
  h1 { font-family: "Space Grotesk", ui-sans-serif, system-ui; font-weight: 800; letter-spacing: 0.2px; font-size: 34px; margin: 10px 0 12px; }
  .lead { font-size: 18px; line-height: 1.8; }
  .hero-ctas { margin-top: 16px; display: flex; gap: 12px; flex-wrap: wrap; }
  .btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 14px; border-radius: 10px; border: 1px solid var(--card-stroke); color: var(--text); text-decoration: none; background: rgba(255,255,255,0.03); }
  .btn:hover { background: rgba(255,255,255,0.06); }
  .btn.primary { background: linear-gradient(90deg, rgba(96,165,250,0.35), rgba(167,139,250,0.35)); border-color: transparent; }
  .btn.primary:hover { background: linear-gradient(90deg, rgba(96,165,250,0.5), rgba(167,139,250,0.5)); }
  .badges { margin-top: 14px; display: flex; gap: 8px; flex-wrap: wrap; }
  .badge { font-size: 12px; padding: 6px 10px; border-radius: 999px; border: 1px solid var(--card-stroke); background: rgba(255,255,255,0.04); color: var(--muted); }
  .orb {
    width: 280px; height: 280px; border-radius: 50%;
    background: radial-gradient(circle at 30% 30%, rgba(167,139,250,0.9), rgba(96,165,250,0.6) 40%, rgba(52,211,153,0.6) 70%, transparent 72%),
                radial-gradient(circle at 70% 70%, rgba(96,165,250,0.6), rgba(17,24,39,0.6) 50%);
    filter: blur(0.2px) saturate(120%);
    box-shadow: inset 0 0 40px rgba(255,255,255,0.15), 0 20px 60px rgba(0,0,0,0.35);
    margin: 0 auto;
    animation: float 9s ease-in-out infinite;
  }

  .section-title { scroll-margin-top: 80px; }
  .contact-cta { text-align: center; }
  .contact-cta .btn { justify-content: center; min-width: 160px; }

  footer.site-footer { border-top: 1px solid var(--card-stroke); background: rgba(0,0,0,0.2); }
  footer .container { padding: 18px 20px; }
  </style>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Space+Grotesk:wght@500;700&display=swap" rel="stylesheet">
</head>
<body>
  <a href="#main" class="skip-link">Skip to content</a>
  <header class="site-header">
    <div class="nav-wrap">
      <div class="brand">Agentic Data Platforms</div>
      <nav>
        <a href="#focus">Focus</a>
        <a href="#projects">Projects</a>
        <a href="#core">Core</a>
        <a href="#teams">Teams</a>
        <a href="#writing">Writing</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>
  <main id="main">
  <div class="container">
  <section class="hero card">
    <div class="hero-grid">
      <div class="hero-left">
        <div class="eyebrow">Agents • DataOps • ML Platforms</div>
        <h1>Building pragmatic AI and data platforms</h1>
        <p class="lead">
          I build data teams and ship platforms that solve real problems: agentic systems, RAG pipelines, and production-ready ML. I focus on simple, reliable architectures that scale, with clear boundaries and strong observability.
        </p>
        <div class="hero-ctas">
          <a class="btn primary" href="mailto:dmaree2@gmail.com">Email me</a>
          <a class="btn" href="https://www.linkedin.com/in/donovan-maree-90452776/" target="_blank" rel="noopener">LinkedIn</a>
        </div>
        <div class="badges">
          <span class="badge">Agentic systems</span>
          <span class="badge">RAG</span>
          <span class="badge">Data platforms</span>
          <span class="badge">Observability</span>
        </div>
      </div>
      <div class="hero-right">
        <div class="orb" aria-hidden="true"></div>
      </div>
    </div>
  </section>

  <h2 id="focus" class="articles-section section-title">What I focus on</h2>
  <div class="articles-section card">
    <ul>
      <li>Agentic systems: planning, tool-use, evaluation, and guardrails</li>
      <li>Retrieval-Augmented Generation: ingestion, chunking, embeddings, grounding, and attribution</li>
      <li>Data platforms: secure multi-tenant foundations, CI/CD, IaC, and monitoring</li>
      <li>ML foundations: Rust/Python hybrid performance, lineage, MLflow + PostgreSQL observability</li>
    </ul>
  </div>

  <h2 id="projects" class="articles-section section-title">Project snapshots</h2>
  <div class="articles-section card">
    <h3>Alter SaaS — LLM Support Agent (Enterprise)</h3>
    <p>
      Multi-tenant support agent that blends Slack/Teams context, code, and docs with strict privacy. Thread-aware, source-attributed answers, configurable knowledge, and SOC2-ready posture.
    </p>
    <p><strong>Stack:</strong> LangChain/LangGraph, BAML, FastAPI, Next.js 14, LangSmith, DeepEval, LlamaIndex, Context7. Infra: PostgreSQL, Qdrant/Weaviate, Redis, MinIO/S3, Kubernetes, Terraform.</p>

    <h3>LaunchData — Data Stack Builder (IDP)</h3>
    <p>
      Internal Developer Platform to deploy client-specific modern data stacks in their cloud. Services include API Gateway, Config, Deployment, and Client management with secure defaults.
    </p>
    <p><strong>Stack:</strong> Docker Compose, PostgreSQL, Redis, JWT, Prometheus/Grafana, centralized logging, health checks, Trivy in CI/CD.</p>

    <h3>System 3 — Foundational ML Framework</h3>
    <p>
      Autonomous ML platform that pairs LLM agents with robust data stacks. It performs automatic feature discovery, self-optimizing hyperparameter/architecture search, continuous drift detection, and performance tuning. System 3 integrates cleanly with LaunchData (provisioning/infra) and Alter (knowledge/agents) to move from data to decisions with minimal human glue.
    </p>
    <p><strong>Stack:</strong> Rust/Python via PyO3, MLflow, PostgreSQL, OpenTelemetry, Docker, GPU-aware orchestration.</p>
  </div>

  <h2 id="core" class="articles-section section-title">Core analytics and data engineering</h2>
  <div class="articles-section card">
    <p><em>(Separate from platform projects)</em></p>
    <ul>
      <li><strong>Warehouses</strong>: Snowflake, PostgreSQL</li>
      <li><strong>Modeling</strong>: dbt (projects, tests, exposures, docs)</li>
      <li><strong>Ingestion</strong>: Airbyte (open-source ops + connectors)</li>
      <li><strong>Languages</strong>: Python, Rust, TypeScript</li>
      <li><strong>ML</strong>: MLflow (tracking/registry), feature lineage, evaluation with DeepEval</li>
      <li><strong>Observability</strong>: OpenTelemetry, Prometheus + Grafana, centralized structured logging</li>
      <li><strong>Vector/Storage</strong>: Qdrant/Weaviate, S3/MinIO</li>
      <li><strong>Services</strong>: FastAPI, JWT auth, Redis for caching</li>
      <li><strong>BI/Analytics</strong>: Metabase, Looker, Tableau, Power BI, Mode, Mixpanel</li>
      <li><strong>Data quality</strong>: Metaplane (ML-based data quality)</li>
      <li><strong>Platform ops</strong>: Docker, Kubernetes, Terraform, CI/CD (GitHub Actions, Trivy security scans)</li>
      <li><strong>Open-source data platforms</strong>: setup and infra for Airbyte, Metabase, dbt (configs, upgrades, monitoring)</li>
    </ul>
  </div>

  <h2 id="teams" class="articles-section section-title">How I build data teams</h2>
  <div class="articles-section card">
    <ul>
      <li>Start with strong foundations: environments, CI/CD, observability, and clear data contracts</li>
      <li>Ship value early with thin vertical slices; expand safely via templates and guardrails</li>
      <li>Make work inspectable: docs by default, ADRs, and automated runbooks</li>
      <li>Keep it boring where it matters; use advanced techniques only when they de-risk</li>
    </ul>
  </div>

  <h2 id="writing" class="articles-section section-title">Selected writing</h2>
  <div class="articles-section card">
    <ul>
      <li><a href="https://medium.com/@donovanmaree/8-strategies-for-chief-data-officers-to-leverage-chatgpt-4f5c664b10ac">8 Strategies for Chief Data Officers to leverage ChatGPT</a></li>
      <li><a href="https://medium.com/@donovanmaree/a-data-team-code-review-practitioners-guide-88abf3720cc1">A Data Team Code Review Practitioner’s Guide</a></li>
      <li><a href="https://medium.com/@donovanmaree/the-rise-of-the-full-stack-data-role-the-one-stop-solution-to-propel-your-data-stack-from-0-to-1-ae6c80591df2">The Rise of the Full Stack Data Role</a></li>
      <li><a href="https://medium.com/@donovanmaree/setting-up-virtual-environments-with-dbt-data-build-tool-on-mac-and-windows-3d62fec4aeb1">Setting up virtual environments with dbt</a></li>
    </ul>
  </div>

  <div id="contact" class="articles-section card contact-cta">
    <p>
      Want to talk platforms, agentic systems, or RAG?
    </p>
    <div class="hero-ctas" style="justify-content:center;">
      <a class="btn primary" href="mailto:dmaree2@gmail.com">Email me</a>
      <a class="btn" href="https://www.linkedin.com/in/donovan-maree-90452776/" target="_blank" rel="noopener">LinkedIn</a>
    </div>
  </div>

  </div>
  </main>
  <footer class="site-footer">
    <div class="container">
      <span>© <span id="year"></span> — Built with pragmatic AI + data platform patterns.</span>
    </div>
  </footer>
  <script>
    (function(){ var y = document.getElementById('year'); if (y) y.textContent = new Date().getFullYear(); })();
  </script>
</body>
</html>
