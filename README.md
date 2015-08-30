## ѧϰĿ��

+ ����һ��Django��Ŀ,����һ��������DjangoӦ��.
+ ΪDjango��Ŀ������̬�ļ��������ļ�
+ ʹ��Django��Model-View-Template(MVT)���ģʽ
+ �������ݿ�ģ��,��Django�ṩ�Ķ����ϵ�󶨹���
+ �������ݿ�ģ�����ɵ�������������̬����ҳ��
+ ʹ��Django�ṩ���û���֤����
+ ����Ӧ�õ��ⲿ����
+ һ��webӦ����������CSS��JavaScript
+ ��ƺ�Ӧ��CSS������webӦ�õĽ��潻��
+ ʹ��Django��cookies��sessions
+ ��Ӧ����ʹ����AJAX�����ĸ߼�����
+ ��PythonAnywhere�������Ӧ�õ�web������

## ��ʼ��ƺ͹滮

������ǰ�ᵽ��,�Ȿ���Ҫ���ǿ���һ������Rango��Ӧ��.Ϊ�˿������Ӧ��,�����Ḳ����������webӦ�ô󲿷ֺ�������.

## ��Ƹ�Ҫ

+ ��Ŀͻ�����Ҫ����һ������Rango����վ,���������û���������Լ����Ƶ���ҳ.
+ ����վ����ҳ��,������߿���:
    + 5���鿴����ҳ��
    + 5��������ߵ�Ŀ¼
    + �ÿ�������߲���Ŀ¼�ķ���
    + ��һ���û��鿴һ��Ŀ¼ҳ,����չ��:Ŀ¼����,��������,ϲ������;
    + ��Ŀ¼�����ҳ��(չʾҳ����������url);
    + һ�������Ŀ¼,�ͻ���ϣ��Ŀ¼������,ÿ��Ŀ¼ҳ�汻���ʵĴ����Ͷ��ٸ��û����'like'��ť����¼.
    + ÿ��Ŀ¼������ͨ��һ���ɶ���URL���ʣ�����. /rango/books-about-django/.
    + ֻ��ע����û�����ΪĿ¼����ҳ��.ͬʱ,�����߿���ע��һ���˻�.
��һ�ۿ���ȥ,���Ӧ�ÿ����������.��ʵ��,������һ��Ŀ¼�б�,���ǿ������ӵ�ҳ��,����?Ȼ��,���ﻹ����ิ�ӵĶ�����Ҫ����.����,���������Ż�һ��ͼ��չʾ����Ҫ����ʲô����.

��Ч��ͼ

## ����׼��

ʹ��python2.7��������Ӧ�ð�װ���»�����

    (rango)itcast@itcast:~/workspace/itcast_project$ pip list
    Django (1.7.8)
    ipdb (0.8.1)
    ipython (3.2.0)
    Pillow (2.8.2)
    pip (7.0.3)
    setuptools (17.0)
    wheel (0.24.0)

�����ϰ����洢��package.txt�������python���⻷���У�����:
    pip install -r package.txt


## helloworld��Ŀ

1.������Ŀ����

    django-admin startproject itcast_project

2.Ŀ¼����

itcast_project/
������ itcast_project       -��Ŀ����Ŀ¼
��?? ������ __init__.py      -�յĽű�,����Python���������Ŀ¼��һ��Python��
��?? ������ settings.py      -�����洢Django��Ŀ���õ��ļ�
��?? ������ urls.py          -�����洢��Ŀ���URLģʽ
��?? ������ wsgi.py          -���������п�������,ͬʱ���԰������������������
������ manage.py            -�ṩ��һϵ�е�Django�������ʱ����

3.����������ݱ�

    cd itcast_project
    python manage.py migrate

4.������Ŀ��Ĭ��ʹ�ö˿�8000

    python manage.py runserver

5.������������µ�ַ
    
    http://127.0.0.1:8000/

![helloworld.png][1]


6.����DjangoӦ��

    python manage.py startapp rango

(rango)itcast@itcast:~/workspace/itcast_project$ python manage.py startapp rango
(rango)itcast@itcast:~/workspace/itcast_project$ tree
.
������ db.sqlite3            -Ĭ��ʹ�õ�sqlite3���ݿ⣬migrate�ǲ����ɵ�
������ itcast_project
��?? ������ __init__.py
��?? ������ settings.py
��?? ������ urls.py
��?? ������ wsgi.py
������ manage.py
������ rango                 -appӦ��Ŀ¼���൱��������Ŀ��һ����ģ��
    ������ admin.py          -��Djangoע�����ģ��,����Ϊ�㴴��Django�Ĺ������
    ������ __init__.py
    ������ migrations
    ��?? ������ __init__.py
    ������ models.py         -�洢��Ӧ��������ģ�͵ĵط����������������ݵ�ʵ��͹�ϵ
    ������ tests.py          -�洢Ӧ�õĲ��Դ���
    ������ views.py          -�����û��������Ӧ

views.py��models.py��ÿ��appӦ���ж�Ҫ�õ�,��������Django���ģʽ����ɲ���,����Model-View-Templateģʽ.

7.��rango appӦ�ù�����itcast_project��Ŀ��

���㴴��ģ�ͺ���ͼ֮ǰ,�����Ҫ����Django�����Ӧ�õĴ���.����������޸�������Ŀ¼���settings.py�ļ�.���ļ��ҵ�INSTALLED_APPSԪ��.��Ԫ������������rango.

    INSTALLED_APPS = (
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'rango',
    )

8.������ͼ

��������rango�д���һ���򵥵���ͼ.��Ϊ���ǵĵ�һ����ͼ,�򵥵İ��ı����͸��ͻ��ˡ�

��rangoĿ¼���views.py�ļ�.ɾ��ע��# Create your views here.������õ�һ�����ļ�.�������´���

    from django.shortcuts import render
    from django.http import HttpResponse
    def index(request):
        return HttpResponse("Rango says hey there world!")

+ ���ǵ�һ�����ȴ�django.httpģ�鵼��HttpResponse����.
+ ��views.py�ļ���ÿ����ͼ��Ӧһ�������ĺ���.���������������ֻ������һ��index��ͼ.
+ ÿ����ͼ���ٴ�һ��������һ����django.httpģ���HttpRequest����.
+ ÿ����ͼ��Ҫ����һ��HttpResponse����.���HttpResponse�����һ���ַ��������������ݸ��ͻ���.

8.URLӳ��

��rangoĿ¼��,����һ������urls.py���ļ�.�ļ����ǿ����������Ӧ��ӳ�䵽URL.

    from django.conf.urls import patterns, url
    from rango import views
    urlpatterns = patterns('',
        url(r'^$', views.index, name='index'),
    )

��δ��뵼��Django�Դ���ӳ��URL����.����rango��viewģ������������ǰ��������ͼ.

Ϊ�˽���ӳ��,�����õ���tuple.��Django�������urlpatterns���������Ԫ��.

���urlpatternsԪ�����һЩdjango.conf.urls.url()�����ĵ���,��ÿ�������ﶼ��һ��Ψһ��ӳ��.������Ĵ�����,����ֻ����url()һ��,��������ֻӳ����һ��URL.django.conf.urls.url()�����ĵ�һ��������������ʽ^$,ָ����ƥ��һ�����ַ���.����ƥ�����ģʽ��URL����ӳ�䵽views.index()�����ͼ.�û���������Ϣ�������HttpRequest��������Ϊ�������ݸ���ͼ.���Ǹ�url()������ѡ����name��ֵΪindex.

    url(regex, view, kwargs=None, name=None, prefix='')
    regex:����ƥ��
    view:��Ӧ��ͼ����
    kwargs:url���Σ����ݸ���ͼ����
    name:��ʶurl������ͬ��ӳ�䣬������ģ���ǩ������
    prefix:����ͼ����ǰ��ǰ׺

9.��Ŀ��url��appӦ����url����

��ĿĿ¼���Ѿ�������һ��urls.py�ļ�.Ϊʲô��app�д�����һ����?��ʵ��,����԰����е���ĿӦ�õ�URL����������ļ���.��������һ������ϰ��,����������Ӧ�õ����.����Ӧ�õ�urls.py�ļ���Ÿ���Ӧ�õ�URL.Ϊ����С���,������Ժ�����Ǽ��뵽��ĿĿ¼��urls.py�ļ���.

�����ζ��������Ҫ����itcast_project���urls.py�ļ�,�����ǵ�rangoӦ�ú�itcast_project����.

��itcast_projectĿ¼���urls.py�ļ�.

    from django.conf.urls import patterns, include, url
    from django.contrib import admin

    urlpatterns = patterns('',
        # Examples:
        # url(r'^$', 'itcast_project.views.home', name='home'),
        # url(r'^blog/', include('blog.urls')),

        url(r'^admin/', include(admin.site.urls)),
        url(r'^rango/', include('rango.urls')), # ��ӵ�app��ӳ�䣬ע��','
    )

������ӳ�佫��Ѱ��ƥ��^rango/��url�ַ���.���ƥ��ɹ��Ļ����ᴫ�ݸ�rango.urls(�����Ѿ����ù���).include()�����Ǵ�django.conf.urls�����.����URL�ַ��������������ͼ��ʾ.�����������,�������ȱ���ȡ����Ȼ������������url�ַ���(rango/)���ݸ����ǵ�itcast_project,����������ƥ�䲢ȥ��rango/Ȼ��ѿ��ַ������ݸ�rangoӦ��.rango����ƥ��һ�����ַ���,���᷵�����Ǵ����index()��ͼ.

