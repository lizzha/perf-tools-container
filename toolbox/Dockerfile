FROM alpine:latest
LABEL maintainer="lizzha@microsoft.com"

RUN echo "@testing http://nl.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories
RUN apk --update --no-cache add \
  sysstat \
  dstat@testing \
  bc
