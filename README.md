# devops

https://www.youtube.com/watch?v=8ULmDxTzAVQ
https://github.com/bakavets/k8s-lessons/blob/master/lesson-16/prod_ClusterIssuer.yaml

nginx ingress setup
```
# https://docs.rancherdesktop.io/how-to-guides/setup-NGINX-Ingress-Controller/
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.1.2/deploy/static/provider/cloud/deploy.yaml
```

cert-manager setup
```
# https://cert-manager.io/docs/installation/
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.13.2/cert-manager.yaml
```

authentik setup
```
# https://goauthentik.io/docs/installation/kubernetes
helm repo add authentik https://charts.goauthentik.io
helm repo update
helm upgrade --install authentik authentik/authentik -f authentik.yml
```


mailu setup
```
# https://github.com/Mailu/helm-charts/blob/master/mailu/README.md
helm repo add mailu https://mailu.github.io/helm-charts/
helm show values mailu/mailu > mailu.yml
helm install mailu mailu/mailu -n mailu-mailserver --values mailu.yml
helm upgrade mailu mailu/mailu -n mailu-mailserver --values mailu.yml
```



