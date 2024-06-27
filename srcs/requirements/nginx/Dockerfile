FROM debian:bullseye

RUN apt-get update \
    && apt-get install -y nginx openssl \
    && apt-get clean 
    # && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /etc/nginx/ssl \
    && openssl req \
        -x509 \
        -newkey rsa:2048 \
        -nodes \ 
        -keyout /etc/nginx/ssl/private_key \
        -out /etc/nginx/ssl/certificate.crt \
        -subj "/C=FR/ST=IDF/L=Paris/O=42/OU=42/CN=yasaidi.42.fr/UID=yasaidi"
    
COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/yasaidi.42.fr.conf /etc/nginx/sites-available/
RUN ln -s /etc/nginx/sites-available/yasaidi.42.fr.conf /etc/nginx/sites-enabled/    

EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]
