初学python的同学一定会遇到的pip安装第三方库速度很慢的问题。

# 什么是pip

pip 是 Python 包管理工具，该工具提供了对Python 包的查找、下载、安装、卸载的功能。

在没有任何设置的情况下，pip默认从https://pypi.org/simple安装第三方库。

# 速度慢的原因

没配置过pip基本url的话，下载速度会很慢，原因是我们请求数据的服务器不在国内。

# 解决办法

更换镜像源，可以用国内的清华镜像源。

pypi 镜像每 5 分钟同步一次。

临时使用

```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
```

注意，simple 不能少, 是 https 而不是 http

设为默认

升级 pip 到最新的版本 (>=10.0.0) 后进行配置：

```
pip install pip -U
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

如果您到 pip 默认源的网络连接较差，临时使用本镜像站来升级 pip：

```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U
```

# 实例

![python初学者必遇到的pip安装第三方库速度慢的问题](https://p6-tt.byteimg.com/origin/pgc-image/a94a7aabfc5a40ebb45f36597e044dca?from=pc)

在终端运行

![python初学者必遇到的pip安装第三方库速度慢的问题](https://p3-tt.byteimg.com/origin/pgc-image/7a787d206aba4793946e7953d923102d?from=pc)

运行结果

![python初学者必遇到的pip安装第三方库速度慢的问题](https://p1-tt.byteimg.com/origin/pgc-image/231908be05c4434d963e9c14e03f3a96?from=pc)