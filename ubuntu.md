Login & Change root password
```bash
ssh root@IP_ADDRESS
passwd
```

Installing Software Updates
```bash
apt-get update && apt-get upgrade
```

Setting the Hostname
```bash
hostnamectl set-hostname HOSTNAME
hostname
```
choose [3 vim.basic]
```
select-editor
```
Update /etc/hosts
```bash
vi /etc/hosts
IPv4 HOSTNAME
IPv6 HOSTNAME
```

Setting the Timezone
```bash
dpkg-reconfigure tzdata
date
```

Add a User Account
```bash
adduser USERNAME
adduser USERNAME sudo
```

Create a SSH folder for USERNAME
```bash
su USERNAME
mkdir ~/.ssh && chmod 700 ~/.ssh
touch ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys
```

Upload SSH key via **Local MAC**
```bash
ssh-keygen -b 4096
scp ~/.ssh/id_rsa.pub USERNAME@IP_ADDRESS:~/.ssh/authorized_keys
```

Configure SSH Daemon
```bash
vi /etc/ssh/sshd_config
PermitRootLogin no (yes)
Port 12345 (22)
AddressFamily inet  #IPv4 only
```

Restart ssh
```bash
sudo systemctl restart ssh
```
