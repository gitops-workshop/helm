# Helm

Build and test:

```
helm lint my-app
helm template my-app
helm install ./my-app --name my-app
```

```
k get all
```

You should see:

```
NAME         READY   STATUS    RESTARTS   AGE
pod/my-app   1/1     Running   0          73s

NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   21d
```

```
k port-forward pod/my-app 8080:8080
```

Open http://localhost:8080

Clean-up:

```
helm list
helme delete --purge my-app
```

Install:

```
helm package my-app
helm repo index .
```