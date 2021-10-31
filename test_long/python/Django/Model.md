1. 改变模型之后, 需要migrate：

   比如编辑 `models.py` 文件，修改DateField为DateTimeField

   - 运行 [`python manage.py makemigrations`](https://docs.djangoproject.com/zh-hans/3.2/ref/django-admin/#django-admin-makemigrations) 为模型的改变生成迁移文件。
   - 运行 [`python manage.py migrate`](https://docs.djangoproject.com/zh-hans/3.2/ref/django-admin/#django-admin-migrate) 来应用数据库迁移。

2. 查询数据

   Model.objects.get()数据不存在会异常,Model.objects.filter()不会.

