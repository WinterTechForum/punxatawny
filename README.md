Super simple status tracking app with in-memory only data.

Supported routes:

- GET `/people`
- GET `/people/{id}`
- POST `/people/{id}`
- DELETE `/people/{id}`


This is built with a `scratch` image so it's super small.

This requires building with static linking for the libraries:

```
$ CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo .
```
