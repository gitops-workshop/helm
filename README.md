# Helm

Set-up

```
kubernetes-helm
helm init --client-only
kubectl -n kube-system get pod
```

Build and test:

```
cd my-app
helm template .
helm template . --set greeting='Hi KubeCon' | kubectl -n default apply -f -
```

```
kubectl logs my-app
```

You should see:

```
2019/11/13 18:38:57 Hi KubeCon
```

Install:

```
helm package my-app
helm repo index .
git add index.yaml *.tgz
git commit -m "Publish"
git push
```

```
helm repo add gitops-workshop https://gitops-workshop.github.io/helm/
helm fetch gitops-workshop/my-app
```

### Clean-up:

```
helm template . --set greeting='Hi KubeCon' | kubectl -n default delete -f -
helm repo remove gitops-workshop
```
