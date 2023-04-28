# trust-k8s

Manifests for deploying Trusted Content (TC) on OpenShift

To deploy on OpenShift with test-data:

```
oc new-project trusted
oc apply -f guac
oc apply -f trust-api
oc apply -f trust-frontend
```

To query the API:

```
HOST=$(oc get route api -o jsonpath='{.spec.host}')
curl https://$HOST/api/trusted
```

Frontend URL:

```
HOST=$(oc get route console -o jsonpath='{.spec.host}')
firefox https://$HOST/
```
