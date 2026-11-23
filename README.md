# homework-web-development-1
Лабораторная работа №1
Институт Информационных Технологий и Кибербезопасности
Дисциплина: Разработка web-приложений
Тема: Создание виртуального окружения. Контроллеры и маршруты

Выполнил: Ибрагимов Магомед Абдуллаевич
Группа: ПИЖ-б-о-25-2

Цель работы: настроить виртуальное пространство. Разработать контроллер приложения и организовать маршруты

Код WebSite.urls
```
from django.contrib import admin
from django.urls import path, include
from news.views import *

urlpatterns = [
    path('admin/', admin.site.urls),
    path('news/', include('news.urls')),
]
```

Код news.views
```
from django.shortcuts import render
from django.http import HttpResponse
# Create your views here.

def index(request):
    print(request)
    return HttpResponse('Hello World')

def test(request):
    return HttpResponse('<h1>Тестовая страница</h1>')
```

Код news.urls
```
from django.urls import path

from .views import *

urlpatterns = [
    path('', index),
    path('test/', test)
]
```
Код settings.py
```

from pathlib import Path

# Build paths inside the project like this: BASE_DIR / 'subdir'.
BASE_DIR = Path(__file__).resolve().parent.parent


# Quick-start development settings - unsuitable for production
# See https://docs.djangoproject.com/en/6.1/howto/deployment/checklist/

# SECURITY WARNING: keep the secret key used in production secret!
SECRET_KEY = 'django-insecure-d2uakrpu#d-^b5!xubu%=#9$d!7*kgs(rpt$$=8=g9!0o+2ypl'

# SECURITY WARNING: don't run with debug turned on in production!
DEBUG = True

ALLOWED_HOSTS = []


# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'news.apps.NewsConfig',
]

MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]

ROOT_URLCONF = 'WebSite.urls'

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

WSGI_APPLICATION = 'WebSite.wsgi.application'


# Database
# https://docs.djangoproject.com/en/6.1/ref/settings/#databases

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}


# Password validation
# https://docs.djangoproject.com/en/6.1/ref/settings/#auth-password-validators

AUTH_PASSWORD_VALIDATORS = [
    {
        'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
    },
]


# Internationalization
# https://docs.djangoproject.com/en/6.1/topics/i18n/

LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'UTC'

USE_I18N = True

USE_TZ = True


# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/6.1/howto/static-files/

STATIC_URL = 'static/'


# Email
# https://docs.djangoproject.com/en/6.1/topics/email/#topic-email-configuration

MAILERS = {
    'default': {
        'BACKEND': 'django.core.mail.backends.console.EmailBackend',
    },
}

```


<br><br><img width="654" height="68" alt="image" src="https://github.com/user-attachments/assets/0a633483-be4a-4154-8093-c9643b0b7f3b" />
<br>Рисунок 1 - Создание виртуального рабочего стола

<br><br><img width="242" height="391" alt="image" src="https://github.com/user-attachments/assets/7298c6fc-461e-4074-8a92-4d998bdf0b4a" />
<br>Рисунок 2 - Корневая папка проекта

<br><br><img width="1919" height="990" alt="image" src="https://github.com/user-attachments/assets/fac89ce0-a901-4d11-9c17-7d6c53292180" />
<br>Рисунок 3 - Запуск веб-сервера

<br><br><img width="1077" height="749" alt="image" src="https://github.com/user-attachments/assets/a57e0ff6-bbb3-44f5-a1bc-fe52ecd7e1da" />
<br>Рисунок 4 - Создание приложения news

<br><br><img width="456" height="273" alt="image" src="https://github.com/user-attachments/assets/2ebe95c9-14d0-446a-8b17-d0c4d2aba0f3" />
<br>Рисунок 5 - Добавление в настройки приложения news

<br><br><img width="627" height="291" alt="image" src="https://github.com/user-attachments/assets/ababa2cf-7134-4dab-9555-55991011409e" />
<br>Рисунок 6 - Написание контроллера

<br><br><img width="870" height="361" alt="image" src="https://github.com/user-attachments/assets/dcfdd72d-00b7-419d-935c-266454c495d6" />
<br>Рисунок 7 - Создание тестового контроллера

<br><br><img width="513" height="170" alt="image" src="https://github.com/user-attachments/assets/3a1db742-8b5b-4081-a293-234cf3961598" />
<br>Рисунок 8 - Добавление ссылок в файл url

<br><br><img width="550" height="244" alt="image" src="https://github.com/user-attachments/assets/8ac3abb1-9056-4d39-ad62-1ced8dd6add4" />
<br>Рисунок 9 - Создание вложенности в файле urls.py

<br><br><img width="1919" height="990" alt="image" src="https://github.com/user-attachments/assets/e5f60ea0-6a57-4f33-bf21-0c6b635dc521" />
<br>Рисунок 10 - Реализация вложенных ссылок

