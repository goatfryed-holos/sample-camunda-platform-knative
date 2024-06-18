Verify operator with cosign (recommended, requires cosign installed)
```shell
curl -sSL https://github.com/knative/operator/releases/download/knative-v1.14.3/operator.yaml \
  | grep 'gcr.io/' | awk '{print $2}' | sort | uniq \
  | xargs -n 1 \
    cosign verify -o text \
      --certificate-identity=signer@knative-releases.iam.gserviceaccount.com \
      --certificate-oidc-issuer=https://accounts.google.com
```

Setup operator
```shell
kubectl apply -f https://github.com/knative/operator/releases/download/knative-v1.14.3/operator.yaml
```

Setup knative serving
```shell
kubectl apply -f knative-serving.yaml
```