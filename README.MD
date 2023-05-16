kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.3.0/deploy/static/provider/cloud/deploy.yaml
kubectl create ingress demo --class=nginx --rule sander.nl/=demo:80
# Apply yaml files

kubectl apply -f ./service.yaml --namespace ingress-nginx
kubectl apply -f ./deployment.yaml --namespace ingress-nginx
kubectl apply -f ./ingress.yaml --namespace ingress-nginx