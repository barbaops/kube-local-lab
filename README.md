# Kubernetes local with Kind

## Helms

**CrossPlane**
````
helm repo add crossplane-stable https://charts.crossplane.io/stable
helm repo update
helm install crossplane --namespace crossplane-system crossplane-stable/crossplane --create-namespace
`````

**Rancher**
``````
helm repo add rancher-latest https://releases.rancher.com/server-charts/latest
helm repo update
helm install rancher rancher-latest/rancher \
  --namespace cattle-system \
  --set hostname=rancher.wbhome \
  --set bootstrapPassword=<sua-senha-desejada>
  --create-namespace
``````

**Istio**
``````
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
kubectl create namespace istio-system
helm install istio-base istio/base -n istio-system
helm install istiod istio/istiod -n istio-system
helm install istio-ingressgateway istio/gateway -n istio-system
``````

**ArgoCD**
``````
helm repo add argo https://argoproj.github.io/argo-helm
helm repo update
kubectl create namespace argocd
helm install argocd argo/argo-cd --namespace argocd
``````

**Predator**
``````
helm repo add predator https://zooz.github.io/predator/
helm repo update
kubectl create namespace predator
helm install predator predator/predator --namespace predator
``````

**Locust**
``````
helm repo add locust https://locustio.github.io/helm-chart/
helm repo update
kubectl create namespace locust
helm install locust locust/locust --namespace locust
``````

**GoldiLocks**
``````
helm repo add fairwinds-stable https://charts.fairwinds.com/stable
helm repo update
kubectl create namespace goldilocks
helm install goldilocks fairwinds-stable/goldilocks --namespace goldilocks
``````

**KubeCost**
``````
helm repo add kubecost https://kubecost.github.io/cost-analyzer/
helm repo update
kubectl create namespace kubecost
helm install kubecost kubecost/cost-analyzer --namespace kubecost
``````
