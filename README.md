# k8s-for-beginners

## Build

#### Go build

- go mod vendor
- CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -ldflags '-w' -o main cmd/[app]/*.go
    > replace `[app]` with "webapp" or "memconsumer" or "pageview"

Explanations:

- `CGO_ENABLED=0`: disable `CGO` to generate a statically linked binary so that it can be packed with some minimized image like `scratch` or `alpine`.
- `-ldflags '-w'`: disable debugging to make the binary size smaller.

#### Docker build

- docker build -t hweicdl/[app]:v0.0.1 cmd/[app]/
    > replace `[app]` with "webapp" or "memconsumer" or "pageview"

## Applications

#### webapp

`webapp` is a simple HTTP server demonstrating how to build a simple Docker image.

#### memconsumer

`memconsumer` is an application which consumes a fixed amount of RAM. It's used to demonstrate how container runtime manages containers which overuse memories.

#### pageview

`pageview` is an web application which records the page view and sync with backend redis db.