10.�׶�ʤ��
+ ����django������,python manage.py runserver
+ ��������,http://127.0.0.1:8000/rango/

![helloworldok.png][2]


11.�ܽ�ع�

1.python manage.py startapp <appname>�������µ�Ӧ��,����<appname>�����Ӧ����.
2.����Ӧ�������뵽settings.py�ļ���INSTALLED_APPS�ʹ��Ŀ�ؼ����µ�Ӧ��.
3.����Ŀ��urls.py�ļ�ӳ��Ӧ��.
4.��Ӧ��Ŀ¼�ﴴ��urls.py�ļ�ʹURL�ַ���ָ����ͼ����.
5.��Ӧ�õ�view.py��,��������ͼҪȷ������һ��HttpResponse����.

12.��ϰ

��ϲ��!���Ѿ�����������rango��.������̱�������¼�.������ͼ��ӳ�������򿪷������ӿ��õ�webӦ�õĵ�һ��.����������ϰһ�¹�����ѧ.

+ �޸ĳ���,ȷ����֪����ΰ�URLӳ�䵽��ͼ.
+ ����һ��about��ͼ,����Rango says here is the about page.
+ �������ͼӳ�䵽/rango/about/.����һ����,��ֻ��Ҫ�༭rangoӦ�����urls.py
+ �޸�index��ͼ��HttpResponse,ʹ�����ذ���aboutҳ�������.
+ ��about��ͼ��ʹ������һ���ص���ҳ������.

13.��ϰ��ʾ

����о���ϰ�����ѵĻ�,���潫�ܰ����������ϰ.

+ index��ͼ����Ҫ����about��ͼ������.

  Rango says: Hello world! `<br/> <a href='/rango/about'>About</a>`

+ ƥ��about/��������ʽ��r^about/.
+ ������ҳ��������`<a href="/rango/">Index</a>` ����ṹ�������aboutҳ�����һ��.

## ģ��;�̬ý��

1.�������ģ���Ŀ¼
+ ��itcast_project��Ŀ��Ŀ¼�£�����templatesĿ¼�������ٴ���rangoĿ¼
    
    mkdir -p templates/rango

2.��Ŀ������ģ�����·��������itcast_project��Ŀ����Ŀ¼��settings.py

+ ����·����Ӳ���룬�����飬��ĿǨ�Ƶ���ķ�����ʱ�������

    TEMPLATE_DIRS = ['<workspace>/itcast_project/']

+ ��̬��ȡ·��
    BASE_DIR = os.path.dirname(os.path.dirname(__file__))
    TEMPLATE_PATH = os.path.join(BASE_DIR, 'templates')
    TEMPLATE_DIRS = [
        TEMPLATE_PATH,
    ]

3.���ģ��

�����Ǵ���ģ��Ŀ¼�����ú�·���Ժ�,������Ҫ��template/rango/Ŀ¼�ｨ��һ������index.html���ļ�,�����ļ�������������:

    <!DOCTYPE html>
    <html>

    <head>
        <title>Rango</title>
    </head>

    <body>
        <h1>Rango says...</h1>
        hello world! <strong>{{ boldmessage }}</strong><br />
        <a href="/rango/about/">About</a><br />
    </body>

    </html>


���HTML���봴��һ���ʺ��û��ļ�HTMLҳ��.�����ע�⵽����������һ�η�HTML����{{boldmessage}}.����Djangoģ��ı���,�����������ʱΪ���������ֵ.һ�����Ǿͻ�����.

Ϊ��ʹ�����ģ��,������Ҫ�����޸�һ��������ǰ������index()��ͼ.������ǲ��������ݼ򵥵���Ϣ,���������������ǵ�ģ��.

��rango/views.py��,ȷ���ļ�ͷ�������´���.

    from django.shortcuts import render

�޸�index()��ͼ��������.

    def index(request):
        context_dict = {'boldmessage': "I am bold font from the context"}
        return render(request, 'rango/index.html', context_dict)

�������ǽ���һ����ģ����ʹ�õ��ֵ�,Ȼ�����ǵ�ȡrender()����.������������û���request,ģ�����ƺ������ֵ���Ϊ����.���render()�����������Щ�����ۺϵ�һ������һ��������HTMLҳ��.Ȼ�󷵻ظ��û��������.

��ģ���ļ������ص�Djangoģ��ϵͳ��ʱ,��ģ������Ҳ�ᱻ����.�ڼ򵥵�������ģ����������ֵ����ģ�������Ӧ��Python����.���������ȴ�����ģ���ļ�,���Ǵ�����һ������boldmessage��ģ�����.��index(request)��ͼ������,�ַ���I am bold font from the contextӳ�䵽ģ�����boldmessage.�����ַ���I am bold font from the context�����滻ģ�������е�{{ boldmessage }}.

�������Ѿ���������ͼ,����Django���񲢷��� http://127.0.0.1:8000/rango/ .�㽫�ῴ��

![template1.png][3]

## ��̬ý��

1.���þ�̬ý��Ŀ¼

Ϊ�����þ�̬ý��,����Ҫ�����洢���ǵ�Ŀ¼.�������ĿĿ¼(����<workspace>/itcast_project/),��������static��Ŀ¼.��static���ٴ���һ��imagesĿ¼.

    mkdir -p static/images

������static/imagesĿ¼�����һ��ͼƬ.��������һ��Ҳϲ��������ô��������Ŀ��jordanΪ��һ��ͼƬ��.

![jordan.jpg][4]


2.������Ŀ�о�̬�ļ�Ŀ¼

��settings.py�ļ�,������Ҫ������������STATIC_URL��STATICFILES_DIRSԪ��,������һ������һ�����澲̬Ŀ¼(STATIC_PATH)�ı���.

    STATIC_PATH = os.path.join(BASE_DIR,'static')
    STATIC_URL = '/static/' #��Ŀ���Ѷ���ô˱���
    STATICFILES_DIRS = (
        STATIC_PATH,
    )


��һ������STATIC_URL�����˵�Django����ʱDjangoӦ��Ѱ�Ҿ�̬ý��ĵ�ַ.����,����������Ĵ���һ����STATIC_URL���ó�/static/,���ǾͿ���ͨ��http://127.0.0.1:8000/static/����������. 

`ע�⣺����Ҫע��б�ܵ���д.�������ô���ý�������һ����鷳.`

STATIC_URL������web��������ý���URL��ַ,STATICFILES_DIRS�����㶨���µ�staticĿ¼.��TEMPLATE_DIRSԪ��һ��.STATICFILES_DIRS��ҪstaticĿ¼�ľ���·��.����,���ǻ�����BASE_DIR����������STATIC_PATH.

��������������ú�,��һ���������Django����.���������Ҫ�鿴���ǵ�jordanͼƬ,����http://127.0.0.1:8000/static/images/jordan.jpg.���û�г�����鿴setings.py�ļ��Ƿ�������ȷ,����������.���������,���ż����������͵��ļ���staticĿ¼����������Ϸ�������.

![template2.png][5]

3.��̬ý���ģ��

�������Ѿ�Ϊ���itcast_project��Ŀ�����˾�̬ý��,����������ģ���������Щý��.

���潫չʾ��μ��뾲̬ý��,��λ��<workspace>/itcast_project/templates/rangoĿ¼��index.html�ļ�.������һ���޸�HTMLԴ����.�¼���������ע�ͱ�ʾ.

    <!DOCTYPE html>

    {% load staticfiles %} <!-- ģ���ǩ���ؾ�̬�ļ�·�� -->

    <html>

    <head>
        <title>Rango</title>
    </head>

    <body>
        <h1>Rango says...</h1>
        hello world! <strong>{{ boldmessage }}</strong><br />
        <a href="/rango/about/">About</a><br />
        <img src="{% static "images/jordan.jpg" %}" alt="Picture of jordan" /> 
    </body>

    </html>

����,������Ҫʹ��{% load static %}��ǩ��ʹ�þ�̬ý��.�������ǲſ�����{% static "jordan.jpg" %} ��ģ�������static�ļ�.Djangoģ���ǩ��{ }����ʾ.�����������������static��ǩ,�������STATIC_URL��jordan.jpg��������,������ʾ.

    <img src="/static/images/jordan.jpg" alt="Picture of Jordan" /> 

�����Ϊʲôԭ��ͼƬ���ܼ������ǿ�����һЩ�ı�������.�����alt���Ե����ã����ͼƬ����ʧ�ܾ���ʾalt�����е��ı�.

����,�������ٴ�����Django�������http://127.0.0.1:8000/rango.���˵Ļ����Կ�����ͼ.

![template3.png][6]


4.�׶�С��

ѧ������,��Ӧ��ѧ��������úʹ���ģ��,�������ͼ��ʹ��ģ��,���ú�ʹ��Django�����;�̬ý���ļ�,�����Ѿ�ѧ�˺ܶ��ˣ�����!

����ģ�岢����ͼ��ʹ�������µĹؼ�.����ҪһЩ����,���ǵ��㳢�Լ��κ�ͷǳ�����������.

