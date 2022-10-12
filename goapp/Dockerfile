FROM golang AS build

WORKDIR /build
ADD app/. /build
RUN  go env -w GO111MODULE=off && go build -o goapp

FROM alpine
WORKDIR /app
COPY --from=build /build/goapp /app/

ENTRYPOINT ["./goapp"]