# 1.模板介绍

视图函数只能返回文本，实际页面大多是带有样式的html代码

模板系统有DTL（Django Template Language）和Jinja2。

DTL是Django内置的模板语言，Jinja2用于flask。

### DTL

是带有特殊语法的HTML文件，可以被Django编译，传递参数进去，实现数据动态化。编译完成后生成一个HTML文件，发送给客户端。

enroll/views.py

```
from django.shortcuts import render
# Create your views here.
def index(request):
    return render(request,'index.html')
```

zsb/urls.py

```
from django.urls import path
from enroll import views

urlpatterns = [
    path('', views.index),
]

```

在项目zsb文件夹下建立templates目录，在templates目录新建一个index.html文件

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>渲染模板</title>
    <h1>这是从模板中渲染得到的html文件</h1>
</head>
<body>

</body>
</html>
```

此时访问http://127.0.0.1:8000/，会返回错误

```
TemplateDoesNotExist at /
index.html
Request Method:	GET
Request URL:	http://127.0.0.1:8000/
Django Version:	2.1.3
Exception Type:	TemplateDoesNotExist
Exception Value:	
index.html
Exception Location:	D:\python\envs\zsb-env\lib\site-packages\django\template\loader.py in get_template, line 19
Python Executable:	D:\python\envs\zsb-env\Scripts\python.exe
Python Version:	3.7.1
Python Path:	
['D:\\python\\envs\\zsb-env\\zsb',
 'D:\\python\\envs\\zsb-env\\zsb',
 'D:\\python\\envs\\zsb-env\\Scripts\\python37.zip',
 'D:\\python\\envs\\zsb-env\\DLLs',
 'D:\\python\\envs\\zsb-env\\lib',
 'D:\\python\\envs\\zsb-env\\Scripts',
 'd:\\python37\\Lib',
 'd:\\python37\\DLLs',
 'D:\\python\\envs\\zsb-env',
 'D:\\python\\envs\\zsb-env\\lib\\site-packages',
 'D:\\Program Files\\JetBrains\\PyCharm '
 '2018.2.5\\helpers\\pycharm_matplotlib_backend']
Server time:	Fri, 16 Nov 2018 08:31:56 +0000
Template-loader postmortem
Django tried loading these templates, in this order:

Using engine django:

django.template.loaders.app_directories.Loader: D:\python\envs\zsb-env\lib\site-packages\django\contrib\admin\templates\index.html (Source does not exist)
django.template.loaders.app_directories.Loader: D:\python\envs\zsb-env\lib\site-packages\django\contrib\auth\templates\index.html (Source does not exist)
Traceback Switch to copy-and-paste view
D:\python\envs\zsb-env\lib\site-packages\django\core\handlers\exception.py in inner
            response = get_response(request) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\core\handlers\base.py in _get_response
                response = self.process_exception_by_middleware(e, request) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\core\handlers\base.py in _get_response
                response = wrapped_callback(request, *callback_args, **callback_kwargs) ...
▶ Local vars
D:\python\envs\zsb-env\zsb\enroll\views.py in index
    return render(request,'index.html') ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\shortcuts.py in render
    content = loader.render_to_string(template_name, context, request, using=using) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\template\loader.py in render_to_string
        template = get_template(template_name, using=using) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\template\loader.py in get_template
    raise TemplateDoesNotExist(template_name, chain=chain) ...
▶ Local vars
Request information
USER
AnonymousUser

GET
No GET data

POST
No POST data

FILES
No FILES data

COOKIES
No cookie data

META
Variable	Value
ALLUSERSPROFILE	
'C:\\ProgramData'
APPDATA	
'C:\\Users\\jkden\\AppData\\Roaming'
ASL.LOG	
'Destination=file'
COMMONPROGRAMFILES	
'C:\\Program Files\\Common Files'
COMMONPROGRAMFILES(X86)	
'C:\\Program Files (x86)\\Common Files'
COMMONPROGRAMW6432	
'C:\\Program Files\\Common Files'
COMPUTERNAME	
'DESKTOP-V5ESOMB'
COMSPEC	
'C:\\WINDOWS\\system32\\cmd.exe'
CONTENT_LENGTH	
''
CONTENT_TYPE	
'text/plain'
DJANGO_SETTINGS_MODULE	
'zsb.settings'
DRIVERDATA	
'C:\\Windows\\System32\\Drivers\\DriverData'
FPS_BROWSER_APP_PROFILE_STRING	
'Internet Explorer'
FPS_BROWSER_USER_PROFILE_STRING	
'Default'
GATEWAY_INTERFACE	
'CGI/1.1'
HOMEDRIVE	
'C:'
HOMEPATH	
'\\Users\\jkden'
HTTP_ACCEPT	
'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8'
HTTP_ACCEPT_ENCODING	
'gzip, deflate, br'
HTTP_ACCEPT_LANGUAGE	
'zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7'
HTTP_CACHE_CONTROL	
'max-age=0'
HTTP_CONNECTION	
'keep-alive'
HTTP_HOST	
'127.0.0.1:8000'
HTTP_UPGRADE_INSECURE_REQUESTS	
'1'
HTTP_USER_AGENT	
('Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) '
 'Chrome/70.0.3538.102 Safari/537.36')
