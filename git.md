Install Git
```bash
sudo apt-get install git
```

Optional Setting
```bash
git config --global user.name "NAME"
git config --global user.email "EMAIL"
git config --list
```

Setup www-data SSH Key
```bash
sudo -u www-data ssh-keygen
sudo cat /var/www/.ssh/id_rsa.pub
```

 Reference
 - http://https://git-scm.com/book/en/v2/Getting-Started-Installing-Git