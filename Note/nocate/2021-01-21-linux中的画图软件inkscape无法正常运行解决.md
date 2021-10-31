![linux中的画图软件inkscape无法正常运行解决](https://p1-tt.byteimg.com/origin/dfic-imagehandler/4ab0062c-980c-4f3b-a2d8-6d2124d94589?from=pc)



# Inkscape介绍

Inkscape是一个类似AI的矢量作图软件，功能虽然不及AI强大，安装包也就100多MB。但是作为一款免费软件，它的功能比很多付费软件都要强。下图是Inkscape的主界面。

![linux中的画图软件inkscape无法正常运行解决](https://p1-tt.byteimg.com/origin/pgc-image/a9ccf903e64e4aaf8f5fb9c30a05ad33?from=pc)



# 在linux上安装软件出了点问题

我原本用的是系统windows10，所以inkscape安装的也是windows版本，只需要要到官网下载安装包，双击安装即可，安装非常简单。

随着本人使用的系统重心的转移，我使用了linux系统，所以打算在linux上安装inkscape。

第一次是在终端中用命令安装的：

```
sudo pacman -S inkscape
```

然后我在程序启动器（开始菜单）中点击图标运行，结果就是，Inkscape的图标在任务栏显示一下，然后就消失了。每一次都这样无法启动，后来通过在终端启动，看到了错误信息：

```
[wu@wu-invalid ~]$ inkscape 
inkscape: error while loading shared libraries: libpoppler.so.105: cannot open shared object file: No such....
```

![linux中的画图软件inkscape无法正常运行解决](https://p1-tt.byteimg.com/origin/pgc-image/f3a6e02ad356415194adf71d2968b535?from=pc)



# 通过不断查资料，最终解决

看到了错误信息之后，我就根据错误信息，到网上查找答案，每次找这些很难找到答案的问题，都是花了很长的时间，才找到解决方法。终于，在一个linux社区中找到了答案：

![linux中的画图软件inkscape无法正常运行解决](https://p6-tt.byteimg.com/origin/pgc-image/6ea54cd7f2cb4a45a1d9886ec8fdd22e?from=pc)



使用以下的命令安装需要的库，inkscape即可正常启动

```
[wu@wu-invalid ~]$ sudo pacman -S {poppler,poppler-glib,poppler-qt5}
```

![linux中的画图软件inkscape无法正常运行解决](https://p3-tt.byteimg.com/origin/pgc-image/6a566423c60b4b9da87271ad744fecd5?from=pc)