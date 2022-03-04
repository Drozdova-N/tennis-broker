FROM golang:1.16.6-alpine3.14
WORKDIR /app
ADD . /app
RUN go build -o main ./cmd/main.go

FROM alpine:latest
RUN apk --no-cache add ca-certificates
WORKDIR /app
COPY --from=0  /app/main .
ENTRYPOINT ["./main"]