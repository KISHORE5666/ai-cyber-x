# 🛡️ AI-CYBER-X Enterprise Security OS

[![Next.js](https://img.shields.io/badge/Frontend-Next.js%2016-black?style=for-the-badge&logo=nextdotjs)](https://nextjs.org/)
[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![TailwindCSS](https://img.shields.io/badge/Styling-TailwindCSS%204-06B6D4?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com/)
[![Docker](https://img.shields.io/badge/Infrastructure-Docker-2496ED?style=for-the-badge&logo=docker)](https://www.docker.com/)

**AI-CYBER-X** is a next-generation, AI-powered Cyber Security Operating System and enterprise security console. It features a modern, responsive security operations center (SOC) dashboard that aggregates, correlates, and visualizes security telemetry across 15 distinct operational security modules. 

The application is structured as a responsive Next.js frontend paired with a modular FastAPI backend simulated engine, ready for deployment in virtualized or containerized infrastructure.

---

## 🚀 Key Modules & Capabilities

The platform implements 15 critical operational phases for enterprise-wide threat tracking and mitigation:

1. **Executive Dashboard**: Unified overview displaying real-time active threats, threats blocked, AI model detections, SIEM events, compliance scores (SOC2, ISO27001, NIST), and SOC KPIs.
2. **Zero Trust & Identity (IAM)**: Access control management utilizing Role-Based Access Control (RBAC), Attribute-Based Access Control (ABAC), MFA enforcement, live user session revocation, and geofencing.
3. **AI Threat Detection Engine**: Machine learning model tracking (Isolation Forest, XGBoost, LSTM Anomaly, Random Forest) and real-time User Behavior Analytics (UBA) anomaly auditing.
4. **SIEM Platform**: High-scale log ingestion tracker with built-in live network flow metrics and active correlation rules for brute-force patterns, lateral movement, and data exfiltration.
5. **SOAR Automation Playbooks**: Automated incident response playbooks for ransomware containment, phishing, credential stuffing, and cloud compromise.
6. **Vulnerability Assessment Platform**: Dedicated CVE vulnerability scans, severity tracking (Critical, High, Medium, Low), and historical patch status audits.
7. **Malware Sandbox Lab**: Static and dynamic binary analysis suite that tracks file names, SHA256 hashes, file entropy, and sandboxing states (analyzed, isolated, active).
8. **Digital Forensics & Incident Response (DFIR)**: Deep analysis of host memory dumps, raw disk images, and network PCAP captures for forensic timeline correlation.
9. **EDR Agent Control**: Host-level security management allowing SOC analysts to isolate hosts, terminate processes, spawn remote shells, and fetch system telemetry.
10. **Cloud Security (CSPM)**: Multi-cloud configuration monitoring for AWS, Azure, and GCP, assessing security posture scores and auditing IAM issues (e.g. public S3 buckets, disabled MFA).
11. **API Security Gateway**: API traffic gateway analytics tracking total requests, blocked attacks, rate limiting, and average routing latency.
12. **Secrets Management**: Vault security metadata tracker for database passwords, cloud API keys, and automated secret rotation pipelines.
13. **Threat Intelligence Feeds**: Centralized Indicator of Compromise (IOC) feeds, feed integrity checks, and direct mapping to the **MITRE ATT&CK** framework.
14. **AI Security Copilot**: An interactive, LLM-powered SOC chat assistant helping security analysts triage ransomware, phishing, and endpoint incidents.
15. **System Health Console**: Real-time status reporting for backend database, Redis cache, Elasticsearch, and the core ML processing engine.

---

## 🛠️ Technology Stack

### Frontend
* **Core**: [Next.js](https://nextjs.org/) (v16.2.12), [React](https://react.dev/) (v19.2.4), [TypeScript](https://www.typescriptlang.org/)
* **Styling**: [TailwindCSS](https://tailwindcss.com/) (v4.0) with custom HSL dark mode variables
* **Animations**: [Framer Motion](https://www.framer.com/motion/) (v12.4.2)
* **Charts**: [Recharts](https://recharts.org/) (v3.10.1)
* **Icons**: [Lucide React](https://lucide.dev/) (v1.27.0)

### Backend
* **Core**: [FastAPI](https://fastapi.tiangolo.com/) (v0.109.0), [Uvicorn](https://www.uvicorn.org/) (v0.27.0)
* **Security & Tokens**: [PyJWT](https://pyjwt.readthedocs.io/), [python-jose](https://python-jose.readthedocs.io/), [passlib](https://passlib.readthedocs.io/)
* **Validation**: [Pydantic](https://docs.pydantic.dev/) (v2.6.0)

---

## 📦 Infrastructure (Docker Compose)

For production environments, the platform is designed to scale with a comprehensive container topology defined in `docker-compose.yml`:
* **Databases**: PostgreSQL (Relational & Core), MongoDB (Threat Intelligence Document Store), Neo4j (Attack Graph Network Engine).
* **Caching & Message Broker**: Redis (Caches & Key-Value Store), Apache Kafka & Zookeeper (Real-time SIEM Log Stream pipeline).
* **Search & Analytics**: Elasticsearch (Log Indexes) & Kibana (Visualization).
* **Monitoring & Metrics**: Prometheus (Metrics Scrapes) & Grafana (Dashboard panels).
* **AI & Machine Learning Tracking**: MLflow server (Model Registry & Experiment runs).

---

## 🚀 Getting Started

### Prerequisites
* [Node.js](https://nodejs.org/) (v22.x or later)
* [Python](https://www.python.org/) (v3.10 or later)
* *(Optional)* [Docker](https://www.docker.com/) & Docker Compose

### Option A: Local Run (No Docker)

#### 1. Start the FastAPI Backend
```bash
# Navigate to the backend directory
cd backend

# Install dependencies
pip install -r requirements.txt

# Start the uvicorn development server
python -m uvicorn main:app --port 8000 --host 127.0.0.1
```
The API documentation will be available at [http://127.0.0.1:8000/api/docs](http://127.0.0.1:8000/api/docs).

#### 2. Start the Next.js Frontend
```bash
# Return to the root directory
cd ..

# Install npm dependencies
npm install

# Start the Next.js development server
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser to view the application.

---

### Option B: Docker Compose Deploy (Full Stack)

To run the complete platform stack including Elasticsearch, Kibana, Kafka, Neo4j, Grafana, MLflow, PostgreSQL, MongoDB, Redis, and the core app containers:

```bash
# Start all containers in detached mode
docker compose up -d
```

---

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

