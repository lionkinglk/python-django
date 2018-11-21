# 3.ORM模型操作数据库

Object Relational Mapping 对象关系映射，通过壳的方式去操作数据库，而不用写原生SQL语句

**通过把表映射成类，把行映射作实例，把字段映射作属性。**

### 创建ORM模型：

在mysql管理器中新建一个数据库orm\_intro，不用建表和表结构，下面通过ORM建立。

settings.py设置数据库连接：

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        # 'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
        'NAME': 'orm_intro',
        'USER': 'root',
        'PASSWORD': '',
        'HOST': '127.0.0.1',
        'PORT': '3306'
    }
}
```

创建一个新的应用orm：

```
Microsoft Windows [版本 10.0.17134.407]
(c) 2018 Microsoft Corporation。保留所有权利。

C:\Users\jkden>workon zsb_env

    virtualenv "zsb_env" does not exist.
    Create it with "mkvirtualenv "

C:\Users\jkden>workon zsb-env
(zsb-env) C:\Users\jkden>cdvirtualenv zsb-env
(zsb-env) d:\python\envs\zsb-env>python manage.py startapp orm
python: can't open file 'manage.py': [Errno 2] No such file or directory

(zsb-env) d:\python\envs\zsb-env>cd zsb

(zsb-env) d:\python\envs\zsb-env\zsb>python manage.py startapp orm

(zsb-env) d:\python\envs\zsb-env\zsb>
```

orm应用的目录结构：包含一个models.py，所有和数据有关的都放在这个models.py中。

![](/assets/orm.png)

创建ORM模型，即数据库结构：

models.py

```
from django.db import models

# Create your models here.

# 将一个普通的类变成可以映射到数据库中的ORM模型
# 必须将父类设置为models.Model或者它的子类


class Book(models.Model):
    # 定义模型，即数据库结构
    id = models.AutoField(primary_key=True)
    name = models.CharField(max_length=100, null=False)
    author = models.CharField(max_length=100, null=False)
    price = models.FloatField(null=False, default=0)
```

将应用orm添加到settings.py中：则在orm应用中创建的ORM模型就可以映射到数据库中

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'orm'
]
```

再用命令行将ORM映射到数据库：

1. 使用makemigrations 生成迁移脚本文件
2. 使用migrate 将新生成的脚本文件映射以数据库

```
(zsb-env) d:\python\envs\zsb-env\zsb>python manage.py makemigrations
Migrations for 'orm':
  orm\migrations\0001_initial.py
    - Create model Book

(zsb-env) d:\python\envs\zsb-env\zsb>python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, orm, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying auth.0001_initial... OK
  Applying admin.0001_initial... OK
  Applying admin.0002_logentry_remove_auto_add... OK
  Applying admin.0003_logentry_add_action_flag_choices... OK
  Applying contenttypes.0002_remove_content_type_name... OK
  Applying auth.0002_alter_permission_name_max_length... OK
  Applying auth.0003_alter_user_email_max_length... OK
  Applying auth.0004_alter_user_username_opts... OK
  Applying auth.0005_alter_user_last_login_null... OK
  Applying auth.0006_require_contenttypes_0002... OK
  Applying auth.0007_alter_validators_add_error_messages... OK
  Applying auth.0008_alter_user_username_max_length... OK
  Applying auth.0009_alter_user_last_name_max_length... OK
  Applying orm.0001_initial... OK
  Applying sessions.0001_initial... OK

(zsb-env) d:\python\envs\zsb-env\zsb>
```

那么，在mySQL管理中，可以看到已经生成的表及结构：

![](/assets/orm_mysql_migrate.png)在models.py中，另建一个类

```
class Publishers(models.Model):
    # id字段会自动添加
    name = models.CharField(max_length=100, null=False)
    address = models.CharField(max_length=100, null=False)
```

再使用命令生成迁移脚本，并映射到数据库

```
(zsb-env) d:\python\envs\zsb-env\zsb>python manage.py makemigrations
Migrations for 'orm':
  orm\migrations\0002_publishers.py
    - Create model Publishers

(zsb-env) d:\python\envs\zsb-env\zsb>python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, orm, sessions
Running migrations:
  Applying orm.0002_publishers... OK

(zsb-env) d:\python\envs\zsb-env\zsb>
```





