# harness-ccm-autostopping

helm chart for the kubernetes autostopping controller and router

## notes

things that must be hard-coded:

namespace must be `harness-autostopping`

service name for router must be `autostopping-router`

deployment name for controller must be `autostopping-controller`

api key secret must be called `harness-api-key`
