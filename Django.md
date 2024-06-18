# Django Tutorial Notes / Reference Guide
## Table of Contents
- [Overview](#overview)
    - [This Project Directory](#project-directory)
- [Working With a Django Project](#working-with-a-project)
    - [Create A Project](#create-a-project)
    - [Run a Project](#run-a-project)
        - [Development Server](#development-server)
- [Sources](#sources)



# Overview

## Django Project Container Directory

Django follows a particular scheme for building projects.

> **Django Container /**
>
>> **manage.py**
>
>> **Django Project Directory**
>
>> **Django Application Directories**

The Django container holds the command line utility *manage.py* and all of the python modules used for a django project.
manage.py will let you interact with the django project in various ways.

## Django Project Module

The Django Project Module is a Python module built during the *django-admin startproject {project-name}* command when the project is first initialized.

#### Django_Project\settings.py

the settings file is used to configure the Django project.

#### Django_Project\urls.py 

the urls file is used to send URL declarations for this project to the URL dispatcher. It will act as a table of contents for the site.
* to define an object of type list *urlpatterns*. This list will contain the result of the imported function django.urls.path
* in order to use a created applications url patterns, you can use the include function

    from django.contrib import admin # Admin interface application included with Django
    from django.urls import path

    urlpatterns = [
        path('admin/', admin.site.urls),
        path('myapp/', include('myapp.urls'))   
    ]

#### wsgi.py / asgi.py

An Entrypoint for compatible web servers for serving the project.t5-ldiedrich

# Working With a Django Project

## Create A Project

From "Django Tutorial" directory:

    django-admin startproject *project_name*

## Run a Project

#### Development Server

From the *Django Container* directory:

    python manage.py runserver

## Create a Django Application Directory

From the *Django Container* directory:
    
    python manage.py startapp *app_name*

## User Management

#### Create a superuser

From the *Django Container* directory:

    python manage.py createsuperuser

# Sources


#### Tutorials used
* [Tutorial followed for this project](docs.djangoproject.com/en/5.0/intro/tutorial01/)

#### django-admin and manage.py resources

* ['django-admin and manage.py' documentation](docs.djangoproject.com/en/5.0/ref/django-admin)
