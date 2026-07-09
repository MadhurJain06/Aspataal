# Aspataal

**Aspataal** is an advanced, production-ready Real-Time Hospital Patient Vitals Monitoring & Anomaly Detection Platform. It is designed to act as a centralized telemetry cockpit for modern hospital wards (such as ICUs, Emergencies, and General wards), delivering instantaneous visibility into patient health metrics while alerting medical staff to critical events.

---

## What Aspataal Is All About

In modern healthcare, delays in detecting abnormal vitals can lead to adverse patient outcomes. Aspataal addresses this by simulating, processing, and visualising critical physiological telemetry streams in real time. It serves as a mock clinic-monitoring and chaos-testing environment, letting engineers and clinicians examine how streaming health telemetry reacts to infrastructure strain, network failures, and emergency scenarios.

---

## Key Highlights & Capabilities

- **Streaming Telemetry**: Simulates key physiological signals (Heart Rate, Blood Pressure, SpO2, and Temperature) at configurable intervals.
- **Clinical Alert Engine**: Instantly flags abnormal signals and categorises them into warnings or critical alarms based on medical thresholds.
- **Zero-Knowledge PII Anonymization (Audit Mode)**: Restricts access to sensitive Personally Identifiable Information (PII) by deterministically hashing patient names (SHA-256) and bucketing age data for k-anonymity on the fly, while leaving medical telemetry intact.
- **Black Box Playback**: Records and buffers streams to allow operators to scrub backward in time and replay clinical vital events second-by-second.
- **Chaos Console**: Simulates real-world emergency stresses—such as mass-casualty events, power outages, and sudden vital surges—to stress-test application elasticity.
- **Native Observability**: Exposes Prometheus metrics out of the box and includes pre-configured Grafana dashboards for monitoring cluster health, API throughput, and alert rates.

---

## Project Repository Structure

The workspace is organized into a clean mono-repo style structure containing:

```text
aspataal-main/
├── backend/            # Node.js + Express server simulating vitals and exporting metrics
├── frontend/           # React + Vite live dashboard with playback and chaos controls
├── monitoring/         # Prometheus scrape definitions and Grafana dashboard JSON
├── k8s/                # Kubernetes Deployment, Service, and HPA manifests
├── docker-compose.yml  # Multi-container orchestration template
└── render.yaml         # Cloud deployment configuration
```

---

## Technology Stack

- **Frontend**: React, Vite, Recharts (for live plotting), Lucide (for iconography), Vanilla CSS.
- **Backend**: Node.js, Express, Prometheus Client (`prom-client`).
- **Telemetry & Monitoring**: Prometheus, Grafana.
- **Infrastructure**: Docker, Docker Compose, Kubernetes (Horizontal Pod Autoscaler).
