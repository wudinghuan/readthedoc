系统：Manjaro Linux

# 安装wireshark

![linux系统中安装wireshark普通用户必做的配置](https://p3-tt.byteimg.com/origin/pgc-image/83fec72426b64e85b64e70492634a58e?from=pc)



刚安装完之后，会发现，没有网卡，这样的话还是不能正常使用（要在root下，但是官方不推荐）

![linux系统中安装wireshark普通用户必做的配置](https://p1-tt.byteimg.com/origin/pgc-image/c4a65135fd1d4e63ba8cc23324764ddb?from=pc)



# 配置wireshark

安装wireshark之后，会创建一个wireshark的用户组

```
cat /etc/group 
```

通过上面的命令可以看到

![linux系统中安装wireshark普通用户必做的配置](https://p6-tt.byteimg.com/origin/pgc-image/c879a19029d34e23a222a7b7aae7bcc2?from=pc)



# 添加本用户到wireshark组

通过命令 whoami 可以查看用户名字

![linux系统中安装wireshark普通用户必做的配置](https://p1-tt.byteimg.com/origin/pgc-image/a8e71f4b0cfe426d8fc20a03f2a1689a?from=pc)



```
sudo usermod -a -G wireshark wu
```

再次cat /etc/group验证用户是否添加到了wireshark组

![linux系统中安装wireshark普通用户必做的配置](https://p6-tt.byteimg.com/origin/pgc-image/1b35ceb7d850468586c315945848dac4?from=pc)



# 修改dumpcap所属组为wireshark组

```
ls -l /usr/bin/dumpcap
```

![linux系统中安装wireshark普通用户必做的配置](https://p6-tt.byteimg.com/origin/pgc-image/96df11d6c4e940639a1406bb512a3a94?from=pc)



如果dumpcap已属于wireshark组，无需修改，否则运行命令：

```
sudo chgrp wireshark /usr/bin/dumpcap
```

# setcap设置文件功能

```
setcap cap_net_raw,cap_net_admin=eip /usr/bin/dumpcap  
```



注销账户再登录，发现有了网卡相关信息，并捕获到了数据

![linux系统中安装wireshark普通用户必做的配置](https://p3-tt.byteimg.com/origin/pgc-image/fb63555a232d4c6ab338b80933398988?from=pc)