# Getting started with a Django website
Documentation from the django tutorial on how to get started with building a django website


### Check django is installed
`python -m django --version`

### Create a project (rename 'mysite')
`django-admin startproject mysite`

### See website on the development server
`python manage.py runserver`

### Create a new 'app' (named 'polls') in 'mysite'
`python manage.py startapp polls`

### Create first view
```
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

### Update polls/urls.py
```
from django.urls import path

from . import views

urlpatterns = [
    path("", views.index, name="index"),
]
```

### Add 'app' to the urls.py file
```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path("polls/", include("polls.urls")),
    path("admin/", admin.site.urls),
]
```

### Now test that the page 'http://localhost:8000/polls/' working
`python manage.py runserver`

