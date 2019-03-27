Super simple status tracking app with in-memory only data.

Supported routes:

- GET `/people`
- GET `/people/{id}`
- POST `/people/{id}`
- DELETE `/people/{id}`


## Building

This is built with a `scratch` image so it's super small.

This requires building with static linking for the libraries:

```
$ CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo .
```

We are using a very slim base image.

It has been deployed to dockerhub as `wtfconf/punxatawny:{tag}`

## Running

This exposes HTTP on port 8000.

## Kubernetes

This can be run in a minikube without doing much more than just running the container directly.

To call it for local dev, expose a service and forward a local port.

```
kubectl run punx --image=wtfconf/punxatawny:0.0.1 --port=8000
kubectl expose deployment punx
kubectl port-forward punx-57fbdff9b5-p8flc :8000                    
http :61906/people              
```                                 

