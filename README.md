# pulp-pods
Pulp running in OpenShift

## Getting Started

- Have an OpenShift cluster or Minishift running and be logged in with the `oc` cli tool
- `oc new-project pulp`
- `oc login -u system:admin`
- `oc adm policy add-scc-to-user anyuid system:serviceaccount:pulp:anyuid`
- `oc login -u developer -p developer`
- Add your certificates to the secrets files (or just use the ones already there)
- `oc create -f pulp-key-secret.yaml`
- `oc create -f pulp-certs-secret.yaml`
- `oc create -f pulp-template.yaml`
- `oc new-app --template=pulp`

## Redeploy the entire application
- `./teardown`
- `oc new-app --template=pulp`

