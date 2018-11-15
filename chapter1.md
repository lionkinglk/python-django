# 1.安装python3.7.1

[https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)

win10 64bit环境

安装时，勾选安装到系统环境变量、pip等，升级pip

```
C:\Users\jkden>python
Python 3.7.1 (v3.7.1:260ec2c36a, Oct 20 2018, 14:57:15) [MSC v.1915 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.

C:\Users\jkden>pip list
Package    Version
---------- -------
pip        10.0.1
setuptools 39.0.1
You are using pip version 10.0.1, however version 18.1 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.

C:\Users\jkden>python -m pip install --upgrade pip
Collecting pip
  Using cached https://files.pythonhosted.org/packages/c2/d7/90f34cb0d83a6c5631cf71dfe64cc1054598c843a92b400e55675cc2ac37/pip-18.1-py2.py3-none-any.whl
Installing collected packages: pip
  Found existing installation: pip 10.0.1
    Uninstalling pip-10.0.1:
      Successfully uninstalled pip-10.0.1
Successfully installed pip-18.1
```

# 2.安装虚拟环境virtualenvwrapper

用于python、django等的版本控制

```
C:\Users\jkden>pip install virtualenvwrapper-win
Collecting virtualenvwrapper-win
  Downloading https://files.pythonhosted.org/packages/f5/23/4cba98733b9122219ce67177d745e4984b524b867cf3728eaa807ea21919/virtualenvwrapper-win-1.2.5.tar.gz
Collecting virtualenv (from virtualenvwrapper-win)
  Downloading https://files.pythonhosted.org/packages/7c/17/9b7b6cddfd255388b58c61e25b091047f6814183e1d63741c8df8dcd65a2/virtualenv-16.1.0-py2.py3-none-any.whl (1.9MB)
    100% |████████████████████████████████| 1.9MB 3.2MB/s
Installing collected packages: virtualenv, virtualenvwrapper-win
  Running setup.py install for virtualenvwrapper-win ... done
Successfully installed virtualenv-16.1.0 virtualenvwrapper-win-1.2.5
```

新建系统环境变量：WORKON\_HOME     d:\python\envs\

重启CMD

创建虚拟环境：mkvirtualenv zsb-env

退出虚拟环境：deactivate

进入虚拟环境：workon zsb-env

```
Microsoft Windows [版本 10.0.17134.407]
(c) 2018 Microsoft Corporation。保留所有权利。

C:\Users\jkden>mkvirtualenv zsb-env
Using base prefix 'd:\\python37'
New python executable in d:\python\envs\zsb-env\Scripts\python.exe
Installing setuptools, pip, wheel...
done.

(zsb-env) C:\Users\jkden>deactivate

C:\Users\jkden>workon zsb-env
(zsb-env) C:\Users\jkden>
```

列出所有虚拟环境：lsvirtualenv

删除某个虚拟环境：rmvirtualenv

进入到虚拟环境所在目录：cdvirtualenv zsb-env

```
C:\Users\jkden>workon zsb-env
(zsb-env) C:\Users\jkden>deactivate

C:\Users\jkden>lsvirtualenv

dir /b /ad "d:\python\envs\"
==============================================================================
zsb-env

C:\Users\jkden>cdvirtualenv zsb-env
D:\Python37>
D:\Python37>workon zsb-env
(zsb-env) D:\Python37>cdvirtualenv zsb-env
(zsb-env) d:\python\envs\zsb-env>
```

# 3.在虚拟环境下安装django

```
(zsb-env) d:\python\envs\zsb-env>pip install django
Collecting django
  Using cached https://files.pythonhosted.org/packages/d1/e5/2676be45ea49cfd09a663f289376b3888accd57ff06c953297bfdee1fb08/Django-2.1.3-py3-none-any.whl
Collecting pytz (from django)
  Downloading https://files.pythonhosted.org/packages/f8/0e/2365ddc010afb3d79147f1dd544e5ee24bf4ece58ab99b16fbb465ce6dc0/pytz-2018.7-py2.py3-none-any.whl (506kB)
    100% |████████████████████████████████| 512kB 5.1MB/s
Installing collected packages: pytz, django
Successfully installed django-2.1.3 pytz-2018.7
```

# 4.下载安装pycharm

