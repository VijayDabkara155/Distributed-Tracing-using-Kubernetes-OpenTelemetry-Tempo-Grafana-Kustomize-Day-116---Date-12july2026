# Distributed Tracing on Kubernetes with OpenTelemetry, Tempo & Grafana

A cloud-native distributed tracing stack deployed on Kubernetes using **Kustomize**, **OpenTelemetry Collector**, **Grafana Tempo**, **Grafana**, and **NGINX Ingress**.

This project demonstrates how to deploy an end-to-end observability platform capable of receiving, storing, and visualizing distributed traces from applications.

---

## 🚀 Architecture

```
Application
      │
      │ OTLP (gRPC/HTTP)
      ▼
OpenTelemetry Collector
      │
      ▼
Grafana Tempo
      │
      ▼
Grafana
      │
      ▼
Distributed Trace Visualization
```

---

## 📦 Tech Stack

- Kubernetes (K3d/K3s)
- Kustomize
- OpenTelemetry Collector
- Grafana Tempo
- Grafana
- NGINX Ingress Controller
- Docker
- kubectl

---

## 📁 Project Structure

```
.
├── base
│   ├── grafana
│   │   ├── datasource.yaml
│   │   ├── deployment.yaml
│   │   ├── ingress.yaml
│   │   └── service.yaml
│   │
│   ├── tempo
│   │   ├── config.yaml
│   │   ├── deployment.yaml
│   │   ├── ingress.yaml
│   │   └── service.yaml
│   │
│   ├── otel-collector
│   │   ├── config.yaml
│   │   ├── deployment.yaml
│   │   ├── ingress.yaml
│   │   └── service.yaml
│   │
│   ├── namespace.yaml
│   └── kustomization.yaml
│
├── overlays
└── setup.sh
```

---

## ✨ Features

- Kubernetes-native deployment
- Modular Kustomize project structure
- OpenTelemetry Collector
- Grafana Tempo tracing backend
- Grafana deployment
- Automatic datasource provisioning
- NGINX Ingress
- ConfigMaps for configuration
- OTLP over gRPC & HTTP support

---

## 📋 Prerequisites

Before deploying, make sure you have:

- Docker
- kubectl
- K3d or K3s
- Kustomize
- NGINX Ingress Controller

---

## 🚀 Deployment

Clone the repository

```bash
git clone https://github.com/<your-username>/distributed-tracing-kubernetes.git

cd distributed-tracing-kubernetes
```

Deploy everything

```bash
kubectl apply -k base/
```

Verify resources

```bash
kubectl get pods,svc,ing -n monitoring
```

---

## 🌐 Access the Applications

Add the following entries to your hosts file.

### Linux / macOS

```
/etc/hosts
```

### Windows

```
C:\Windows\System32\drivers\etc\hosts
```

Add

```
127.0.0.1 grafana.local
127.0.0.1 tempo.local
127.0.0.1 otel.local
```

Then open

| Service | URL |
|----------|-----|
| Grafana | http://grafana.local |
| Tempo | http://tempo.local |
| OpenTelemetry Collector | http://otel.local |

---

## 📊 Kubernetes Resources

The project deploys

- Namespace
- ConfigMaps
- Deployments
- Services
- Ingress Resources

---

## 📸 Current Deployment

Successfully deployed

- ✅ Grafana
- ✅ Tempo
- ✅ OpenTelemetry Collector
- ✅ Kubernetes Services
- ✅ Kubernetes Ingress
- ✅ ConfigMaps
- ✅ Kustomize Base

---

## 🔍 Health Checks

Tempo Ready

```
http://tempo.local/ready
```

Tempo Metrics

```
http://tempo.local/metrics
```

---

## 🛠️ Future Improvements

- Deploy an instrumented Node.js application
- Generate distributed traces
- Visualize traces in Grafana
- Add Prometheus metrics
- Add Loki for centralized logging
- Add Jaeger UI comparison
- Helm chart support
- CI/CD with GitHub Actions

---

## 📚 Learning Objectives

This project demonstrates

- Kubernetes fundamentals
- Kustomize
- Distributed Tracing
- OpenTelemetry
- Grafana Tempo
- Grafana
- Kubernetes Ingress
- Cloud Native Observability

---

## 🤝 Contributing

Contributions, improvements, and suggestions are welcome.

Fork the repository, create a feature branch, and submit a pull request.

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Vijay Dabkara**

---

⭐ If you found this project useful, consider giving it a **Star** on GitHub.
