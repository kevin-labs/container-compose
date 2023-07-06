FROM debian:11

COPY --from=ochinchina/supervisord:latest /usr/local/bin/supervisord /usr/local/bin/supervisord

# 复制二进制
COPY bin/ /usr/local/bin/wstunnel
RUN chmod +x /usr/local/bin/wstunnel

# 运行配置
CMD ["/usr/local/bin/supervisord","-c","/supervisord.conf", "-d"]