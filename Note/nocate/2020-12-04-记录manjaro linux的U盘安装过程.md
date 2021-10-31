![记录manjaro linux的U盘安装过程](https://p3-tt.byteimg.com/origin/pgc-image/9ea8a18a408b4e959ee6ec1fe56b8b7a?from=pc)

# 安装时间：

2020-12-4

# 我的电脑配置：

磁盘上有windows10

11年的电脑，传统（legacy）bios

英伟达显卡

只有一个硬盘

# 用到的软件

微pe

ventoy

两个软件都放在硬盘上

# manjaro版本

这个时间下载的最新稳定版，桌面环境为kde

# 安装过程

# 为manjaro留出空间

我在windows10中用diskgenius在磁盘最后的位置留了100g空闲空间：分出了100g的空间分区之后，把分区删除就会得到100g的空闲空间

用windows自带的磁盘管理工具也可以执行这步操作

# 制作启动盘

1. 在windows10系统中，打开微pe，把pe系统安装到硬盘
2. 重启电脑，进入pe系统
3. 插入U盘
4. 在pe系统中打开diskgenius分区工具
5. 将U盘的分区全删掉
6. 保存更改
7. 在工具栏中选择将U盘设置为hdd模式
8. 在硬盘栏中选择重设U盘的主引导记录
9. 打开ventoy，在pe系统中可以运行这个软件
10. 在ventoy中点击安装，把ventoy安装到U盘，这时U盘会被分成两个区



![记录manjaro linux的U盘安装过程](https://p3-tt.byteimg.com/origin/pgc-image/41ad24ac5daa48a6a8e4c0ac633858f2?from=pc)

1. 在diskgenius中将容量最大的那个区（用来放iso文件的）格式化
2. 把iso复制到U盘的这个分区

# 安装

1. 重启电脑，以U盘启动，这是进入ventoy界面，发现有一个manjaro的选项，选择进入
2. 这时进入了一个界面，



![记录manjaro linux的U盘安装过程](https://p3-tt.byteimg.com/origin/pgc-image/385f468ff9ab4d83a85b38794282ff16?from=pc)

这里选择

- tz为：亚洲-上海
- lang为：zh_cn
- driver为：**free**（我试过选择nonfree，结果进入不了manjaro live继续安装）

然后就选择图中选择的选项，回车，进入系统安装

- 点击下图最下面的按钮“Launch Installer”启动安装程序



![记录manjaro linux的U盘安装过程](https://p3-tt.byteimg.com/origin/pgc-image/57d0526b9caa45cc836f4047d070b43b?from=pc)

- 然后为了节省时间，我不连接网络安装
- 选择地区为 中国上海



![记录manjaro linux的U盘安装过程](https://p6-tt.byteimg.com/origin/pgc-image/61bd3f8144004648857877db11089b89?from=pc)

（这张图来源于网络）

- 键盘默认，直接点继续



![记录manjaro linux的U盘安装过程](https://p6-tt.byteimg.com/origin/pgc-image/44452780b4604b5d93b348753496e485?from=pc)

（这张图来源于网络）

下一步的分区是**重点**

- 我选择了手动分区，选择你的硬盘，如下图



![记录manjaro linux的U盘安装过程](https://p3-tt.byteimg.com/origin/pgc-image/7039cff2cd7f433a947ba55e2fbbb7ae?from=pc)

（这张图来源于网络）

- 然后选择我腾出来的100g空闲空间



![记录manjaro linux的U盘安装过程](https://p6-tt.byteimg.com/origin/pgc-image/c6ad19f875e24027971b67c3108cae3a?from=pc)

（这张图来源于网络）

- 点击创建，这是挂载目录，我只挂载一个根目录/，并在下面选择标记为root。其实安装完成后其他目录会自动生成，网上看到的还挂载了boot啊home啊usr啊等等，但是我按照他们的这些挂载方法都分区失败了。
- 分区这步弄完了，后面都是很简单的配置，这里不细说