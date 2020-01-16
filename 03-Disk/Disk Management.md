## Disk Management

### What You Will Learn

*****

* Partitions
* MBR
* GPT
* Mount points
* fdisk
* Creating file systems
* Mounting file systems
* Unmount file systems
* How to prepare swap space to use
* File System Table
* Disk UUIDs and Labels

### Partitions(`隔断;分割;隔板;隔离物;隔墙`)

*****

* Disks can be divided into parts, called partitions.
* Partitions allow you to separate data.
* Partitioning schemes(`方案`)
  * 1) OS, 2) Application, 3) User, 4) Swap
  * 1) OS, 2) User home directories
  * As a system administrator, you decide.

### Partitioning

*****

* Can protect the overall system.
* Keep users from creating outages by using a home directory partition

```
# I must review things i write before.
# But these days i don't want to learn any more.
# Learning needs long-term persistence, every time you are lazy, you lose a lot

$ df -h
Filesystem Size Used Avail Use% Mounted on
/dev/sda2 100G 75G 25G 75% /
/dev/sda1 488M 111M 342M 25% /boot
/dev/sda3 10G 10G 0 100% /home
```

### MBR

*****

* Master Boot Record
* Can only address 2 TB of disk space
* Being phased out by GPT
  * GPT = GUID Partition Table
* 4 Primary Partitions
* Extended partitions allow you to create logical partitions

### GPT

*****

* GUID Partition Table
* GUID = Global Unique Identifier
* Replacing the MBR partitioning scheme
* Part of UEFI
* UEFI = Unified Extensible Firmware Interface
* UEFI is replacing BIOS
* Supports up to 128 partitions
* Supports up to 9.4 ZB disk sizes
* Not supported by older operating systems
* May requier newer or special tools

### Mount points

*****

* A directory used to access the data on a partition
* /(slash) is always a mount point
* /home 
  * /home/jason is on the partition mounted on /home
* /export/home 
  * export/home/jason

### Mounting over existing data

*****

```
mkdir /home/sarah
mount /dev/sdb2 /home
# You will not be able to see /home/sarah now

umount /home
# You can now see /home/sarah again.
```

### fdisk

*****

* Alternatives(`备选方案`): gdisk, parted
* Earlier versions of fdisk did not support GPT
```
fdisk /path/to/device
```