LOCALAPPDATA	
'C:\\Users\\jkden\\AppData\\Local'
LOGONSERVER	
'\\\\DESKTOP-V5ESOMB'
NUMBER_OF_PROCESSORS	
'4'
ONEDRIVE	
'C:\\Users\\jkden\\OneDrive'
OS	
'Windows_NT'
PATH	
'D:\\Python37\\Scripts\\;D:\\Python37\\;C:\\WINDOWS\\system32;C:\\WINDOWS;C:\\WINDOWS\\System32\\Wbem;C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\;C:\\WINDOWS\\System32\\OpenSSH\\;C:\\Users\\jkden\\AppData\\Local\\Microsoft\\WindowsApps;D:\\python\\envs\\zsb-env\\Scripts'
PATHEXT	
'.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.PY;.PYW'
PATH_INFO	
'/'
PROCESSOR_ARCHITECTURE	
'AMD64'
PROCESSOR_IDENTIFIER	
'Intel64 Family 6 Model 58 Stepping 9, GenuineIntel'
PROCESSOR_LEVEL	
'6'
PROCESSOR_REVISION	
'3a09'
PROGRAMDATA	
'C:\\ProgramData'
PROGRAMFILES	
'C:\\Program Files'
PROGRAMFILES(X86)	
'C:\\Program Files (x86)'
PROGRAMW6432	
'C:\\Program Files'
PROMPT	
'(zsb-env) $P$G'
PSMODULEPATH	
('C:\\Program '
 'Files\\WindowsPowerShell\\Modules;C:\\WINDOWS\\system32\\WindowsPowerShell\\v1.0\\Modules')
PUBLIC	
'C:\\Users\\Public'
PYCHARM_HOSTED	
'1'
PYCHARM_MATPLOTLIB_PORT	
'59144'
PYTHONIOENCODING	
'UTF-8'
PYTHONPATH	
('D:\\Program Files\\JetBrains\\PyCharm '
 '2018.2.5\\helpers\\pycharm_matplotlib_backend;D:\\python\\envs\\zsb-env\\zsb')
PYTHONUNBUFFERED	
'1'
QUERY_STRING	
''
REMOTE_ADDR	
'127.0.0.1'
REMOTE_HOST	
''
REQUEST_METHOD	
'GET'
RUN_MAIN	
'true'
SCRIPT_NAME	
''
SERVER_NAME	
'DESKTOP-V5ESOMB'
SERVER_PORT	
'8000'
SERVER_PROTOCOL	
'HTTP/1.1'
SERVER_SOFTWARE	
'WSGIServer/0.2'
SESSIONNAME	
'Console'
SYSTEMDRIVE	
'C:'
SYSTEMROOT	
'C:\\WINDOWS'
TEMP	
'C:\\Users\\jkden\\AppData\\Local\\Temp'
TMP	
'C:\\Users\\jkden\\AppData\\Local\\Temp'
USERDOMAIN	
'DESKTOP-V5ESOMB'
USERDOMAIN_ROAMINGPROFILE	
'DESKTOP-V5ESOMB'
USERNAME	
'jkden'
USERPROFILE	
'C:\\Users\\jkden'
VBOX_MSI_INSTALL_PATH	
'D:\\Program Files\\Oracle\\VirtualBox\\'
VIRTUAL_ENV	
'd:\\python\\envs\\zsb-env'
WINDIR	
'C:\\WINDOWS'
WORKON_HOME	
'd:\\python\\envs\\'
_OLD_VIRTUAL_PATH	
'D:\\Python37\\Scripts\\;D:\\Python37\\;C:\\WINDOWS\\system32;C:\\WINDOWS;C:\\WINDOWS\\System32\\Wbem;C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\;C:\\WINDOWS\\System32\\OpenSSH\\;C:\\Users\\jkden\\AppData\\Local\\Microsoft\\WindowsApps'
_OLD_VIRTUAL_PROMPT	
'$P$G'
wsgi.errors	
<_io.TextIOWrapper name='<stderr>' mode='w' encoding='UTF-8'>
wsgi.file_wrapper	
''
wsgi.input	
<_io.BufferedReader name=844>
wsgi.multiprocess	
False
wsgi.multithread	
True
wsgi.run_once	
False
wsgi.url_scheme	
'http'
wsgi.version	
(1, 0)
Settings
Using settings module zsb.settings
Setting	Value
ABSOLUTE_URL_OVERRIDES	
{}
ADMINS	
[]
ALLOWED_HOSTS	
[]
APPEND_SLASH	
True
AUTHENTICATION_BACKENDS	
['django.contrib.auth.backends.ModelBackend']
AUTH_PASSWORD_VALIDATORS	
'********************'
AUTH_USER_MODEL	
'auth.User'
BASE_DIR	
'D:\\python\\envs\\zsb-env\\zsb'
CACHES	
{'default': {'BACKEND': 'django.core.cache.backends.locmem.LocMemCache'}}
CACHE_MIDDLEWARE_ALIAS	
'default'
CACHE_MIDDLEWARE_KEY_PREFIX	
'********************'
CACHE_MIDDLEWARE_SECONDS	
600
CSRF_COOKIE_AGE	
31449600
CSRF_COOKIE_DOMAIN	
None
CSRF_COOKIE_HTTPONLY	
False
CSRF_COOKIE_NAME	
'csrftoken'
CSRF_COOKIE_PATH	
'/'
CSRF_COOKIE_SAMESITE	
'Lax'
CSRF_COOKIE_SECURE	
False
CSRF_FAILURE_VIEW	
'django.views.csrf.csrf_failure'
CSRF_HEADER_NAME	
'HTTP_X_CSRFTOKEN'
CSRF_TRUSTED_ORIGINS	
[]
CSRF_USE_SESSIONS	
False
DATABASES	
{'default': {'ATOMIC_REQUESTS': False,
             'AUTOCOMMIT': True,
             'CONN_MAX_AGE': 0,
             'ENGINE': 'django.db.backends.dummy',
             'HOST': '',
             'NAME': '',
             'OPTIONS': {},
             'PASSWORD': '********************',
             'PORT': '',
             'TEST': {'CHARSET': None,
                      'COLLATION': None,
                      'MIRROR': None,
                      'NAME': None},
             'TIME_ZONE': None,
             'USER': ''}}
