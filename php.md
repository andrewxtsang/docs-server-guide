Add PHP73 source
```bash
sudo add-apt-repository ppa:ondrej/php
```

Install PHP73
```bash
sudo apt-get update
sudo apt-get install php7.3 php7.3-cli php7.3-common php7.3-curl php7.3-fpm php7.3-gd php7.3-json php7.3-mbstring php7.3-mysql php7.7-readline php7.3-xml php7.3-zip
```

Edit PHP Conf
```bash
sudo vi /etc/php/7.3/fpm/php.ini
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
sudo systemctl restart php7.3-fpm
```
