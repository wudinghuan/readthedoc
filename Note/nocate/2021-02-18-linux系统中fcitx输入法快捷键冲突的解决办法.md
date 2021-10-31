![linux系统中fcitx输入法快捷键冲突的解决办法](https://p1-tt.byteimg.com/origin/dfic-imagehandler/676ec373-936a-4d98-8c60-1f943d9326b3?from=pc)



感觉linux中输入法的快捷键冲突的情况很常碰到，比如最近我在inkscape中就无法切换中文，很是不舒服，网上看了不少别人的解决方法，结果都没奏效。最后自己摸索出了一个方法。

总的来说就是**更改激活输入法**。下面是具体步骤：

> 系统：Manjaro Linux
>
> 桌面环境：KDE
>
> 输入法：Fcitx

# 将要作为默认输入的输入法放在第一个

右键输入法图标，点击配置。配置就是设置。

![linux系统中fcitx输入法快捷键冲突的解决办法](https://p3-tt.byteimg.com/origin/pgc-image/a6c3c8dc55144908a60236f226b74dbf?from=pc)



![linux系统中fcitx输入法快捷键冲突的解决办法](https://p6-tt.byteimg.com/origin/pgc-image/9d3b54b4b3a24def8658b430c4468054?from=pc)



# 进入高级选项

选择**全局配置选项**卡，点击**显示高级选项**，将会显示更多可以设置的选项。

![linux系统中fcitx输入法快捷键冲突的解决办法](https://p3-tt.byteimg.com/origin/pgc-image/13585899e57d493799ae7ea4c1a436ff?from=pc)



点击**程序**选项卡，选择“默认输入法状态”为**激活**

![linux系统中fcitx输入法快捷键冲突的解决办法](https://p1-tt.byteimg.com/origin/pgc-image/321e3021869147d59fe7b048e4ab81ee?from=pc)



这样设置之后，输入法默认就是中文输入，在中文输入情况下，完全可以切换为英文输入状态。而在原来的英文输入状态下，因为快捷键冲突，是无法切换为中文的。