DATABASE_ROUTERS	
[]
DATA_UPLOAD_MAX_MEMORY_SIZE	
2621440
DATA_UPLOAD_MAX_NUMBER_FIELDS	
1000
DATETIME_FORMAT	
'N j, Y, P'
DATETIME_INPUT_FORMATS	
['%Y-%m-%d %H:%M:%S',
 '%Y-%m-%d %H:%M:%S.%f',
 '%Y-%m-%d %H:%M',
 '%Y-%m-%d',
 '%m/%d/%Y %H:%M:%S',
 '%m/%d/%Y %H:%M:%S.%f',
 '%m/%d/%Y %H:%M',
 '%m/%d/%Y',
 '%m/%d/%y %H:%M:%S',
 '%m/%d/%y %H:%M:%S.%f',
 '%m/%d/%y %H:%M',
 '%m/%d/%y']
DATE_FORMAT	
'N j, Y'
DATE_INPUT_FORMATS	
['%Y-%m-%d',
 '%m/%d/%Y',
 '%m/%d/%y',
 '%b %d %Y',
 '%b %d, %Y',
 '%d %b %Y',
 '%d %b, %Y',
 '%B %d %Y',
 '%B %d, %Y',
 '%d %B %Y',
 '%d %B, %Y']
DEBUG	
True
DEBUG_PROPAGATE_EXCEPTIONS	
False
DECIMAL_SEPARATOR	
'.'
DEFAULT_CHARSET	
'utf-8'
DEFAULT_CONTENT_TYPE	
'text/html'
DEFAULT_EXCEPTION_REPORTER_FILTER	
'django.views.debug.SafeExceptionReporterFilter'
DEFAULT_FILE_STORAGE	
'django.core.files.storage.FileSystemStorage'
DEFAULT_FROM_EMAIL	
'webmaster@localhost'
DEFAULT_INDEX_TABLESPACE	
''
DEFAULT_TABLESPACE	
''
DISALLOWED_USER_AGENTS	
[]
EMAIL_BACKEND	
'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST	
'localhost'
EMAIL_HOST_PASSWORD	
'********************'
EMAIL_HOST_USER	
''
EMAIL_PORT	
25
EMAIL_SSL_CERTFILE	
None
EMAIL_SSL_KEYFILE	
'********************'
EMAIL_SUBJECT_PREFIX	
'[Django] '
EMAIL_TIMEOUT	
None
EMAIL_USE_LOCALTIME	
False
EMAIL_USE_SSL	
False
EMAIL_USE_TLS	
False
FILE_CHARSET	
'utf-8'
FILE_UPLOAD_DIRECTORY_PERMISSIONS	
None
FILE_UPLOAD_HANDLERS	
['django.core.files.uploadhandler.MemoryFileUploadHandler',
 'django.core.files.uploadhandler.TemporaryFileUploadHandler']
FILE_UPLOAD_MAX_MEMORY_SIZE	
2621440
FILE_UPLOAD_PERMISSIONS	
None
FILE_UPLOAD_TEMP_DIR	
None
FIRST_DAY_OF_WEEK	
0
FIXTURE_DIRS	
[]
FORCE_SCRIPT_NAME	
None
FORMAT_MODULE_PATH	
None
FORM_RENDERER	
'django.forms.renderers.DjangoTemplates'
IGNORABLE_404_URLS	
[]
INSTALLED_APPS	
['django.contrib.admin',
 'django.contrib.auth',
 'django.contrib.contenttypes',
 'django.contrib.sessions',
 'django.contrib.messages',
 'django.contrib.staticfiles']
INTERNAL_IPS	
[]
LANGUAGES	
[('af', 'Afrikaans'),
 ('ar', 'Arabic'),
 ('ast', 'Asturian'),
 ('az', 'Azerbaijani'),
 ('bg', 'Bulgarian'),
 ('be', 'Belarusian'),
 ('bn', 'Bengali'),
 ('br', 'Breton'),
 ('bs', 'Bosnian'),
 ('ca', 'Catalan'),
 ('cs', 'Czech'),
 ('cy', 'Welsh'),
 ('da', 'Danish'),
 ('de', 'German'),
 ('dsb', 'Lower Sorbian'),
 ('el', 'Greek'),
 ('en', 'English'),
 ('en-au', 'Australian English'),
 ('en-gb', 'British English'),
 ('eo', 'Esperanto'),
 ('es', 'Spanish'),
 ('es-ar', 'Argentinian Spanish'),
 ('es-co', 'Colombian Spanish'),
 ('es-mx', 'Mexican Spanish'),
 ('es-ni', 'Nicaraguan Spanish'),
 ('es-ve', 'Venezuelan Spanish'),
 ('et', 'Estonian'),
 ('eu', 'Basque'),
 ('fa', 'Persian'),
 ('fi', 'Finnish'),
 ('fr', 'French'),
 ('fy', 'Frisian'),
 ('ga', 'Irish'),
 ('gd', 'Scottish Gaelic'),
 ('gl', 'Galician'),
 ('he', 'Hebrew'),
 ('hi', 'Hindi'),
 ('hr', 'Croatian'),
 ('hsb', 'Upper Sorbian'),
 ('hu', 'Hungarian'),
 ('ia', 'Interlingua'),
 ('id', 'Indonesian'),
 ('io', 'Ido'),
 ('is', 'Icelandic'),
 ('it', 'Italian'),
 ('ja', 'Japanese'),
 ('ka', 'Georgian'),
 ('kab', 'Kabyle'),
 ('kk', 'Kazakh'),
 ('km', 'Khmer'),
 ('kn', 'Kannada'),
 ('ko', 'Korean'),
 ('lb', 'Luxembourgish'),
 ('lt', 'Lithuanian'),
 ('lv', 'Latvian'),
 ('mk', 'Macedonian'),
 ('ml', 'Malayalam'),
 ('mn', 'Mongolian'),
 ('mr', 'Marathi'),
 ('my', 'Burmese'),
 ('nb', 'Norwegian Bokmål'),
 ('ne', 'Nepali'),
 ('nl', 'Dutch'),
 ('nn', 'Norwegian Nynorsk'),
 ('os', 'Ossetic'),
 ('pa', 'Punjabi'),
 ('pl', 'Polish'),
 ('pt', 'Portuguese'),
 ('pt-br', 'Brazilian Portuguese'),
 ('ro', 'Romanian'),
 ('ru', 'Russian'),
 ('sk', 'Slovak'),
 ('sl', 'Slovenian'),
 ('sq', 'Albanian'),
 ('sr', 'Serbian'),
 ('sr-latn', 'Serbian Latin'),
 ('sv', 'Swedish'),
 ('sw', 'Swahili'),
 ('ta', 'Tamil'),
 ('te', 'Telugu'),
 ('th', 'Thai'),
 ('tr', 'Turkish'),
 ('tt', 'Tatar'),
 ('udm', 'Udmurt'),
 ('uk', 'Ukrainian'),
 ('ur', 'Urdu'),
 ('vi', 'Vietnamese'),
 ('zh-hans', 'Simplified Chinese'),
 ('zh-hant', 'Traditional Chinese')]
