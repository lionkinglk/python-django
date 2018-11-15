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

# 



