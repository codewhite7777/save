FROM	debian:buster

RUN		apt-get update -y
RUN		apt-get upgrade -y
RUN		apt-get install -y nginx
RUN		mkdir -p /etc/nginx/ssl
RUN		apt-get install -y openssl
RUN		openssl req -x509 -nodes \
		-out /etc/nginx/ssl/alee.crt \
		-keyout /etc/nginx/ssl/alee.key \
		-subj "/C=KR/ST=Seoul/L=Gangnam/O=42/OU=42/CN=alee.42.fr/UID=alee"

COPY	conf/nginx.conf	/etc/nginx/nginx.conf

CMD		["nginx", "-g", "daemon off;"]