LANGUAGES_BIDI	
['he', 'ar', 'fa', 'ur']
LANGUAGE_CODE	
'en-us'
LANGUAGE_COOKIE_AGE	
None
LANGUAGE_COOKIE_DOMAIN	
None
LANGUAGE_COOKIE_NAME	
'django_language'
LANGUAGE_COOKIE_PATH	
'/'
LOCALE_PATHS	
[]
LOGGING	
{}
LOGGING_CONFIG	
'logging.config.dictConfig'
LOGIN_REDIRECT_URL	
'/accounts/profile/'
LOGIN_URL	
'/accounts/login/'
LOGOUT_REDIRECT_URL	
None
MANAGERS	
[]
MEDIA_ROOT	
''
MEDIA_URL	
''
MESSAGE_STORAGE	
'django.contrib.messages.storage.fallback.FallbackStorage'
MIDDLEWARE	
['django.middleware.security.SecurityMiddleware',
 'django.contrib.sessions.middleware.SessionMiddleware',
 'django.middleware.common.CommonMiddleware',
 'django.middleware.csrf.CsrfViewMiddleware',
 'django.contrib.auth.middleware.AuthenticationMiddleware',
 'django.contrib.messages.middleware.MessageMiddleware',
 'django.middleware.clickjacking.XFrameOptionsMiddleware']
MIGRATION_MODULES	
{}
MONTH_DAY_FORMAT	
'F j'
NUMBER_GROUPING	
0
PASSWORD_HASHERS	
'********************'
PASSWORD_RESET_TIMEOUT_DAYS	
'********************'
PREPEND_WWW	
False
ROOT_URLCONF	
'zsb.urls'
SECRET_KEY	
'********************'
SECURE_BROWSER_XSS_FILTER	
False
SECURE_CONTENT_TYPE_NOSNIFF	
False
SECURE_HSTS_INCLUDE_SUBDOMAINS	
False
SECURE_HSTS_PRELOAD	
False
SECURE_HSTS_SECONDS	
0
SECURE_PROXY_SSL_HEADER	
None
SECURE_REDIRECT_EXEMPT	
[]
SECURE_SSL_HOST	
None
SECURE_SSL_REDIRECT	
False
SERVER_EMAIL	
'root@localhost'
SESSION_CACHE_ALIAS	
'default'
SESSION_COOKIE_AGE	
1209600
SESSION_COOKIE_DOMAIN	
None
SESSION_COOKIE_HTTPONLY	
True
SESSION_COOKIE_NAME	
'sessionid'
SESSION_COOKIE_PATH	
'/'
SESSION_COOKIE_SAMESITE	
'Lax'
SESSION_COOKIE_SECURE	
False
SESSION_ENGINE	
'django.contrib.sessions.backends.db'
SESSION_EXPIRE_AT_BROWSER_CLOSE	
False
SESSION_FILE_PATH	
None
SESSION_SAVE_EVERY_REQUEST	
False
SESSION_SERIALIZER	
'django.contrib.sessions.serializers.JSONSerializer'
SETTINGS_MODULE	
'zsb.settings'
SHORT_DATETIME_FORMAT	
'm/d/Y P'
SHORT_DATE_FORMAT	
'm/d/Y'
SIGNING_BACKEND	
'django.core.signing.TimestampSigner'
SILENCED_SYSTEM_CHECKS	
[]
STATICFILES_DIRS	
[]
STATICFILES_FINDERS	
['django.contrib.staticfiles.finders.FileSystemFinder',
 'django.contrib.staticfiles.finders.AppDirectoriesFinder']
STATICFILES_STORAGE	
'django.contrib.staticfiles.storage.StaticFilesStorage'
STATIC_ROOT	
None
STATIC_URL	
'/static/'
TEMPLATES	
[{'APP_DIRS': True,
  'BACKEND': 'django.template.backends.django.DjangoTemplates',
  'DIRS': [],
  'OPTIONS': {'context_processors': ['django.template.context_processors.debug',
                                     'django.template.context_processors.request',
                                     'django.contrib.auth.context_processors.auth',
                                     'django.contrib.messages.context_processors.messages']}}]
