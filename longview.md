Prepare nginx for longview
```bash
sudo vi /etc/nginx/conf.d/nginx_status.conf
```
```
server {
    listen 127.0.0.1:80;
    server_name 127.0.0.1;
    location /nginx_status {
        stub_status on;
        allow 127.0.0.1;
        deny all;
    }
}
```
```bash
sudo service nginx restart
```

Install Longview
```bash
sudo curl -s https://lv.linode.com/XXX | sudo bash
```

Allow firewall
```bash
sudo ufw allow from 96.126.119.66
```

Check Longview for Nginx conf
```bash
sudo vi /etc/linode/longview.d/Nginx.conf
location http://127.0.0.1/nginx_status
```

Install Longview for MySQL
```bash
mysql
CREATE USER 'linode-longview'@'localhost' IDENTIFIED BY '***************';
flush privileges;
```

Edit Longview for MySQL
```bash
username linode-longview 
password ***************
```

Useful command
```bash
dpkg-reconfigure -phigh linode-longview
service longview status
service longview start
/etc/init.d/longview debug
```

Reference
- https://www.linode.com/docs/platform/longview/longview
- https://www.linode.com/docs/platform/longview/longview-app-for-nginx
- https://www.linode.com/docs/platform/longview/longview-app-for-mysql
