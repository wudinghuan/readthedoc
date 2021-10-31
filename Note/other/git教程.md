---

---
## 基本拉取推送pull push

https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-to-ssh

#github中master改为main

```bash
git init
git remote add origin https://gitee.com/xxx/xxx.git #orgin是任意取的一个名字
git pull origin master #master是这个仓库的分支(主分支)

复制文件到该文件夹

git add .
git commit -m "上传网页"
git push origin master
```

https://gitee.com/meanswu/toolbox.git

```bash
git remote -v  #查看仓库链接

git remote rm origin #删除仓库

$ git remote set-url origin git@github.com:USERNAME/REPOSITORY.git #修改为ssh
```

```bash
#错误解决:相关文章https://blog.csdn.net/songyuc/article/details/115251254
[wu@wu-invalid xxx]$ git push origin main
error: 源引用表达式 main 没有匹配
error: 推送一些引用到 'origin' 失败

执行以下语句再push
git branch -m main
```

提交前删除将要提交的文件:

git rm --cache 文件



## 合并

没pull, 本地仓库有文件, 已commit, 向远程仓库push

git pull错误fatal: refusing to merge unrelated histories

https://blog.csdn.net/qq_39400546/article/details/100150320

```bash
git push --force origin master
git pull origin master --allow-unrealted-histories
```



```bash
#查看提交信息

$ git log
commit cd5058a2881eaae265cceecdaeb1c4f795f6c189 (HEAD -> master)
Author: wu <111111@qq.com>
Date:   Mon Oct 11 15:02:01 2021 +0800

    创建demo.py


$ git status #查看文件状态,有没有add,有没有commit
On branch master
nothing to commit, working tree clean
```

## 配置

```bash
$ git config -l #显示配置信息
$ git config --global user.name xxxx #设置全局变量 名称
$ git config --global user.email 111111@qq.com #设置全局变量 邮箱
```

## pull,push特殊情况

1. 本地仓库没pull,本地仓库文件没提交,pull会怎样

2. 本地仓库没pull,本地仓库文件已提交,pull会怎样

   

3. 本地仓库没pull,本地仓库文件没提交,push会怎样

4. 本地仓库没pull,本地仓库文件已提交,push会怎样

5. 本地仓库已pull,pull之后,远程仓库改动,本地也改动,本地仓库文件已提交,push会怎样



## 其他

```bash
#查看版本提交
$ git reflog
cf69d7e (HEAD -> other, master) HEAD@{0}: checkout: moving from master to other
cf69d7e (HEAD -> other, master) HEAD@{1}: commit: 来自其他用户
b641fab (origin/master) HEAD@{2}: initial pull

#回退到上一个版本 版本回退
$ git reset --hard HEAD^
#回退到指定版本
$ git reset --hard 版本号 # $ git reset --hard cf69d7e
```

