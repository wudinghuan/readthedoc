![AutoHotkey笔记｜自动在文本编辑器加上指定内容](https://p6-tt.byteimg.com/origin/dfic-imagehandler/3e21778e-0a01-4c88-9c7c-c31054cc15db?from=pc)



最近正在进行数控实训, 但是在宿舍无法使用数控机床, 于是在网上找了一个仿真软件来练习. 可是仿真软件不能通过键盘输入, 只能通过鼠标点击编辑CNC代码, 于是打算用AutoHotkey写一个自动添加行号的辅助工具.

功能:

只要按下一个按键,就会自动输入指定内容, 如图

![AutoHotkey笔记｜自动在文本编辑器加上指定内容](https://p3-tt.byteimg.com/origin/pgc-image/b09a8424eb8e4075bdae375b4c958ccf?from=pc)



第一版本的源代码是这样的

```
line=1
Enter::
	StringLen, len, line
	Send `;{Enter}N
	if(len=1){
		Send 000
	}
	if(len=2){
		Send 00
	}
	if(len=3){
		Send 0
	}
	Send %line%{space}
	line++
return 
```

这个程序出现了一些奇奇怪怪的问题, 比如字体变了, line的值也变得乱七八糟, 如图

![AutoHotkey笔记｜自动在文本编辑器加上指定内容](https://p6-tt.byteimg.com/origin/pgc-image/eaeae3d4fbbe4dd08821c61de1edba24?from=pc)



后来改成了这个版本, 问题解决了

```
line=1
Esc::
	Send `;
	Send {Enter}N
	if(line>0 and line<10){
		Send 000
	}
	if(line>9 and line<100){
		Send 00
	}
	if(line>99 and line<1000){
		Send 0
	}
	Send %line%{space}
	line++
return 
```

我想, 可能是用StringLen求line这个数字的长度的过程中出现了错误, 或者是使用Enter键作为热键导致出现错误.



另外我也用AutoIt写了相同功能的程序, 将在下篇文章中介绍