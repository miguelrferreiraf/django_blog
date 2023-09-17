# django_blog PROJECT

![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)

This project is a relecture of a project I found in a book, that is only available in Mac OS. 

![django](img/django.png)

## Overview
This project holds some nice features available by Django framework along with some helpful technologies as Waitress, which originally didn't feature in the project.

Originally, the project used Gunicorn as WSGI server and Heroku for deploying. Unfortunately Gunicorn doesn't run in Windows OS since `fcntl` module can't be run in this OS.
I used Waitress and made some alterations in root directory and added a `server.py` archive along with `manage.py` in order to raise a new useble prompt command.

### Home

Basic home appearance.
![home](img/home.png)

### Sign up page
![signup](img/singup.png)

