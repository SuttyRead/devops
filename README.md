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
kubectl create namespace authentik
helm upgrade --install authentik authentik/authentik -n authentik -f authentik.yaml
# https://<ingress-host-name>/if/flow/initial-setup/
```

mailu setup
```
# https://github.com/Mailu/helm-charts/blob/master/mailu/README.md
helm repo add mailu https://mailu.github.io/helm-charts/
helm repo update
kubectl create namespace mailu-mailserver
helm upgrade --install mailu mailu/mailu -n mailu-mailserver --values mailu/mailu.yaml
```

nextcloud setup
```
https://github.com/nextcloud/helm/blob/main/charts/nextcloud/README.md
helm repo add nextcloud https://nextcloud.github.io/helm/
helm repo update
helm show values nextcloud/nextcloud > nextcloud-values.yaml
kubectl create namespace nextcloud
helm upgrade --install nextcloud nextcloud/nextcloud -n nextcloud -f nextcloud-values.yaml
```

gitlab-ce setup
```
helm show values gitlab/gitlab > gitlab-values-old.yaml
kubectl create namespace gitlab
helm upgrade --install gitlab gitlab/gitlab -n gitlab -f gitlab-values-new.yaml

change gitlab shell from clusterIp to LoadBalancer
```

