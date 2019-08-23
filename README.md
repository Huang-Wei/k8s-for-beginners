# k8s-for-beginners

## Go build

CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -ldflags '-w' -o k8s-for-beginners

- `CGO_ENABLED=0`: disable `CGO` to generate a statically linked binary so that it can be packed with some minimized image like `scratch` or `alpine`.
- `-ldflags '-w'`: disable debugging to make the binary size smaller.