+ ������ϣ��ʹ�õ�ģ�岢����������templatesĿ¼��,���Ŀ¼��Ҫ��д��settings.py�ļ�.�������ģ����ʹ��Djangoģ�����(����{{ bariable_name }}).���������ͼ�������Щ����.
+ ��Ӧ�õ�views.py�ļ�����һ��ߴ���һ���µ���ͼ.
+ ����ͼ��,����һ���ֵ������԰�ģ�����ݴ��ݸ�ģ������.
+ ʹ��render()���������ɷ���.ȷ������request,Ȼ����ģ���ļ�,����������ֵ�!
+ ����㻹û���޸�urls.py�ļ�����Ӧ���е�urls.py�е�ӳ��,����Ҫ�޸�һ��.
+ �����ҳ���ϻ�ȡһ����̬ý���ļ�Ҳ��һ������Ҫ���յĺ���Ҫ�Ĳ���.
+ ����Ҫ��ӵľ�̬�ļ�����staticĿ¼.���Ŀ¼������settings.py�����õ�STATICFILES_DIRSԪ��.
+ ��ģ������Ӿ�̬ý������.����һ��HTML��ҳ��ͼƬ��<img />��ǩ.
+ �ǵ���{% load staticfiles %}��{% static "filename" %}������ģ�������þ�̬�ļ�.

5.��ϰ

+ ��aboutҳ��Ҳ��һ��about.htmlģ��������.
+ ��about.htmlģ����,����ľ�̬ý��������ͼƬ.


## ģ�ͺ����ݿ�

ͨ����˵�������ݿ���Ҫ����������ิ�ӵ�SQL���.������Django��,�����ϵӳ��(ORM)�����Ǵ�����һ��,����ͨ��ģ�ʹ������ݿ��.��ʵ��,ģ���������������ģ��/ͼ���һ��Python����.������ͨ��SQL�������ݿⲻͬ,��ֻ��ʹ��Python������ܲ������ݿ�.���ǽ���ѧϰ����������ݿⲢΪrango����ģ��.

1.rango����������,�����ǿ���rango������.�����г���rango���ݹؼ��ļ�������.

+ rangoʵ������һ����ҳĿ¼ - һ������������վ���ӵ���վ
+ ����಻ͬ��վ��Ŀ¼,ÿ��Ŀ¼�а����������.
+ һ��Ŀ¼Ҫ������,������������.
+ һ��ҳ��Ҫ��Ŀ¼,����,URL��һЩ��ͼ.


2.����Django������ݿ⣬Django���Զ���settings.py�����һ������DATABASES���ֵ�.����������.

    DATABASES = {
        'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
        }
    }


�ܿ���Ĭ����SQLite3��Ϊ������ݿ�.SQLite�Ǹ������������ݿ�����ǿ���������.���ǽ�����Ҫ����DATABASE_PATH���NAME��ֵ��.����������ҪUSER,PASSWORD,HOST��PORT�ȹؼ���.

    ע��:���ڽ̳���˵ʹ��SQLite���滹��,���Ƕ��ڲ������Ӧ����˵���ܲ�����õ�ѡ��,����Ӧ��ʹ����������׳�͸����͵����ݿ�����.Djangoͬ��֧����PostgreSQL��MySQL�������������ݿ�����.

3.����ģ��

������ΪRango������������ģ��.��rango/models.py��,���Ƕ��������̳���djnago.db.models.Model����.��������ֱ���Ŀ¼��ҳ��.����Category��Page����.

    class Category(models.Model):
        name = models.CharField(max_length=128, unique=True)

        def __unicode__(self):  
            return self.name

    class Page(models.Model):
        category = models.ForeignKey(Category)
        title = models.CharField(max_length=128)
        url = models.URLField()
        views = models.IntegerField(default=0)

        def __unicode__(self):      #Python2, use __str__ on Python3
            return self.title

���㶨����һ��ģ��,����Ҫ�ƶ���ѡ�����������Լ���ص������б�.Django�ṩ������ڽ��ֶ�.һЩ���õ�����.

    CharField���洢�ַ����ݵ��ֶ�(�����ַ���).max_length�ṩ����󳤶�.
    URLField����CharFieldһ��,�������洢��Դ��URL.��Ҳ����ʹ��max_length����.
    IntegerField���洢����.
    DateField���洢Python��datetime.date.

�鿴Django documentation on model fields��ȡ�����б�.

ÿ���ֶζ���һ��unique����.�������ΪTrue,��ô���������ݿ�ģ���������ֶ����ֵ������Ψһ��.����,�������涨���Categoryģ��.name�ֶα�����Ϊunique - ����ÿһ��Ŀ¼�����ֶ�������Ψһ��.

������������ֶ���Ϊ���ݿ�Ĺؼ��ֻ�ǳ�����.�����Ϊÿ���ֶ�����һ��Ĭ��ֵ(default='value'),Ҳ�������ó�NULL(null=True).

DjangoҲ�ṩ������ģ��/��ļ򵥻���.������Ʒ�װ��3���ֶ���,����.

    ForeignKey������1�Զ��ϵ���ֶ�����.
    OneToOneField������һ���ϸ��1��1��ϵ�ֶ�����.
    ManyToManyFeild�����Զ�Զ��ϵ�ֶ�����.

���������ǵ�����,Page��category�ֶ���ForeignKey����.�������ǿ��Դ���һ��1�Զ��ϵ��Categoryģ��/��,���Category����Ϊ���캯����һ������.Django���Զ���Ϊÿ��ģ�ͱ��д���ID�ֶ�.�����㲻ͬΪÿ��ģ�ʹ������������Ѿ�Ϊ��������!

ע��:������ģ���ʱ��,��ô���`__unicode__()`���� - �ȼ���`__strr__()`����.����㲻��Ϥ����������,�����������ú�Java��toString()��������.`__unicode__()`����Ϊģ��ʵ���ṩunicode���ʽ.�������ǵ�Categoryģ��ͨ��`__unicode__()`��������Ŀ¼�����֣����㿪ʼ��Django�Ĺ��������⽫��ǳ�����. ������������`__unicode__()`������debugҲ�ǳ�����.�����Categoryģ����û��`__unicode__`�������᷵��`<Category: Category object>`.����ֻ֪����һ��Ŀ¼,��������һ����?���������`__unicode__()`�������ǽ��᷵��`<Category: python>`,�����python��Ŀ¼������.

4.������Ǩ�����ݿ�

+ �������ݿ��
python manage.py migrate
+ ��¼����ģ��ǰ��仯
python manage.py makemigrations <app_name>
+ ����makemigrations��¼������ģ�ͱ仯�ļ��ٴθ������ݱ�
python manage.py migrate

5.Django Shell

ͨ��Django shell����Djangoģ�ͣ���������debug�ǳ�����.�������ǽ�չʾ��������ַ�ʽ������Categoryʵ��.

Ϊ�˵õ�shell������Ҫ��һ�ε���Django��Ŀ��Ŀ¼���manage.py.

    python manage.py shell

���ʵ�����ᴴ��һ��Python�������������������Ŀ������.����Ժ�ģ�ͽ��н���.���������չʾ����һ����.ע������Կ���ÿ������Ĺ���.

    # Import the Category model from the rango application
    >>> from rango.models import Category

    # Show all the current categories
    >>> print Category.objects.all()
    [] # Returns an empty list (no categories have been defined!)

    # Create a new category object, and save it to the database.
    >>> c = Category(name="Test")
    >>> c.save()

    # Now list all the category objects stored once more.
    >>> print Category.objects.all()
    [<Category: test>] # We now have a category called 'test' saved in the database!

    # Quit the Django shell.
    >>> quit()

���������������ȵ���������Ҫ������ģ��.Ȼ���ӡ�����ڵ�Ŀ¼,��������Ϊ���ǵ�ͼ���ǿ��������Ҳ�ǿ�.Ȼ�󴴽�������һ��Ŀ¼,��ӡ.

6.���ù������

Django��ͻ����һ�����Ծ������ṩ�ڽ�����ҳ�������,��������ͱ༭�洢��ģ�͵�����,Ҳ���������ݿ�ͼ����.��settings.py�ļ���,ע�⵽��һ��Ĭ�ϰ�װ��django.contib.adminapp,�������urls.py��ҲĬ��������adminƥ��.


����http://127.0.0.1:8000/admin/.��������ǰ���ù���Ա�˻����û�������������¼Django�������.�������ֻ����Groups��Usersͼ����������Ҫ��Django����rangoģ��.���Դ�rango/admin.py�������´���:

    from django.contrib import admin
    from rango.models import Category, Page

    admin.site.register(Category)
    admin.site.register(Page)

��������Ϊ�����ڹ������ע��ģ��.���������Ҫ����ģ��,������admin.stie.register()�����ﴫ��ģ����Ϊ����.

��������Դ���һ������Ա���������ݿ�.

    python manage.py createsuperuser

����Ա�˻�������Django��������½ʱʹ��.������ʾ�����û���,�����ַ������.ע��Ҫ��ס�û���������.

![admin1.png][7]

����Django����:

    python manage.py runserver

���֮�����·���http://127.0.0.1:8000/admin/,����ؿ�������ͼ��.

![admin2.png][8]

![admin.png][9]

7.�������ɲ������ݽű�

