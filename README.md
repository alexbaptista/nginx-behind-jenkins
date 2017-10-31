# nginx-behind-jenkins
NGINX config for Jenkins


Generate self-signed SSL

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout server.key -out server.crt
