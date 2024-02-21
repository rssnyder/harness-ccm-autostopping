# harness-ccm-autostopping

helm chart for the kubernetes autostopping controller and router

## usage

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

## development notes

things that must be hard-coded:

namespace: `harness-autostopping`

service name for router: `autostopping-router`

deployment name for controller: `autostopping-controller`

configmap: `harness-autostopping-enforcement`

secret name for api key: `harness-api-key`