�����ݿ����������ݻ�ǳ��鷳.��࿪���߻�����������ݿ��������������.�������һ��С�Ŀ����Ŷ���,ÿ���˶��ô�������.�����дһ���ű�������ÿ���˵������ϴ�����,�����Ϳ��Ա����������ݵĲ���.����������ҪΪ������ݿⴴ�� population script.����ű��Զ���Ϊ������ݿ����ɲ�������.

������Ҫ��Django��Ŀ�ĸ�Ŀ¼�ﴴ��population script(����<workspace>/itcast_project/).����populate_rango.py�ļ���������.

    import os
    os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'itcast_project.settings')

    import django
    django.setup()

    from rango.models import Category, Page


    def populate():
        python_cat = add_cat('Python')

    add_page(cat=python_cat,
        title="Official Python Tutorial",
        url="http://docs.python.org/2/tutorial/")

    add_page(cat=python_cat,
        title="How to Think like a Computer Scientist",
        url="http://www.greenteapress.com/thinkpython/")

    add_page(cat=python_cat,
        title="Learn Python in 10 Minutes",
        url="http://www.korokithakis.net/tutorials/python/")

    django_cat = add_cat("Django")

    add_page(cat=django_cat,
        title="Official Django Tutorial",
        url="https://docs.djangoproject.com/en/1.5/intro/tutorial01/")

    add_page(cat=django_cat,
        title="Django Rocks",
        url="http://www.djangorocks.com/")

    add_page(cat=django_cat,
        title="How to Tango with Django",
        url="http://www.tangowithdjango.com/")

    frame_cat = add_cat("Other Frameworks")

    add_page(cat=frame_cat,
        title="Bottle",
        url="http://bottlepy.org/docs/dev/")

    add_page(cat=frame_cat,
        title="Flask",
        url="http://flask.pocoo.org")

    # Print out what we have added to the user.
    for c in Category.objects.all():
        for p in Page.objects.filter(category=c):
            print "- {0} - {1}".format(str(c), str(p))

    def add_page(cat, title, url, views=0):
        p = Page.objects.get_or_create(category=cat, title=title, url=url, views=views)[0]
        return p

    def add_cat(name):
        c = Category.objects.get_or_create(name=name)[0]
        return c

    # Start execution here!
    if __name__ == '__main__':
        print "Starting Rango population script..."
        populate()


��Ȼ��������������,���Ƿǳ���.���ļ���ͷ���Ƕ�������ຯ��,������ڵײ���ʼִ�� Ѱ��`if __name__ == '__main__'`��һ�п�ʼ.���ǵ�����populate()����.

����:������Djangoģ��ʱȷ���Ѿ�������Django����,���ѻ�������DJANGO_SETTINGS_MODULE����Ϊ��Ŀ�����ļ�.Ȼ�����django.setup()������django����.�������ô���ͻ�����һ��.�����Ϊʲô������Ҫ�ڵ�������֮����ܵ���Category��Page.
populate()�����������add_cat()��add_page()����,���������������ᴴ���µ�Ŀ¼��ҳ��.populate()����ҳ���Ŀ¼���浽���ݿ�.����������ն������ҳ���Ŀ¼.

ע��:����ʹ��get_or_create()��������ģ��ʵ��.���ǿ�����get_or_creat()��������������ݿ����Ƿ����.��������ھʹ�����.�⽫�������ǵĴ���������������Լ����. get_or_create()��������(object,created)Ԫ��.���û�������ݿ��ҵ�,��ô���object��������get_or_create()���������ʵ��.������ʵ�岻����,��ô��������ͷ��غ����ʵ�������ʵ��.created��һ������ֵ;���get_or_create()����ģ��ʵ��Ļ����᷵��true. [0]�᷵��objectԪ��ĵ�һ��λ��,��������������һ��,Pythonʹ��zero-based numbering. official Django documentation ���Բ鿴get_or_vreate()��������ϸ����.
�������˳��Ժ�,���ǿ�����DJango��Ŀ��Ŀ¼ִ������.

    python populate_rango.py

    Starting Rango population script...
    - Python - Official Python Tutorial
    - Python - How to Think like a Computer Scientist
    - Python - Learn Python in 10 Minutes
    - Django - Official Django Tutorial
    - Django - Django Rocks
    - Django - How to Tango with Django
    - Other Frameworks - Bottle
    - Other Frameworks - Flask

�������Ǽ��һ���Ƿ�ı������ݿ�.����Django����,����������,�鿴�µ�Ŀ¼��ҳ��.������Pages�ῴ������.

![admin4.png][10]

��Ȼ��Ҫ����һЩʱ����дpopulation script,�������Ŷ�Э���п��Է����ÿ����.�����ڵ�Ԫ�����л����ô�.


8.�׶�С�ᣬ����ģ�ͣ���5������.

+ �����Ӧ�����models.py�ļ��ﴴ���µ�ģ��.
+ �޸�admin.pyע�����¼ӵ�ģ��
+ ʹ��python manage.py makemigrations ��¼���ݿ����
+ ʹ��python manage.py migrateӦ�ø���.�⽫��Ϊ���ģ�������ݿ��ｨ����Ҫ�Ľṹ
+ Ϊ�����ģ�ʹ���/�޸�population script.

�ܻ���һЩʱ���㲻�ò�ɾ�����ݿ�.���������������Ҫ����migrate����,Ȼ����createsuperuser����,Ϊÿ��appִ��sqlmigrate����Ϳ�.

9.��ϰ,�������������ϰ��������ѧ.

+ ����Ŀ¼ģ��views��likes���Բ�����Ϊ0.
+ ���� population script ,��PythonĿ¼���ó����128�κ�ϲ��64��,DjangoĿ¼���64�κ�ϲ��32��,the Other FramenworkĿ¼���32��,ϲ��16��.
+ �鿴part two of official Django tutorial .�����Ṯ������ѧͬʱѧϰ���������ζ��ƹ������.

10.��ʾ,�������ҪһЩ�����Ļ�,�������ʾ�������.

+ �޸�Categoryģ��,����views��likes,���ǵ��ֶ�ΪIntegerFields.
+ �޸�populate.py�ű����add_cat����,����views��likes����.һ������Ի�ȡĿ¼c,��Ϳ���ͨ��c.views���޸��������,likesҲһ��.
+ Ϊ�˶��ƹ������,����Ҫ�޸�rango/admin.py�ļ�,����PageAdmin��,�����̳���admin.ModelAdmin.
+ ��PageAdmin����,����list_display = ('title', 'category', 'url').
+ ���ע��PageAdmin�ൽDjango�������.��Ҫ�޸�admin.site.register(Page).��Rango��admin.py�ļ����޸ĳ�admin.site.register(Page, PageAdmin).


## ģ��,ģ�����ͼ

���������Ѿ�������ģ�Ͳ��ҵ�����һЩ����,��������Ҫ����Щ��һ��.���ǽ���Ū����������ͼ�з��������Լ����ͨ��ģ��չʾ����.

### ��������:��������ҳ��

��Django�д�����������ҳ�����ִ������5��.

    1.����,����Ӧ�õ�views.py�ļ��е�����Ҫ��ӵ�ģ��.
    2.����ͼ�����ģ��,��������Ҫ������.
    3.��ģ�͵����ݴ��ݸ�ģ��.
    4.����ģ����û���������.
    5.�����û��ӳ��URL,ӳ��һ�°�.

����Ĳ�����������ʹ��Django���ģ��,��ͼ��ģ��.

### չʾrango��ҳ�ϵ�Ŀ¼

������Ҫ��rango����ҳ��ʾ5������Ŀ¼.

1.������Ҫ��ģ��

Ϊ�˴ﵽĿ��,������Ҫ�������Ĳ���.����,��rango/view.py������rango��models.py�ļ���Categoryģ��(CategoryӦ���Ѿ���������ϰ��������likes��views���ֶ�)

    # Import the Category model
    from rango.models import Category

2.�޸�index��ͼ

���˵�һ��,������Ҫ�޸�index()����.�����ǻ���һ��,���index()�������������ҳ����ͼ.�޸�����.

    from rango.models import Category
    def index(request):
        category_list = Category.objects.order_by('-likes')[:5]
        context_dict = {'categories': category_list}
        return render(request, 'rango/index.html', context_dict)

�����������˵�2���͵�3��.����,���Ƿ���Categoryģ�͵õ�5������Ŀ¼.������order_by()������ϲ�����������н�������,ע�����'-'.�������ȡǰ5��Ŀ¼���浽category_list

���������ݿ����,���ǰ�����б�(category_list)�������ֵ�context_dict.����ֵ�ͬʱ����Ϊrender()�Ĳ������ظ�ģ��.

����:ע��Categoryģ�Ͱ���likes�ֶ�.�������Ĳ�����ǰ���½ڵ���ϰ��,����Ҫ�������.

3.�޸�indexģ��

�޸�����ͼ��,���ʣ�µľ��Ǹ���rango/index.htmlģ����.��������.

    <!DOCTYPE html>
    <html>
    <head>
        <title>Rango</title>
    </head>

    <body>
        <h1>Rango says...hello world!</h1>

        {% if categories %}
            <ul>
                {% for category in categories %}
                <li>{{ category.name }}</li>
                {% endfor %}
            </ul>
        {% else %}
            <strong>There are no categories present.</strong>
        {% endif %}

        <a href="/rango/about/">About</a>
    </body>
    </html>

������������Djangoģ���������if��for�������.��ҳ���<body>�����Ǽ��categories�Ƿ�Ϊ��(����,{% if categories %}).

