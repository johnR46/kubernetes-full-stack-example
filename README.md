# kubernetes-full-stack-example
Source code for blog post https://nirajsonawane.github.io/2020/04/25/Deploy-React-Spring-Boot-MongoDB-Fullstack-application-on-Kubernetes/



# for GKE

Prepare ingress controller and map domain
# Add Nginx Helm Repesitory
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

# Deploy Nginx Controller on GKE
helm install ingress-nginx ingress-nginx/ingress-nginx --namespace kube-system

# You need to wait for few minutes before you will get the EXTERNAL-IP
# Get Controller IP Address
echo $(kubectl --namespace kube-system get services ingress-nginx-controller \
  --output jsonpath='{.status.loadBalancer.ingress[0].ip}')

# X
