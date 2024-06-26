FROM debian:bullseye

RUN apt-get update -y \
    && apt-get upgrade -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get install -y nginx openssl

COPY ./conf/nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /etc/nginx/ssl \
    && openssl req \
        -x509 \
        -newkey rsa:2048 \
        -nodes \ 
        -keyout /etc/nginx/ssl/private.key \
        -out /etc/nginx/ssl/certificate.crt \
        -subj "/C=FR/ST=IDF/L=Paris/O=42/OU=42/CN=yasaidi.42.fr/UID=yasaidi"

CMD ["nginx", "-g", "daemon off;"]

EXPOSE 443
