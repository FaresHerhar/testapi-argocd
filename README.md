# README

## Some yaml scripts for debugging

> Curl pod

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: curlimages
  namespace: trbl
spec:
  containers:
  - name: curlimages
    image: curlimages/curl
    command:
      - sleep
      - "3600"
    imagePullPolicy: IfNotPresent
  restartPolicy: Always
```

> DNS Lookup Pos

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: dnsutils
  namespace: trbl
spec:
  containers:
  - name: dnsutils
    image: k8s.gcr.io/e2e-test-images/jessie-dnsutils:1.3
    command:
      - sleep
      - "3600"
    imagePullPolicy: IfNotPresent
  restartPolicy: Always

```

> Shell Aliases

```shell
alias kdns="kubectl exec -i -t dnsutils -n trbl -- nslookup"
alias kcurl="kubectl exec -i -t curlimages -n trbl -- curl"
```
