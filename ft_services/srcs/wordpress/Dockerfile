FROM alpine:3.12.0
#FROM alpine:latest

RUN apk update \
		&& apk --update --no-cache add nginx \
				php7 php7-fpm php7-mbstring php7-session \
				php7-common php7-iconv php7-json php7-gd php7-curl php7-xml \
				php7-mysqli php7-imap php7-cgi fcgi php7-pdo php7-pdo_mysql \
				php7-soap php7-xmlrpc php7-posix php7-mcrypt php7-gettext php7-ldap \
				php7-ctype php7-dom mysql-client

RUN wget https://wordpress.org/latest.tar.gz
RUN tar -xvf latest.tar.gz && \
	rm -f latest.tar.gz && \
	mv wordpress /etc/
COPY wp-config.php /etc/wordpress/
COPY default.conf /etc/nginx/conf.d/

EXPOSE 5050

COPY setup.sh /usr/sbin/setup.sh

RUN chmod +x /usr/sbin/setup.sh && \
	mkdir -p /run/nginx

COPY wordpress.sql /run/nginx/wordpress.sql

CMD /bin/sh "/usr/sbin/setup.sh" && php-fpm7 \
		&& nginx -g "daemon off;"
