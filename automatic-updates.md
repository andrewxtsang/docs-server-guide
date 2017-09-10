Automatic Updates
```bash
sudo apt-get install unattended-upgrades apticron
sudo dpkg-reconfigure unattended-upgrades
sudo vi /etc/apt/apt.conf.d/50unattended-upgrades
```

```
Unattended-Upgrade::Allowed-Origins {
        "${distro_id}:${distro_codename}";
        "${distro_id}:${distro_codename}-security";
//      "${distro_id}:${distro_codename}-updates";
//      "${distro_id}:${distro_codename}-proposed";
//      "${distro_id}:${distro_codename}-backports";
};
Unattended-Upgrade::Mail "user@example.com";
Unattended-Upgrade::Remove-Unused-Dependencies "true";
Unattended-Upgrade::Automatic-Reboot "true";
Unattended-Upgrade::Automatic-Reboot-Time "02:00";
```

Enable
```bash
sudo vi /etc/apt/apt.conf.d/20auto-upgrades
```
```
APT::Periodic::Update-Package-Lists "7";
APT::Periodic::Unattended-Upgrade "1";
APT::Periodic::Download-Upgradeable-Packages "1";
APT::Periodic::AutocleanInterval "7";
```

Change Notification Email
```bash
vi /etc/apticron/apticron.conf
EMAIL="root@example.com"
```

Reference
- https://help.ubuntu.com/16.04/serverguide/automatic-updates.html
- https://www.hiroom2.com/2016/05/18/ubuntu-16-04-auto-apt-update-and-apt-upgrade/