�����Ϊ��,�Ὠ��һ������HTML�б�(��`<ul>`��ǩ��).forѭ��({% for category in categories %})��������`<li>`��ǩ���ӡ��ÿ��Ŀ¼������({{ category.name }}).

���������categories,�������There are no categories present..

��Ϊģ������,���е����������{%��%}��ǩ��,���еı�������{{��}}��.

������� http://127.0.0.1:8000/rango/ ,����ͼ��ʾ.

![rango1.png][11]

### ������ϸҳ��

ͨ��rango����ϸ����,������Ҫ�г�Ŀ¼��ÿ��ҳ��.����������Ҫ�˷��������.������Ҫ����һ���µ���ͼ��Ϊ����.����ͬʱ��Ҫ����URLģʽ��URL�ַ�������Ӧÿ��Ŀ¼������.

1.URL�����ӳ��

���������ֽ��URL����.��һ�ַ�����Ϊ���ǵ�Ŀ¼��URL������Ψһ��ID,���ǿ��Դ�����/rango/category/1/����/rango/category/2/,���������1��2�������ǵ�ID.������������������˵��̫�����.��������֪�����ֹ�����Ŀ¼,��������ô֪��1��2�����ĸ�Ŀ¼��?�û�����һ�¾Ͳ���֪��.

��һ�ַ���������Ŀ¼����ΪURL./rango/category/Python/���᷵�ظ����ǹ���Python��Ŀ¼.����һ���򵥵�,�ɶ���URL.

ע��:������ҳ��˵,���һ������URL��������Ҫ��.

2.ΪCategory������Slug�ֶ�

Ϊ�˽�������url������Ҫ��Categoryģ��������slug�ֶ�.����������Ҫ��django����slugify����,��������������ǰѿո������ַ�����,����"how do i create a slug in django"����ת����"how-do-i-create-a-slug-in-djang".

    ����:��Ȼ������URL���ÿո�,�������ǲ�����ȫ.

���������ǽ�����дCategoryģ�͵�save����,���ǽ������slugify����������slug�ֶ�.ע���κ�ʱ��Ŀ¼���Ƹ��Ķ������slug.������һ���޸�ģ��.

    from django.template.defaultfilters import slugify

    class Category(models.Model):
        name = models.CharField(max_length=128, unique=True)
        views = models.IntegerField(default=0)
        likes = models.IntegerField(default=0)
        slug = models.SlugField(unique=True)

        def save(self, *args, **kwargs):
                self.slug = slugify(self.name)
                super(Category, self).save(*args, **kwargs)

        def __unicode__(self):
                return self.name

��ɾ��db.sqlite3���ݿ��ļ���������Ҫ����������������ģ�ͺ����ݿ�.

    rm db.sqlite3
    python manage.py migrate
    python manage.py makemigrations rango
    python manage.py migrate

��Ϊ����slugû������Ĭ��ֵ,����ģ�����Ѿ����������,����migrate������������ѡ��.ѡ���ṩĬ��ֵѡ�����Ĭ��ֵ''.�������Ͻ����޸�.������������population�ű�.��Ϊÿ��Ŀ¼����ִ��save����,������д��save�������ᱻִ���޸�slug�ֶ�.����Django����,�㽲���ڹ�����濴���޸ĵ�����.

�ڹ�����������ϣ������дĿ¼����ʱ���Զ����slug�ֶ�.��������ķ����޸�rango/admin.py.

    from django.contrib import admin
    from rango.models import Category, Page

    class CategoryAdmin(admin.ModelAdmin):
        prepopulated_fields = {'slug':('name',)}

    admin.site.register(Category, CategoryAdmin)    #ע����װ��
    admin.site.register(Page)

�ڹ�����波�������µ�Ŀ¼.�����˰�!�������ǿ��Լ���slug�ֶ��������ǵ�url.


3.Ŀ¼��ͼ����

��rango/views.py��,������Ҫ����Pageģ��.Ȼ��������ǵ�category()��ͼ:����.

    from rango.models import Page
    def category(request, category_name_slug):
        context_dict = {}
        try:
            category = Category.objects.get(slug=category_name_slug)
            context_dict['category_name'] = category.name
            pages = Page.objects.filter(category=category)
            context_dict['pages'] = pages
            context_dict['category'] = category
        except Category.DoesNotExist:
            pass
        return render(request, 'rango/category.html', context_dict)

��index()��ͼһ�����ǵ�����ͼҲҪִ��ͬ���Ļ�������.������Ҫ����һ���ֵ�,Ȼ���Դ�ģ���е�������,����������ӵ��ֵ���.����ͨ������category_name_slug��ֵ���������ĸ�Ŀ¼.�����Categoryģ�����ҵ�Ŀ¼,���Ǿͻ��context_dict�ֵ䴫�ݸ����ҳ��.

4.Ŀ¼ģ��

����Ϊ���ǵ�����ͼ����ģ��.��<workspace>/itcast_project/templates/rango/Ŀ¼����category.html.

    <!DOCTYPE html>
    <html>
    <head>
        <title>Rango</title>
    </head>

    <body>
        <h1>{{ category_name }}</h1>
        {% if category %}
            {% if pages %}
            <ul>
                {% for page in pages %}
                <li><a href="{{ page.url }}">{{ page.title }}</a></li>
                {% endfor %}
            </ul>
            {% else %}
                <strong>No pages currently in category.</strong>
            {% endif %}
        {% else %}
            The specified category {{ category_name }} does not exist!
        {% endif %}
    </body>
    </html>

�����HTML����ͬ��������չʾ����ΰ�����ͨ���ֵ䴫�ݸ�ģ��.�����õ���category_name������category��pages����.���category��ģ�������Ĳ�û�ж���,���������ݿⲢû�з������Ŀ¼,��ô�ͻ���ʾһ���ѺõĴ�����Ϣ.�෴�Ļ��������,���ǽ�����pages.���pagesû�б�������߲�����Ԫ��,����ͬ��Ҳ������ѺõĴ�����ʾ.����Ļ�Ŀ¼�������ҳ��ͻ�д��HTML����.������pages�б��ÿ��ҳ�����Ƕ���չʾ����title��url.

ע��:Djangoģ�����{% if %}��ǩ���Ǽ������Ƿ���ģ�������ĵĺ÷���.��������Ĵ�����ʹ���Լ��ٴ���ķ���.


5.��������URLӳ��

������������������ΰ�category_name_url����ֵ���ݸ�category().������Ҫ�޸�rango��urls.py�ļ���urlpatternsԪ��.

    urlpatterns = patterns('',
        url(r'^$', views.index, name='index'),
        url(r'^about/$', views.about, name='about'),
        url(r'^category/(?P<category_name_slug>[\w\-]+)/$', views.category,name='category'),)  # New!


���ܿ�����������ʽr'^(?P<category_name_slug>\w+)/$ƥ��ʱ�����view.category()����.���ǵ�������ʽ��ƥ��URLб��ǰ���е���ĸ����(���� a-z, A-Z, ���� 0-9)�����ַ�(-).Ȼ������ֵ��Ϊcategory_name_slug�������ݸ�views.category(),�������������ǿ�Ƶ�request����֮��.

ע��:����ϣ��������URLʱ,һ��Ҫȷ�����URLģʽ����ȷƥ�����.Ϊ�˸���һ�����˽�,�����ǿ�һ�����������. url(r'^category/(?P<category_name_slug>[\w\-]+)/$', views.category, name='category') ���ǿ��Դ������ҵ���category/�ͺ����/֮����ַ���,��������Ϊ����category_name_slug���ݸ�views.category()����.����,URLcategory/python-books/���᷵�ص�category_name_slug������python-books. ��Ҫ֪���������е���ͼ�������������һ������.���������`request`�����ṩHTTP�����û��������Ϣ����������URLʱ,���Ը���ͼ����Ѿ������Ĳ���.ʹ�����������,���ǵ�category��ͼ��������. def category(request, category_name_slug): ���Ӳ�����λ�ò���Ҫ,��Ҫ������URLģʽ�ж���Ĳ�������.ע�����Ϊ���ǵ���ͼ��URLģʽƥ���ж���category_name_slug����.

6.�޸�indexģ��

��Ȼ���ǵ���ͼ�Ѿ�������,���ǻ�Ҫ����๤��.���ǵ�indexģ����Ҫ�޸Ĳ��ṩ���û�category�б�.���ǿ���ͨ��slugΪindex.htnlģ�������Ŀ¼ҳ��.

    <!DOCTYPE html>
    <html>
    <head>
        <title>Rango</title>
    </head>

    <body>
        <h1>Rango says..hello world!</h1>

        {% if categories %}
            <ul>
                {% for category in categories %}
                <!-- Following line changed to add an HTML hyperlink -->
                <li>
                <a href="/rango/category/{{ category.slug }}">{{ category.name }}</a>
                </li>
                {% endfor %}
            </ul>
       {% else %}
            <strong>There are no categories present.</strong>
       {% endif %}

    </body>
    </html>

����Ϊÿ���б�Ԫ��(`<li>`)����һ��HTML������(`<a>`).��������һ��href����,������{{ category.slug}}������Ŀ��URL.


7.Demo

