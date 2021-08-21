FROM nginx:1.17-alpine

LABEL org.opencontainers.image.authors="ahmetcan.com.tr"

RUN apk add --no-cache openssl

COPY default.conf /etc/nginx/conf.d/
ADD domains /etc/nginx/domains
COPY options-ssl-nginx.conf /etc/nginx/
COPY hsts.conf /etc/nginx/
COPY nginx.sh /customization/

RUN chmod +x /customization/nginx.sh

EXPOSE 80

CMD ["/customization/nginx.sh"]