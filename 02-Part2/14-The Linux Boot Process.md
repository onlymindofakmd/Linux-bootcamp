## The Linux Boot Process

### What You Will Learn

*****

* BIOS
* Boot loaders
* Linux Kernel
* Runlevels

### BIOS

*****

* Basic Input/Output System
* Special firmware
* It's operating system independent
  * This is not unique(`唯一的;独一无二的;`) to the Linux OS
* Primary purpose is to find and execute the boot loader
* Performs the POST
  * Power-on Self Test
* Knows about bootable devices
  * Hard drives
  * USB drives
  * DVD drives
  * etc.
* The boot device search order can be changed

### Boot Loaders

*****

* LILO
  * Linux loader
* GRUB
  * Grand Unified Bootloader
  * Replaced LILO
* Boot loaders start the operating system
* Boot loaders can start the operating system with different options

### Initial RAM Disk

*****

* Initrd(`初始化内存盘`)
  * initial RAM disk
* Temporary filesystem that is loaded from disk and stored in memory
* Contains helpers and modules required to load the permanent OS file system

### The /boot Directory

*****

* /boot
  * Contains the files required to boot Linux
  * initrd
  * kernel
  * boot loader configuration

```
$ ls -F /boot
abi-3.13.0-46-generic initrd.img-3.13.0-46-generic
config-3.13.0-46-generic System.map-3.13.0-46-generic
grub/ vmlinuz-3.13.0-46-generic$ ls -F /boot
abi-3.13.0-46-generic initrd.img-3.13.0-46-generic
config-3.13.0-46-generic System.map-3.13.0-46-generic
grub/ vmlinuz-3.13.0-46-generic
```

### Kernel Ring Buffer

*****

* Contains messages from the Linux kernel
* `dmesg`
* `/var/log/dmesg`

### Runlevels / Description

*****

Runlevels | Description
:--: | :--:
0 | Shut down the system
1,S,s | Single user mode. Used for maintenance(`维护;保养;维持;保持`)
2 | Muti-user mode with graphical interface(Debian/Ubuntu)
3 | Muti-user text mode (RedHat/CentOS)
4 | Undefined
5 | Muti-user mode with graphical interface(RedHat/CentOS)
6 | Reboot

### Init

*****

```
# This may not use in lastest version Linux distros
/etc/inittab:
id:3:initdefault
```
* Being phased out by systemd

### Systemd

*****

* Use targets instead of runlevels
```
# cd
/lib/systemd/system
# ls -l runlevel5.target
lrwxrwxrwx. 1 root root 16 Jul 17 2014
runlevel5.target -> graphical.target
# systemctl set-default graphical.target
```

### Changing runlevels or targets

*****

* telinit RUNLEVEL
  * `telinit 5`
* systemctl isolate TARGET
  * `systemctl isolate graphical.target`

### Rebooting

*****

```
# telinit 6
# systemctl isolate reboot.target
# reboot
```
shutdown [options] time [message]

```
# shutdown -r 15:30 "rebooting!"
# shutdown -r +5 "rebooting soon!"
# shutdown -r now
```

### Poweroff

*****

```
# telinit 0
# systemctl isolate poweroff.target
# poweroff
```