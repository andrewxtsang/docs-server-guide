Create a Swap File
```bash
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
sudo sh -c 'echo "/swapfile none swap sw 0 0" >> /etc/fstab'
sudo sh -c 'echo "vm.swappiness=30" >> /etc/sysctl.conf'
sudo sh -c 'echo "vm.vfs_cache_pressure=50" >> /etc/sysctl.conf'
```