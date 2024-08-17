# Logging with Logging Operator, Fluentd, and Carvel YTT

TODO: Intro

## Do

```bash
# Execute only if using Argo CD
yq --inplace \
    ".spec.source.helm.valuesObject.logging.enabled = true" \
    apps/simple-app.yaml

# Execute only if using Flux
yq --inplace ".spec.values.logging.enabled = true" \
    apps/simple-app.yaml

git add .

git commit -m "Logging"

git push

kubectl --namespace production get logging-all
```

* Wait until new resources are created

```sh
curl "http://simple-app.$INGRESS_HOST?something=else"

echo "http://grafana.$INGRESS_HOST"
```

* Open it in a browser
* Use `admin` as the user and `prom-operator` as the password
* Open `Explore`
* Choose `Loki` as the data source
* Filter by `app_kubernetes_io_name` set to `cncf-demo`
* Search for `something`

## Continue The Adventure

TODO:
