Add official source file
```bash
sudo wget http://nginx.org/keys/nginx_signing.key
sudo apt-key add nginx_signing.key
sudo vi /etc/apt/sources.list.d/nginx.list
deb [arch=amd64] http://nginx.org/packages/mainline/ubuntu/ bionic nginx
```

Install NGINX 1.17
```bash
sudo apt-get update
sudo apt-get install nginx
sudo systemctl enable nginx
```

Change folder owner
```bash
mkdir /var/www
sudo chown -R www-data:www-data /var/www
```

Edit NGINX Conf
```bash
sudo vi /etc/nginx/nginx.conf
worker_processes 1; (auto) #for low traffic
events {
  worker_connections 65536;
  use epoll;
  multi_accept on;
}
http {
  server_tokens off;
  sendfile on;
  tcp_nopush on;
  tcp_nodelay on;
}
```

Restart Service
```bash
sudo systemctl restart nginx
```

Set Authentication
```bash
openssl passwd
sudo vi /etc/nginx/auth
LOGIN:PASSWORD
```

Useful Command
```bash
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
nginx -t
```

Reference
- https://www.linode.com/docs/web-servers/nginx/configure-nginx-for-optimized-performance
- https://www.linode.com/docs/web-servers/nginx/nginx-ssl-and-tls-deployment-best-practices
- https://blog.serverdensity.com/troubleshoot-nginx/
- https://www.nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls/
