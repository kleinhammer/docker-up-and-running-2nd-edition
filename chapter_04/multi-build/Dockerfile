# Build Container

FROM golang:alpine as builder
RUN apk update && apk add git && \
CGO_ENABLED=0 go install github.com/kleinhammer/helloworld@4cd14a9afef6b06fc1126e8476ece21865ebee07

# Prod Container

FROM scratch
COPY --from=builder /go/bin/helloworld /helloworld
EXPOSE 8080
CMD ["/helloworld"]
