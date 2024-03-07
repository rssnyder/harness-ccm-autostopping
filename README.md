# harness-ccm-autostopping

helm chart for the kubernetes autostopping controller and router

## usage

> :warning: You must have the target cluster set up in Harness with a K8s and CCM K8s connector before you deploy this chart

install repo
`helm repo add harness-ccm-autostopping https://rssnyder.github.io/harness-ccm-autostopping`

update repo
`helm repo update harness-ccm-autostopping`

deploy chart (you must set your namespace to `harness-autostopping`)
```
helm upgrade -i harness-autostopping --namespace harness-autostopping --create-namespace \
  harness-ccm-autostopping/harness-ccm-autostopping \
  --set accountId=wlgELJ0TTre5aZhzpt8gVA \
  --set connectorId=_lab_ccm \
  --set apiToken=sat.wlgELJ0TTre5aZhzpt8gVA.xxxxxxxxxxxx
```

- accountId: your Harness account ID
- connectorId: the ID for the CCM K8s connector for this cluster
- apiToken: a Harness API key with at least ccm:read for all account level resources

## development notes

things that must be hard-coded:

namespace: `harness-autostopping`

service name for router: `autostopping-router`

service name for controller: `autostopping-controller` (therefor also hard-coded in the router configmap)

deployment name for controller: `autostopping-controller`

configmap: `harness-autostopping-enforcement`

secret name for api key: `harness-api-key`
