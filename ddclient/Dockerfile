FROM alpine:3.4
MAINTAINER Karl Bowden <karl@bearded.sexy>

ENV DDCLIENT_VERSION=3.8.3

RUN apk update && \
    apk add \
        ca-certificates \
        wget \
        perl \
        perl-json \
        perl-io-socket-ssl \
        tar && \
    rm -rf /var/cache/apk/* && \
    update-ca-certificates && \
    wget http://sourceforge.net/projects/ddclient/files/ddclient/ddclient-$DDCLIENT_VERSION/ddclient-$DDCLIENT_VERSION.tar.bz2 && \
    tar -xvf /ddclient-3.8.3.tar.bz2 ddclient-3.8.3/ddclient --strip-components 1 && \
    wget -O /usr/share/perl5/vendor_perl/JSON/Any.pm https://github.com/karenetheridge/JSON-Any/raw/master/lib/JSON/Any.pm && \
    mkdir -p /var/cache/ddclient/

VOLUME ["/config"]

CMD ["/ddclient", "-foreground", "-file", "/config/ddclient.conf"]
