# 1.命令行方式创建

进入到虚拟环境目录下

### 创建项目

```
(zsb-env) d:\python\envs\zsb-env>django-admin startproject zsb
(zsb-env) d:\python\envs\zsb-env>cd zsb

(zsb-env) d:\python\envs\zsb-env\zsb>dir
 驱动器 D 中的卷是 Work
 卷的序列号是 B93C-3380

 d:\python\envs\zsb-env\zsb 的目录

2018/11/15  14:34    <DIR>          .
2018/11/15  14:34    <DIR>          ..
2018/11/15  14:34               550 manage.py
2018/11/15  14:34    <DIR>          zsb
               1 个文件            550 字节
               3 个目录 299,580,813,312 可用字节
```

![](/assets/zsb.png)

### 运行项目

```
(zsb-env) d:\python\envs\zsb-env\zsb>python manage.py runserver
Performing system checks...

System check identified no issues (0 silenced).

You have 15 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
November 15, 2018 - 14:38:36
Django version 2.1.3, using settings 'zsb.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```

### 浏览器中预览![](/assets/django_default_page.png)

### 

### 