TEST_NON_SERIALIZED_APPS	
[]
TEST_RUNNER	
'django.test.runner.DiscoverRunner'
THOUSAND_SEPARATOR	
','
TIME_FORMAT	
'P'
TIME_INPUT_FORMATS	
['%H:%M:%S', '%H:%M:%S.%f', '%H:%M']
TIME_ZONE	
'UTC'
USE_I18N	
True
USE_L10N	
True
USE_THOUSAND_SEPARATOR	
False
USE_TZ	
True
USE_X_FORWARDED_HOST	
False
USE_X_FORWARDED_PORT	
False
WSGI_APPLICATION	
'zsb.wsgi.application'
X_FRAME_OPTIONS	
'SAMEORIGIN'
YEAR_MONTH_FORMAT	
'F Y'
You're seeing this error because you have DEBUG = True in your Django settings file. Change that to False, and Django will display a standard page generated by the handler for this status code.TemplateDoesNotExist at /
index.html
Request Method:	GET
Request URL:	http://127.0.0.1:8000/
Django Version:	2.1.3
Exception Type:	TemplateDoesNotExist
Exception Value:	
index.html
Exception Location:	D:\python\envs\zsb-env\lib\site-packages\django\template\loader.py in get_template, line 19
Python Executable:	D:\python\envs\zsb-env\Scripts\python.exe
Python Version:	3.7.1
Python Path:	
['D:\\python\\envs\\zsb-env\\zsb',
 'D:\\python\\envs\\zsb-env\\zsb',
 'D:\\python\\envs\\zsb-env\\Scripts\\python37.zip',
 'D:\\python\\envs\\zsb-env\\DLLs',
 'D:\\python\\envs\\zsb-env\\lib',
 'D:\\python\\envs\\zsb-env\\Scripts',
 'd:\\python37\\Lib',
 'd:\\python37\\DLLs',
 'D:\\python\\envs\\zsb-env',
 'D:\\python\\envs\\zsb-env\\lib\\site-packages',
 'D:\\Program Files\\JetBrains\\PyCharm '
 '2018.2.5\\helpers\\pycharm_matplotlib_backend']
Server time:	Fri, 16 Nov 2018 08:31:56 +0000
Template-loader postmortem
Django tried loading these templates, in this order:

Using engine django:

django.template.loaders.app_directories.Loader: D:\python\envs\zsb-env\lib\site-packages\django\contrib\admin\templates\index.html (Source does not exist)
django.template.loaders.app_directories.Loader: D:\python\envs\zsb-env\lib\site-packages\django\contrib\auth\templates\index.html (Source does not exist)
Traceback Switch to copy-and-paste view
D:\python\envs\zsb-env\lib\site-packages\django\core\handlers\exception.py in inner
            response = get_response(request) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\core\handlers\base.py in _get_response
                response = self.process_exception_by_middleware(e, request) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\core\handlers\base.py in _get_response
                response = wrapped_callback(request, *callback_args, **callback_kwargs) ...
▶ Local vars
D:\python\envs\zsb-env\zsb\enroll\views.py in index
    return render(request,'index.html') ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\shortcuts.py in render
    content = loader.render_to_string(template_name, context, request, using=using) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\template\loader.py in render_to_string
        template = get_template(template_name, using=using) ...
▶ Local vars
D:\python\envs\zsb-env\lib\site-packages\django\template\loader.py in get_template
    raise TemplateDoesNotExist(template_name, chain=chain) ...
▶ Local vars
Request information
USER
AnonymousUser

GET
No GET data

POST
No POST data

FILES
No FILES data

COOKIES
No cookie data

META
Variable	Value
ALLUSERSPROFILE	
'C:\\ProgramData'
APPDATA	
'C:\\Users\\jkden\\AppData\\Roaming'
ASL.LOG	
'Destination=file'
COMMONPROGRAMFILES	
'C:\\Program Files\\Common Files'
COMMONPROGRAMFILES(X86)	
'C:\\Program Files (x86)\\Common Files'
COMMONPROGRAMW6432	
'C:\\Program Files\\Common Files'
COMPUTERNAME	
'DESKTOP-V5ESOMB'
COMSPEC	
'C:\\WINDOWS\\system32\\cmd.exe'
CONTENT_LENGTH	
''
CONTENT_TYPE	
'text/plain'
DJANGO_SETTINGS_MODULE	
'zsb.settings'
DRIVERDATA	
'C:\\Windows\\System32\\Drivers\\DriverData'
FPS_BROWSER_APP_PROFILE_STRING	
'Internet Explorer'
FPS_BROWSER_USER_PROFILE_STRING	
'Default'
GATEWAY_INTERFACE	
'CGI/1.1'
HOMEDRIVE	
'C:'
HOMEPATH	
'\\Users\\jkden'
HTTP_ACCEPT	
'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8'
HTTP_ACCEPT_ENCODING	
'gzip, deflate, br'
HTTP_ACCEPT_LANGUAGE	
'zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7'
HTTP_CACHE_CONTROL	
'max-age=0'
HTTP_CONNECTION	
'keep-alive'
HTTP_HOST	
'127.0.0.1:8000'
HTTP_UPGRADE_INSECURE_REQUESTS	
'1'
HTTP_USER_AGENT	
('Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) '
 'Chrome/70.0.3538.102 Safari/537.36')
LOCALAPPDATA	
'C:\\Users\\jkden\\AppData\\Local'
LOGONSERVER	
'\\\\DESKTOP-V5ESOMB'
NUMBER_OF_PROCESSORS	
'4'
ONEDRIVE	
'C:\\Users\\jkden\\OneDrive'
OS	
'Windows_NT'
PATH	
'D:\\Python37\\Scripts\\;D:\\Python37\\;C:\\WINDOWS\\system32;C:\\WINDOWS;C:\\WINDOWS\\System32\\Wbem;C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\;C:\\WINDOWS\\System32\\OpenSSH\\;C:\\Users\\jkden\\AppData\\Local\\Microsoft\\WindowsApps;D:\\python\\envs\\zsb-env\\Scripts'
PATHEXT	
'.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.PY;.PYW'
PATH_INFO	
'/'
PROCESSOR_ARCHITECTURE	
'AMD64'
PROCESSOR_IDENTIFIER	
'Intel64 Family 6 Model 58 Stepping 9, GenuineIntel'
PROCESSOR_LEVEL	
'6'
PROCESSOR_REVISION	
'3a09'
PROGRAMDATA	
'C:\\ProgramData'
PROGRAMFILES	
'C:\\Program Files'
PROGRAMFILES(X86)	
'C:\\Program Files (x86)'
PROGRAMW6432	
'C:\\Program Files'
PROMPT	
'(zsb-env) $P$G'
PSMODULEPATH	
('C:\\Program '
 'Files\\WindowsPowerShell\\Modules;C:\\WINDOWS\\system32\\WindowsPowerShell\\v1.0\\Modules')
