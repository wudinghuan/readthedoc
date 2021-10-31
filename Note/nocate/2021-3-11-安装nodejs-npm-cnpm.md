因为要安装hexo搭建博客,所以要安装nodejs, npm, cnpm

> 系统: Manjaro Linux 

### 1.安装nodejs

`sudo pacman -S nodejs`

输入以下命令, 有出现版本信息说明安装了 

`node -v`

### 2.安装npm

`sudo pacman -S npm`

如果提示**错误：无法从 mirrors.aliyun.com : The requested URL returned error: 404 获取文件 'npm-6.14.11-1-any.pkg.tar.zst'**,需要更新一下:

`sudo pacman -Sy` 

然后再执行安装命令

### 3.安装cnpm

`sudo npm install -g cnpm -registry=https://registry.npm.taobao.org`