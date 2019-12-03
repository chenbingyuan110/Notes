## 文件系统
### 常用目录
+ `/` 文件系统最上级根目录，一般只存放目录，不存放文件
+ `/bin` 存放用户的可执行程序，该目录中的文件都是可执行的、普通用户可以使用的命令
+ `/dev` 设备文件储存目录，比如声卡、磁盘文件等
+ `/boot` 存放Linux内核及引导系统程序文件
 + `/boot/vmlinuz` Linux的内核文件
 + `/boot/grub` 存放系统的引导文件
+ `/lost+found` 系统产生错误时，会将一些一时的片段放置在该目录下
+ `/mnt` 光盘的挂载点
 + `/mnt/cdrom` 通常的光盘挂载点
+ `/media` 光盘的挂载点
+ `/opt` 给主机额外安装软件所摆放的目录
+ `/proc` 此目录下的数据都在内存中，如系统核心、外部设备、网络状态。由于数据都在内存中所以不占磁盘空间
+ `/root` 系统管理员`root`的家目录，系统的第一个启动的分区为`/`，所以最好将`/root`和`/`放置在一个分区中
+ `/sbin` 放置系统管理员使用的可执行命令，如`fdisk`、`shutdown`、`mount`等
+ `/srv` 服务启动之后需要访问的数据目录
+ `/etc` 存放系统配置文件，某些服务器配置文件也放这里
+ `/home` 普通用户主目录默认存放位置
+ `/lib` 库文件存放目录
+ `/tmp` 临时文件目录，程序运行产生的临时文件放于此。与`/var/tmp`目录相似
+ `/usr` 系统存放程序的目录。当安装一个官方提供的软件包时，大多安装于此，如果涉及服务器配置文件的，会把配置文件安装在`/etc`目录中
 + `/usr/share` 用于存放共用文件的目录
 + `/usr/share/fonts` 设计字体目录
 + `/usr/share/man` 程序说明文件存放目录
 + `/usr/share/doc` 系统说明文件存放目录
 + `/usr/bin` 普通用户可执行文件目录
 + `/usr/sbin` 超级权限用户`root`可执行命令存放目录
 + `/usr/local` 存放用户自编译安装软件，一般是通过源码包安装的软件，如果没有特别指定安装目录的话，一般安装在这个目录中
 + `/usr/local/bin` 普通用户可执行文件目录
 + `/usr/local/sbin` 超级权限用户`root`可执行命令存放目录
 + `/usr/include` 以及程序头文件存放目录
 + `/usr/src` 用于存放内核源码的目录
+ `/var` 放置系统执行过程中经常变化的文件，此目录的内容经常变动
 + `/var/log` 用来存放系统日志文件
 + `/var/lib` 用来存放一些库文件
 + `/var/spool/mail` 邮件存放的目录
 + `/var/run` 程序或服务启动后，其`PID`存放在该目录下