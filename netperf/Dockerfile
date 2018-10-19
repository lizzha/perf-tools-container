FROM alpine:latest
RUN apk add wget gcc libc-dev make && \
    wget https://github.com/HewlettPackard/netperf/archive/netperf-2.7.0.tar.gz && \
    tar -zxf netperf-2.7.0.tar.gz && \
    cd netperf-netperf-2.7.0 && ./configure && make && make install

FROM alpine:latest
LABEL maintainer="lizzha@microsoft.com"
WORKDIR /root/
COPY --from=0 /usr/local/bin/netperf /usr/local/bin/
COPY --from=0 /usr/local/bin/netserver /usr/local/bin/
