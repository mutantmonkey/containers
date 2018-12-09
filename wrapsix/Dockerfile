FROM debian:stretch
LABEL maintainer "mutantmonkey <docker@mutantmonkey.mx>"

ENV WRAPSIX_VERSION 0.2.1

RUN set -x \
    && apt-get update \
    && apt-get -y install build-essential curl linux-headers-amd64 \
    && cd /tmp \
	&& curl -sSL "https://www.wrapsix.org/download/wrapsix-${WRAPSIX_VERSION}.tar.bz2" -o wrapsix.tar.bz2 \
	&& tar -xvf wrapsix.tar.bz2 \
	&& cd "wrapsix-${WRAPSIX_VERSION}" \
    && ./configure --prefix=/usr --sysconfdir=/etc --sbindir=/usr/bin \
	&& make \
	&& make install \
	&& apt-get -y remove build-essential curl linux-headers \
	&& apt-get -y autoremove \
	&& rm -rf /tmp/* /var/cache/apt/lists/*

ENTRYPOINT ["wrapsix"]
