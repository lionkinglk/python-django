# 5.视图与url分发器

视图一般写在app的views.py中，并且视图的第一个参数永远是request.

视图函数的返回值必须是django.http.response.httpresponseBase的子类的对象

新建app

```
d:\python\envs\zsb-env\zsb>workon zsb-env
(zsb-env) d:\python\envs\zsb-env\zsb>python manage.py startapp enroll
(zsb-env) d:\python\envs\zsb-env\zsb>
```

![](/assets/enroll-file-tree.png)

zsb/enroll/views.py

```
from django.shortcuts import render
from django.http import HttpResponse
# Create your views here.
def enroll(request):
    return HttpResponse("报名首页")
```

zsb/zsb/urls.py

```
from django.contrib import admin
from django.urls import path
from enroll import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('enroll/', views.enroll),
]
```

预览

![](/assets/enrollhtml.png)

