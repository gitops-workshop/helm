# Helm

### 1. Set-up

```
brew install kubernetes-helm
helm init --client-only
```

### 2. Template The App

```
cd my-app
helm template .
helm template . --set greeting='Hi KubeCon' 
```

### 3. Package The App

```
helm package my-app
helm repo index .
```

### 4. Publish The App

```
git add index.yaml *.tgz
git commit -m "Publish"
git push
```

### 5. Get The App From A Repo

```
helm repo add gitops-workshop https://gitops-workshop.github.io/helm/
helm fetch gitops-workshop/my-app
```

### Clean-Up

```
helm repo remove gitops-workshop
```
