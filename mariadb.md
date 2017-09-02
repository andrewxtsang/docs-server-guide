Add official source
```bash
sudo apt-get install software-properties-common
sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8sudo 
sudo add-apt-repository 'deb [arch=amd64,i386,ppc64el]http://nyc2.mirrors.digitalocean.com/mariadb/repo/10.2/ubuntuxenial main'
```

Install MariaDB 10.2
```bash
sudo apt-get update
sudo apt-get install mariadb-server mariadb-client
sudo systemctl enable mysql
sudo mysql_secure_installation
```

