Install ngxtop
```bash
sudo apt-get install python-pip
pip install ngxtop
```

Check log
```bash
ngxtop --no-follow -l /var/log/nginx/access.log
ngxtop --no-follow -l /var/log/nginx/access.log -i 'status >= 400'
```

Useful command
```bash
pip -V
pip show ngxtop
```

Reference
- https://github.com/lebinh/ngxtop
- http://hatemegalaxy.blogspot.hk/2015/12/nginx-1-ngxtop-how-to-install-and-use.html
- http://xmodulo.com/monitor-nginx-web-server-command-line-real-time.html