#


## ArgoCD

Install the ArgoCD base and wait until the service is ready:

```shell script
kubectl create ns argocd
kubectl apply -k bases/argocd
```

Port-forward ArgoCD to a local port:

```shell script
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Generate an SSH key and save to Github:

```shell script
ssh-keygen -t rsa -b 4096 -C "name.surname@gmail.com"
> save to overlays/argocd/key/id_rsa_argocd
```

Configure ArgoCD application resources:

```shell script
kubectl create ns argocd
kubectl apply -k overlays/argocd
```



