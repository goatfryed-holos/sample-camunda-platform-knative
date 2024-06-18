# Setup
Prepare
```shell
kubectl apply -f camunda.yaml
```

Refer to https://docs.camunda.io/docs/self-managed/setup/deploy/local/local-kubernetes-cluster/

```shell
helm upgrade --install \
    -f camunda-platform-core-kind-values.yaml \
    --namespace camunda-platform \
    camunda-platform camunda/camunda-platform
```

## connectors
Find connectors in the camunda marketplace

## Camunda Desktop Modeler
add connector templates used.
Find the connector element-templates
https://docs.camunda.io/docs/components/modeler/desktop-modeler/search-paths/


https://marketplace.camunda.com/en-US/apps/415933/rest-connector for SM (self managed).


