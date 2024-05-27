FROM debian:bullseye

RUN apt-get update && \
    apt-get install -y mariadb-server mariadb-client mariadb-common

EXPOSE 3306

CMD ["mysqld"]
