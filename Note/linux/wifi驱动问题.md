
安装驱动:
在设置-硬件里安装出错:modprobe: ERROR: could not insert 'wl': Exec format error
解决方法:终端输入 sudo modprobe wl

以前安装过,但是现在没网
解决:在/var/cache/pacman/pkg/目录下查找到驱动文件,用命令安装
pamac install ./linux54-broadcom-wl-6.30.223.271-150-x86_64.pkg.tar.zst
