
<html>
<head>
<style>
body {
  font-family: Arial, sans-serif;
}
  
.intro-text {
  font-family: 'Arial', sans-serif;
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 20px;
}

.articles-section {
  font-family: 'Roboto', sans-serif;
  font-size: 18px;
  line-height: 2;
}

.articles-section a {
  color: #1a73e8;
  text-decoration: none;
}

.articles-section a:hover {
  text-decoration: underline;
}

</style>
<link href="https://fonts.googleapis.com/css?family=Roboto&display=swap" rel="stylesheet">
</head>
<body>
  <section class="intro-text">
    <h2>Building pragmatic AI and data platforms</h2>
    <p>
      I build data teams and ship platforms that solve real problems: agentic systems, RAG pipelines, and production-ready ML. I focus on simple, reliable architectures that scale, with clear boundaries and strong observability.
    </p>
  </section>

  <h2 class="articles-section">What I focus on</h2>
  <div class="articles-section">
    <ul>
      <li>Agentic systems: planning, tool-use, evaluation, and guardrails</li>
      <li>Retrieval-Augmented Generation: ingestion, chunking, embeddings, grounding, and attribution</li>
      <li>Data platforms: secure multi-tenant foundations, CI/CD, IaC, and monitoring</li>
      <li>ML foundations: Rust/Python hybrid performance, lineage, MLflow + PostgreSQL observability</li>
    </ul>
  </div>

  <h2 class="articles-section">Project snapshots</h2>
  <div class="articles-section">
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

  <h2 class="articles-section">Core analytics and data engineering</h2>
  <div class="articles-section">
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

  <h2 class="articles-section">How I build data teams</h2>
  <div class="articles-section">
    <ul>
      <li>Start with strong foundations: environments, CI/CD, observability, and clear data contracts</li>
      <li>Ship value early with thin vertical slices; expand safely via templates and guardrails</li>
      <li>Make work inspectable: docs by default, ADRs, and automated runbooks</li>
      <li>Keep it boring where it matters; use advanced techniques only when they de-risk</li>
    </ul>
  </div>

  <h2 class="articles-section">Selected writing</h2>
  <div class="articles-section">
    <ul>
      <li><a href="https://medium.com/@donovanmaree/8-strategies-for-chief-data-officers-to-leverage-chatgpt-4f5c664b10ac">8 Strategies for Chief Data Officers to leverage ChatGPT</a></li>
      <li><a href="https://medium.com/@donovanmaree/a-data-team-code-review-practitioners-guide-88abf3720cc1">A Data Team Code Review Practitioner’s Guide</a></li>
      <li><a href="https://medium.com/@donovanmaree/the-rise-of-the-full-stack-data-role-the-one-stop-solution-to-propel-your-data-stack-from-0-to-1-ae6c80591df2">The Rise of the Full Stack Data Role</a></li>
      <li><a href="https://medium.com/@donovanmaree/setting-up-virtual-environments-with-dbt-data-build-tool-on-mac-and-windows-3d62fec4aeb1">Setting up virtual environments with dbt</a></li>
    </ul>
  </div>

  <div class="articles-section">
    <p>
      Want to talk platforms, agentic systems, or RAG? Reach me at <a href="mailto:dmaree2@gmail.com">dmaree2@gmail.com</a> or on <a href="https://www.linkedin.com/in/donovan-maree-90452776/">LinkedIn</a>.
    </p>
  </div>
</body>
</html>
