
Install ngxtop
```bash
echo "deb http://deb.goaccess.io/ $(lsb_release -cs) main" | sudo tee -a /etc/apt/sources.list.d/goaccess.list
wget -O - http://deb.goaccess.io/gnugpg.key | sudo apt-key add -
sudo apt-get update
sudo apt-get install goaccess
sudo apt-get install geoip-database
```

Setup config
```bash
vi /etc/goaccess.conf
```
```
time-format %H:%M:%S
date-format %d/%b/%Y
log-format %h %^[%d:%t %^] "%r" %s %b "%R" "%u"
```

Check log
```bash
goaccess -f /var/log/nginx/access.log
cat access.log.* | goaccess
zcat -f /var/log/nginx/access.log* | goaccess
```

Reference
- https://goaccess.io/
- https://blog.gtwang.org/linux/analysing-nginx-logs-using-goaccess/
