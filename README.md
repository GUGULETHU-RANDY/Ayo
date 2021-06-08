# Ayo
Ayo Assignment

To download all packages and dependencies: run

RUN mvn -B dependency:resolve dependency:resolve-plugins
## downloads all dependencies required either the application or by plugins called during a build process.

To start dev env run:

docker-compose up -d
To stop run:

docker-compose down
Setup /etc/hosts
Edit you /etc/hosts file in your machine like this:

127.0.0.1 roshambo.com
Self Signed local certificate
To generate a local cert we use mkcert. Follow these steps to generate your local dev cert

mkcert "roshambo.com"
// Now we need to install the CA from mkcert in our machine/browser
mkcert --install
Copy generated certs .pem files to nginx/certs

Note that if later you want another subdomain you will have to generate a new certificate with that new subdomain. This certificate is only valid for:

roshambo.com
```
$cd jenkins
$docker-compose up -d
```

# Running Jenkins over PWD Platform

Ensure that you provide sufficient permission while trying this on PWD Platform

```
$chmod 666 /var/run/docker.sock

 visit the URL to get response:
 http://localhost:8080/roshambo or https for port 8443

