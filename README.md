# 📒 k8s-notes-deployment

<div align="center">

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=00D9FF&center=true&vCenter=true&width=600&lines=Creating+Namespace...+✅;Applying+Deployment...+✅;Service+is+Running...+✅;Notes+App+LIVE+on+Kubernetes!+🚀" alt="Typing animation" />

![Kubernetes](https://img.shields.io/badge/Kubernetes-Manifests-blue?style=flat-square&logo=kubernetes)
![Docker](https://img.shields.io/badge/Docker-Container-blue?style=flat-square&logo=docker)
![Namespace](https://img.shields.io/badge/Namespace-notes--app-orange?style=flat-square)

> Kubernetes YAML manifests to deploy a Notes App inside a cluster — covering Deployments, Services, and Namespaces.

</div>

---

## 🏗️ Architecture
```
┌──────────────────────────────────────┐
│         Namespace: notes-app         │
│                                      │
│  ┌─────────────┐   ┌──────────────┐  │
│  │  Deployment │──▶│    Service   │  │
│  │  (Pods)     │   │  (port 8000) │  │
│  └─────────────┘   └──────┬───────┘  │
└─────────────────────────── │ ────────┘
                             │ port-forward
                             ▼
                      http://localhost:8000
```

---

## ✨ What's Inside

| File | Purpose |
|---|---|
| `namespace.yml` | Isolates resources under `notes-app` namespace |
| `deployment.yml` | Defines Pods and container specs |
| `service.yml` | Exposes the app internally within the cluster |

---

## 🚀 Deploy
```bash
# 1. Create namespace
kubectl apply -f namespace.yml

# 2. Deploy the app
kubectl apply -f deployment.yml

# 3. Create service
kubectl apply -f service.yml

# 4. Verify
kubectl get all -n notes-app
```

---

## 🌍 Access the App
```bash
kubectl port-forward service/notes-app-service -n notes-app 8000:8000 --address=0.0.0.0
```
Then open 👉 **http://localhost:8000**

---

## 📌 Note
App source was cloned from an existing project. This repo focuses purely on the **Kubernetes deployment configuration**.

---

<div align="center">

**Harshita Goel** · [GitHub](https://github.com/Erharshita-cloud) · harshitagoel1503@gmail.com

⭐ Star this repo if it helped you learn Kubernetes!

</div>
