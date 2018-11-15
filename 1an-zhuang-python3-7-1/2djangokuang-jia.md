# 2.django框架

Django 是一个 Web 框架，框架的作用在于处理 request 和 reponse，其他的不是框架所关心的内容。所以怎么部署 Django 不是 Django 所需要关心的。

Django 所提供的是一个开发服务器，这个开发服务器，没有经过安全测试，而且使用的是 Python 自带的 simple HTTPServer 创建的，在安全性和效率上都是不行的，而uWSGI 是一个全功能的 HTTP 服务器，他要做的就是把 HTTP 协议转化成语言支持的网络协议。比如把 HTTP 协议转化成 WSGI 协议，让 Python 可以直接使用。 

uwsgi 是一种 uWSGI 的内部协议，使用二进制方式和其他应用程序进行通信。



