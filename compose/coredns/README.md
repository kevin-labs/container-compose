# CoreDNS 

coredns
https://coredns.io/


### 创建配置文件 Corefile 
```
.:53 {
    forward . 8.8.8.8 9.9.9.9
    log
    errors
}
```
### 测试

```
docker run -it --rm \
--name coredns \
-v ~/docker-app/coredns/coredns:/root \
-p 192.168.20.1:53:53/udp \
coredns/coredns -conf /root/Corefile
```

### 生产

```
docker run -d \
--name coredns \
--restart=always \
-v ~/docker-app/coredns/coredns:/root \
-p 192.168.20.1:53:53/udp \
coredns/coredns -conf /root/Corefile
```

## 参考

https://github.com/burkeazbill/docker-coredns

https://dev.to/robbmanes/running-coredns-as-a-dns-server-in-a-container-1d0
https://ragingtiger.github.io/
