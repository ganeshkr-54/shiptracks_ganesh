# Base Helm chart for universal deployments

See default (base) values in `values.yaml`.

This chart should be used as dependency, example (parent `Chart.yaml`):

```
dependencies:
  - name: base
    version: "0.1.0"
    repository: "cm://h.cfcr.io/oceaneering/dev"
    import-values:
      - child: base
        parent: base
```

Deployments should be defined in parent chart `values.yaml`, example:

```
deployments:
  - web

web:
  image:
    repository: nginx
    tag: stable
  volumes:
    temp:
      emptyDir: {}
      mounts:
        - mountPath: /temp
  service:
    ports:
      - port: 80
  ingress:
    hosts:
      - host: example.com
        paths:
          - path: /
```

Values can be overridden during deployment, example:

```
helm upgrade --install ... --debug --dry-run --set web.image.tag=latest
```
