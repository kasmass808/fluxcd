# fluxcd
fluxcd configuration

curl -s https://fluxcd.io/install.sh | sudo bash
flux version
minikube start
kubectl get no
kubectl create ns flux-system
flux install

flux create source git fluxcd \
  --url=https://github.com/kasmass808/fluxcd \
  --branch=main \
  --interval=10m
kubectl get gitrepo -n flux-system

kubectl apply -f clusters/minikube/kustomization.yaml
kubectl get kustomizations -n flux-system
