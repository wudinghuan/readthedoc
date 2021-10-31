安装picgo用于typora上传图片

> 系统:Manjaro Linux

以下路径均以本人电脑路径为例子



typora使用picogo的文章:

https://zhuanlan.zhihu.com/p/137310314

我在验证图片时出错,解决方法如下:



### 1.安装命令行版picgo

电脑要先安装node

`sudo cnpm install picgo -g`

或者

`sudo npm install picgo -g`



### 2.手动配置picgo

复制**/usr/lib/node_modules/**下的**picgo/**目录到**/home/wu/.config/Typora/**

在**/home/wu/.config/Typora/**下新建目录**linux/**

复制**/usr/lib/node_modules/picgo/bin/picgo**文件到**/home/wu/.config/Typora/picgo/linux/**



### 3.

最后验证成功

![image-20210311215017381](https://i.loli.net/2021/03/11/uWncy2GBXUSOHIN.png)