# Flask Application – CI/CD with Jenkins, Docker, Kubernetes & k6

## 📌 Overview  
This project is a **Flask-based web application** that is:  
- Containerized with **Docker**  
- Deployed to **Kubernetes**  
- Automated with **Jenkins pipelines** for **code quality** and **release**  
- Performance tested with **k6**  

---

## ⚙️ Features  
- **Jenkins Pipelines**  
  - *Code Quality Pipeline*: runs linting, tests, and static analysis.  
  - *Release Pipeline*: builds Docker images, pushes to registry, and deploys to Kubernetes.  
- **Dockerfile** for containerization.  
- **Kubernetes Manifests** for deployment and service exposure.  
- **k6 Load Testing Script** for performance validation.  

---

## ☸️ Kubernetes Deployment  

The Flask application is deployed using Kubernetes with focus on **availability, scalability, and reliability**.

### 🔹 Deployment Strategy
- **Replicas: 3** → ensures high availability. If one pod fails, others continue serving traffic.  
- **RollingUpdate strategy** → allows zero-downtime deployments. Pods are updated incrementally.  
- **Max Surge / Max Unavailable** → `1`, balancing deployment speed and stability.
### 🔹 Resource Management
- **Requests** → `CPU: 50m`, `Memory: 64Mi`  
- **Limits** → `CPU: 100m`, `Memory: 128Mi`  
Ensures pods have necessary resources without overloading the cluster.
### 🔹 Health Checks
- **Liveness Probe** → checks if the app is alive; restarts pod if failed.  
- **Readiness Probe** → ensures pod is ready before receiving traffic.  
- Both probes target `/` endpoint on port `5000` with appropriate delays and intervals.
