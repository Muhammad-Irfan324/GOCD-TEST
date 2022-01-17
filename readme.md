Using Kind for Kubernetes Cluster

Prerequisite - INSTALL DOCKER

Using Kind for creating a kubernetes cluster

Documentation [kind](https://kind.sigs.k8s.io/docs/user/quick-start/)

For installig [kubectl](https://kubernetes.io/docs/tasks/tools/)

For installing [Helm](https://helm.sh/docs/intro/install/)

For Installing Ingress Load balancer on Prem
   
    - kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/master/manifests/namespace.yaml

    - kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)" 

    - kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/master/manifests/metallb.yaml

    - kubectl get pods -n metallb-system --watch

    - docker network inspect -f '{{.IPAM.Config}}' kind

    - kubectl apply -f configmap.yaml
 
    - helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

    - helm repo add nginx-stable https://helm.nginx.com/stable

    - helm install ingress-nginx ingress-nginx/ingress-nginx -f ingress.yaml
