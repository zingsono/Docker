FROM php:7.4.3-fpm-alpine3.11
RUN apk update && apk add git nginx curl tzdata && cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo "Asia/Shanghai" > /etc/timezone && apk del tzdata
# /var/www/html/

COPY tz.php ./
COPY nginx.conf /etc/nginx/nginx.conf
COPY entrypoint.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]

# docker run --name phptest -p 9009:80 -itd registry.cn-hangzhou.aliyuncs.com/mszs/php:7.4-fpm-nginx-alpine
