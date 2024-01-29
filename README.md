# Vector Helm Charts

Official Helm charts for Vector. Currently supported:
- [Vector](charts/vector/README.md) (vector/vector)

# How to use the Vector Helm Repository [Coming Soon]

You need to add this repository to your Helm repositories:

```shell
helm repo add vector https://helm.vector.dev
helm repo update
```
# How to use the Vector Helm (Local)
Use `helm package .` to build the `.tgz` file and then run the following command:

```shell
helm install ./vector-0.30.0.tgz \
  --namespace vector \
  --create-namespace \
  --values values.yaml
```

## Uninstalling CtrlB-Vector
To delete everything and start fresh, do this whenenver you update the `values.yaml` file:

```
kubectl delete pods -l app.kubernetes.io/name=vector -n vector
```

```
kubectl delete namespace vector
```

## Checking Applied Config (For Debugging Only)
To verify if the configs have been applied correctly or not: 

```
kubectl get configmaps -n vector
```

```
kubectl edit configmap vector -n vector
```