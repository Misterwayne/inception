FROM debian:buster

RUN 	apt update -y
RUN	apt upgrade -y
RUN	apt install nginx -y 
RUN	apt install vim -y 
RUN	apt install curl -y 
	

RUN	mkdir -p /etc/nginx/ssl

RUN 	apt install openssl -y

RUN	openssl req -x509 -nodes -out /etc/nginx/inception.crt -keyout /etc/nginx/ssl/inception.key -subj "/C=FR/ST=IDF/L=Paris/O=42/UO=42/CN=mwane.42.fr/UID=mwane"

RUN	mkdir -p /var/run/nginx

COPY	conf/nginx.conf /etc/nginx/nginx.conf

RUN	chmod 755 /var/www/html

RUN	chown -R www-data:www-data /var/www/html

CMD	nginx -g daemon off