[https://www.jetbrains.com/pycharm/download/\#section=windows](https://www.jetbrains.com/pycharm/download/#section=windows)

Professional版本

修改hosts文件：将0.0.0.0 account.jetbrains.com添加到hosts文件最后

复制激活码

```
K71U8DBPNE-eyJsaWNlbnNlSWQiOiJLNzFVOERCUE5FIiwibGljZW5zZWVOYW1lIjoibGFuIHl1IiwiYXNzaWduZWVOYW1lIjoiIiwiYXNzaWduZWVFbWFpbCI6IiIsImxpY2Vuc2VSZXN0cmljdGlvbiI6IkZvciBlZHVjYXRpb25hbCB1c2Ugb25seSIsImNoZWNrQ29uY3VycmVudFVzZSI6ZmFsc2UsInByb2R1Y3RzIjpbeyJjb2RlIjoiSUkiLCJwYWlkVXBUbyI6IjIwMTktMDUtMDQifSx7ImNvZGUiOiJSUzAiLCJwYWlkVXBUbyI6IjIwMTktMDUtMDQifSx7ImNvZGUiOiJXUyIsInBhaWRVcFRvIjoiMjAxOS0wNS0wNCJ9LHsiY29kZSI6IlJEIiwicGFpZFVwVG8iOiIyMDE5LTA1LTA0In0seyJjb2RlIjoiUkMiLCJwYWlkVXBUbyI6IjIwMTktMDUtMDQifSx7ImNvZGUiOiJEQyIsInBhaWRVcFRvIjoiMjAxOS0wNS0wNCJ9LHsiY29kZSI6IkRCIiwicGFpZFVwVG8iOiIyMDE5LTA1LTA0In0seyJjb2RlIjoiUk0iLCJwYWlkVXBUbyI6IjIwMTktMDUtMDQifSx7ImNvZGUiOiJETSIsInBhaWRVcFRvIjoiMjAxOS0wNS0wNCJ9LHsiY29kZSI6IkFDIiwicGFpZFVwVG8iOiIyMDE5LTA1LTA0In0seyJjb2RlIjoiRFBOIiwicGFpZFVwVG8iOiIyMDE5LTA1LTA0In0seyJjb2RlIjoiR08iLCJwYWlkVXBUbyI6IjIwMTktMDUtMDQifSx7ImNvZGUiOiJQUyIsInBhaWRVcFRvIjoiMjAxOS0wNS0wNCJ9LHsiY29kZSI6IkNMIiwicGFpZFVwVG8iOiIyMDE5LTA1LTA0In0seyJjb2RlIjoiUEMiLCJwYWlkVXBUbyI6IjIwMTktMDUtMDQifSx7ImNvZGUiOiJSU1UiLCJwYWlkVXBUbyI6IjIwMTktMDUtMDQifV0sImhhc2giOiI4OTA4Mjg5LzAiLCJncmFjZVBlcmlvZERheXMiOjAsImF1dG9Qcm9sb25nYXRlZCI6ZmFsc2UsImlzQXV0b1Byb2xvbmdhdGVkIjpmYWxzZX0=-Owt3/+LdCpedvF0eQ8635yYt0+ZLtCfIHOKzSrx5hBtbKGYRPFDrdgQAK6lJjexl2emLBcUq729K1+ukY9Js0nx1NH09l9Rw4c7k9wUksLl6RWx7Hcdcma1AHolfSp79NynSMZzQQLFohNyjD+dXfXM5GYd2OTHya0zYjTNMmAJuuRsapJMP9F1z7UTpMpLMxS/JaCWdyX6qIs+funJdPF7bjzYAQBvtbz+6SANBgN36gG1B2xHhccTn6WE8vagwwSNuM70egpahcTktoHxI7uS1JGN9gKAr6nbp+8DbFz3a2wd+XoF3nSJb/d2f/6zJR8yJF8AOyb30kwg3zf5cWw==-MIIEPjCCAiagAwIBAgIBBTANBgkqhkiG9w0BAQsFADAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBMB4XDTE1MTEwMjA4MjE0OFoXDTE4MTEwMTA4MjE0OFowETEPMA0GA1UEAwwGcHJvZDN5MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAxcQkq+zdxlR2mmRYBPzGbUNdMN6OaXiXzxIWtMEkrJMO/5oUfQJbLLuMSMK0QHFmaI37WShyxZcfRCidwXjot4zmNBKnlyHodDij/78TmVqFl8nOeD5+07B8VEaIu7c3E1N+e1doC6wht4I4+IEmtsPAdoaj5WCQVQbrI8KeT8M9VcBIWX7fD0fhexfg3ZRt0xqwMcXGNp3DdJHiO0rCdU+Itv7EmtnSVq9jBG1usMSFvMowR25mju2JcPFp1+I4ZI+FqgR8gyG8oiNDyNEoAbsR3lOpI7grUYSvkB/xVy/VoklPCK2h0f0GJxFjnye8NT1PAywoyl7RmiAVRE/EKwIDAQABo4GZMIGWMAkGA1UdEwQCMAAwHQYDVR0OBBYEFGEpG9oZGcfLMGNBkY7SgHiMGgTcMEgGA1UdIwRBMD+AFKOetkhnQhI2Qb1t4Lm0oFKLl/GzoRykGjAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBggkA0myxg7KDeeEwEwYDVR0lBAwwCgYIKwYBBQUHAwEwCwYDVR0PBAQDAgWgMA0GCSqGSIb3DQEBCwUAA4ICAQC9WZuYgQedSuOc5TOUSrRigMw4/+wuC5EtZBfvdl4HT/8vzMW/oUlIP4YCvA0XKyBaCJ2iX+ZCDKoPfiYXiaSiH+HxAPV6J79vvouxKrWg2XV6ShFtPLP+0gPdGq3x9R3+kJbmAm8w+FOdlWqAfJrLvpzMGNeDU14YGXiZ9bVzmIQbwrBA+c/F4tlK/DV07dsNExihqFoibnqDiVNTGombaU2dDup2gwKdL81ua8EIcGNExHe82kjF4zwfadHk3bQVvbfdAwxcDy4xBjs3L4raPLU3yenSzr/OEur1+jfOxnQSmEcMXKXgrAQ9U55gwjcOFKrgOxEdek/Sk1VfOjvS+nuM4eyEruFMfaZHzoQiuw4IqgGc45ohFH0UUyjYcuFxxDSU9lMCv8qdHKm+wnPRb0l9l5vXsCBDuhAGYD6ss+Ga+aDY6f/qXZuUCEUOH3QUNbbCUlviSz6+GiRnt1kA9N2Qachl+2yBfaqUqr8h7Z2gsx5LcIf5kYNsqJ0GavXTVyWh7PYiKX4bs354ZQLUwwa/cG++2+wNWP+HtBhVxMRNTdVhSm38AknZlD+PTAsWGu9GyLmhti2EnVwGybSD2Dxmhxk3IPCkhKAK+pl0eWYGZWG3tJ9mZ7SowcXLWDFAk0lRJnKGFMTggrWjV8GYpw5bq23VmIqqDLgkNzuoog==
```

打开PyCharm选择Activation code激活，然后复制下面的激活码点击激活。

# 5.数据库MySQL

下载安装MySQL，或使用Laragon、phpstudy等集成环境

[https://laragon.org/](https://laragon.org/)

# 6.安装pymysql库

```
(zsb-env) d:\python\envs\zsb-env>pip install pymysql
Collecting pymysql
  Downloading https://files.pythonhosted.org/packages/a7/7d/682c4a7da195a678047c8f1c51bb7682aaedee1dca7547883c3993ca9282/PyMySQL-0.9.2-py2.py3-none-any.whl (47kB)
    100% |████████████████████████████████| 51kB 182kB/s
Collecting cryptography (from pymysql)
  Downloading https://files.pythonhosted.org/packages/5a/cb/e723c4a2b810ee2cdbc6b6bc93b6d28b78f2504361c7b3c8977fdcf49b9d/cryptography-2.4.1-cp37-cp37m-win_amd64.whl (1.3MB)
    100% |████████████████████████████████| 1.3MB 356kB/s
Collecting cffi!=1.11.3,>=1.7 (from cryptography->pymysql)
  Downloading https://files.pythonhosted.org/packages/ca/f2/e375b7469a2dfe9d1feac81a10df97f18cd771b9a10ac62ca9864b760f7c/cffi-1.11.5-cp37-cp37m-win_amd64.whl (165kB)
    100% |████████████████████████████████| 174kB 664kB/s
Collecting six>=1.4.1 (from cryptography->pymysql)
  Downloading https://files.pythonhosted.org/packages/67/4b/141a581104b1f6397bfa78ac9d43d8ad29a7ca43ea90a2d863fe3056e86a/six-1.11.0-py2.py3-none-any.whl
Collecting asn1crypto>=0.21.0 (from cryptography->pymysql)
  Downloading https://files.pythonhosted.org/packages/ea/cd/35485615f45f30a510576f1a56d1e0a7ad7bd8ab5ed7cdc600ef7cd06222/asn1crypto-0.24.0-py2.py3-none-any.whl (101kB)
    100% |████████████████████████████████| 102kB 3.2MB/s
Collecting idna>=2.1 (from cryptography->pymysql)
  Downloading https://files.pythonhosted.org/packages/4b/2a/0276479a4b3caeb8a8c1af2f8e4355746a97fab05a372e4a2c6a6b876165/idna-2.7-py2.py3-none-any.whl (58kB)
    100% |████████████████████████████████| 61kB 2.3MB/s
Collecting pycparser (from cffi!=1.11.3,>=1.7->cryptography->pymysql)
  Downloading https://files.pythonhosted.org/packages/68/9e/49196946aee219aead1290e00d1e7fdeab8567783e83e1b9ab5585e6206a/pycparser-2.19.tar.gz (158kB)
    100% |████████████████████████████████| 163kB 3.8MB/s
Building wheels for collected packages: pycparser
  Running setup.py bdist_wheel for pycparser ... done
  Stored in directory: C:\Users\jkden\AppData\Local\pip\Cache\wheels\f2\9a\90\de94f8556265ddc9d9c8b271b0f63e57b26fb1d67a45564511
Successfully built pycparser
Installing collected packages: pycparser, cffi, six, asn1crypto, idna, cryptography, pymysql
Successfully installed asn1crypto-0.24.0 cffi-1.11.5 cryptography-2.4.1 idna-2.7 pycparser-2.19 pymysql-0.9.2 six-1.11.0
```



