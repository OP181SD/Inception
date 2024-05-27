FROM debian:bullseye

RUN apt-get update && \
    apt-get install -y mariadb-server mariadb-client mariadb-common

# Exposer le port par défaut de MariaDB
EXPOSE 3306

# Commande par défaut pour démarrer MariaDB au lancement du conteneur
CMD ["mysqld"]