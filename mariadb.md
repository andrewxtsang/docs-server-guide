Add official source
```bash
sudo apt-get install software-properties-common
sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
sudo add-apt-repository "deb [arch=amd64,arm64,ppc64el] http://mariadb.mirror.liquidtelecom.com/repo/10.4/ubuntu $(lsb_release -cs) main"
```

Install MariaDB 10.4
```bash
sudo apt-get update
sudo apt-get install mariadb-server mariadb-client
sudo systemctl enable mariadb.service
sudo mysql_secure_installation
```

Edit config

```bash
sudo vi /etc/mysql/my.cnf
```

```bash
log_error               = /var/log/mysql/error.log
log_warnings            = 2
slow_query_log          = 1
slow_query_log_file     = /var/log/mysql/slow.log
long_query_time         = 3
```

```bash
bind-address = 0.0.0.0
wait_timeout = 60
max_allowed_packet = 32M
```

Create user

```mysql
CREATE USER 'USERNAME'@'localhost' IDENTIFIED BY 'PASSWORD';
GRANT ALL PRIVILEGES ON *.* TO 'USERNAME'@'localhost' WITH GRANT OPTION;
```

Useful Command

```bash
sudo systemctl stop mysql
sudo systemctl start mysql
sudo systemctl status mysql
sudo systemctl restart mysql
```