PUBLIC	
'C:\\Users\\Public'
PYCHARM_HOSTED	
'1'
PYCHARM_MATPLOTLIB_PORT	
'59144'
PYTHONIOENCODING	
'UTF-8'
PYTHONPATH	
('D:\\Program Files\\JetBrains\\PyCharm '
 '2018.2.5\\helpers\\pycharm_matplotlib_backend;D:\\python\\envs\\zsb-env\\zsb')
PYTHONUNBUFFERED	
'1'
QUERY_STRING	
''
REMOTE_ADDR	
'127.0.0.1'
REMOTE_HOST	
''
REQUEST_METHOD	
'GET'
RUN_MAIN	
'true'
SCRIPT_NAME	
''
SERVER_NAME	
'DESKTOP-V5ESOMB'
SERVER_PORT	
'8000'
SERVER_PROTOCOL	
'HTTP/1.1'
SERVER_SOFTWARE	
'WSGIServer/0.2'
SESSIONNAME	
'Console'
SYSTEMDRIVE	
'C:'
SYSTEMROOT	
'C:\\WINDOWS'
TEMP	
'C:\\Users\\jkden\\AppData\\Local\\Temp'
TMP	
'C:\\Users\\jkden\\AppData\\Local\\Temp'
USERDOMAIN	
'DESKTOP-V5ESOMB'
USERDOMAIN_ROAMINGPROFILE	
'DESKTOP-V5ESOMB'
USERNAME	
'jkden'
USERPROFILE	
'C:\\Users\\jkden'
VBOX_MSI_INSTALL_PATH	
'D:\\Program Files\\Oracle\\VirtualBox\\'
VIRTUAL_ENV	
'd:\\python\\envs\\zsb-env'
WINDIR	
'C:\\WINDOWS'
WORKON_HOME	
'd:\\python\\envs\\'
_OLD_VIRTUAL_PATH	
'D:\\Python37\\Scripts\\;D:\\Python37\\;C:\\WINDOWS\\system32;C:\\WINDOWS;C:\\WINDOWS\\System32\\Wbem;C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\;C:\\WINDOWS\\System32\\OpenSSH\\;C:\\Users\\jkden\\AppData\\Local\\Microsoft\\WindowsApps'
_OLD_VIRTUAL_PROMPT	
'$P$G'
wsgi.errors	
<_io.TextIOWrapper name='<stderr>' mode='w' encoding='UTF-8'>
wsgi.file_wrapper	
''
wsgi.input	
<_io.BufferedReader name=844>
wsgi.multiprocess	
False
wsgi.multithread	
True
wsgi.run_once	
False
wsgi.url_scheme	
'http'
wsgi.version	
(1, 0)
Settings
Using settings module zsb.settings
Setting	Value
ABSOLUTE_URL_OVERRIDES	
{}
ADMINS	
[]
ALLOWED_HOSTS	
[]
APPEND_SLASH	
True
AUTHENTICATION_BACKENDS	
['django.contrib.auth.backends.ModelBackend']
AUTH_PASSWORD_VALIDATORS	
'********************'
AUTH_USER_MODEL	
'auth.User'
BASE_DIR	
'D:\\python\\envs\\zsb-env\\zsb'
CACHES	
{'default': {'BACKEND': 'django.core.cache.backends.locmem.LocMemCache'}}
CACHE_MIDDLEWARE_ALIAS	
'default'
CACHE_MIDDLEWARE_KEY_PREFIX	
'********************'
CACHE_MIDDLEWARE_SECONDS	
600
CSRF_COOKIE_AGE	
31449600
CSRF_COOKIE_DOMAIN	
None
CSRF_COOKIE_HTTPONLY	
False
CSRF_COOKIE_NAME	
'csrftoken'
CSRF_COOKIE_PATH	
'/'
CSRF_COOKIE_SAMESITE	
'Lax'
CSRF_COOKIE_SECURE	
False
CSRF_FAILURE_VIEW	
'django.views.csrf.csrf_failure'
CSRF_HEADER_NAME	
'HTTP_X_CSRFTOKEN'
CSRF_TRUSTED_ORIGINS	
[]
CSRF_USE_SESSIONS	
False
DATABASES	
{'default': {'ATOMIC_REQUESTS': False,
             'AUTOCOMMIT': True,
             'CONN_MAX_AGE': 0,
             'ENGINE': 'django.db.backends.dummy',
             'HOST': '',
             'NAME': '',
             'OPTIONS': {},
             'PASSWORD': '********************',
             'PORT': '',
             'TEST': {'CHARSET': None,
                      'COLLATION': None,
                      'MIRROR': None,
                      'NAME': None},
             'TIME_ZONE': None,
             'USER': ''}}
DATABASE_ROUTERS	
[]
DATA_UPLOAD_MAX_MEMORY_SIZE	
2621440
DATA_UPLOAD_MAX_NUMBER_FIELDS	
1000
DATETIME_FORMAT	
'N j, Y, P'
DATETIME_INPUT_FORMATS	
['%Y-%m-%d %H:%M:%S',
 '%Y-%m-%d %H:%M:%S.%f',
 '%Y-%m-%d %H:%M',
 '%Y-%m-%d',
 '%m/%d/%Y %H:%M:%S',
 '%m/%d/%Y %H:%M:%S.%f',
 '%m/%d/%Y %H:%M',
 '%m/%d/%Y',
 '%m/%d/%y %H:%M:%S',
 '%m/%d/%y %H:%M:%S.%f',
 '%m/%d/%y %H:%M',
 '%m/%d/%y']
