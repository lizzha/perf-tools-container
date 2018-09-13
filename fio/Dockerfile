FROM alpine:latest
RUN apk add git make gcc libc-dev linux-headers && \
    git clone git://git.kernel.dk/fio.git && \ 
    cd fio/ && ./configure && make && make install

FROM alpine:latest
LABEL maintainer="lizzha@microsoft.com"
WORKDIR /root/
COPY --from=0 /usr/local/bin/fio .
ENTRYPOINT ["./fio"]
