# 1.web服务器与应用服务器

通俗的讲，Web服务器传送页面使浏览器可以浏览，然而应用程序服务器提供的是客户端应用程序可以调用\(call\)的方法\(methods\)。确切一点，你可以说：Web服务器专门处理HTTP请求\(request\)，但是应用程序服务器是通过很多协议来为应用程序提供\(serves\)商业逻辑\(business logic\)。

应用服务器处理业务逻辑，web服务器则主要是让客户可以通过浏览器进行访问。 

 应用服务器处理业务逻辑，web服务器是用于处理HTML文件的。

web服务器通常比应用服务器简单，如apache就是web服务器，Jboss就是EJB应用服务器。  

应用服务器：Weblogic、Tomcat、Jboss 、wsgi

WEB SERVER：IIS、 Apache、Nginx

### uwsgi??

#### WSGI

WSGI是一种WEB服务器==网关接口==。 是一个Web服务器（如nginx）与应用服务器（如uWSGI）通信的一种规范（协议）。

在生产环境中使用WSGI作为python web的服务器。Python Web服务器网关接口，是Python应用程序或框架和Web服务器之间的一种接口，被广泛接受。WSGI没有官方的实现, 因为WSGI更像一个协议，只要遵照这些协议，WSGI应用\(Application\)都可以在任何服务器\(Server\)上运行。

#### uWSGI

uWSGI实现了WSGI的所有接口，是一个快速、自我修复、开发人员和系统管理员友好的服务器。uWSGI代码完全用C编写，效率高、性能稳定。

uwsgi是一种线路协议而不是通信协议，在此常用于在uWSGI服务器与其他网络服务器的数据通信。uwsgi协议是一个uWSGI服务器自有的协议，它用于定义传输信息的类型。



