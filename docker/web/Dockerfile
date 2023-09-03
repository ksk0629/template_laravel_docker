FROM nginx:1.20-alpine

ENV TZ Europe/London

RUN chmod 755 -R /root

COPY ./docker/web/default.conf /etc/nginx/conf.d/default.conf