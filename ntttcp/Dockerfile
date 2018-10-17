FROM alpine:latest
RUN apk add wget gcc libc-dev make && \
    wget https://github.com/Microsoft/ntttcp-for-linux/archive/v1.3.4.tar.gz && \
    tar -zxvf v1.3.4.tar.gz && \
    cd ntttcp-for-linux-1.3.4/src/ && make && make install

FROM alpine:latest
LABEL maintainer="lizzha@microsoft.com"
WORKDIR /root/
COPY --from=0 /usr/bin/ntttcp /usr/bin
ENTRYPOINT ["/usr/bin/ntttcp"]
