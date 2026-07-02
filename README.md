# VistA on OpenShift

## Instructions

```shell
oc new-project vista
oc adm policy add-scc-to-user anyuid -z iris-operator -n vista
oc apply -k openshift
```

Then use the UI to create to deploy the `IRIS Operator`
and wait for it to finish deploying.

```shell
oc create -f ./openshift/iriscluster.yaml
# if you need to delete and recreate the iriscluster,
# restart the iris operator pod for faster results.
# the reconciliation of the iris operator is extremely long.
```

Then scale the stateful set named `iris-data` down to 0,
and set the resources for the pod (due to community license):

```yaml
resources:
  limits:
    cpu: 500m
    memory: 8Gi
  requests:
    cpu: 250m
    memory: 4Gi
```

And scale back to 1 pod.

## Resources

1. [InterSystems Kubernetes Operator Docs](https://docs.intersystems.com/components/csp/docbook/DocBook.UI.Page.cls?KEY=AIKO)
2. [Download IKO](https://developer.intersystems.com/next-steps/get-intersystems-iris-community-edition-with-an-install-kit/)
3. [InterSystems Container Registry](https://containers.intersystems.com/contents/containers)
4. [InterSystems Community Docker Repo](https://hub.docker.com/u/worldvista)
5. [IRIS Community Project](https://github.com/intersystems-community/iris-k8s-monitoring)
6. [Secured Rest API](https://github.com/intersystems-community/secured-rest-api)
7. [My Secured Rest API](https://github.com/jkeam/secured-rest-api)
