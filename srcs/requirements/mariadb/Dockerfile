
FROM debian:bullseye

RUN apt-get update \
    && apt-get install -y mariadb-server mariadb-client \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY ./conf/mariadbconfig.cnf /etc/mysql/mariadb.conf.d/mariadbconfig.cnf

# Expose le port 3306 utilisé par MariaDB pour les connexions
EXPOSE 3306

# Démarre le serveur MariaDB au démarrage du conteneur
CMD ["mysqld"]