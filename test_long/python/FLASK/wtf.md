1. 使用wtf, 需要在form中{{form.csrf_token()}}

2. 使用quick_form在html中`{%import "bootstrap/wtf.html" as wtf %}`然后才可以使用来自py文件的form `{%wtf.quick_form(form)%}`

3. 设置属性\样式

   {{ form.name(class="xxx", placeholder="xxx") }}

