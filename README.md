# awa-scraping-engine

🚀 Overview

AWA Scraping is an enterprise-grade, cloud-native, distributed scraping platform designed to collect, clean, and deliver structured product data from complex, high-volume, Cloudflare-protected, and JavaScript-heavy websites at scale. It brings together Airflow orchestration, Scrapy-based client workers, a high-performance FastAPI-powered SeleniumBase automation server, browser pooling, proxy distribution, and cloud-native deployment.

The platform supports multi-site, large-scale extraction pipelines with stateful browser automation, retry mechanisms, live progress tracking, resumable crawls, slicing of massive datasets, and multi-format export options including databases, cloud storage, APIs, and BI tools. It has been validated against multiple real-world commercial websites across e-commerce, grocery, transport, and marketplaces — sites that require robust automation to bypass dynamic rendering, session binding, anti-bot systems, and rate-limiting heuristics.
🧩 Core Features

✔ Distributed, Scalable Architecture
Airflow-managed DAGs orchestrate scraping and automation workflows.
Redis/RabbitMQ broker distributes tasks to multiple Scrapy workers.
Supports horizontal scaling of workers and browser automation servers.
Built for thousands to millions of items across multiple domains.

✔ Hybrid Engine (Scrapy + SeleniumBase)
Scrapy workers perform fast, lightweight crawl tasks
FastAPI SeleniumBase Server handles JavaScript-heavy flows, multi-step navigation, DOM extraction, login flows, infinite scroll, and advanced automation. Workers request dynamic content from the Seleniumbase server via an REST API.

✔ Browser Pooling & Session Reuse
SeleniumBase browsers initialized in pools stay warm for fast reuse.
Smart lifecycle management (restart after N tasks, per-site policies).
Auto-recovering browsers reduce failure rates on JS-heavy websites.

✔ Proxy & Anti-Bot Handling
Integrated rotating-proxy support (residential/datacenter).
Per-domain routing rules, cooldown logic, IP health checks.
Request fingerprint randomization, User-Agent & header rotation, Auto-detector for blocked/banned pages.
Designed for Cloudflare/Incapsula/Akamai-protected websites.
Optional 2Captcha integration

✔ Resumable, Fault-Tolerant Scraping
Per-task checkpoints stored in Redis/Postgres.
DAG-level retries + worker-level retries.
Automatic requeueing of failed batches and progress tracking.

✔ Multi-Format Export System
Export pipeline supports:
CSV, JSON, Parquet
Postgres / MySQL
S3 / MinIO / GCS
REST callback APIs
Google Sheets (optional adapter)
BI dashboard ingestion endpoints (Metabase / Superset / PowerBI pipelines)

✔ CI/CD Integrated
GitHub Actions for linting, dry-run tests, environment builds.
Automated container image versioning.
Supports deployment to Kubernetes cluster via Helm.
Optional environment provisioning via Terraform

✔ Cloud-Native Deployment
Fully containerized.
Kubernetes support for all services (workers, Selenium server, Airflow, broker)
Kubespray for on-prem clusters.
Terraform templates for provisioning cloud infrastructure.

🏗 System Architecture

![System Architecture Diagram](./images/architecture_diagram.png)

🌐 Supported Target Categories
🔹E-commerce & marketplace platforms
🔹Grocery delivery & hyperlocal stores
🔹Automotive listing directories
🔹Price-comparison and catalog aggregation sites

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
