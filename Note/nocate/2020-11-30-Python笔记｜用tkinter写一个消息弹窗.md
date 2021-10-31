![Python笔记｜用tkinter写一个消息弹窗](https://p3-tt.byteimg.com/origin/pgc-image/e5a0938a0c284ba4b9b4a9ce445b335f?from=pc)



代码

```
from tkinter import messagebox
messagebox.askokcancel('这是标题','你好,tkinter')
```

运行后如下

![Python笔记｜用tkinter写一个消息弹窗](https://p1-tt.byteimg.com/origin/pgc-image/4e7f754386964a6d8715462f26984f6d?from=pc)



这时出现了两个窗口, 一个时tkinter的主体窗口, 一个就是我写的MessageBox. 点击确认会返回True, 点取消返回False.

运行代码

```
messagebox.askquestion("问题",'消息')
```



![Python笔记｜用tkinter写一个消息弹窗](https://p1-tt.byteimg.com/origin/pgc-image/71ee810ac5d44fa59efedd515a2f24a7?from=pc)



发现和上一个例子看上去没什么区别, 只是下面两个按钮的文本变了

另一个例子

```
messagebox.showerror('显示错误','错误信息')
```

![Python笔记｜用tkinter写一个消息弹窗](https://p1-tt.byteimg.com/origin/pgc-image/a246487ff2d84bce83a8861716651ef6?from=pc)



发现图标变成了叉号

```
更多方法,可以通过 help(messagbox) 查看
```