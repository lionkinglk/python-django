# 3.DTL常用标签

### if标签

可以使用if...elif...else...endif

可以使用python中的比较运算符

```
from django.shortcuts import render
# Create your views here.


def index(request):
    context = {
        'age': 18
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
    <hr>
    {% if age >= 18 %}
        <p>您是成年人了</p>
    {% elif age == 18 %}
        <p>您刚刚18岁，小了点儿</p>
    {% else %}
        <p>你还是未成年人</p>
    {% endif %}
</body>
</html>
```

也可以使用in, not in, is, is not等判断运算符

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

```
<!DOCTYPE html>
<html lang="zh_cn">
<head>
    <meta charset="UTF-8">
    <title>渲染模板</title>
</head>
<body>
    <h1>这是从模板中渲染得到的html文件</h1>
    <hr>
    {% if '三国演义' in books %}
        <p>图书馆中有你要的三国演义</p>
    {% else %}
        <p>图书馆中没有三国演义</p>
    {% endif %}
</body>
</html>
```

### for...in...标签









