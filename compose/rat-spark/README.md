https://github.com/XZB-1248/Spark

https://github.com/XZB-1248/Spark/releases/download/v0.2.1/server_linux_amd64.tar.gz


```
FROM alpine:latest
ENV GOST_VERSION="2.4"

ADD https://github.com/ginuerzh/gost/releases/download/v${GOST_VERSION}/gost_${GOST_VERSION}_linux_386.tar.gz /root/

RUN \
cd /root && \
tar xzvf gost_${GOST_VERSION}_linux_386.tar.gz && \
cp /root/gost_${GOST_VERSION}_linux_386/gost /bin/ && \
chmod +x /bin/gost
```