---

---

---

---

---

---

# 本地使用jekyll(主要用于测试)

## 基本安装与使用

#### 1.设置gem环境变量

编辑/home/你的用户名/.bashrc文件,在最后面加上

`export PATH=$PATH:/home/wu/.local/share/gem/ruby/2.7.0/bin`

要对全部用户启用,编辑/etc/profile文件,加上上面的代码

#### 2.安装jekyll

gem install jekyll

#### 3.设置国内源

不设置国内源,jekyll时会一直runnig!

设置方法:

`bundle config mirror.https://rubygems.org https://gems.ruby-china.com`

#### 4.创建网页

`jekyll new 要新建的文件夹名字`

#### 5.更换主题

...

## 下载主题

#### 1.在github下载time-machine主题

下载https://github.com/pages-themes/time-machine.git zip

#### 2.编译运行

解压zip, cd到解压目录下, 执行gem install jekyll-theme-time-machine安装主题到电脑, 执行bundle install 安装需要的文件, jekyll bulid编译或者直接jekyll server查看.



# Github上使用jekyll

1. #### 开启github page, 选择jekyll主题

   详细步骤网上很多, 或者直接看github page的官方文档

2. #### 最少必备文件

   \_posts文件夹

   index.md

   README.md(选择主题后自动生成的说明)

   _config.yml

3. #### _config.yml的编写

   ```yml
   #以下内容都是可选的
   
   title: 博客的标题
   descrbe: 博客的描述
   theme: jekyll-theme-cayman #jrkyll主题
   showdownload: false #不显示下载按钮
   ```

4. #### 文章命名

   >  文章放在\_posts目录下

   名字格式yyyy-m-dd.md或yyyy-mm-dd.md

5. #### 仓库名和用户名不同时, config文件要修改

   比如我建了一个仓库, 叫blog, 然后给这个仓库开启了github page, 基本部署完jekyll主题之后, 注意在\_config.yml中添加:  baseurl: /blog/    否则无法访问到\_posts的文章!!
   
6. #### 自定义layout注意事项

   > 站点为xxxx.githu.io/blog

   自定义了layout的模板之后, 比如编写了default.html, 在default.html中:

   文章链接要使用\<a href="{{ site.baseurl}}{{post.url}}">{{ post.title }}</a>

   而不是\<a href="{{post.url}}">{{ post.title }}</a> 

   否则文章链接不正确.(_config.yml中定义 baseurl: /blog)

   ```
   <ul>
     {% for post in site.posts %}
         <li>
         <h2><a href="{{ site.baseurl}}{{post.url}}">{{ post.title }}</a></h2>
         </li>
         site.baseurl:{{site.baseurl}}<br>
         baseurl:{{baseurl}}<br>
         post.url:{{post.url}}<br>
         page:{{page}}<br>
     {% endfor %}
     </ul>
   ```

   

7. #### 使用不带日期命名的文章

   https://jekyllrb.com/docs/collections/

   - 在与\_posts同层级下创建_cposts目录

   - 此时的_config.yml

     ```yml
     baseurl: /blog
     
     collections:
         cposts:
             output: true
     ```

   - 放文章如test.md到_cposts目录下

   - 增加内容到index.md

     ```jinja2
     <h1>文章</h1>
     <ul>
         {% for post in site.cposts %}
             <li>
                 <a href="{{site.baseurl}}{{ post.url }}">
                 {{ post.title }}
                 </a>
             </li>
         {% endfor %}
     </ul>
     ```

   
   这时带日期命名的文章无法识别, 文章开头也必须写明模板:
   
   ```
   ---
   layout: xxx
   ---
   
   示例:
   ---
   layout: default
   ---
   
   ```
   
   解决这个问题, 让md文件默认使用layout: https://jekyllrb.com/docs/configuration/front-matter-defaults/
   
   添加一下内容到config.yml:
   
   ```yml
   #给cposts这个集合下的文章默认使用default layout
   defaults:
     -
       scope:
         path: "" # an empty string here means all files in the project
       values:
         layout: "default"
   ```
   
   

# 一些知识

#### 1. html与md的区别

使用index.html, 不加

```
---
layout: xxxx
---
```

不会有样式. 而使用index.md可以不加也有样式
