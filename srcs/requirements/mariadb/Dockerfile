
FROM debian:bullseye

RUN apt-get update \
    && apt-get install -y mariadb-server mariadb-client \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY ./conf/50-server.cnf /etc/mysql/mariadb.conf.d/

EXPOSE 3306

CMD ["mysqld"]
