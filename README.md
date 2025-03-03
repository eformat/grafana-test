# grafana-test

Deploy Operator only

```bash
oc apply -f operator-namespace.yaml
helm upgrade --install grafana . --set operator=true --namespace openshift-grafana
```

Cluster scoped grafana

```bash
helm upgrade --install grafana . --namespace grafana --create-namespace
```

Namespaced scoped grafana

```bash
helm upgrade --install grafana . --namespace grafana --create-namespace --set thanosClusterScoped=false
```

Deploy demo app to generate metrics in your namespace

```bash
oc apply -f test-app.yaml
```
