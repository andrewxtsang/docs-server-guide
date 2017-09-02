Install UFW
```bash
sudo apt-get install ufw
```

Set default rules
```bash
sudo ufw default allow outgoing
sudo ufw default deny incoming
```

Add rules
```bash
sudo ufw allow SSH_PORT
sudo ufw allow 80/tcp
sudo ufw allow https/tcp
```

Enable firewall
```bash
sudo ufw enable
```

Useful command
```bash
sudo ufw status
```