Install Fail2ban
```bash
sudo apt-get install fail2ban
```

Configure Fail2ban
```bash
sudo cp /etc/fail2ban/fail2ban.conf /etc/fail2ban/fail2ban.local
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
```

Useful command
```bash
systemctl enable fail2ban
systemctl restart fail2ban
fail2ban-client status
```

Manually UnBan IP Banned by Fail2Ban
```
sudo fail2ban-client set ssh-iptables unbanip IP_ADDRESS
```

Reference
- https://www.linode.com/docs/security/using-fail2ban-for-security
- https://gist.github.com/Telling/7fd4bc5ee4caaff88f4b
- [Adding Cloudflare support to fail2ban](http://www.normyee.net/blog/2012/02/02/adding-cloudflare-support-to-fail2ban)

