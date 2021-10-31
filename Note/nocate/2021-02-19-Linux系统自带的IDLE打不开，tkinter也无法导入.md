众所周知，Linux是自带了python的，无需安装。
最近安装了Manjaro Linux，于是想敲下python代码，却发现无法打开IDLE！

------

IDLE是Python的集成开发环境 ，自1.5.2b1以来已与该语言的默认实现捆绑在一起。 它被打包为Python包装的可选部分，包含许多Linux发行版 。 它完全用Python和Tkinter GUI工具包编写（ Tcl / Tk的 包装函数）。

------

出现的错误提示如下所示：

```
Your Python may not be configured for Tk.
```

![Linux系统自带的IDLE打不开，tkinter也无法导入](https://p1-tt.byteimg.com/origin/pgc-image/3cc4b7909fb04c28964f2196ee1ac472?from=pc)



进入命令行，导入tkinter，同样是会提示错误的：

![Linux系统自带的IDLE打不开，tkinter也无法导入](https://p1-tt.byteimg.com/origin/pgc-image/f1288e883a4743c9a26280fad12e65f3?from=pc)



解决的办法是安装一下tk，在命令行中输入

```
sudo pacman -S tk
```

![Linux系统自带的IDLE打不开，tkinter也无法导入](https://p6-tt.byteimg.com/origin/pgc-image/d63c57b9a2e040a094499d33ef4fd4d1?from=pc)



安装完之后，就可以打开IDLE和导入tkinter了！

![Linux系统自带的IDLE打不开，tkinter也无法导入](https://p1-tt.byteimg.com/origin/pgc-image/3e9aa4fd912942348df58e5a00238f5c?from=pc)



![Linux系统自带的IDLE打不开，tkinter也无法导入](https://p6-tt.byteimg.com/origin/pgc-image/aeddec4929c3424ebd122b7bb0210d3c?from=pc)