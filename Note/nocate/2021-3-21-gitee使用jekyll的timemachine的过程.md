2021-3-20
---



1. 创建一个不同于用户名的仓库, 比如blog

2. 启用page, 不需要勾选强制开启https

3. 在仓库根下创建_config.yml文件: 

   内容有:

   ```yaml
   title: Time Machine theme
   description: Time Machine is a theme for GitHub Pages.
   theme: jekyll-theme-time-machine
   permalink: none
   baseurl: "/blog"
   url: "http://meanswu.gitee.io/blog"
   ```

   

4. 在仓库根下创建index.md文件: 

   内容:

   ```html
   <h1>文章</h1>
   
   <p>{{site.url}}</p>  <!--显示site.url的内容-->
     <ul>
     {% for post in site.posts %}
         <li>
         <h2><a href="{{site.url}}/{{ post.title }}">{{ post.title }}</a></h2>
         <p>{{ post.excerpt }}</p>
         </li>
     {% endfor %}
     < /ul>
   ```

   

5. 在仓库根下创建_posts文件夹, 并放入md文件, md文件不需要写日期了

6. ~~通过 http://meanswu.gitee.io/blog/文章名 访问文章, 点击链接会变成 http://meanswu.gitee.io/文章名, 将无法找到文章~~

7. 可以通过克隆github上别人的项目, 获得css, js, html等需要的文件, 或者本地运行`jekyll new-theme 主题名字`创建一个项目

8. 运行jekyll server, 修改项目文件, 使得博客达到自己的要求. 可以使用开发者工具调试, 比如可以看到路径是否出错, jquery.min.js是否找不到(找不到的话可以到网上下载一个)



### 问题

**1运行server之后, 页面没有样式:**

记得在index.md或index.html添加front matter:

```
---
layout: default
---
```

**2点击进文章出现Internal Server Error**:

```
incompatible character encodings: UTF-8 and ASCII-8BIT

------

WEBrick/1.6.0 (Ruby/2.7.2/2020-10-01) at 127.0.0.1:4000
```

遇到这个情况是路径不正确, 可以到_site下查看文章的位置, 比如应该是`http://127.0.0.1:4000/post/Gitee使用jekyll的timemachine的过程.html`的, 结果页面显示的链接是`http://127.0.0.1:4000/Gitee使用jekyll的timemachine的过程.html`, 到index.md修改文章的url.