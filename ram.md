Reboot Server if out-of-memory
```bash
sudo vi /etc/sysctl.conf
vm.panic_on_oom=1
kernel.panic=10
```
Check Log in `/var/log/messages`