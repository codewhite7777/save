FROM	debian:buster

RUN		apt-get update -y
RUN		apt-get upgrade -y
RUN		apt-get install -y wget
RUN		apt-get install -y php7.3 php-fpm php-mysql mariadb-client
RUN		wget https://ko.wordpress.org/wordpress-6.1.1-ko_KR.tar.gz -P /var/www
RUN		cd /var/www && tar -xzf wordpress-6.1.1-ko_KR.tar.gz && rm wordpress-6.1.1-ko_KR.tar.gz
RUN		chown -R root:root /var/www/wordpress
RUN		wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN		chmod +x wp-cli.phar
RUN		mv wp-cli.phar /usr/local/bin/wp

COPY	conf/www.conf	/etc/php/7.3/fpm/pool.d/www.conf
COPY	tools/config.sh	/config.sh

EXPOSE	9000

ENTRYPOINT	["bash", "config.sh"]