DATE_FORMAT	
'N j, Y'
DATE_INPUT_FORMATS	
['%Y-%m-%d',
 '%m/%d/%Y',
 '%m/%d/%y',
 '%b %d %Y',
 '%b %d, %Y',
 '%d %b %Y',
 '%d %b, %Y',
 '%B %d %Y',
 '%B %d, %Y',
 '%d %B %Y',
 '%d %B, %Y']
DEBUG	
True
DEBUG_PROPAGATE_EXCEPTIONS	
False
DECIMAL_SEPARATOR	
'.'
DEFAULT_CHARSET	
'utf-8'
DEFAULT_CONTENT_TYPE	
'text/html'
DEFAULT_EXCEPTION_REPORTER_FILTER	
'django.views.debug.SafeExceptionReporterFilter'
DEFAULT_FILE_STORAGE	
'django.core.files.storage.FileSystemStorage'
DEFAULT_FROM_EMAIL	
'webmaster@localhost'
DEFAULT_INDEX_TABLESPACE	
''
DEFAULT_TABLESPACE	
''
DISALLOWED_USER_AGENTS	
[]
EMAIL_BACKEND	
'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST	
'localhost'
EMAIL_HOST_PASSWORD	
'********************'
EMAIL_HOST_USER	
''
EMAIL_PORT	
25
EMAIL_SSL_CERTFILE	
None
EMAIL_SSL_KEYFILE	
'********************'
EMAIL_SUBJECT_PREFIX	
'[Django] '
EMAIL_TIMEOUT	
None
EMAIL_USE_LOCALTIME	
False
EMAIL_USE_SSL	
False
EMAIL_USE_TLS	
False
FILE_CHARSET	
'utf-8'
FILE_UPLOAD_DIRECTORY_PERMISSIONS	
None
FILE_UPLOAD_HANDLERS	
['django.core.files.uploadhandler.MemoryFileUploadHandler',
 'django.core.files.uploadhandler.TemporaryFileUploadHandler']
FILE_UPLOAD_MAX_MEMORY_SIZE	
2621440
FILE_UPLOAD_PERMISSIONS	
None
FILE_UPLOAD_TEMP_DIR	
None
FIRST_DAY_OF_WEEK	
0
FIXTURE_DIRS	
[]
FORCE_SCRIPT_NAME	
None
FORMAT_MODULE_PATH	
None
FORM_RENDERER	
'django.forms.renderers.DjangoTemplates'
IGNORABLE_404_URLS	
[]
INSTALLED_APPS	
['django.contrib.admin',
 'django.contrib.auth',
 'django.contrib.contenttypes',
 'django.contrib.sessions',
 'django.contrib.messages',
 'django.contrib.staticfiles']
INTERNAL_IPS	
[]
LANGUAGES	
[('af', 'Afrikaans'),
 ('ar', 'Arabic'),
 ('ast', 'Asturian'),
 ('az', 'Azerbaijani'),
 ('bg', 'Bulgarian'),
 ('be', 'Belarusian'),
 ('bn', 'Bengali'),
 ('br', 'Breton'),
 ('bs', 'Bosnian'),
 ('ca', 'Catalan'),
 ('cs', 'Czech'),
 ('cy', 'Welsh'),
 ('da', 'Danish'),
 ('de', 'German'),
 ('dsb', 'Lower Sorbian'),
 ('el', 'Greek'),
 ('en', 'English'),
 ('en-au', 'Australian English'),
 ('en-gb', 'British English'),
 ('eo', 'Esperanto'),
 ('es', 'Spanish'),
 ('es-ar', 'Argentinian Spanish'),
 ('es-co', 'Colombian Spanish'),
 ('es-mx', 'Mexican Spanish'),
 ('es-ni', 'Nicaraguan Spanish'),
 ('es-ve', 'Venezuelan Spanish'),
 ('et', 'Estonian'),
 ('eu', 'Basque'),
 ('fa', 'Persian'),
 ('fi', 'Finnish'),
 ('fr', 'French'),
 ('fy', 'Frisian'),
 ('ga', 'Irish'),
 ('gd', 'Scottish Gaelic'),
 ('gl', 'Galician'),
 ('he', 'Hebrew'),
 ('hi', 'Hindi'),
 ('hr', 'Croatian'),
 ('hsb', 'Upper Sorbian'),
 ('hu', 'Hungarian'),
 ('ia', 'Interlingua'),
 ('id', 'Indonesian'),
 ('io', 'Ido'),
 ('is', 'Icelandic'),
 ('it', 'Italian'),
 ('ja', 'Japanese'),
 ('ka', 'Georgian'),
 ('kab', 'Kabyle'),
 ('kk', 'Kazakh'),
 ('km', 'Khmer'),
 ('kn', 'Kannada'),
 ('ko', 'Korean'),
 ('lb', 'Luxembourgish'),
 ('lt', 'Lithuanian'),
 ('lv', 'Latvian'),
 ('mk', 'Macedonian'),
 ('ml', 'Malayalam'),
 ('mn', 'Mongolian'),
 ('mr', 'Marathi'),
 ('my', 'Burmese'),
 ('nb', 'Norwegian Bokmål'),
 ('ne', 'Nepali'),
 ('nl', 'Dutch'),
 ('nn', 'Norwegian Nynorsk'),
 ('os', 'Ossetic'),
 ('pa', 'Punjabi'),
 ('pl', 'Polish'),
 ('pt', 'Portuguese'),
 ('pt-br', 'Brazilian Portuguese'),
 ('ro', 'Romanian'),
 ('ru', 'Russian'),
 ('sk', 'Slovak'),
 ('sl', 'Slovenian'),
 ('sq', 'Albanian'),
 ('sr', 'Serbian'),
 ('sr-latn', 'Serbian Latin'),
 ('sv', 'Swedish'),
 ('sw', 'Swahili'),
 ('ta', 'Tamil'),
 ('te', 'Telugu'),
 ('th', 'Thai'),
 ('tr', 'Turkish'),
 ('tt', 'Tatar'),
 ('udm', 'Udmurt'),
 ('uk', 'Ukrainian'),
 ('ur', 'Urdu'),
 ('vi', 'Vietnamese'),
 ('zh-hans', 'Simplified Chinese'),
 ('zh-hant', 'Traditional Chinese')]
