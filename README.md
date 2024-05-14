# Self-Signes cert with Nginx server

Want to learn more about ssl encryption and how to share a 
root certificate. Will eventually try implementing Lets Encrypt and create 
automated certificate renewal.

# Notes
## About self-signed certificate
 - Communication between Server and client will be encrypted
 - Since self-cert is not signed by trusted certificates authorities, users cannot automatically validate identity of server
 - Ideal if your domain is not in the www (your site is accessible from internet)

## Creating the SSL certificate
 - TLS/SSL works by having a public certificate and a private key
    >



# Links
[Will be following along this Digital Ocean article](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-20-04-1)
[Interesting - Setting up LEMP ((Linux, Nginx, MySQL, PHP) on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04)

