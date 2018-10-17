FROM alpine:latest
RUN apk add git make gcc libc-dev linux-headers libaio libaio-dev && \
    git clone git://git.kernel.dk/fio.git && \ 
    cd fio/ && ./configure && make && make install

FROM alpine:latest
LABEL maintainer="lizzha@microsoft.com"
WORKDIR /root/
COPY --from=0 /usr/lib/libaio* /usr/lib/
COPY --from=0 /usr/local/bin/fio /usr/local/bin
ENTRYPOINT ["/usr/local/bin/fio"]
