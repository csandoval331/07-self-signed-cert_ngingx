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
 - ```bash
    $ sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt
    * req - specifies that we want to use X.509 certificate signing request (CSR)

    **openssl output**
    Country Name (2 letter code) [AU]:US
    State or Province Name (full name) [Some-State]:Illinois
    Locality Name (eg, city) []:Chicago
    Organization Name (eg, company) [Internet Widgits Pty Ltd]:
    Organizational Unit Name (eg, section) []:
    Common Name (e.g. server FQDN or YOUR name) []:10.0.1.3
    Email Address []:charlysandoval331@gmail.com
   ```
 - ```bash
    $ sudo openssl dhparam -out /etc/nginx/dhparam.pem 4096
    - will take a while to generate 769 Byte file
    - file has less than 1000 characters
    - why did it take so long to generate this file?
   ```


# Notes - [setting up server blocks - step 5](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04#step-5-%E2%80%93-setting-up-server-blocks-recommended)
- easily manage multiple websites using symbolic links to add sites to "nginx sites-enabled" directory
- remove sites by removing symbolic link
```bash
$ sudo mkdir -p /var/www/your-domain/html
 * -p helps create necessary parent dir

$ echo "your_domain" >> /etc/hosts
 * I was able to create domain name "your_domain" by adding  it to hosts file
```



# Links
- [Will be following along this Digital Ocean article](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-20-04-1)
- [Cipherlist.eu is a useful resource for understanding encryption settings](https://cipherlist.eu/)
- [ read up on HTTP Strict Transport Security, specifically about “preload” functionality.](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
- [Interesting - Setting up LEMP ((Linux, Nginx, MySQL, PHP) on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04)

