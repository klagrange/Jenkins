### Steps
```
# Add ingress to minikube
minikube addons enable ingress

# Setup custom routing to minikube instance
echo "$(minikube ip) on-minikube-ingress.local" | sudo tee -a /etc/hosts'

# Add objects to cluster
kubectl apply -f ./on-minikube-ingress

# Sanity check: ensure jenkins UI is up
curl on-minikube-ingress.local

# Setup jenkins kubernetes plugin to spin dynamic slaves on our minikube cluster
# loosely based on this docu: https://www.oracle.com/webfolder/technetwork/tutorials/obe/oci/configure_jenkins_kubernetes_plugin/configurekubernetesplugin.html
```
