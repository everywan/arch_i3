# centos

主要用于NAS

软路由: 软路由是指利用台式机或服务器的供应商配合一定软件而形成的路由解决方案，主要靠对软件的设置，实现路由器路由器的功能，它的软件与硬件是独立分开的。软路由使用普通计算机，使用通用的操作系统，如Linux或windows，因此软路由的设置事实上是windows或linux的设置。根据使用的操作系统不同，可以分为基于windows平台和基于Linux/bsd平台开发的软件路由器。
从而可以实现一些复杂的功能, 如更强的防火墙(由操作系统控制)

gen8 + exsi + p420阵列卡 系统的一些问题
1. 开机时需要摁 `f10->f5`, 添加阵列卡 raid 配置, 然后才可以在 exsi 中识别出硬盘.
2. gen8 主板带测速功能, 当硬盘低于900转会报警然后自动重启.
  - gen8 主板查脚为 6pin 类型的, 需要该为4pin才能接其他风扇
  - 我尝试换了下 电源/风扇, 确实安静了, 但是主板自检失败, 总是重启