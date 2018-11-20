# 5.数据库MySQL

下载安装MySQL，或使用Laragon、phpstudy等集成环境

[https://laragon.org/](https://laragon.org/)

```
Microsoft Windows [版本 10.0.17134.407]
(c) 2018 Microsoft Corporation。保留所有权利。

C:\Users\jkden>workon zsb-env
(zsb-env) C:\Users\jkden>cdvirtualenv zsb-env
(zsb-env) d:\python\envs\zsb-env>pip install mysqlclient
```

提示错误：

```
    building '_mysql' extension
    error: Microsoft Visual C++ 14.0 is required. Get it with "Microsoft Visual C++ Build Tools": https://visualstudio.microsoft.com/downloads/
```

到https://www.lfd.uci.edu/~gohlke/pythonlibs/找到mysqlclient编译包下载对应版本：

```
(zsb-env) d:\python\envs\zsb-env>pip install mysqlclient-1.3.13-cp37-cp37m-win_amd64.whl
Processing .\mysqlclient-1.3.13-cp37-cp37m-win_amd64.whl
Installing collected packages: mysqlclient
Successfully installed mysqlclient-1.3.13

(zsb-env) d:\python\envs\zsb-env>pip list
Package      Version
------------ -------
asn1crypto   0.24.0
cffi         1.11.5
cryptography 2.4.1
Django       2.1.3
idna         2.7
mysqlclient  1.3.13
pip          18.1
pycparser    2.19
PyMySQL      0.9.2
pytz         2018.7
setuptools   40.6.2
six          1.11.0
wheel        0.32.2

(zsb-env) d:\python\envs\zsb-env>
```

把以前安装的PyMySQL删除：

```
(zsb-env) d:\python\envs\zsb-env>pip uninstall pymysql
Uninstalling PyMySQL-0.9.2:
  Would remove:
    d:\python\envs\zsb-env\lib\site-packages\pymysql-0.9.2.dist-info\*
    d:\python\envs\zsb-env\lib\site-packages\pymysql\*
Proceed (y/n)? y
  Successfully uninstalled PyMySQL-0.9.2

(zsb-env) d:\python\envs\zsb-env>pip list
Package      Version
------------ -------
asn1crypto   0.24.0
cffi         1.11.5
cryptography 2.4.1
Django       2.1.3
idna         2.7
mysqlclient  1.3.13
pip          18.1
pycparser    2.19
pytz         2018.7
setuptools   40.6.2
six          1.11.0
wheel        0.32.2
```



