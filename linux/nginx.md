```
server {
        listen 80;
        listen [::]:80;
        server_name timofeevsk.ga;
        return 302 https://www.timofeevsk.ga$request_uri;
}

server {
        listen 443 ssl;
        listen [::]:443 ssl;
        server_name timofeevsk.ga;
        return 302 https://www.timofeevsk.ga$request_uri;
        ssl_certificate     /path;
        ssl_certificate_key /path;

}

server {
        listen 80;
        listen [::]:80;
        server_name www.timofeevsk.ga;
        return 302 https://$server_name$request_uri;
}

server {
        listen 443 ssl;
        listen [::]:443 ssl;
        server_name www.timofeevsk.ga;
        ssl_certificate     /path
        ssl_certificate_key /path
        ssl_protocols       TLSv1 TLSv1.1 TLSv1.2;
        location / {
                    proxy_pass http://127.0.0.1:81;
        }
}
server {
        listen 80;
        listen [::]:80;
        server_name speedtest.neighboranatoli.ga;
        return 302 https://$server_name$request_uri;

}

server {
        listen 443 ssl;
        listen [::]:443 ssl;
        server_name speedtest.neighboranatoli.ga;
        ssl_certificate /path;
        ssl_certificate_key /path;
        ssl_protocols       TLSv1 TLSv1.1 TLSv1.2;
        location / {
                    proxy_pass http://127.0.0.1:3000;
        }
}

```