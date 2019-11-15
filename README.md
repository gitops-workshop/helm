# Helm

Set-up

```
brew install kubernetes-helm
helm init --client-only
```

Build and test:

```
cd my-app
helm template .
helm template . --set greeting='Hi KubeCon' 
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
helm repo remove gitops-workshop
```