�����Ƿ���rango��ҳ.�㽫�ῴ���г����е�Ŀ¼.��ЩĿ¼���ǿ��Ե��������.���Python�����������PythonĿ¼��ͼ,����ͼ��ʾ.����㿴������Official Python Tutorial�б�,˵�����Ѿ��ɹ��˽�����ͼ.���ŷ��ʲ����ڵ�Ŀ¼,����/rango/category/computers,�㽫�ῴ��ҳ�治���ڵ���Ϣ.

![rango2.png][12]

8.��ϰ

+ �޸�indexҳ��Ҳ����5�������ʵ�ҳ��.

9.��ʾ

+ �޸�population�ű�,Ϊÿ��ҳ�������������.

## ��Ȥ�ı�

Django�Դ���ϵͳʹ��web���ռ��û���Ϣ��ü�.ͨ��Django��s documentation on forms����֪���������ܰ�������:

+ ��ʾһ��HTML���Զ����ɵĴ��岿��(����һ���ı��ֶλ�������ѡ����).
+ ��һϵ�й������ύ����.
+ ��֤���������½���������ʾ��.
+ ���ύ�ı�����ת������ص�Python��������.

ʹ��Django���������ĺô����������Խ�ʡ��Ĵ���ʱ���HTML������鷳.�ⲿ�����ǽ���ע�����ͨ�������û�����Ŀ¼��ҳ��.

1.��������

������������������������û�ͨ������������.

+ ��DjangoӦ��Ŀ¼����forms.pyĿ¼���洢�ͱ���ص���.
+ Ϊÿ��ʹ�ñ���ģ�鴴��ModelForm��.
+ ������ı�.
+ �������޸ı�����ͼ,����չʾ��,�洢������,���û������������(���߸���û������)ʱ��ʾ�����־.
+ �������޸������ģ��.

Ϊ����ͼ����urlpatternӳ��(����㴴����һ���µ�).
������̽������ǰ�Ķ�����Щ,���Ǵ�������ͼҲ��ǳ�����.������������,����������ξͷǳ���������.

2.ҳ���Ŀ¼��

����,������Ҫ��rangoӦ��Ŀ¼�ﴴ������forms.py�ļ�.�����ⲽ���ǲ�����Ҫ,���ǿ��԰ѱ�����models.py��,�����⽫��ʹ���ǵĴ�����׶�.

��rango��forms.pyģ�������ǽ��ᴴ��һЩ�̳���ModelForm����.ʵ����,ModelForm��һ����������,����������һ���Ѿ����ڵ�ģ���ﴴ��Django��.��Ϊ���Ƕ���������ģ��(Category��Page),���ǽ���ֱ�Ϊ���Ǵ���ModelForms.

��rango/forms.py����������:

    #coding:utf-8
    from django import forms
    from rango.models import Page, Category

    class CategoryForm(forms.ModelForm):
        name = forms.CharField(max_length=128, help_text="Please enter the category name.")
        views = forms.IntegerField(widget=forms.HiddenInput(), initial=0)
        likes = forms.IntegerField(widget=forms.HiddenInput(), initial=0)
        slug = forms.CharField(widget=forms.HiddenInput(), required=False)

        # �ڲ���
        class Meta:
            # model��������ģ����Ĺ�����fields���������ʾ�������ֶ�
            model = Category
            fields = ('name',)

    class PageForm(forms.ModelForm):
        title = forms.CharField(max_length=128, help_text="Please enter the title of the page.")
        url = forms.URLField(max_length=200, help_text="Please enter the URL of the page.")
        views = forms.IntegerField(widget=forms.HiddenInput(), initial=0)

        class Meta:
            # model��������ģ����Ĺ������ų�exclude��������ֶΣ������ֶ���ʾ
            model = Page
            exclude = ('category',)
            #fields = ('title', 'url', 'views')


ֵ��ע�����Django1.7+��Ҫͨ��fieldsָ���������ֶ�,����ͨ��excludeָ���ų����ֶ�.

DjangoΪ�����ṩ����ඨ�Ʊ��ķ���.�������������,����ָ����������Ҫչʾ�ֶεĴ��ڲ���.���������ǵ�PageForm����,����Ϊtitle�ֶζ���forms.CharField,Ϊurl�ֶζ���forms.URLField.�����ֶζ�Ϊ�û��ṩ�ı�����.ע���ֶ������max_length����,�������ֶ���󳤶�.

���Կ�����ÿ���������������ϲ����IntegerField�ֶ�.���ǿ����ڲ���������widget=forms.Hiddeninput()�����ش������,����initial=0������Ĭ��ֵΪ0.���ǲ����û�ȥ�Լ������ֶ�Ϊ0��һ�ַ���.Ȼ��������PageForm����,���������������ֶ�,�������ǻ��ǵ��ڱ�������ֶ�.���fields�ų���views,��ô�����������ֶ�(�����Ѿ�������)���ҽ����᷵�ظ�ģ��0ֵ.����ģ�ͽ����Ĳ�ͬ�п��ܻ�����һ������.�����ģ�������ǰ���Щ�ֶζ���Ϊdefault=0��ô���ǿ����Զ��ķ���Ĭ��ֵ,�Ӷ�����not null����.����������¾Ͳ���Ҫ�����ֶ���.�ڱ�������Ҳ������slug�ֶβ�����Ϊwidget=forms.HiddenInput()ֵ,�������ǲ�û�������ó�ʼֵ����Ĭ��ֵ,��������Ϊ����Ҫ(required=False).������Ϊ���ǵ�ģ�ͽ��Ḻ������ֶ�.ʵ����,���㶨��ģ�ͺͱ�ʱһ��Ҫע���һ��Ҫ�����ʹ������е�����.

����CharField��IntegerField����������.����,Django�ṩ��EmailField(e-mail��ַ���),ChoiceField(���밴ť)��DateField(����/ʱ�����).�����������ͬ�����ֶο���ʹ��,���ǿ���Ϊ����ִ�д���(�����Ƿ��ṩ��һ����Ч������?).ǿ�ҽ����㿴һ��official Django documentation on widgets�������Լ������.

����̳�ModelForm�������þ�����Ҫ��������Ҫ���ĸ�ģ���ṩ��.����ͨ��Meta����ʵ��.��Meta������model����Ϊ������Ҫʹ�õ�ģ��.����CategoryForm������Categoryģ��.���Django����������Ҫ��ģ�ͱ�������Ҫ.�������԰��������ڴ洢��չʾ������ʱ��ȡ����.

����Ҳ������Meat������������ϣ�������ı��ֶ�.��fieldsԪ������������������ֶ�.

`ע��:ǿ�ҽ���鿴 official Django documentation on forms����ȡ����.`

3.��������Ŀ¼��ͼ

����CategoryForm���Ժ�,������Ҫ����һ���µ���ͼ��չʾ������������.��rango/views.py���������´���.

    from rango.forms import CategoryForm

    def add_category(request): 
        if request.method == 'POST':
            form = CategoryForm(request.POST)
            if form.is_valid():
                form.save(commit=True)
                return index(request)
            else:
                print form.errors
        else:
            form = CategoryForm()
        return render(request, 'rango/add_category.html', {'form': form})


�µ�add_category()��ͼ���Ӽ������Ĺؼ�����.����,���HTTP���󷽷���GET����POST.���Ǹ��ݲ�ͬ�ķ��������д���,����չʾһ����(�����GET)���ߴ��������(�����POST) ,���б�������ͬURL.add_category()��ͼ�����������ֲ�ͬ���:

+ Ϊ���Ŀ¼�ṩһ���µĿհױ�;
+ �����û��ύ�����ݸ�ģ��,��ת��Rango��ҳ;
+ �����������,�ڱ���չʾ������Ϣ.


Django�������������û��������HTTPPOST����ʵ��.���������Դ洢������,���һ��ܶ�ÿ�����ֶ��Զ����ɴ�����Ϣ.�����ζ��Django������洢���Ĵ�����Ϣ�Ա������ݿ������������.�������Ŀ¼��Ϊ�յĻ����᷵�ز���Ϊ�յĴ���.

ע�⵽render()�н������add_category.htmlģ��,���ģ���������ҳ��.


4.��������Ŀ¼ģ��

����templates/rango/add_category.html�ļ�.

    <!DOCTYPE html>
    <html>
    <head>
        <title>Rango</title>
    </head>
    <body>
        <h1>Add a Category</h1>

        <form id="category_form" method="post" action="/rango/add_category/">

            {% csrf_token %}
            {% for hidden in form.hidden_fields %}
                {{ hidden }}
            {% endfor %}

            {% for field in form.visible_fields %}
                {{ field.errors }}
                {{ field.help_text }}
                {{ field }}
            {% endfor %}

            <input type="submit" name="submit" value="Create Category" />
        </form>
    </body>
    </html>


ע��:ʹ�����غͿɼ����ֶ�����ΪHTTP����״̬Э��.�㲻������������ͬ��HTTP����֮�䱣��״̬,��Ϊʵ�������൱����.Ϊ�˰����������,�������ص�HTML���ֶο���ʹwebӦ�ô��ݸ��û�HTML����Ҫ������,ֻ���û��ύ��ʱ��Ż᷵������.
������Ҳע�⵽�˴���{% csrf_token %},���ǿ�վ����α������,�����ڱ��������ύ����HTTPPOST�����İ�ȫ.Django���Ҫ��ʹ��CSRFtoken.�����������ı������CSRF����,�п��ܻ����ύ��ʱ��������.�鿴 official Django documentation on CSRF tokens �Ի�ȡ������Ϣ.


