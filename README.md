# NeoPi


### Neoverse Edge Server: Hawkeye EDS-5410
* Key Features
   * 24-core Arm Neoverse-N2 Processors
   * 48GB ECC DDR5
   * Up to 2x 100GbE QSFP56 (with Break out Cable)
   * 1x 1GbE RJ45
   * 1x USB-C USB 3.0
   * 1x USB-C Consoles (Connect to Both CPU & MCU)
   * 1x USB-C USB 2.0 (Connect to MCU)
   * 1x m.2 M Key Connector for PCIe Extension

<img src="https://github.com/user-attachments/assets/f652e263-107c-4de1-b764-d62ad9b1eac1" width=350>


---
### Connect to ASUS WiFi Router

```
SSID: SPACE or SPACE_5G
Password: arm12345
```

Or use brower to log into admin of ASUS WiFi router
```
https://192.168.72.1
Login: admin
Password: arm123
```

---
### Download SSH terminal utility

Download PuTTY - a free implementation of SSH and Telnet for Windows and Unix platforms.
```
https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
```

---
### Remote access to Neoverse edge server

```
$ ssh root@192.168.72.10 -X
Password: root 
or
$ sudo apt install sshpass
$ sshpass -p root ssh root@192.168.72.10 -X
```

