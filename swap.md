Create a Swap File (1x-2x size of ram)
```bash
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
```

Allow Swap on after reboot
```bash
sudo sh -c 'echo "/swapfile none swap sw 0 0" >> /etc/fstab'
sudo sh -c 'echo "vm.swappiness=10" >> /etc/sysctl.conf'
sudo sh -c 'echo "vm.vfs_cache_pressure=50" >> /etc/sysctl.conf'
```