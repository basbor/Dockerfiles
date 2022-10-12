FROM golang

WORKDIR /app
ADD app/. /app
RUN  go env -w GO111MODULE=off && go build -o goapp

ENTRYPOINT ["./goapp"]