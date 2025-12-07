# awa-scraping-engine

🚀 Overview

AWA Scraping is an enterprise-grade, cloud-native, distributed scraping platform designed to collect, clean, and deliver structured product data from complex, high-volume, Cloudflare-protected, and JavaScript-heavy websites at scale. It brings together Airflow orchestration, Scrapy-based client workers, a high-performance FastAPI-powered SeleniumBase automation server, browser pooling, proxy distribution, and cloud-native deployment.

The platform supports multi-site, large-scale extraction pipelines with stateful browser automation, retry mechanisms, live progress tracking, resumable crawls, slicing of massive datasets, and multi-format export options including databases, cloud storage, APIs, and BI tools. It has been validated against multiple real-world commercial websites across e-commerce, grocery, transport, and marketplaces — sites that require robust automation to bypass dynamic rendering, session binding, anti-bot systems, and rate-limiting heuristics.
🧩 Core Features

✔ Distributed, Scalable Architecture <br>
Airflow-managed DAGs orchestrate scraping and automation workflows. <br>
Redis/RabbitMQ broker distributes tasks to multiple Scrapy workers. <br>
Supports horizontal scaling of workers and browser automation servers. <br>
Built for thousands to millions of items across multiple domains. <br>

✔ Hybrid Engine (Scrapy + SeleniumBase) <br>
Scrapy workers perform fast, lightweight crawl tasks. <br>
FastAPI SeleniumBase Server handles JavaScript-heavy flows, multi-step navigation, DOM extraction, login flows, infinite scroll, and advanced automation. Workers request dynamic content from the Seleniumbase server via an REST API. <br>

✔ Browser Pooling & Session Reuse <br>
SeleniumBase browsers initialized in pools stay warm for fast reuse. <br>
Smart lifecycle management (restart after N tasks, per-site policies). <br>
Auto-recovering browsers reduce failure rates on JS-heavy websites. <br>

✔ Proxy & Anti-Bot Handling <br>
Integrated rotating-proxy support (residential/datacenter). <br>
Per-domain routing rules, cooldown logic, IP health checks. <br>
Request fingerprint randomization, User-Agent & header rotation, Auto-detector for blocked/banned pages. <br>
Designed for Cloudflare/Incapsula/Akamai-protected websites. <br>
Optional 2Captcha integration <br>

✔ Resumable, Fault-Tolerant Scraping <br>
Per-task checkpoints stored in Redis/Postgres. <br>
DAG-level retries + worker-level retries. <br>
Automatic requeueing of failed batches and progress tracking. <br>

✔ Multi-Format Export System <br>
Export pipeline supports: <br>
CSV, JSON, Parquet <br>
Postgres / MySQL <br>
S3 / MinIO / GCS <br>
REST callback APIs <br>
Google Sheets (optional adapter) <br>
BI dashboard ingestion endpoints (Metabase / Superset / PowerBI pipelines) <br>

✔ CI/CD Integrated <br>
GitHub Actions for linting, dry-run tests, environment builds. <br>
Automated container image versioning. <br>
Supports deployment to Kubernetes cluster via Helm. <br>
Optional environment provisioning via Terraform <br>

✔ Cloud-Native Deployment <br>
Fully containerized. <br>
Kubernetes support for all services (workers, Selenium server, Airflow, broker) <br>
Kubespray for on-prem clusters. <br>
Terraform templates for provisioning cloud infrastructure. <br>

🏗 System Architecture <br>

![System Architecture Diagram](./images/architecture.png)

🌐 Supported Target Categories <br>
🔹E-commerce & marketplace platforms <br>
🔹Grocery delivery & hyperlocal stores <br>
🔹Automotive listing directories <br>
🔹Price-comparison and catalog aggregation sites <br>

💲 Pricing & Licensing Models
Below is a suggested freelance-friendly pricing structure with man-hours:

1. Full Purchase License (One-Time Fee)
Includes full delivery of source code, documentation, deployment scripts.
Recommended price range
$3,500 – $9,000+ (depending on modules included)

Estimated man-hours
75 – 180 hours
Ideal for agencies or enterprises wanting full control.

2. SaaS Subscription Model
You host + maintain the service.

Suggested pricing
$99–$299/month (single site)
$299–$799/month (multi-site scraping)
$1,500+/month (enterprise + support)

Includes:
Managed hosting
Monitoring
Scaling
Updates
Support

3. Hybrid Model
A lower one-time customization fee + monthly operational fee.
Complex multi-step or authenticated flows
Cloudflare/Akamai-protected domains
