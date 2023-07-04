FROM debian:11

COPY spark/ /

RUN chmod +x /spark && chmod +x /built

CMD ["/spark","-config","/config.json"]