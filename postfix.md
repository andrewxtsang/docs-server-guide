Install Postfix
```bash
sudo apt-get install postfix mailutils
Internet Site
[default]
```

Add Gmail Username and Password
```bash
sudo vi /etc/postfix/sasl_passwd
[smtp.gmail.com]:587 username@gmail.com:password
```

Secure
```bash
sudo chmod 600 /etc/postfix/sasl_passwd
sudo postmap /etc/postfix/sasl_passwd
```

Configure the Postfix Relay Server
```bash
sudo vi /etc/postfix/main.cf
relayhost = [smtp.gmail.com]:587
smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_tls_security_level = encrypt
smtp_tls_CAfile = /etc/ssl/certs/ca-certificates.crt
```
Restart Postfix
```bash
sudo systemctl enable postfix
sudo systemctl restart postfix
```

Test Postfix
```bash
mail -s "Test mail" example@gmail.com <<< "A test message"
```

Reference
- https://www.linode.com/docs/email/postfix/configure-postfix-to-send-mail-using-gmail-and-google-apps-on-debian-or-ubuntu
- https://www.digitalocean.com/community/tutorials/how-to-set-up-a-mail-relay-with-postfix-and-mailgun-on-ubuntu-16-04
