
```
cd /etc/nginx/sites-available
sudo rm -rf default
sudo echo "
server {
    listen 80;
    server_name _;
    location / {
        proxy_pass http://192.168.10.100:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
"
```
