# django_blog PROJECT

![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)

This project is a relecture of a project I found in a book, that is only available in Mac OS. 

![django](img/django.png)

## Overview
This project holds some nice features available by Django framework along with some helpful technologies as Waitress, which originally didn't feature in the project.

Originally, the project used Gunicorn as WSGI server and Heroku for deploying. Unfortunately, Gunicorn doesn't run in Windows OS since `fcntl` module can't be run in this OS.
I used Waitress and made some alterations in root directory and added a `server.py` archive along with `manage.py` in order to raise a new useble prompt command.

### Home

Basic home appearance.
<img src="https://raw.githubusercontent.com/miguelrferreiraf/django_blog/main/img/home.png" alt="flask" width="55%" height="55%">

### Sign up page

This blog uses Django applications that allow the creation of users accounts for commenting posts.
<img src="https://raw.githubusercontent.com/miguelrferreiraf/django_blog/main/img/singup.png" alt="flask" width="45%" height="54%">

### WSGI Waitress Server

We should create a `server.py` in project root directory and its code goes like this:

```
from waitress import serve
    
from django_project.wsgi import application
    
if __name__ == '__main__':
    serve(application, port='8000')
```
After this, we proceed with alterations in `wsgi.py` archive in order to add Whitenoise static files serving adding Whitenoise `get_wsgi_application()` application.

```
import os

from django.core.wsgi import get_wsgi_application

os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'django_project.settings')

# Upgrading in default format into this:
from whitenoise import WhiteNoise
application = WhiteNoise(get_wsgi_application())
```
### Running

Run `python server.py` and open in `127.0.0.1:8000`

