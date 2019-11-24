# k8s-for-beginners

CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -ldflags '-w' -o main cmd/[folder]/*.go

> replace `[folder]` with "webapp" or "memconsumer"

- `CGO_ENABLED=0`: disable `CGO` to generate a statically linked binary so that it can be packed with some minimized image like `scratch` or `alpine`.
- `-ldflags '-w'`: disable debugging to make the binary size smaller.

And then use Docker to build the image:

```
docker build -t hweicdl/[folder]:v0.0.1 cmd/[folder]/
```

## webapp

`Webapp` is a simple HTTP server demonstrating how to build a simple Docker image.

## memconsumer

`Memconsumer` is an application which consumes a fixed amount of RAM. It's used to demonstrate how container runtime manages containers which overuse memories.