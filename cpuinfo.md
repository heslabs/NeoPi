# CPU


---
### uname -a

```
root@hawkeye:~# uname -a
Linux hawkeye 5.15.72-mb5421-release-1.0.0.b3 #1 SMP PREEMPT Mon Apr 14 17:55:27 CST 2025 aarch64 aarch64 aarch64 GNU/Linux

```

### lsb_release -a
```
root@hawkeye:~# lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 22.04 LTS
Release:        22.04
Codename:       jammy
```

---
### CPU

```
processor       : 23
BogoMIPS        : 2000.00
Features        : fp asimd aes pmull sha1 sha2 crc32 atomics fphp asimdhp cpuid asimdrdm jscvt fcma lrcpc dcpop sha3 sm3 sm4 asimddp sha512 sve asimdfhm dit uscat ilrcpc flagm ssbs sb paca pacg dcpodp sve2 sveaes svepmull svebitperm svesha3 svesm4 flagm2 frint svei8mm svebf16 i8mm bf16 dgh rng bti
CPU implementer : 0x41
CPU architecture: 8
CPU variant     : 0x0
CPU part        : 0xd49
CPU revision    : 0

root@hawkeye:~# cat /proc/cpuinfo 
```

---
### MEM

```
root@hawkeye:~# cat /proc/meminfo 
MemTotal:       49877504 kB
MemFree:        48452608 kB
MemAvailable:   44658432 kB
Buffers:           72512 kB
Cached:           145152 kB
SwapCached:            0 kB
Active:           114368 kB
Inactive:         166912 kB
Active(anon):      11008 kB
Inactive(anon):    77376 kB
Active(file):     103360 kB
Inactive(file):    89536 kB
Unevictable:        2688 kB
Mlocked:            2688 kB
SwapTotal:             0 kB
SwapFree:              0 kB
Dirty:                 0 kB
Writeback:             0 kB
AnonPages:         66880 kB
Mapped:            39936 kB
Shmem:             22848 kB
KReclaimable:      38208 kB
Slab:             312512 kB
SReclaimable:      38208 kB
SUnreclaim:       274304 kB
KernelStack:        5168 kB
PageTables:         7616 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:    24938752 kB
Committed_AS:     163200 kB
VmallocTotal:   137170124800 kB
VmallocUsed:       22080 kB
VmallocChunk:          0 kB
Percpu:            13824 kB
AnonHugePages:         0 kB
ShmemHugePages:        0 kB
ShmemPmdMapped:        0 kB
FileHugePages:         0 kB
FilePmdMapped:         0 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:     524288 kB
Hugetlb:               0 kB

```

---
### SSD 

```
root@hawkeye:~# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root       1.9T  968M  1.8T   1% /
tmpfs            24G     0   24G   0% /dev/shm
tmpfs           9.6G   23M  9.5G   1% /run
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/nvme0n1p2  224M   29M  178M  14% /boot
/dev/nvme0n1p1   64M  6.0K   64M   1% /boot/efi
tmpfs           4.8G     0  4.8G   0% /run/user/0
```

---
### Network

```
demo@hawkeye:~/admin$ ifconfig
eth2: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.52.101  netmask 255.255.255.0  broadcast 192.168.52.255
        inet6 fe80::4260:5aff:fe02:efd2  prefixlen 64  scopeid 0x20<link>
        ether 40:60:5a:02:ef:d2  txqueuelen 1000  (Ethernet)
        RX packets 4603  bytes 541156 (541.1 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1179  bytes 200037 (200.0 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
