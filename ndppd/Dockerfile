FROM debian:sid
LABEL maintainer "mutantmonkey <containers@mutantmonkey.mx>"

RUN apt-get update && apt-get install -y ndppd && rm -rf /var/lib/apt/lists/*

VOLUME ["/etc/ndppd"]

ENTRYPOINT ["ndppd"]
CMD ["-c", "/etc/ndppd/ndppd.conf"]
