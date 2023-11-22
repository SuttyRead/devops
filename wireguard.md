### Use ubuntu with docker

### Run docker container wg-easy with UI
```
docker run -d \
  --name=wg-easy \
  -e WG_HOST=31.172.141.158 \
  -e PASSWORD=amazonka \
  -v ~/.wg-easy:/etc/wireguard \
  -p 51820:51820/udp \
  -p 51821:51821/tcp \
  --cap-add=NET_ADMIN \
  --cap-add=SYS_MODULE \
  --sysctl="net.ipv4.conf.all.src_valid_mark=1" \
  --sysctl="net.ipv4.ip_forward=1" \
  --restart unless-stopped \
  weejewel/wg-easy
```

* Open http://local_ip:51821/ for example http://192.168.31.162:51821/
* Enter password from docker parameter (-e PASSWORD=amazonka \)
* Add client and use vpn
* Open port on router 51820 for vpn
