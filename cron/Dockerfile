FROM alpine:3.14

LABEL org.opencontainers.image.authors="ahmetcan.com.tr"

RUN apk update && \
    apk add rust cargo && \
    apk add --no-cache docker-cli python3 && \
    apk add --no-cache --virtual .docker-compose-deps python3-dev libffi-dev openssl-dev gcc libc-dev make && \
    apk add py3-pip

RUN pip3 install docker-compose && \
    apk del .docker-compose-deps


COPY renew_certs.sh /etc/periodic/daily/renew_certs

RUN chmod +x /etc/periodic/daily/renew_certs

WORKDIR /workdir

CMD ["crond", "-f", "-l", "0"]
