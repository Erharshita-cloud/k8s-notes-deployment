📒 Notes App – Kubernetes Deployment

This repository contains Kubernetes manifests for deploying the Notes App.
The app was cloned from an existing project, and here I created the Kubernetes configuration files to run it inside a cluster.

----
🚀 Steps I Followed
1️⃣ Created a Deployment

Defined Pods for the Notes App in deployment.yml

Apply it:

kubectl apply -f deployment.yml

2️⃣ Created a Namespace

Organized resources under a dedicated namespace (notes-app) in namespace.yml

Apply it:

kubectl apply -f namespace.yml

3️⃣ Created a Service

Exposed the Pods internally using service.yml

Apply it:

kubectl apply -f service.yml


Check service:

kubectl get svc -n notes-app

4️⃣ Access the App

Since no external LoadBalancer/NodePort was used, I accessed the app using port-forwarding:

kubectl port-forward service/notes-app-service -n notes-app 8000:8000 --address=0.0.0.0


Now open 👉 http://localhost:8000 in your browser.
----

----
🛠️ Tools Used

Kubernetes (Deployment, Namespace, Service)

Docker (for container image)

Notes App (base project)
----

----
📌 Note

The application source was cloned from another repository.
This repo focuses on the Kubernetes deployment part only.
----
