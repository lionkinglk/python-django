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



