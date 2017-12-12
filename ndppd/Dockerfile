FROM debian:sid
LABEL maintainer "mutantmonkey <containers@mutantmonkey.mx>"

RUN apt-get update && apt-get install -y ndppd && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["ndppd"]
