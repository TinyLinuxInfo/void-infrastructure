FROM  ghcr.io/void-linux/void-linux:latest-full-x86_64

RUN xbps-install -Suy xbps && xbps-install -Sy nginx tini

WORKDIR /srv/www
COPY nginx.conf /etc/nginx/nginx.conf
COPY ssl.conf /etc/nginx/fragments/ssl.conf
COPY dhparam.pem /etc/nginx/dhparam.pem
ENTRYPOINT ["/usr/bin/tini", "--", "nginx", "-g daemon off;"]