5.ӳ������Ŀ¼��ͼ

����������Ҫӳ��add_category()��ͼ.��ģ��������ʹ��/rango/add_category/URL���ύ.����������Ҫ�޸�rango/urls.py��urlpattterns.

    urlpatterns = patterns('',
        url(r'^$', views.index, name='index'),
        url(r'^about/$', views.about, name='about'),
        url(r'^add_category/$', views.add_category, name='add_category'), # NEW MAPPING!
        url(r'^category/(?P<category_name_slug>[\w\-]+)/$', views.category,    name='category'),
    )

6.�޸���ҳ����

��Ϊ���һ��,����������ҳ���������.�޸�rango/index.html�ļ�,��`</body>`ǰ������´���.

`<a href="/rango/add_category/">Add a New Category</a><br />`

7.Demo

������һ��!����Django����,����http://127.0.0.1:8000/rango/.���¼ӵ�������ת������Ŀ¼ҳ��,Ȼ������ҳ��.��ͼ������Ŀ¼����ҳ��ͼ.

![rango3.png][13]


8.��������ҳ����ͼ

��һ����Ҫ���û����ڸ�����Ŀ¼����ҳ��.������Ҫ�ظ�������ͬ�����̣�����һ���µ���ͼ(add_page()),һ���µ�ģ��(rango/add_page.html),URLӳ�����Ŀ¼ҳ������һ������.

    from rango.forms import PageForm

    def add_page(request, category_name_slug):
        try:
            cat = Category.objects.get(slug=category_name_slug)
        except Category.DoesNotExist:
            cat = None

        if request.method == 'POST':
            form = PageForm(request.POST)
            if form.is_valid():
                if cat:
                    page = form.save(commit=False)
                    page.category = cat
                    page.views = 0
                    page.save()
                    # probably better to use a redirect here.
                    return category(request, category_name_slug)
                else:
                    print form.errors
        else:
            form = PageForm()

        context_dict = {'form':form, 'category': cat}
        return render(request, 'rango/add_page.html', context_dict)

9.�������ҳ��ģ��

����rango/add_page.html�ļ�

    <!DOCTYPE html>
    <html>
    <head>
	<title>Rango</title>
    </head>
    <body>
	<h1>Add a page</h1>
	<form id="page_form" method="post" >
	{% csrf_token %}
	{% for hidden in form.hidden_fields %}
		{{hidden}}
	{% endfor %}

	{% for field in form.visible_fields %}
		{{ field.errors }}
		{{ field.help_text }}
		{{ field }}
	{% endfor %}
		<input type="submit" name="submit" value="Create Page" />
		<input type="reset" value="reset" id="reset" name="reset" />
	</form>
    </body>
    </html>

10.���ҳ��URLӳ��

    urlpatterns = patterns('',
        url(r'^$', views.index, name='index'),
        url(r'^about/$', views.about, name='about'),
        url(r'^add_category/$', views.add_category, name='add_category'), # NEW MAPPING!
        url(r'^category/(?P<category_name_slug>[\w\-]+)/$', views.category,    name='category'),
        url(r'^category/(?P<category_name_slug>[\w\-]+)/add_page/$', views.add_page, name='add_page'),
    )

11.�޸�category��ͼ

    def category(request, category_name_slug):
        context_dict = {} 
        try:
            category = Category.objects.get(slug=category_name_slug)
            context_dict['category_name'] = category.name
            pages = Page.objects.filter(category=category)
            context_dict['pages'] = pages
            context_dict['category'] = category
	    context_dict['category_name_slug']=category_name_slug #�¼�
        except Category.DoesNotExist:
            pass
        return render(request, 'rango/category.html', context_dict)

12.�޸�category.html

    <!DOCTYPE html>
    <html>
    <head>
    <title>Rango</title>
    </head>

    <body>
    <h1>{{ category_name }}</h1>

    {% if category %}
        {% if pages %}
        <ul>
            {% for page in pages %}
            <li><a href="{{ page.url }}">{{ page.title }}</a></li>
            {% endfor %}
        </ul>
        {% else %}
            <strong>No pages currently in category.</strong>
        {% endif %}
    {% else %}
        The specified category {{ category_name }} does not exist!
    {% endif %}
    <a href="/rango/category/{{category_name_slug}}/add_page/">Add a New page</a><br />
    </body>
    </html>

13.���δ������ѡ����

����Pageģ����һ��url��������ΪURLField����.����Ӧ��HTML��,Djangoϣ���κ��ı������URL�ֶ���һ��������URL.Ȼ��,�û��ܷ���������http://www.url.com������ʽ��Щ������

������ʱ���û����벢����һ����ȷ,���ǿ�����дModelFormģ����clean()����.����������ڱ����ݴ洢��ģ��ʵ��֮ǰ������,������������������֤�����޸��û����������.�����������������,���ǿ��Լ��url�ֶε�ֵ�Ƿ���http://��ͷ��������ǣ����ǿ������û�ǰ�������http://.

    class PageForm(forms.ModelForm):
        ...
        #url = forms.URLField(max_length=200, help_text="Please enter the URL of the page.")
        url = forms.CharField(max_length=200, help_text="Please enter the URL of the page.")

 ����ʵ��ֻ�ܰ�class PageForm�У�URLField�ֶλ���CharField�ֶΡ�


    class PageForm(forms.ModelForm):

    ...

        def clean(self):
            cleaned_data = self.cleaned_data
            url = cleaned_data.get('url')
            if url and not url.startswith('http://'):
                url = 'http://' + url
                cleaned_data['url'] = url

            return cleaned_data

��clean()������.

�����ݵ��ֵ��ModelForm��cleaned_data���Ի�ȡ.
��ϣ�����ı��ֶο�����cleaned_data�ֵ��л�ȡ.ʹ��.get()�ֵ䷽����ȡ��ֵ.����û�û�б��ֶ�,��ôcleaned_data�ֵ��û������.�����������.get()�᷵��None�����������쳣.�⽫������Ĵ�����Ӽ��!
������ϣ������ı��ֶ�.���������һ��ֵ,������ֵ.���������ϣ����ֵ,������ڴ洢��cleaned_data�ֵ�֮ǰ����һЩ�߼����޸����ֵ.
����ÿ�ζ����Է���cleaned_data�ֵ�������clean()����.���û�н���õ�������ʾ.
���С����˵������ڱ����ݴ洢֮ǰ�����޸�.���Ƿǳ������,��������һЩ�ֶ���Ҫ�趨Ĭ��ֵʱ�����߱��е����ݷ����˶�ʧ.

ע��:��д������Django����ṩ����������Ӧ�ö��⹦�ܵ�һ�����ŵķ���.����ModelFormģ����clean()����һ��,Django�ṩ����లȫ�ķ������Թ�����д.


14.��ʾ

+ �޸�category()��ͼ,��category_name_slug�������ͼ��context_dict�ֵ�.
+ �޸�category.html���/rango/category/<category_name_url>/add_page/����.
+ ȷ��ֻ�������Ŀ¼����ʱ�Ż�������ӣ�ҳ����ڻ򲻴��ڽԿ�.����,��ģ����{% if category %} .... {% else %} A category by this name does not exist {% endif %}.
+ ��rangp/urls.py�޸�URLӳ��.


## �û���֤

���������̻���Django���û���֤����.���ǽ���ʹ��Django��׼��django.contrib.auth��authӦ��.

+ �û�.
+ Ȩ��:һϵ�еĶ����Ʊ�־(���� yes/no)�����û��������򲻿�����ʲô.
+ Ⱥ��:Ϊ��ֹһ���û��ṩȨ�޵ķ���.
+ �û���¼�ı�����ͼ����,������������.

���û���֤����Django�������ܶ�.���ǽ��ӻ�����ʼѧϰ.�⽫�ǳ������ڽ���ʹ�����ǵ����ĺ��������е�����.

1.������֤

����ʹ��Django����֤֮ǰ,����Ҫȷ�������rango��Ŀ��settings.py�ļ����Ѿ��������������.��settings.py�ļ����ҵ�INSTALLED_APPSԪ��,���django.contrib.auth��django.contrib.contenttypes�Ƿ���Ԫ����.

    INSTALLED_APPS = (
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'rango',
    )


django.contrib.authΪDjango�ṩ������֤ϵͳ,django.contrib.contenttypes����ͨ����֤��Ӧ�ó��������ٰ�װ�����ݿ�ģ��.

ע��:�������Ҫ��INSTALLED_APPSԪ�������authӦ��,����Ҫ������python manage.py migrate�����и������ݿ�.

����Ĭ�Ͻ����� PBKDF2 algorithm���д���,�����԰�ȫ�ı������û�������.Django���ṩ��ʹ�ò�ͬ�Ĺ�ϣ�㷨����߰�ȫ�ȼ�.

�����ϣ������ʹ�����ֹ�ϣ�㷨,����Ҫ��settings.py�����PASSWORD_HASHERSԪ��:

    PASSWORD_HASHERS = (
        'django.contrib.auth.hashers.PBKDF2PasswordHasher',
        'django.contrib.auth.hashers.PBKDF2SHA1PasswordHasher',
    )

Django����ʹ��PASSWORD_HASERS��ĵ�һ����ϣ�㷨(���� settings.PASSWORD_HASHERS[0]).

