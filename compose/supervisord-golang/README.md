https://github.com/ochinchina/supervisord

https://hub.docker.com/r/ochinchina/supervisord

### Ws tunnel
https://github.com/erebe/wstunnel/releases/download/v5.0/wstunnel-linux-x64


### Dockerfile
```
FROM debian:11
COPY --from=ochinchina/supervisord:latest /usr/local/bin/supervisord /usr/local/bin/supervisord
CMD ["/usr/local/bin/supervisord","-c","/supervisord.conf", -d]
```


### conf
```
[program:wstunnel entet] 接收wss流量
command = /usr/local/bin/wstunnel -v --server wss://0.0.0.0:51031 -r 127.0.0.1:51030
[program:wstunnel goto 01] 将wss发送给 host1
command = /usr/local/bin/wstunnel -v --udp -L 127.0.0.1:51032:127.0.0.1:51030  wss://host_ip:51031
[program:wstunnel goto 02] 将wss发送给 host2
command = /usr/local/bin/wstunnel -v --udp -L 127.0.0.1:51033:127.0.0.1:51030  wss://host_ip:51031
```