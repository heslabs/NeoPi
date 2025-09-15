# Networks


---
### Serial

```
sudo chmod ugo+rwx /dev/ttyUSB*
putty -serial -sercfg 115200,8,n,1,N -fn "client:Ubuntu Mono 16"  /dev/ttyUSB0
```
 
---
### netplan

```
sudo ip a
sudo systemctl enable systemd-networkd.service
sudo systemctl start systemd-networkd.service
sudo netplan apply
```


#### 00-installer-config.yaml

```
network:
    version: 2
    renderer: networkd
    ethernets: 
        enP2p4s0:
            dhcp4: true
```
