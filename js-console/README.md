Running on Openshift

```shell 
oc new-build --name js-console --binary --strategy source --image-stream httpd
```
```shell
oc start-build js-console --from-dir . --follow
```
```shell
oc new-app --image-stream=js-console:latest
```
```shell
oc expose svc/js-console
```

