# 📦 Kubernetes Ingress Example: Serving Multiple Apps via a Single Ingress

This project demonstrates how to:

- Deploy two NGINX applications (`video` and `wear`) in the `sun` namespace.
- Serve custom HTML content using ConfigMaps.
- Expose both applications through a single Ingress resource using path-based routing.
- Utilize the NGINX Ingress Controller deployed in the `ingress-nginx` namespace.

## 🗂️ Project Structure


.
├── configmap-wear-video.yaml
├── deployment-wear-video.yaml
├── service-wear-video.yaml
├── ingress.yaml
├── ingress-controller.yaml
└── README.md

## 📄 Deployment Steps

Kubectl apply -f .

## 🌐 Accessing the Applications

Assuming the Ingress Controller's service is of type NodePort, find the port number:

kubectl get svc ingress-nginx-controller -n ingress-nginx
Then access:

Video App: http://localhost:31403/video

Wear App: http://localhost:31403/wear

Replace 31403 with your actual NodePort.Each should return the corresponding HTML content.