LANGUAGES_BIDI	
['he', 'ar', 'fa', 'ur']
LANGUAGE_CODE	
'en-us'
LANGUAGE_COOKIE_AGE	
None
LANGUAGE_COOKIE_DOMAIN	
None
LANGUAGE_COOKIE_NAME	
'django_language'
LANGUAGE_COOKIE_PATH	
'/'
LOCALE_PATHS	
[]
LOGGING	
{}
LOGGING_CONFIG	
'logging.config.dictConfig'
LOGIN_REDIRECT_URL	
'/accounts/profile/'
LOGIN_URL	
'/accounts/login/'
LOGOUT_REDIRECT_URL	
None
MANAGERS	
[]
MEDIA_ROOT	
''
MEDIA_URL	
''
MESSAGE_STORAGE	
'django.contrib.messages.storage.fallback.FallbackStorage'
MIDDLEWARE	
['django.middleware.security.SecurityMiddleware',
 'django.contrib.sessions.middleware.SessionMiddleware',
 'django.middleware.common.CommonMiddleware',
 'django.middleware.csrf.CsrfViewMiddleware',
 'django.contrib.auth.middleware.AuthenticationMiddleware',
 'django.contrib.messages.middleware.MessageMiddleware',
 'django.middleware.clickjacking.XFrameOptionsMiddleware']
MIGRATION_MODULES	
{}
MONTH_DAY_FORMAT	
'F j'
NUMBER_GROUPING	
0
PASSWORD_HASHERS	
'********************'
PASSWORD_RESET_TIMEOUT_DAYS	
'********************'
PREPEND_WWW	
False
ROOT_URLCONF	
'zsb.urls'
SECRET_KEY	
'********************'
SECURE_BROWSER_XSS_FILTER	
False
SECURE_CONTENT_TYPE_NOSNIFF	
False
SECURE_HSTS_INCLUDE_SUBDOMAINS	
False
SECURE_HSTS_PRELOAD	
False
SECURE_HSTS_SECONDS	
0
SECURE_PROXY_SSL_HEADER	
None
SECURE_REDIRECT_EXEMPT	
[]
SECURE_SSL_HOST	
None
SECURE_SSL_REDIRECT	
False
SERVER_EMAIL	
'root@localhost'
SESSION_CACHE_ALIAS	
'default'
SESSION_COOKIE_AGE	
1209600
SESSION_COOKIE_DOMAIN	
None
SESSION_COOKIE_HTTPONLY	
True
SESSION_COOKIE_NAME	
'sessionid'
SESSION_COOKIE_PATH	
'/'
SESSION_COOKIE_SAMESITE	
'Lax'
SESSION_COOKIE_SECURE	
False
SESSION_ENGINE	
'django.contrib.sessions.backends.db'
SESSION_EXPIRE_AT_BROWSER_CLOSE	
False
SESSION_FILE_PATH	
None
SESSION_SAVE_EVERY_REQUEST	
False
SESSION_SERIALIZER	
'django.contrib.sessions.serializers.JSONSerializer'
SETTINGS_MODULE	
'zsb.settings'
SHORT_DATETIME_FORMAT	
'm/d/Y P'
SHORT_DATE_FORMAT	
'm/d/Y'
SIGNING_BACKEND	
'django.core.signing.TimestampSigner'
SILENCED_SYSTEM_CHECKS	
[]
STATICFILES_DIRS	
[]
STATICFILES_FINDERS	
['django.contrib.staticfiles.finders.FileSystemFinder',
 'django.contrib.staticfiles.finders.AppDirectoriesFinder']
STATICFILES_STORAGE	
'django.contrib.staticfiles.storage.StaticFilesStorage'
STATIC_ROOT	
None
STATIC_URL	
'/static/'
TEMPLATES	
[{'APP_DIRS': True,
  'BACKEND': 'django.template.backends.django.DjangoTemplates',
  'DIRS': [],
  'OPTIONS': {'context_processors': ['django.template.context_processors.debug',
                                     'django.template.context_processors.request',
                                     'django.contrib.auth.context_processors.auth',
                                     'django.contrib.messages.context_processors.messages']}}]
TEST_NON_SERIALIZED_APPS	
[]
TEST_RUNNER	
'django.test.runner.DiscoverRunner'
THOUSAND_SEPARATOR	
','
TIME_FORMAT	
'P'
TIME_INPUT_FORMATS	
['%H:%M:%S', '%H:%M:%S.%f', '%H:%M']
TIME_ZONE	
'UTC'
USE_I18N	
True
USE_L10N	
True
USE_THOUSAND_SEPARATOR	
False
USE_TZ	
True
USE_X_FORWARDED_HOST	
False
USE_X_FORWARDED_PORT	
False
WSGI_APPLICATION	
'zsb.wsgi.application'
X_FRAME_OPTIONS	
'SAMEORIGIN'
YEAR_MONTH_FORMAT	
'F Y'
You're seeing this error because you have DEBUG = True in your Django settings file. Change that to False, and Django will display a standard page generated by the handler for this status code.
```



