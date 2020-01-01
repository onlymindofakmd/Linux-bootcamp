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
