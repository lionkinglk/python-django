# 7.url命名与反转

url可能会经常变化，给url取个名字，以后使用名字反转就可以了

在'path'函数中，传递一个'name'函数即可

例如，可用于检测网站是否登录，如未登录跳转到登录页面。

zsb\zsb\urls.py

```
from django.contrib import admin
from django.urls import path
from enroll import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('enroll/', views.enroll, name='enroll'),
    path('enroll/<enroll_id>', views.enroll_detail),
    path('search', views.search, name='search')
```

zsb\enroll\views.py

```
from django.shortcuts import render
from django.shortcuts import redirect,reverse
from django.http import HttpResponse
# Create your views here.
def enroll(request):
    return HttpResponse("报名首页")
def enroll_detail(request,enroll_id):
    text = "报名人员id是 %s" % enroll_id
    return HttpResponse(text)
def search(request):
    username = request.GET.get('username')
    if username:
        text = "查找姓名 %s" % username
        return HttpResponse(text)
    else:
        return redirect(reverse('enroll'))
```

### 应用命名空间

当有多个app时，在各个应用中，可以建立urls.py，如果多个应用的url命名重复时，在反转url时需要指定url所在的命名空间

```
app_name='namestring'

return redirect(reverse('namestring:enroll'))
```

### 实例命名空间



