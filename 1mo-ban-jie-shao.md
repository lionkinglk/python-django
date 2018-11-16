# 1.模板介绍

视图函数只能返回文本，实际页面大多是带有样式的html代码

模板系统有DTL（Django Template Language）和Jinja2。

DTL是Django内置的模板语言，Jinja2用于flask。

### DTL

是带有特殊语法的HTML文件，可以被Django编译，传递参数进去，实现数据动态化。编译完成后生成一个HTML文件，发送给客户端。

enroll/views.py

```
from django.shortcuts import render
# Create your views here.
def index(request):
    return render(request,'index.html')
```

zsb/urls.py

```
from django.urls import path
from enroll import views

urlpatterns = [
    path('', views.index),
]
```

在项目zsb文件夹下建立templates目录，在templates目录新建一个index.html文件

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>渲染模板</title>
    <h1>这是从模板中渲染得到的html文件</h1>
</head>
<body>

</body>
</html>
```

此时访问[http://127.0.0.1:8000/，会返回错误](http://127.0.0.1:8000/，会返回错误)

```
TemplateDoesNotExist at /
index.html
Request Method:    GET
Request URL:    http://127.0.0.1:8000/
Django Version:    2.1.3
Exception Type:    TemplateDoesNotExist
Exception Value:    
index.html
Exception Location:    D:\python\envs\zsb-env\lib\site-packages\django\template\loader.py in get_template, line 19
Python Executable:    D:\python\envs\zsb-env\Scripts\python.exe
Python Version:    3.7.1
Python Path:    
['D:\\python\\envs\\zsb-env\\zsb',
 'D:\\python\\envs\\zsb-env\\zsb',
 'D:\\python\\envs\\zsb-env\\Scripts\\python37.zip',
 'D:\\python\\envs\\zsb-env\\DLLs',
 'D:\\python\\envs\\zsb-env\\lib',
 'D:\\python\\envs\\zsb-env\\Scripts',
 'd:\\python37\\Lib',
 'd:\\python37\\DLLs',
 'D:\\python\\envs\\zsb-env',
 'D:\\python\\envs\\zsb-env\\lib\\site-packages',
 'D:\\Program Files\\JetBrains\\PyCharm '
 '2018.2.5\\helpers\\pycharm_matplotlib_backend']
Server time:    Fri, 16 Nov 2018 08:31:56 +0000
Template-loader postmortem
Django tried loading these templates, in this order:

Using engine django:

django.template.loaders.app_directories.Loader: D:\python\envs\zsb-env\lib\site-packages\django\contrib\admin\templates\index.html (Source does not exist)
django.template.loaders.app_directories.Loader: D:\python\envs\zsb-env\lib\site-packages\django\contrib\auth\templates\index.html (Source does not exist)
Traceback Switch to copy-and-paste view

```

应该先在zsb/settings.py中指定模板文件的位置

```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': ['templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```

```
os.path.join(BASE_DIR, 'templates')
```



