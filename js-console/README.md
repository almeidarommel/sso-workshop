## Running on Openshift with oc login and the same project

1) Building app js-console on src directory using s2i:
```shell 
oc new-build --name js-console --binary --strategy source --image-stream httpd
```
2) Starting build js-console from the same dir:
```shell
oc start-build js-console --from-dir . --follow
```
3) Creating new-app from image-stream:
```shell
oc new-app --image-stream=js-console:latest
```
4) Exposing route for access app:
```shell
oc expose svc/js-console
```

