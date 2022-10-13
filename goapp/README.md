# Go App Sample

## Container Build

```
docker image build -t kledsonhugo/goapp:1.0.0 . --no-cache
```

- Output example

  ```
  $ docker image build -t kledsonhugo/goapp:1.0.0 . --no-cache
  [+] Building 20.7s (13/13) FINISHED
   => [internal] load build definition from Dockerfile                                              0.0s
   => => transferring dockerfile: 247B                                                              0.0s
   => [internal] load .dockerignore                                                                 0.1s
   => => transferring context: 2B                                                                   0.0s
   => [internal] load metadata for docker.io/library/alpine:latest                                 19.9s
   => [internal] load metadata for docker.io/library/golang:latest                                 15.8s
   => CACHED [build 1/4] FROM docker.io/library/golang@sha256:25de7b6b28219279d                     0.0s
   => [stage-1 1/3] FROM docker.io/library/alpine@sha256:bc41182d7ef5ffc53a40b0                     0.0s
   => => resolve docker.io/library/alpine@sha256:bc41182d7ef5ffc53a40b044e72519                     0.0s
   => => sha256:bc41182d7ef5ffc53a40b044e725193bc10142a1243f395ee852a8d9730fc2a 1.64kB / 1.64kB     0.0s
   => => sha256:1304f174557314a7ed9eddb4eab12fed12cb0cd9809e4c28f29af86979a3c87 528B / 528B         0.0s
   => => sha256:9c6f0724472873bb50a2ae67a9e7adcb57673a183cea8b06eb778dca859181b 1.47kB / 1.47kB     0.0s
   => [internal] load build context                                                                 0.0s
   => => transferring context: 56B                                                                  0.0s
   => [build 2/4] WORKDIR /build                                                                    0.0s
   => [build 3/4] ADD app/. /build                                                                  0.0s
   => [stage-1 2/3] WORKDIR /app                                                                    0.0s
   => [build 4/4] RUN  go env -w GO111MODULE=off && go build -o goapp                               0.6s
   => [stage-1 3/3] COPY --from=build /build/goapp /app/                                            0.0s
   => exporting to image                                                                            0.0s
   => => exporting layers                                                                           0.0s
   => => writing image sha256:60f94739db10c24acef738999b1ea8d3fb176688ce9936903                     0.0s
   => => naming to docker.io/kledsonhugo/goapp:1.0.0                                                0.0s
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