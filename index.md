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

  /* Bullets (scoped) */
  .bulleted ul { list-style: none; padding-left: 0; }
  .bulleted li { position: relative; padding-left: 22px; }
  .bulleted li::before { content: ""; position: absolute; left: 0; top: 9px; width: 8px; height: 8px; border-radius: 50%; background: radial-gradient(circle at 30% 30%, var(--brand), var(--brand-2)); box-shadow: 0 0 8px rgba(96,165,250,0.5); }

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
  /* Agent Mesh hero */
  .mesh { width: 100%; max-width: 560px; margin: 0 auto; display: block; }
  .mesh text { font-size: 10px; fill: #cbd5e1; letter-spacing: .2px; }
  .mesh .node { filter: drop-shadow(0 2px 6px rgba(0,0,0,.35)); }
  .mesh .node circle { fill: rgba(17,24,39,0.85); stroke: rgba(255,255,255,0.15); stroke-width: 1; }
  .mesh .node.active circle { stroke: rgba(96,165,250,0.9); }
  .mesh .edge { stroke: rgba(255,255,255,0.18); stroke-width: 1; }
  .mesh .pulse { stroke: url(#edgeGrad); stroke-width: 2; stroke-linecap: round; }

  .section-title { scroll-margin-top: 80px; }
  .contact-cta { text-align: center; }
  .contact-cta .btn { justify-content: center; min-width: 160px; }

  footer.site-footer { border-top: 1px solid var(--card-stroke); background: rgba(0,0,0,0.2); }
  footer .container { padding: 18px 20px; }

  /* Subtle 2025-style micro-interactions */
  @keyframes shimmer {
    0% { background-position: -200% 0; }
    100% { background-position: 200% 0; }
  }
  .shimmer-text {
    background: linear-gradient(100deg, rgba(255,255,255,0.15), rgba(255,255,255,0.75), rgba(255,255,255,0.15));
    -webkit-background-clip: text; background-clip: text; color: transparent;
    background-size: 200% 100%;
    animation: shimmer 6s ease-in-out infinite;
  }
  .hero { position: relative; overflow: hidden; }

  /* Project styling upgrades */
  .projects .project { position: relative; padding: 14px 16px 10px 18px; border: 1px solid var(--card-stroke); border-radius: 12px; margin: 14px 0; background: rgba(255,255,255,0.03); }
  .projects .project::before { content: ""; position: absolute; left: 8px; top: 12px; width: 6px; height: 6px; border-radius: 50%; background: radial-gradient(circle at 30% 30%, var(--brand), var(--brand-2)); box-shadow: 0 0 10px rgba(96,165,250,0.55); }
  .projects .project:hover { box-shadow: 0 10px 24px rgba(0,0,0,0.28); transform: translateY(-1px); transition: box-shadow .25s ease, transform .25s ease; }
  .projects h3 { display: inline-block; padding-right: 8px; background-image: linear-gradient(90deg, rgba(96,165,250,0.35), rgba(167,139,250,0.35)); background-repeat: no-repeat; background-size: 100% 8px; background-position: 0 100%; border-radius: 4px; }
  .projects p strong { color: #cbd5e1; }
  canvas.deploy-wave { width: 100%; height: 90px; display: block; margin-top: 8px; border-radius: 8px; border: 1px solid var(--card-stroke); background: rgba(255,255,255,0.02); }

  /* PH capsule */
  #ph .ph-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(180px,1fr)); gap: 12px; }
  #ph .ph-tile { border: 1px solid var(--card-stroke); border-radius: 12px; padding: 10px; background: rgba(255,255,255,0.03); display: flex; flex-direction: column; gap: 6px; min-height: 140px; }
  #ph .ph-title { font-weight: 600; font-size: 14px; color: #e5e7eb; }
  #ph .ph-meta { color: var(--muted); font-size: 12px; display: flex; justify-content: space-between; }
  #ph .ph-ava { width: 28px; height: 28px; border-radius: 8px; background: rgba(255,255,255,0.06); border: 1px solid var(--card-stroke); }
  #ph .ph-badges { display: flex; gap: 6px; flex-wrap: wrap; }
  #ph .ph-badge { font-size: 11px; padding: 4px 8px; border-radius: 999px; border: 1px solid var(--card-stroke); background: rgba(255,255,255,0.04); color: var(--muted); }
  #ph .ph-empty { color: var(--muted); font-size: 14px; }

  @media (prefers-reduced-motion: reduce) {
    .shimmer-text { animation: none !important; transition: none !important; }
  }
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
        <svg id="agent-mesh" class="mesh" viewBox="0 0 560 360" aria-hidden="true" role="img">
          <defs>
            <linearGradient id="edgeGrad" x1="0%" y1="0%" x2="100%" y2="0%">
              <stop offset="0%" stop-color="rgba(96,165,250,0.0)" />
              <stop offset="50%" stop-color="rgba(167,139,250,0.9)" />
              <stop offset="100%" stop-color="rgba(52,211,153,0.0)" />
            </linearGradient>
          </defs>
          <!-- Edges -->
          <g id="edges" class="edges" stroke-linecap="round">
            <path id="p1" class="edge" d="M120,180 L220,120"/>
            <path id="p2" class="edge" d="M220,120 L320,120"/>
            <path id="p3" class="edge" d="M320,120 L420,180"/>
            <path id="p4" class="edge" d="M220,120 L220,60"/>
            <path id="p5" class="edge" d="M320,120 L320,60"/>
            <path id="p6" class="edge" d="M220,120 L260,200"/>
            <path id="p7" class="edge" d="M320,120 L360,200"/>
            <path id="p8" class="edge" d="M120,180 L180,260"/>
            <path id="p9" class="edge" d="M420,180 L380,260"/>
          </g>
          <!-- Nodes -->
          <g class="nodes">
            <g class="node" transform="translate(110,170)">
              <circle r="16"/><text x="24" y="4">Planner</text>
            </g>
            <g class="node" transform="translate(210,110)">
              <circle r="16"/><text x="24" y="4">Retriever</text>
            </g>
            <g class="node" transform="translate(320,110)">
              <circle r="16"/><text x="24" y="4">Grounder</text>
            </g>
            <g class="node" transform="translate(420,170)">
              <circle r="16"/><text x="24" y="4">Answer</text>
            </g>
            <g class="node" transform="translate(220,60)">
              <circle r="12"/><text x="20" y="4">Vector DB</text>
            </g>
            <g class="node" transform="translate(320,60)">
              <circle r="12"/><text x="20" y="4">Docs/Code</text>
            </g>
            <g class="node" transform="translate(260,200)">
              <circle r="12"/><text x="20" y="4">Tools</text>
            </g>
            <g class="node" transform="translate(360,200)">
              <circle r="12"/><text x="20" y="4">Policy</text>
            </g>
            <g class="node" transform="translate(180,260)">
              <circle r="12"/><text x="20" y="4">Memory</text>
            </g>
            <g class="node" transform="translate(380,260)">
              <circle r="12"/><text x="20" y="4">Slack/API</text>
            </g>
          </g>
        </svg>
      </div>
    </div>
    
  </section>

  <h2 id="focus" class="articles-section section-title">What I focus on</h2>
  <div class="articles-section card bulleted">
    <ul>
      <li>Agentic systems: planning, tool-use, evaluation, and guardrails</li>
      <li>Retrieval-Augmented Generation: ingestion, chunking, embeddings, grounding, and attribution</li>
      <li>Data platforms: secure multi-tenant foundations, CI/CD, IaC, and monitoring</li>
      <li>ML foundations: Rust/Python hybrid performance, lineage, MLflow + PostgreSQL observability</li>
    </ul>
  </div>

  <h2 id="projects" class="articles-section section-title">Project snapshots</h2>
  <div class="articles-section card projects">
    <div class="project">
      <h3>Alter SaaS — LLM Support Agent (Enterprise)</h3>
      <p>
        Multi-tenant support agent that blends Slack/Teams context, code, and docs with strict privacy. Thread-aware, source-attributed answers, configurable knowledge, and SOC2-ready posture.
      </p>
      <p><strong>Stack:</strong> LangChain/LangGraph, BAML, FastAPI, Next.js 14, LangSmith, DeepEval, LlamaIndex, Context7. Infra: PostgreSQL, Qdrant/Weaviate, Redis, MinIO/S3, Kubernetes, Terraform.</p>
      <canvas class="deploy-wave" width="520" height="90" aria-hidden="true"></canvas>
    </div>

    <div class="project">
      <h3>LaunchData — Data Stack Builder (IDP)</h3>
      <p>
        Internal Developer Platform to deploy client-specific modern data stacks in their cloud. Services include API Gateway, Config, Deployment, and Client management with secure defaults.
      </p>
      <p><strong>Stack:</strong> Docker Compose, PostgreSQL, Redis, JWT, Prometheus/Grafana, centralized logging, health checks, Trivy in CI/CD.</p>
      <canvas class="deploy-wave" width="520" height="90" aria-hidden="true"></canvas>
    </div>

    <div class="project">
      <h3>System 3 — Foundational ML Framework</h3>
      <p>
        Autonomous ML platform that pairs LLM agents with robust data stacks. It performs automatic feature discovery, self-optimizing hyperparameter/architecture search, continuous drift detection, and performance tuning. System 3 integrates cleanly with LaunchData (provisioning/infra) and Alter (knowledge/agents) to move from data to decisions with minimal human glue.
      </p>
      <p><strong>Stack:</strong> Rust/Python via PyO3, MLflow, PostgreSQL, OpenTelemetry, Docker, GPU-aware orchestration.</p>
      <canvas class="deploy-wave" width="520" height="90" aria-hidden="true"></canvas>
    </div>
  </div>

  <h2 id="core" class="articles-section section-title">Core analytics and data engineering</h2>
  <div class="articles-section card bulleted">
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
  <div class="articles-section card bulleted">
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

  <h2 id="producthunt" class="articles-section section-title">Product Hunt contributions</h2>
  <div id="ph" class="articles-section card">
    <div class="ph-grid" data-loading="true"></div>
    <div class="ph-empty" aria-live="polite" style="display:none;">No contributions loaded.</div>
  </div>

  <div id="contact" class="articles-section card contact-cta">
    <p>
      Want to talk platforms, agentic systems, or RAG?
    </p>
    <div class="hero-ctas" style="justify-content:center;">
      <a class="btn primary" href="mailto:dmaree2@gmail.com">Email me</a>
      <a class="btn" href="https://www.linkedin.com/in/donovan-maree-90452776/" target="_blank" rel="noopener">LinkedIn</a>
      <a class="btn" href="https://www.producthunt.com/@donovandata" target="_blank" rel="noopener">Product Hunt</a>
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
    (function(){
      var y = document.getElementById('year'); if (y) y.textContent = new Date().getFullYear();
      var reduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

      // Agent Mesh pulse runs
      (function mesh(){
        var svg = document.getElementById('agent-mesh'); if (!svg || reduce) return;
        var steps = [ ['p1','p2','p3'], ['p1','p4','p2','p5','p3'], ['p1','p6','p2','p7','p3'] ];
        var idx = 0;
        function run(){
          var seq = steps[idx % steps.length]; idx++;
          var i = 0, circle = document.createElementNS('http://www.w3.org/2000/svg','circle');
          circle.setAttribute('r','3'); circle.setAttribute('fill','#a78bfa'); svg.appendChild(circle);
          function moveNext(){
            if (i >= seq.length) { svg.removeChild(circle); setTimeout(run, 6000); return; }
            var path = svg.querySelector('#'+seq[i++]); if (!path) { moveNext(); return; }
            var len = path.getTotalLength(); var t=0;
            function step(){ t += 2; if (t>len){ moveNext(); return; }
              var p = path.getPointAtLength(t); circle.setAttribute('cx', p.x); circle.setAttribute('cy', p.y);
              requestAnimationFrame(step);
            }
            step();
          }
          moveNext();
        }
        setTimeout(run, 1200);
      })();

      // Deploy Wave per project
      (function deploy(){
        var canvases = document.querySelectorAll('canvas.deploy-wave'); if (!canvases.length) return;
        var io = new IntersectionObserver(function(entries){
          entries.forEach(function(en){ if (en.isIntersecting) { animate(en.target); io.unobserve(en.target); } });
        }, { threshold: 0.4 });
        canvases.forEach(function(cv){ io.observe(cv); });
        function animate(cv){
          var dpr = Math.max(1, window.devicePixelRatio||1); var w = cv.clientWidth, h = 90; cv.width = w*dpr; cv.height = h*dpr; var ctx = cv.getContext('2d'); ctx.scale(dpr,dpr);
          var cols = Math.floor(w/18), rows = 4, cx = Math.floor(cols/2), cy = Math.floor(rows/2);
          var built = {}, order=[]; for (var y=0;y<rows;y++){ for (var x=0;x<cols;x++){ var dist = Math.abs(x-cx)+Math.abs(y-cy); order.push({x:x,y:y,d:dist}); }}
          order.sort(function(a,b){ return a.d-b.d; });
          var t=0; function build(){
            ctx.clearRect(0,0,w,h);
            // draw grid
            for (var y=0;y<rows;y++){
              for (var x=0;x<cols;x++){
                var key = x+','+y; var on = built[key];
                ctx.fillStyle = on? 'rgba(167,139,250,0.35)':'rgba(255,255,255,0.05)';
                ctx.fillRect(6+x*12, 10+y*16, 10, 10);
              }
            }
            if (t < order.length){ var n = order[t++]; built[n.x+','+n.y]=true; requestAnimationFrame(build); }
            else { telemetry(); }
          }
          function telemetry(){
            var k=0; function loop(){
              ctx.clearRect(0,0,w,h);
              // grid background
              for (var y=0;y<rows;y++){
                for (var x=0;x<cols;x++){
                  ctx.fillStyle = 'rgba(255,255,255,0.06)'; ctx.fillRect(6+x*12, 10+y*16, 10, 10);
                }
              }
              // OTel lines
              for (var i=0;i<3;i++){
                var y = 80 - i*14; ctx.beginPath();
                for (var x=0;x<w;x++){
                  var amp = 2 + i; var v = Math.sin((x+k*2)/28 + i) * amp;
                  var yy = y + v; if (x===0) ctx.moveTo(x,yy); else ctx.lineTo(x,yy);
                }
                ctx.strokeStyle = 'rgba(96,165,250,'+(0.25 - i*0.06)+')'; ctx.lineWidth = 1; ctx.stroke();
              }
              k++; if (!reduce) requestAnimationFrame(loop);
            }
            loop();
          }
          build();
        }
      })();

      // Product Hunt capsule
      (function ph(){
        var wrap = document.querySelector('#ph .ph-grid'); if (!wrap) return;
        fetch('assets/data/ph.json', { cache: 'no-store' }).then(function(r){ return r.json(); }).then(function(items){
          wrap.innerHTML = '';
          if (!items || !items.length){ document.querySelector('#ph .ph-empty').style.display='block'; return; }
          items.slice(0,8).forEach(function(it){
            var a = document.createElement('a'); a.href = it.url; a.target = '_blank'; a.rel='noopener'; a.className='ph-tile';
            var img = document.createElement('div'); img.className='ph-ava'; img.style.backgroundImage = it.image?('url('+it.image+')'):''; img.style.backgroundSize='cover'; img.style.backgroundPosition='center';
            var title = document.createElement('div'); title.className='ph-title'; title.textContent = it.title;
            var meta = document.createElement('div'); meta.className='ph-meta'; meta.innerHTML = '<span>'+ (it.role||'') +'</span><span>▲ '+(it.upvotes||0)+'</span>';
            var badges = document.createElement('div'); badges.className='ph-badges';
            (it.badges||[]).slice(0,2).forEach(function(b){ var s=document.createElement('span'); s.className='ph-badge'; s.textContent=b; badges.appendChild(s); });
            a.appendChild(img); a.appendChild(title); a.appendChild(meta); a.appendChild(badges); wrap.appendChild(a);
          });
        }).catch(function(){ document.querySelector('#ph .ph-empty').style.display='block'; });
      })();
    })();
  </script>
</body>
</html>
