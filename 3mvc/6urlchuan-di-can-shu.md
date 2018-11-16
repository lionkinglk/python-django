# 6.URL传递参数

在URL中加入参数 path\('enroll/&lt;enroll\_id&gt;', views.enroll\_detail\)

在VIEWS中加入带该参数的视图函数 def enroll\_detail\(request,enroll\_id\):

zsb/enroll/views.py

```
from django.shortcuts import render
from django.http import HttpResponse
# Create your views here.
def enroll(request):
    return HttpResponse("报名首页")
def enroll_detail(request,enroll_id):
    text = "报名人员id是 %s" % enroll_id
    return HttpResponse(text)
```

zsb/zsb/urls.py

```
from django.contrib import admin
from django.urls import path
from enroll import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('enroll/', views.enroll),
    path('enroll/<enroll_id>', views.enroll_detail)
]
```

预览

![](/assets/url_parm.png)

