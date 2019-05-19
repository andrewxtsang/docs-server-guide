Logrotate Config
```bash
vi /etc/logrotate.conf
# use date as a suffix of the rotated file
dateext
```

```bash
vi /etc/logrotate.d/nginx
monthly
dateext
rotate 12
#compress
#delaycompress
```

Reference
- https://www.linode.com/docs/uptime/logs/use-logrotate-to-manage-log-files
