FROM alpine
RUN apk add darkhttpd
ONBUILD ARG DIR=./build/
ONBUILD COPY $DIR /var/www/localhost/htdocs
ONBUILD EXPOSE 80
ONBUILD CMD ["darkhttpd", "/var/www/localhost/htdocs"]
