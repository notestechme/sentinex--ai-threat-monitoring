# 🧠 SENTINEX — AI Threat Detection & Response Framework

**SENTINEX** is an intelligent, event-driven monitoring framework built for detecting anomalies and threats across hybrid environments. It integrates with OpenTelemetry pipelines, performs real-time ML inference, and feeds alert data to SIEMs or messaging services.

---

## 🚨 Core Features

- 🔍 **Real-Time Anomaly Detection** — stream-based classification using scikit-learn & custom models
- 🛰️ **Telemetry Collector Integration** — supports OpenTelemetry, Elastic APM, Prometheus
- 🧠 **AI Model Orchestration** — pluggable ML inference engine for threat scoring
- 📡 **Alert Forwarding** — webhook + Slack + Kafka output support
- 💾 **ElasticSearch Logging** — logs all threat evidence and model decisions
- 📈 **Grafana Dashboard** — includes JSON templates for live status boards

---

## 📦 Architecture Overview

[ Agents ] -> [ OpenTelemetry Collector ] -> [ SENTINEX Core (Python) ]
|
+------v-------+
| ML Inference |
+------v-------+
| Alert Router |
+------v-------+
| ElasticStore |
+--------------+
---

## ⚙️ Technologies Used

- Python 3.10+
- scikit-learn + ONNX runtime
- OpenTelemetry
- ElasticSearch / Logstash / Kibana (ELK)
- Docker & Docker Compose
- Optional: Redis for alert queues

---

## 📁 Project Structure

sentinex/
├── core/
│ └── threat_detector.py
├── models/
│ └── anomaly_v1.onnx
├── config/
│ └── routing.yaml
├── telemetry/
│ └── otel-config.yaml
├── dashboards/
│ └── grafana-threat.json
└── README.md
---

## 🛠️ Setup Instructions

1. Clone the repo  
2. Update `config/routing.yaml` with your alert targets  
3. Run with Docker:
```bash
docker-compose up -d
Access Grafana at http://localhost:3000 — import grafana-threat.json

🤝 Contribution
We welcome PRs, model improvements, and new alert output integrations. Please open issues for suggestions.

