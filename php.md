Add PHP73 source
```bash
sudo add-apt-repository ppa:ondrej/php
```

Install PHP73
```bash
sudo apt-get update
sudo apt-get install php7.3 php7.3-cli php7.3-common php7.3-curl php7.3-fpm php7.3-gd php7.3-json php7.3-mbstring php7.3-mysql php7.3-readline php7.3-xml php7.3-zip php7.3-sqlite php7.3-bcmath
```

Edit PHP config
```bash
sudo vi /etc/php/7.3/fpm/php.ini
```

```bash
cgi.fix_pathinfo = 0    # default 1
allow_url_include = Off
expose_php = Off
display_errors = Off
log_errors = On
session.cookie_httponly = 1    # default empty
session.use_only_cookies = 1   # default empty
session.cookie_secure = 1      # for ssl
```

(optional)
```bash
memory_limit = 256M            # default 128M
```

Restart Services
```bash
sudo systemctl restart php7.3-fpm
```
