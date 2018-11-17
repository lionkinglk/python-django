# 2.模板中使用变量

在views.py中，定义一个context上下文字典，里面可以包含列表\[\]和元组\(\)

```
    context = {
        'username': 'lionkinglk'
    }
```

在模板文件index.html中使用{{  }}访问字典中的键值

```
{{ username }}
```

---

可以在views.py中建立一个对象，在index.html中使用**.点**的方式访问其属性

```
class Person(object):
    def __init__(self, username):
        self.username = username


def index(request):
    p = Person("张三")
    context = {
        'person':p
    }
    return render(request, 'index.html', context=context)
```

```
{{ person.username }}
```

context是一个字典：

```
def index(request):
    context = {
        'book': {
            'bookname': '三国演义',
            'author': '罗贯中'
        },
        'store': {
            'storename': '西单图书大厦',
            'telephone': '010-77889911'
        }
    }
    return render(request, 'index.html', context=context)
```

```
<!DOCTYPE html>
<html lang="zh_cn">
<head>
    <meta charset="UTF-8">
    <title>渲染模板</title>
</head>
<body>
    <h1>这是从模板中渲染得到的html文件</h1>
    {{ book.bookname }}<hr>
    {{ book.author }}<hr>
    {{ store.storename }}<hr>
    {{ store.telephone }}<hr>
</body>
</html>
```

chrome中预览：

# 这是从模板中渲染得到的html文件

三国演义

---

罗贯中

---

西单图书大厦

---

010-77889911

---



但是字典的key不能用python字典的属性名,如keys、values、items等

```
from django.shortcuts import render
# Create your views here.


def index(request):
    context = {
        'book': {
            'bookname': '三国演义',
            'author': '罗贯中',
            #但是字典的key不能用python字典的属性名,如keys、values、items等
            'keys': '不能用'
        }
    }
    return render(request, 'index.html', context=context)

```

如果用了keys，那么用

```
{{book.keys}}
```

渲染时，会得到

# 这是从模板中渲染得到的html文件

不能用

去掉keys，则应该返回字典的所有keys

dict\_keys\(\['bookname', 'author'\]\)

---

context字典也可以是一个列表或元组

```
from django.shortcuts import render
# Create your views here.


def index(request):
    context = {
        'books': ['三国演义',
                  '西游记',
                  '红楼梦',
                  '水浒传']
    }
    return render(request, 'index.html', context=context)

```

使用渲染

得到：三国演义 

