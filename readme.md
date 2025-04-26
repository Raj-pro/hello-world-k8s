# 🚀 Hello World Kubernetes App

A simple "Hello, World" web app served with NGINX on a local Kubernetes (Kind) cluster. Optional GitOps integration with Argo CD.

## 📁 Project Structure

```bash
app/index.html          # Simple HTML page
docker/Dockerfile       # Dockerfile to build custom NGINX image
k8s/deployment.yaml     # Kubernetes Deployment
k8s/service.yaml        # Kubernetes Service

README.md
demo/video.mp4          # (Optional) Demo video
```
⚙️ Steps to Deploy
Build and Load Docker 
```
Imagedocker build -t hello-world-nginx -f docker/Dockerfile .
kind load docker-image hello-world-nginx --name hello-world-cluster
```
Create Kind Cluster
```
kind create cluster --name hello-world-cluster
kubectl get nodes
```
Deploy to Kubernetes
```
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```
Access Application
Open in browser:
```
http://localhost:30007
```


Check out the demo video on YouTube:

[![Demo Video](https://img.youtube.com/vi/VqNFodQ4C0w/0.jpg)](https://youtu.be/VqNFodQ4C0w)

[Watch the full video here](https://youtu.be/VqNFodQ4C0w)
