# 3.项目结构介绍

![](/assets/zsb.png)

manage.py 和项目交互的命令，如以上用到的python manage.py runserver

settings.py 配置信息

urls.py URL路由，用来做url与视图函数映射的，一个url请求对应一个视图页面

wsgi.py 项目与WSGI协议兼容的web服务器入口，部署时需用到

