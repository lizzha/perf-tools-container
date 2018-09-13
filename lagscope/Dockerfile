FROM alpine:latest
RUN apk add git gcc libc-dev make && \
    git clone https://github.com/Microsoft/lagscope && \
    cd lagscope/src/ && make && make install

FROM alpine:latest
LABEL maintainer="lizzha@microsoft.com"
WORKDIR /root
COPY --from=0 /usr/bin/lagscope .
ENTRYPOINT ["./lagscope"]
