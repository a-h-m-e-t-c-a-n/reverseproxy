FROM certbot/certbot:v1.18.0

LABEL org.opencontainers.image.authors="ahmetcan.com.tr"

RUN apk add --no-cache bash

COPY certbot.sh /opt/

RUN chmod +x /opt/certbot.sh

ENTRYPOINT ["/opt/certbot.sh"]