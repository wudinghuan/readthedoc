![linux版的WPS-Office缺失windings等字体](https://p6-tt.byteimg.com/origin/dfic-imagehandler/f7e889ef-73a8-4d80-9551-e24c7546fe99?from=pc)



在Linux上新安装的WPS-Office往往，会因为没安装相关字体提示以下错误：

![linux版的WPS-Office缺失windings等字体](https://p3-tt.byteimg.com/origin/pgc-image/d0ead22814174493b14f4c6b69ee08f7?from=pc)



解决方法就是安装字体，Manjaro Linux的安装命令如下：

```
sudo pacman -S ttf-wps-fonts
```

安装玩之后，再启动WPS就不会再提示错误了