# nginx-behind-jenkins
NGINX config for Jenkins, to use as reverse-proxy

Refer: https://wiki.jenkins.io/display/JENKINS/Running+Jenkins+behind+Nginx

## Instructions

* Install NGINX
* Use jenkins conf (conf.d/jenkins.conf) at (/etc/nginx/conf.d/)
* optional - Usage with SSL (conf.d/jenkins-ssl.conf)

## Instructions (Jenkins)

* Configure security options (CSRF Protection > Crumb Algorithm), set "Enable Proxy Compatibility"

```
http://<JENKINS_HOST>/configureSecurity
```

## Aditional

How to generate self-signed SSL ?

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout server.key -out server.crt
```

How to import SSL to JVM trusted store (Jenkins REST API with SSL)?

```
keytool -import -trustcacerts -alias jenkins -file /etc/ssl/certs/jenkins/server.crt -keystore /usr/lib/jvm/<JAVA_VERSION>/jre/lib/security/cacerts
```
