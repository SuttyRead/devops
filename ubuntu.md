### to connect machine by ssh(ssh name@ip)
```
ssh ubuntu@192.168.31.101
```

### Update and upgrade system
```
apt-get update && apt-get upgrade -y
```

### Install qemu-guest-agent for monitoring and see ip in proxmox
```
apt-get install qemu-guest-agent
```

### Set static ip for machine
```
nano /etc/netplan/*.yaml
```

### Verify your ethernet name 'enp0s18', 
```
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s18:
      dhcp4: no
      addresses:
        - 192.168.31.101/24
      routes:
        - to: default
          via: 192.168.31.1
          on-link: true
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]
```

###
```
netplan apply
```

### Install docker 
follow https://docs.docker.com/engine/install/ubuntu/

```
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```