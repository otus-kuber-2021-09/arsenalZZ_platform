FROM nginx:latest

WORKDIR /app

COPY homework.html .
COPY default.conf /etc/nginx/conf.d/default.conf

RUN set -x \
  && groupadd --gid 1001 web \
  && useradd --uid 1001 --gid web web \
  && chown -R  web:web /var/cache/nginx \
  && touch /var/run/nginx.pid \
  && chown -R web:web /var/run/nginx.pid

USER 1001
EXPOSE 8000
