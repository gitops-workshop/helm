# Hands-On: Helm

### 1. Install The Helm CLI

```
brew install kubernetes-helm
helm init --client-only
```

### 2. Fork and Clone This Git Repo

Click the fork button

```
git clone git@github.com:${username}/secrets.git

```

### 3. Template Your App

```
cd my-app
helm template .
helm template . --set greeting='Hi KubeCon' 
```

### 4. Package Your App

```
helm package my-app
helm repo index .
```

### 5. Publish You App

```
git add index.yaml *.tgz
git commit -m "Publish"
git push
```

Open Github and enable website https://github.com/${username}/helm/settings

### 5. Fetch You App From The Repo

```
helm repo add gitops-workshop https://${username}.github.io/helm/
helm fetch gitops-workshop/my-app
```

### Clean-Up

```
helm repo remove gitops-workshop
```
