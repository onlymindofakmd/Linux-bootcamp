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

### File Systems

*****

* ext = Extended file system
  * ext2, ext3, and ext4 are later releases
  * Often the default file system type
* Other file systems:
  * ReiserFS
  * JFS
  * XFS
  * ZFS
  * Btrfs

```
mkfs -t TYPE DEVICE
mkfs -t ext3 /dev/sdb2
mkfs -t ext4 /dev/sdb3
mkfs.ext4 /dev/sdb3

# ls -1 /sbin/mkfs*
/sbin/mkfs
/sbin/mkfs.btrfs
/sbin/mkfs.cramfs
/sbin/mkfs.ext2
/sbin/mkfs.ext3
/sbin/mkfs.ext4
/sbin/mkfs.minix
/sbin/mkfs.xfs
```

### Mounting with mount

*****

```
# mount DEVICE MOUNT_POINT
mount /dev/sdb3 /opt
```

### The mount command

*****

```
# mount
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev)
tmpfs on /run type tmpfs (rw,nosuid,nodev,mode=755)
...
/dev/sda2 on / type xfs (rw,relatime,attr2,inode64,
noquota)
/dev/sdb3 on /opt type ext4 (rw,relatime,data=ordered)
```

### The df command

*****

```
# df -h
Filesystem Size Used Avail Use% Mounted on
/dev/sda2 198G 1.7G 196G 1% /
devtmpfs 489M 0 489M 0% /dev
tmpfs 497M 0 497M 0% /dev/shm
tmpfs 497M 6.5M 491M 2% /run
tmpfs 497M 0 497M 0% /sys/fs/cgroup
/dev/sdb3 484G 73M 459G 1% /opt
```

### Manual mounts do not persist

*****

In order to make mounts persist between reboots, add an entry in the /etc/fstab file

### Unmount with unmount command

```
# umount DEVICE_OR_MOUNT_POINT
umount /opt
umount /dev/sdb3
```

### Preparing swap space

*****

```
# mkswap /dev/sdb1
Setting up swapspace version 1, size = 1048572 KiB
no label, UUID=619dc6d9-1b0b-4a9a-9df5-bfc343fb8d6e
# swapon /dev/sdb1
# swapon -s
Filename Type Size Used Priority
/dev/sda1 partition 2047996 0 -1
/dev/sdb1 partition 1048572 0 -2
```

### /etc/fstab - The File System Table

*****

* Controled what devices get mounted and where on boot.
* Each entry is made up of 6 fields
  * device
  * mount point
  * file system type
  * mount options
  * dump
  * fsck order

### Sample /etc/fstab file

*****

```
# device mount point FS options dump fsck
/dev/sda2 / xfs defaults 0 1
/dev/sda1 swap swap defaults 0 0
UUID=dbae4fe7-b06f-4319-85dc-b93ba4a16b17 / xfs defaults 0 1
LABEL=opt /opt ext4 defaults 1 1
/dev/sda1 swap swap defaults 0 0
```

### Viewing Labels and UUIDs

*****

```
# lsblk –f
NAME FSTYPE LABEL UUID MOUNTPOINT
sda
├─sda1 swap 1cb76bec-a1fa-4ac6-8296-c508e936b744 [SWAP]
└─sda2 xfs root dbae4fe7-b06f-4319-85dc-b93ba4a16b17 /
# blkid
/dev/sda1: UUID="1cb76bec-a1fa-4ac6-8296-c508e936b744" TYPE="swap"
/dev/sda2: LABEL="root" UUID="dbae4fe7-b06f-4319-85dc-b93ba4a16b17" TYPE="
xfs"
```

### Labeling a file system.

*****

```
# e2label /dev/sdb3 opt
```