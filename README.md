# openshift-django-sample
A django sample for openshift, compatible with the new directory layout

Written for django 1.7.x and python 3.3, but can be adapted to python 2.7 (instructions in this file)

Licence: MIT for the parts that are in my domain (most is openshift and django code)

This git repository intends to provide a starter django app for deployment
on openshift. The Django project name used in this repo is 'myproject'
but can be changed, or you can delete the 'myproject' folder and install
a new one with `django-admin.py startproject <project name>`.

Deployment on openshift:

* Create an account at https://www.openshift.com
* Install rhc: https://developers.openshift.com/en/managing-client-tools.html
* Setup your machine: `$ rhc setup`
* Create a python application: `$ rhc app create django python-3.3`
* Add this repo as upstream:
```
  $ cd django
  $ git remote add upstream -m master https://github.com/ZackYovel/openshift-django-sample
  $ git pull -s recursive -X theirs upstream master
```
* Push your code to openshift: `$ git push`


Work with python 2.7:
---------------------

1. In wsgi.py un-comment the line: `#execfile(virtualenv, dict(__file__=virtualenv)) # for Python v2.7`
2. Still there, comment-out any un-commented line between the `try` and the `except`, such that the line you've un-commented previously remains the only un-commented line
3. Follow the steps of 'Deployment on openshift' above, but use python-2.7 instead of python-3.3

Good luck!

