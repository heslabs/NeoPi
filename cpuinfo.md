# CPU


---
### OS

```
root@hawkeye:~# uname -a
Linux hawkeye 5.15.72-mb5421-release-1.0.0.b3 #1 SMP PREEMPT Mon Apr 14 17:55:27 CST 2025 aarch64 aarch64 aarch64 GNU/Linux

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
