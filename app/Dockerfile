FROM alpine:3.24.3

RUN apk add --no-cache nginx curl bind-tools nano \
    && mkdir -p /run/nginx \
    && printf '%s\n' \
        'server {' \
        '    listen 80;' \
        '    server_name _;' \
        '    root /var/www/html;' \
        '    index index.html;' \
        '}' > /etc/nginx/http.d/default.conf

COPY index.html /var/www/html/index.html

EXPOSE 80

USER nginx

HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
    CMD curl --fail --silent --show-error http://127.0.0.1/ > /dev/null || exit 1

CMD ["nginx", "-g", "daemon off;"]