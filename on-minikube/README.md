### Steps
```
# Create customized jenkins image
docker build . -t my-jenkins-image:1.0
docker tag my-jenkins-image:1.0 klagbambu/jenkins:1.0
docker push klagbambu/jenkins:1.0

# Run instance of image in cluster
kubectl apply -f jenkins-namespace.yaml
kubectl apply -f jenkins-deployment.yaml
kubectl apply -f jenkins-service.yaml

# Ping jenkins page for sanity check
curl "`minikube ip`:32592"

# Get jenkins master IP inside cluster
kubectl get pods --namespace="jenkins-on-minikube" | grep jenkins
kubectl describe pods jenkins-XXXXX --namespace="jenkins-on-minikube" | grep IP

# Add Kubernetes plugin to jenkins
# Jenkins UI -> "Manage Jenkins" -> "Configure System" -> "Cloud" -> "Kubernetes"

# Configure slave workers
```
