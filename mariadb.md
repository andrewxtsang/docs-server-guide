Add official source
```bash
sudo apt-get install software-properties-common
sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
sudo vi /etc/apt/sources.list.d/mariadb.list
deb [arch=amd64,i386] http://mirror.jmu.edu/pub/mariadb/repo/10.2/ubuntu xenial main
deb-src http://mirror.jmu.edu/pub/mariadb/repo/10.2/ubuntu xenial main
```

Install MariaDB 10.2
```bash
sudo apt-get update
sudo apt-get install mariadb-server mariadb-client
sudo systemctl enable mysql
sudo mysql_secure_installation
```

Edit config
```bash
sudo vi /etc/mysql/my.cnf

general_log_file        = /var/log/mysql/mysql.log
general_log             = 1
log_error               = /var/log/mysql/error.log
log_warnings            = 2
slow_query_log          = 1
slow_query_log_file     = /var/log/mysql/slow.log
long_query_time         = 3
```

Useful Command
```bash
sudo systemctl stop mysql
sudo systemctl start mysql
sudo systemctl status mysql
sudo systemctl restart mysql
```
