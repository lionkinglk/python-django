# 3.DTL常用标签

在index.html模板文件中，输入标签时，可以使用tab快捷键

如 输入 if，再按tab键

即可自动补充完整代码段：

```
    {% if 光标位于此处等待进一步输入 %}

    {% endif %}
```

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
    <ul>
        {% for book in books %}
            <li>{{ book }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

反向遍历 reversed

```
    <ul>
        {% for book in books reversed %}
            <li>{{ book }}</li>
        {% endfor %}
    </ul>
```

可以使用python中对字典属性，items,keys,values

```
from django.shortcuts import render
# Create your views here.


def index(request):
    context = {
        'books': ['三国演义',
                  '西游记',
                  '红楼梦',
                  '水浒传'],
        'author': {
            'name': '施耐庵',
            'age': 80,
            'sex': '男'
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
    <ul>
        {% for book in books reversed %}
            <li>{{ book }}</li>
        {% endfor %}
    </ul>
    <ul>
        {% for key in author.keys %}
            <li>{{ key }}</li>
        {% endfor %}
    </ul>
    <ul>
        {% for value in author.values %}
            <li>{{ value }}</li>
        {% endfor %}
    </ul>
    <ul>
        {% for key,value in author.items %}
            <li>{{ key}}:{{value }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

DTL中for中提供的一些变量：

forloop.counter：当前循环的下标。以1作为起始值。

forloop.counter0：当前循环的下标。以0作为起始值。

forloop.revcounter：当前循环的反向下标值。比如列表有5个元素，那么第一次遍历这个属性是等于5，第二次是4，以此类推。并且是以1作为最后一个元素的下标。

forloop.revcounter0：类似于forloop.revcounter。不同的是最后一个元素的下标是从0开始。

forloop.first：是否是第一次遍历。

forloop.last：是否是最后一次遍历。

forloop.parentloop：如果有多个循环嵌套，那么这个属性代表的是上一级的for循环。

```
from django.shortcuts import render
# Create your views here.


def index(request):
    context = {
        'authors': [
            {'name': '施耐庵',
             'age': 80,
             'sex': '男'},
            {'name': '罗贯中',
             'age': 90,
             'sex': '男'},
            {'name': '某女女',
             'age': 18,
             'sex': '女'}
        ]
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
    <table>
        <thead>
            <tr>
                <td>NO.</td>
                <td>name</td>
                <td>age</td>
                <td>sex</td>
            </tr>
        </thead>
        <tbody>
            {% for author in authors %}
                {% if forloop.first %}
                    <tr style="background-color: aqua">
                {% elif forloop.last %}
                    <tr style="background-color: palevioletred">
                {% else %}
                    <tr>
                {% endif %}
                        <td>{{ forloop.counter }}</td>
                        <td>{{ author.name }}</td>
                        <td>{{ author.age }}</td>
                        <td>{{ author.sex }}</td>
                    </tr>
            {% endfor %}
        </tbody>
    </table>
</body>
</html>
```





