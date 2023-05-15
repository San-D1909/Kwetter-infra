# Create Azure Kubernetes Service

# Connect to AKS with command line

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.3.0/deploy/static/provider/cloud/deploy.yanl

# Create a dns and link it to the public ip adress of your "ingress-nginx-controller" service in kubernetes.
Example given: 192.168.0.1

# Go to freenom.com and create an account and get a free domain. Then link the ip from the previous step.
Example given: sander.nl

# Change sander.nl to your domain

kubectl create ingress demo --class=nginx --rule sander.nl/=demo:80

# Apply yanl files

kubectl apply -f ./service.yanl --namespace ingress-nginx
kubectl apply -f ./deployment.yanl --namespace ingress-nginx
kubectl apply -f ./ingress.yanl --namespace ingress-nginx