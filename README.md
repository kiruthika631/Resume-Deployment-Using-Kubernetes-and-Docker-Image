# Resume-Deployment-Using-Kubernetes-and-Docker-Image
 Resume website built with HTML and deployed using Docker + Kubernetes.
# Resume-deployment-with-kubernetes-and-docker-image
Resume deployment with Docker &amp; Kubernetes deployment files
# Resume Frontend
A simple static resume website built with HTML and deployed using Docker + Kubernetes.
## Structure
resume
docker-compose.yml  frontend  k8s-deployment.yaml
frontend
Dockerfile  index.html
## Files Structure
- `frontend/Dockerfile` → Dockerfile to build the frontend image
- `frontend/index.html` → Resume webpage
- `docker-compose.yml` → Local multi-container deployment
- `k8s-deployment.yaml` → Kubernetes Deployment + Service
## Run Locally (Docker)
```bash
docker build -t resume-frontend .
docker run -p 8080:80 resume-frontend
## Steps
minikube status
minikube start
cd ~/resume/frontend
minikube image build -t resume-frontend:1.0 .
kubectl apply -f k8s-frontend.yaml
kubectl get deployments
kubectl get pods -o wide
kubectl get svc
kubectl describe pod -l app=resume-frontend
kubectl logs -l app=resume-frontend
minikube ip
http://$(minikube ip):30050
minikube service resume-frontend --url
kubectl port-forward svc/resume-frontend 8080:80
