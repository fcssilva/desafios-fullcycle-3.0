FROM golang:latest AS build

WORKDIR /app

COPY main.go ./

RUN go build main.go && cp main /go/bin/

FROM scratch

COPY --from=build /go/bin/main /go/bin/main

ENTRYPOINT ["/go/bin/main"]