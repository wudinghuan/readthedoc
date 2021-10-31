2021-3-20

系统: Manjaro Linux

---

如果移动了python创建的虚拟环境文件夹, 需要修改两个文件,才能正常运行`flask run` 

### 1.修改xxx/bin/下的**activate**文件

修改这行信息

`VIRTUAL_ENV="/home/wu/文档/programming/python/Pratice/FLask/Proj1"`

为正确的路径

### 2.修改xxx/bin/下的**flask**文件

修改这行信息

`#!/home/wu/文档/programming/python/Pratice/FLask/Proj1/bin/python`

为正确的路径