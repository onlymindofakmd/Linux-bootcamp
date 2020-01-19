## 你可以把Linux内核当成一家软件外包公司的老板

### Linux系统结构

*****

![linux](linux.jpeg "linux")

![操作系统内核体系结构图](linux_sys.jpeg "操作系统内核体系结构图")

### 关于这部分内容的一些思考回答/记录

*****

* Linux源代码 - https://github.com/torvalds/linux or https://elixir.bootlin.com/linux/latest/source
  * kernel:内核管理核心代码，其中包含了进程管理子系统
  * fs - （file system）:文件管理子系统
  * mm - 内存管理子系统，这里更多的是CPU体系结构的内存管理，与具体物理内存管理相关的代码在 arch/（某种架构）/mm
  * net - 网络子系统
  * drivers - 设备子系统，其中存放各种硬件的驱动程序，drivers/block 下存放块设备的驱动程序
* Linux内核相关
  * https://www.kernel.org/
  * https://courses.linuxchix.org/kernel-hacking-2002/08-overview-kernel-source.html