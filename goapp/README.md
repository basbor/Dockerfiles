# Go App Sample

## Container Build

```
docker image build -t kledsonhugo/goapp:1.0.0 . --no-cache
```

- Output example

  ```
  $ docker image build -t kledsonhugo/goapp:1.0.0 . --no-cache
  [+] Building 6.6s (9/9) FINISHED
   => [internal] load build definition from Dockerfile                       0.0s
   => => transferring dockerfile: 131B                                       0.0s
   => [internal] load .dockerignore                                          0.0s
   => => transferring context: 2B                                            0.0s
   => [internal] load metadata for docker.io/library/golang:latest           5.9s
   => [1/4] FROM docker.io/library/golang@sha256:25de7b6b28219279a4          0.0s
   => [internal] load build context                                          0.0s
   => => transferring context: 56B                                           0.0s
   => CACHED [2/4] WORKDIR /app                                              0.0s
   => [3/4] ADD app/. /app                                                   0.0s
   => [4/4] RUN  go env -w GO111MODULE=off && go build -o goapp              0.5s
   => exporting to image                                                     0.0s
   => => exporting layers                                                    0.0s
   => => writing image sha256:e47d7bf5f8982d83abdf7abbd8648f0e02a2d          0.0s
   => => naming to docker.io/kledsonhugo/goapp:1.0.0                         0.0s
  $
  ```

## Container Run

```
docker run kledsonhugo/goapp:1.0.0
```

- Output example

  ```
  $ docker run kledsonhugo/goapp:1.0.0
  My Go app
  $
  ```