# 🚀 Hello World Kubernetes App

A simple "Hello, World" web app served with NGINX on a local Kubernetes (Kind) cluster. Optional GitOps integration with Argo CD.

## 📁 Project Structure

```bash
app/index.html          # Simple HTML page
docker/Dockerfile       # Dockerfile to build custom NGINX image
k8s/deployment.yaml     # Kubernetes Deployment
k8s/service.yaml        # Kubernetes Service
argo-app.yaml           # (Optional) Argo CD Application
README.md
demo/video.mp4          # (Optional) Demo video
```
⚙️ Steps to DeployBuild and Load Docker Imagedocker build -t hello-world-nginx -f docker/Dockerfile .
kind load docker-image hello-world-nginx --name hello-world-cluster
Create Kind Clusterkind create cluster --name hello-world-cluster
kubectl get nodes
Deploy to Kuberneteskubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
Access ApplicationOpen in browser:http://localhost:30007
🚀 (Optional) Setup GitOps with Argo CDInstall Argo CD:kubectl create namespace argocd
kubectl apply -n argocd -f [https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml](https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml)
Port-forward ArgoCD:kubectl port-forward svc/argocd-server -n argocd 8080:443
Create ArgoCD Application:kubectl apply -f argo-app.yaml
