FROM golang:alpine

COPY root /

RUN apk add --no-cache ca-certificates \
        dpkg \
        gcc \
        git \
        musl-dev \
        bash

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN chmod +x /entrypoint.sh

RUN export GO111MODULE="on"

RUN go get github.com/tockins/realize

WORKDIR /app

CMD ["realize", "start", "--test"]

