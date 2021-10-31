2021/7/2

> 我参考的文章是https://blog.csdn.net/ITNewerKing/article/details/106070806
>
> 系统：manjaro linux

#### 问题1：启动httpd失败，提示找不到module

文章使用的php7,我的是php8, 所以修改的这段内容

```
LoadModule php7_module modules/libphp7.so
AddHandler php7-script php
Include conf/extra/php7_module.conf
```

不同，后面的文件以这个路径 `/etc/httpd/` 为参考寻找，（在网上很难搜到答案），我的修改是

```
LoadModule php_module modules/libphp.so
AddHandler php8-script php
Include conf/extra/php_module.conf
```

成功解决

#### 问题2：访问http://localhost/phpmyadmin/提示`Composer detected issues in your platform: Your Composer dependencies require the following PHP extensions to be installed: iconv`

我没安装php74-mcrypt

解决方法：到找到php.ini,取消extension=iconv这行注释。

#### 问题3：php提示以下错误

> PHP Warning:  PHP Startup: Unable to load dynamic library 'pdo_dblib' (tried: /usr/lib/php/modules/pdo_dblib (/usr/lib/php/modules/p
> do_dblib: cannot open shared object file: No such file or directory), /usr/lib/php/modules/pdo_dblib.so (/usr/lib/php/modules/pdo_db
> lib.so: cannot open shared object file: No such file or directory)) in Unknown on line 0

终端运行

```
 sudo pacman -S php-dblib 
```

解决

