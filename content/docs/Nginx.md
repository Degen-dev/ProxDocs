---
title: "Nginx"
date: 2022-08-31T18:28:11Z
draft: false
---

Nginx is a common tool used for load balancing as well as reverse-proxying. We will be using Nginx to pass your instance to your domains as well as to add SSL to your site.

Assuming you are running a Linux system based off of Debian, run the following command to install nginx:
```sh
$ sudo apt install nginx
```

After you have Nginx installed, configure it in `/etc/nginx/nginx.conf`. The configuration I would recommend can be found below:
```nginx
user root; # change this to be the user you are hosting your instance on
worker_processes auto;
pid /run/nginx.pid;
include /etc/nginx/modules-enabled/*.conf;

events {
        worker_connections 1024;
}

http {
    include /etc/nginx/mime.types;
    default_type application/octet-stream;
    map_hash_bucket_size 128;

    sendfile on;
    tcp_nopush on;

    tcp_nodelay on;

    reset_timedout_connection on;

    access_log off;
    error_log off;
    
    server {
        listen 80 default_server;
        listen [::]:80 default_server;
        server_name your.domain.com; # replace with your actual domain

        location / { 
                # Upgrade WebSockets
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'Upgrade';
                # Increase header buffer
                proxy_connect_timeout 10; 
                proxy_send_timeout 90; 
                proxy_read_timeout 90; 
                proxy_buffer_size 128k;
                proxy_buffers 4 256k;
                proxy_busy_buffers_size 256k;
                proxy_temp_file_write_size 256k;
                proxy_pass http://127.0.0.1:8080; # change this to the port UltraViolet is listening on

            # The small block below will block googlebot
            if ($http_user_agent ~ (Googlebot)) {
                return 403;
            }
        }
    }
}
```

## Authors
- [Degen-dev (Degenerate)](https://github.com/Degen-dev)
- [EnderKingJ](https://github.com/EnderKingJ)