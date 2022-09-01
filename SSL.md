# SSL/TLS
This will require that you have followed the ProxDocs guide to install and use [Nginx](https://github.com/Degen-dev/ProxDocs/blob/master/Nginx.md).

SSL will allow users to access your instance in a secure manner. Using Nginx and Certbot will allow you to generate and use SSL certificates for free. To install Certbot, run the following command:
```sh
$ sudo apt install certbot
```
After installing Certbot run the following command to add SSL to your site:
```sh
$ certbot --nginx -d your.domain.com
```
Don't forget to replace `your.domain.com` with your actual domain.

## Authors
- [Degen-dev (Degenerate)](https://github.com/Degen-dev)
- [EnderKingJ](https://github.com/EnderKingJ)
