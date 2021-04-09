# project_Django_React_Spotify

## next steps

- part 2

# intro

based on YT TechWithTim

1. run virtualenv (pyenv)
2. we will need npm and Node.js
3. VSCode ext.
    - Prettier - Code formatter
    - Django
    - ES7 React ... snippets
    - JavaScript (ES6) code snippets
4. python pkg:
    - django
    - djangorestframework

## Django setup

1. Create a Django dir structure project `django-admin startproject music_controller`
2. Create django-app within `music_controller` project, `django-admin startapp api`
3. `settings.py` add api app to `INSTALLED_APPS` -> `api.apps.ApiConfig` it is class inside apps.py file
4. `settings.py` add `rest_framework`

We will be writing endpoints in `views.py`
1. Add simple endpoint that return "Hello" using `HttpResponse` from `django.http`
2. U can return HTML tag e.g. `return HttpResponse('<h1>Hello<h1>')`

How to conest url with this view? Create file `urls.py` inside api-app, it will hold urls local to this app. The main `urls.py` is located in project dir, the inside `urlpatterns` list routes URLs to views. 
1. `main:urls.py` add route to test view, `path('', include('api.urls'))`
2. `app:urls.py` map route to main view,
    - need to import view if U want to bind route
```py
form .views import main

urlpatterns = [
    path('', main),
]
```
3. play with different urls e.g. change for /home

## Django make migrations

1. `python ./manage.py makemigrations` at the start of project and everytime U change model or database.
2. `python ./manage.py migrate`
NOTE: .gitignore from GitHub will exclude `db.sqlite3` file

# Django Run Server

- `python ./manage.py runserver` if 8000 port is already used try: `runserver [PORT]`, will restart if U change and save Django files.


# LINKs

- [Django doc](https://docs.djangoproject.com/en/3.2/)