ARG ALPINE_VERSION=3.18

FROM golang:1.21-alpine${ALPINE_VERSION} as builder

ARG TASKFILE_VERSION=3.30.1

RUN go install github.com/go-task/task/v3/cmd/task@v${TASKFILE_VERSION}

FROM alpine:${ALPINE_VERSION}

COPY --from=builder /go/bin/task /usr/bin/task

ENTRYPOINT ["/usr/bin/task"]
