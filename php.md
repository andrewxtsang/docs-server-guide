Add PHP71 source
```bash
sudo add-apt-repository ppa:ondrej/php
```

Install PHP71
```bash
sudo apt-get update
sudo apt-get install php7.1-fpm php7.1-mysql php7.1-mbstring php7.1-common php7.1-xml php7.1-gd php7.1-curl php7.1-cli php7.1-zip php7.1-mcrypt php7.1-sqlite
```

Edit PHP Conf
```bash
sudo vi /etc/php/7.1/fpm/php.ini
cgi.fix_pathinfo = 0 (1)
allow_url_include = Off
expose_php = Off
display_errors = Off
log_errors = On
session.cookie_httponly = 1
session.use_only_cookies = 1
session.cookie_secure = 1   #for ssl
```

Restart Services
```bash
sudo systemctl restart php7.1-fpm
```
