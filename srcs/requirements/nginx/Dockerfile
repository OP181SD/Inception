# Utiliser l'image Debian Bullseye comme base
FROM debian:bullseye

# Met à jour la liste des paquets disponibles et met à jour les paquets déjà installés
RUN apt-get update -y && \
    apt-get upgrade -y

RUN apt-get install -y nginx

RUN apt-get install -y openssl

# Création du répertoire SSL avec l'option -p pour créer récursivement les répertoires si nécessaire
RUN mkdir -p /etc/nginx/ssl

# Copie du fichier de configuration NGINX
COPY ./conf/nginx.conf /etc/nginx/nginx.conf

# Génération du certificat SSL auto-signé
RUN openssl req \
    -x509  # Crée un certificat auto-signé \
    -nodes  # Ne chiffre pas la clé privée Spécifie le fichier de sortie pour la clé privée \
    -keyout /etc/nginx/ssl/nginx-unsecured.key # Spécifie le fichier de sortie pour le certificat auto-signé \rmat \
    -out /etc/nginx/ssl/nginx-selfsigned.crt -subj "/C=FR/ST=IDF/L=Paris/O=42/OU=42/CN=yasaidi.42.fr" # Définit les infoions du certificat (DN) \ 
# Exécuter NGINX en premier plan pour que Docker puisse le gérer correctement
CMD ["nginx", "-g", "daemon off;"]

# Exposition du port 443 pour HTTPS
EXPOSE 443