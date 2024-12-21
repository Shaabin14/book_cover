# Ex.06 Book Front Cover Page Design
# Date:28.10.2024
# AIM:
To design a book front cover page using HTML and CSS.

# DESIGN STEPS:
## Step 1:
Create a Django Admin project.

## Step 2:
Create an app in the Django interface.

## Step 3:
Create a folder named 'static' in the app folder.

## Step 4:
Create a new HTML file in the static folder.

## Step 5:
Write the HTML code with relevant CSS properties.

## Step 6:
Choose the appropriate style and color scheme.

## Step 7:
Insert the images in their appropriate places.

## Step 8:
Publish the website in the LocalHost.

# PROGRAM:
views.py
```
from django.shortcuts import render
def book(request):
    return render(request,'book.html')
```
book.html
```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Book Cover</title>
    <link rel="stylesheet" href="css/style.css">

<style>
{% load static%}
    * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body, html {
    height: 100%;
    font-family: 'Arial', sans-serif;
    width: 600px;
    height: 800px;
    display: flex;
    background-image: url("{% static 'photo.jpg'%}");
    background-repeat: no-repeat;
    background-size: 590px 800px;
    justify-content: flex-end; 
    align-items: center;
    margin: 50px auto;
    border: 2px solid #ddd;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
}

.cover-content {
    text-align: center;
    background-color: rgba(14, 13, 13, 0.7);
    padding: 20px 30px;
    border-radius: 10px;
}

.book-title {
    
    font-size: 2.3rem;
    color: #17f72a;
    margin-bottom: 10px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    left:525px;
    top:130px;
    position:absolute;

}

.author-name {
    font-size: 2rem;
    color: #17f72a;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
    left:520px;
    top:720px;
    position:absolute;
}
@media (max-width: 768px) {
    .book-cover {
        width: 300px;
        height: 450px;
        padding-bottom: 30px; 
    }

    .book-title {
        font-size: 2rem;
    }

    .author-name {
        font-size: 1.2rem;
    }
}
.images{
    height: 300px;
    width: 300px;
    display: inline-block;
}
</style>
</head>
{% load static %}
<body>
    </div>
    {% load static %}
    <div class="book-cover">
        <div class="images"><img src="{% static 'tree.png'%}" width="300px" height="300px"></div>
        <div class="cover-content">
            <h1 class="book-title" align="center">THE ENCHANTED FOREST</h1>
            <h2 class="author-name">BY SHAABIN RS</h2>
        </div>
    </div>
</body>
</html>
```
css
```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body, html {
    height: 100%;
    font-family: 'Arial', sans-serif;
}
.book-cover {
    width: 800px;
    height: 1000px;
    background: url('WhatsApp\ Image\ 2024-12-05\ at\ 13.45.15_b0d3bf20.jpg') no-repeat  center/cover;
    display: flex;
    justify-content: flex-end; 
    align-items: center;
    margin: 50px auto;
    border: 2px solid #ddd;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
}

.cover-content {
    text-align: center;
    background-color: rgba(14, 13, 13, 0.7);
    padding: 20px 30px;
    border-radius: 10px;
}

.book-title {
    
    font-size: 2.5rem;
    color: #17f72a;
    margin-bottom: 10px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    left:850px;
    top:250px;
    position:absolute;

}

.author-name {
    font-size: 2rem;
    color: #fff;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
    left:520px;
    top:720px;
    position:absolute;
}
@media (max-width: 768px) {
    .book-cover {
        width: 300px;
        height: 450px;
        padding-bottom: 30px; 
    }

    .book-title {
        font-size: 1.5rem;
    }

    .author-name {
        font-size: 1.2rem;
    }
}
.images{
    height: 300px;
    width: 300px;
    display: inline-block;
}
```
settings.py
```
from pathlib import Path
import os
BASE_DIR = Path(__file__).resolve().parent.parent

SECRET_KEY = 'django-insecure-4&dk95-615$p23ql8au%4yu4x$b)wn076wvku&g(z_al22ub*j'
DEBUG = True

ALLOWED_HOSTS = ['*']

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'bookapp'
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

ROOT_URLCONF = 'vijay.urls'

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

WSGI_APPLICATION = 'vijay.wsgi.application'

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

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

LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'UTC'

USE_I18N = True

USE_TZ = True

STATIC_URL = 'static/'
STATICFILES_DIRS=[os.path.join(BASE_DIR,'bookapp/static')]

DEFAULT_AUTO_FIELD = 'django.db.models.BigAutoField'

```
urls.py
```
from django.contrib import admin
from django.urls import path
from bookapp import views

urlpatterns = [
    #path('admin/', admin.site.urls),
    path('book',views.book)
]
```
# OUTPUT:
![book cover](https://github.com/user-attachments/assets/c488076e-6548-4bdf-a872-6782c1804faa)

# RESULT:
The program for designing book front cover page using HTML and CSS is completed successfully.
