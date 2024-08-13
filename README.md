# Django project

## Setup instructions

- Create a new repo
- pip3 install Django
- pip3 freeze > requirements.txt
- django-admin startproject **project_name** . ( . - means current directory)
- python3 manage.py runserver

- copy the invalid host header, usually starting - '8000-sometext'
- include the host header in the settings.py file under ALLOWED_HOSTS
- refresh to check and close the server

- python3 manage.py startapp **app_name** (creates a new app)

- in the appname/views.py add - 'from django.http import HttpResponse'
- add a view function eg below
'def index(request):
    return HttpResponse("Hello World!")'

- in the projectname/urls.py add - 'include' after the 'path' import (from django.urls)
- below include 'from appname import views as index_views'
- in the urlpatterns array add to the top - 'path('', index_views.index, name='index'),'
- in the projectname/settings.py add to the installed apps - 'appname'
- rerun the server with - 'python3 manage.py runserver'