Ȼ����Ĭ��������㲻��Ҫ�޸�PASSWORD_HASHERS,DjangoĬ�����django.contrib.auth.hashers.PBKDF2PasswordHasher.

2.�û�ģ��

Django��֤ϵͳ����Ҫ�Ĳ��־���User����,��λ��django.contrib.auth.models.User.һ��User��������˺�DjangoӦ�ý������û�.

Userģ����Ҫ��5������.������:

+ �˻����û���
+ �˻�����
+ �û������ַ
+ �û���
+ �û���

ģ��Ҳ������һЩ������is_active(�����˻��ǻ���Ƿǻ״̬).�鿴official Django documentation on the user model,������������Userģ�������б�.


3.�����û�����

�����ϣ����Userģ���������������,����Ҫ����һ����Userģ����ص�ģ��.�������ǵ�rangoӦ��,����ϣ��Ϊ���ǵ��û�������������.����ϣ������:

+ URLField - �����û�д���Լ�����վ
+ ImageField - �����û������ǵĵ��������ͼƬ

������rango��models.py�ļ�������ģ��.�����Ǽ���UserProfileģ��:

    from django.contrib.auth.models import User

    class UserProfile(models.Model):
        user = models.OneToOneField(User)
        website = models.URLField(blank=True)
        picture = models.ImageField(upload_to='profile_images', blank=True)

    def __unicode__(self):
        return self.user.username

ע��������Userģ����ʹ��һ��һ��ϵ.��Ϊ����ʹ����Ĭ��Userģ��,������Ҫ��models.py�ļ��е���.

���������ǻ�����ֱ�Ӽ̳�Userģ����������Щ�ֶ�.������Ϊ����Ӧ��Ҳ������Ҫ��ȡUserģ��,�������ﲻ����ʹ�ü̳�,����ʹ��һ��һ��ϵ������.

����rango�����Ѿ������������ֶ��������û�����,���ṩ��һ��`__unicode__()`��������ʵ������.

����website��picture�����ֶ�,���Ƕ�������blank=True.����ʹ���е��ֶζ�Ϊ��,��ζ���û�����Ϊÿһ���������ֶ�ֵ.

ע��ImageField�ֶ���һ��upload_to����.�������ֵ������MEDIA_ROOT���������ṩ�ϴ��ĵ�ͼƬ��·��.����,MEDIA_ROOT����Ϊ<workspace>/itcast_project/media/,��ôupload_to=profile_imges����ʹͼƬ������<workspace>/itcast_project/media/profile_images/Ŀ¼.

`����:DjangoImageFieldʹ��pythonͼƬ��(pil).�����ڰ�װDjangoʱ�Ѿ�������ΰ�װpil.�����û�а�װ���ھͿ��԰�װ��.�����û�а�װpil,��ô��������pilģ�鲻���ҵ��Ĵ���!
������UserProfileģ��,������Ҫ�޸�rango��admin.py�ļ�ʹ����������UserPrifileģ��.��admin.py�ļ����������.`

    from rango.models import UserProfile

    admin.site.register(UserProfile)

ע��:�������޸�ģ�ͺ���Ҫ�������ݿ�.

    python manage.py makemigrations rango
    python manage.py migrate.

4.�����û�ע�������ͼ��ģ��

ע��:����������ֳɵ��û�ע�������ʹ��,���Ǵ��ļ��ٴ���ע��ͱ��ķ����̶�.
Ϊ�û��ṩע�����������Ҫ���¼���:

+ ����UserForm��UserProfileForm.
+ ���Ӵ������û���ͼ.
+ ����չʾUserForm��UserProfileForm��ģ��.
+ ӳ��URL.
+ ����ҳ����ע��ҳ����

5.ע���

��rango/forms.py��,������Ҫ���������̳���forms.ModelForm����.һ����ΪUserģ�ʹ�����,һ����ΪUserProfile������.�������̳���ModelForm����������ṩչʾHTML������Ҫ�ı��ֶ�.

��rango/forms.py�ļ�,�����Ǵ�����������.

    from django import forms
    from django.contrib.auth.models import User
    from rango.models import Category, Page, UserProfile

    class UserForm(forms.ModelForm):
        password = forms.CharField(widget=forms.PasswordInput())
        class Meta:
            model = User
            fields = ('username', 'email', 'password')

    class UserProfileForm(forms.ModelForm):
        class Meta:
            model = UserProfile
            fields = ('website', 'picture')

ע�⵽�������������Ƕ�������Meta��.��Meta�������ж��嶼�ᱻ�������ĸ�������.ÿ��Meta���ٰ���һ��model�ֶ�,�����Ժ�ģ��֮�����.���������ǵ�UserForm���о͹�����Userģ��.��Django1.7+���������fields����exclude����������Ҫչʾ���ֶ�.

�������ǽ�����ҪչʾUserģ�͵�username,email��password�ֶ�,��UserProfileģ�͵�website��picture�ֶ�.���û�ע���ʱ��������Ҫ����UserPrifileģ�͵�user�ֶ�.

�����˰�UserForm����һ������password����.��Userģ��ʵ��Ĭ�ϰ���password����ʱ,HTML��Ԫ�ؽ�������������.����û���������,��ô�������ͻ�ɼ�.���������޸�password������ΪCharFieldʵ����ʹ��PasswordInput()�齨,��ʱ�û�����ͻᱻ����.


6.����register��ͼ

�������Ǵ�����ͱ����������.��rango��views.py�ļ�,����������ͼ����:

    from rango.forms import UserForm, UserProfileForm

    def register(request):
        registered = False
        if request.method == 'POST':
            user_form = UserForm(data=request.POST)
            profile_form = UserProfileForm(data=request.POST)
            if user_form.is_valid() and profile_form.is_valid():
                user = user_form.save()
                user.set_password(user.password)
                user.save()
                profile = profile_form.save(commit=False)
                profile.user = user

                if 'picture' in request.FILES:
                    profile.picture = request.FILES['picture']

                profile.save()
                registered = True
            else:
                print user_form.errors, profile_form.errors
        else:
            user_form = UserForm()
            profile_form = UserProfileForm()
        return render(request,'rango/register.html',
                        {'user_form': user_form, 
                        'profile_form': profile_form, 
                        'registered': registered} )


������ǰ��add_category()��ͼ���,���������������ͬ��ModelFormʵ��,һ����Userģ�͵�,��һ����UserProfileģ�͵�.����û��ϴ�ͼ�����ǻ�����Ҫ��������.

���ǻ���Ҫ��������ģ��ʵ��֮�������.�����µ�Userģ��ʵ����,������Ҫ��profile.user = user����������UserProfileʵ��.

7.����ע��ģ��

�������Ǵ���rang/register.html�������´���:

    <!DOCTYPE html>
    <html>
    <head>
        <title>Rango</title>
    </head>

    <body>
        <h1>Register with Rango</h1>

        {% if registered %}
        Rango says: <strong>thank you for registering!</strong>
        <a href="/rango/">Return to the homepage.</a><br />
        {% else %}
        Rango says: <strong>register here!</strong><br />

        <form id="user_form" method="post" action="/rango/register/"
                enctype="multipart/form-data">

            {% csrf_token %}

            <!-- Display each form. The as_p method wraps each element in a paragraph
                 (<p>) element. This ensures each element appears on a new line,
                 making everything look neater. -->
            {{ user_form.as_p }}
            {{ profile_form.as_p }}

            <!-- Provide a button to click to submit the form. -->
            <input type="submit" name="submit" value="Register" />
        </form>
        {% endif %}
    </body>
    </html>

���HTMLģ��ʹ��registered���������ע���Ƿ�ɹ�.��registeredΪFalseʱģ���չʾע���,����,���˱�������ֻ��չʾһ���ɹ���Ϣ.

`����:�����ע�⵽��<form>Ԫ�����enctype����.����ϣ���û�ͨ�����ϴ��ļ�ʱ,�����enctype���ó�multipart/form-data.������Ի��������������ض��ķ�ʽ�ѱ����ݷ��ظ�������.ʵ����,����ļ��ᱻ�ֳ�һ���Ĵ���.���˽����鿴 this great Stack Overflow answer.��ҲӦ���ǵü���CSRF����.ȷ�������<form>���������{% csrf_token %}.`


8.��ͼregister��URLӳ��

����Ϊ���ǵ�����ͼ����URLӳ��.��rango/urls.py�ļ����޸�urlpatternsԪ������:


    urlpatterns = patterns('',
        url(r'^$', views.index, name='index'),
        url(r'^category/(?P<category_name_slug>[\w\-]+)/$', views.category,name='category'), 
        url(r'^add_category/$', views.add_category, name='add_category'), 
        url(r'^category/(?P<category_name_slug>[\w\-]+)/add_page/$', views.add_page, name='add_page'),
        url(r'^register/$', views.register, name='register'),  # New!
    )
 
�¼����ģʽ��URL,rango/register/ָ��register()��ͼ.

9.��ҳ��������

���,������Ҫ����ҳindex.htmlģ�����������.�����Ŀ¼���Ӻ������������.

    <a href="/rango/register/">Register Here</a>

10.Demo
��������Ե��Register Here�����ӽ��뵽ע��ҳ��.�������Կ�!�������Django��������ע��һ���˻�.�����Ը������ϴ�һ������ͼƬ.���ע���������������һ��.


