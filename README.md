# A Flask app on top of Openshift 4

Create a very simple hello world Python app with Flask framework, and deploy into Openshift 4.

## Build and Push to Docker Hub from Openshift 4
```
$ oc new-build . --name=hello-world-python --to-docker --to=docker.io/dockerusername/hello-world-python

$ oc start-build hello-world-python --from-dir=. --follow --wait
```

## Deploy to OpenShift 4
```
$ oc new-app . --docker-image=dockerusername/hello-world-python --name=hello-world-python-app
```

## Expose a Secure URL for this Flask app
```
$ oc create route edge --service=hello-world-python-app
```