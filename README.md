# A Flask app on top of Openshift 4

Create a very simple hello world Python app with Flask framework, and deploy into Openshift 4.

## Build and Push to Docker Hub from Openshift 4
```
$ oc new-build . --name=hello-world-python --to-docker --to=docker.io/dockerusername/hello-world-python

$ oc start-build hello-world-python --from-dir=. --follow --wait
```

