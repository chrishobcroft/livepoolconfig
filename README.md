# livepoolconfig

## Hardware

- 2Gb RAM
- 2 x 2198MHz vCPU
- 10Gb Disk

## Firewall

Expose ports 22

## Commands
```
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
sudo nano /etc/fstab
```
Add this to `/etc/fstab`
```
/swapfile swap swap defaults 0 0
```
Then continue
```
sudo apt update && \
sudo apt upgrade -y

wget https://github.com/Livepool-io/transcoder/releases/download/v0.5.7/0.5.7-55441d23_livepool-linux-amd64.tar.gz
tar -xzf 0.5.7-55441d23_livepool-linux-amd64.tar.gz
cd livepool-linux-amd64
./livepool -ethAcctAddr (insert your Ethereum address here)
