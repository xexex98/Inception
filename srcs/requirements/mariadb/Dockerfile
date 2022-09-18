FROM alpine:3.15

RUN apk update && apk upgrade

RUN apk add mysql mysql-client \
	&& rm -rf /var/cache/apk/*
	
RUN	sed -i "7i user=mysql\ndatadir=/var/lib/mysql/" /etc/my.cnf.d/mariadb-server.cnf && \
	mariadb-install-db --user=mysql --datadir=/var/lib/mysql --auth-root-authentication-method=normal && \
	mkdir -p /run/mysqld && \
	chown -R mysql:mysql /run/mysqld

RUN mkdir -p /run/mysqld

RUN	mkdir -p /var/lib/mysql

COPY ./conf/my.cnf /etc/mysql/

EXPOSE 3306
