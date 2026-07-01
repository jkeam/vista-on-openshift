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
oc apply -f ./openshift/iriscluster.yaml
```

## Resources

1. [InterSystems Kubernetes Operator Docs](https://docs.intersystems.com/components/csp/docbook/DocBook.UI.Page.cls?KEY=AIKO)
2. [Download IKO](https://developer.intersystems.com/next-steps/get-intersystems-iris-community-edition-with-an-install-kit/)
3. [InterSystems Container Registry](https://containers.intersystems.com/contents/containers)
4. [IRIS Community Project](https://github.com/intersystems-community/iris-k8s-monitoring)
5. [Secured Rest API](https://github.com/intersystems-community/secured-rest-api)
