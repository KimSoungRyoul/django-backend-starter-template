# [django-backend-starter Template]
[![Python 3.11](https://img.shields.io/badge/python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3111/)
[![Django](https://img.shields.io/badge/Django-4.2-092E20?style=flat&logo=django&logoColor=white)](https://www.djangoproject.com/start/overview/)
[![Checked with mypy](https://www.mypy-lang.org/static/mypy_badge.svg)](https://mypy-lang.org/)


[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Imports: isort](https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336)](https://pycqa.github.io/isort/)

## [django-backend-starter template docs](#)


## QuickStart

1. create django-project
   ~~~shell
   pip install django
   ~~~   

   ~~~shell
   django-admin startproject --template=https://github.com/KimSoungRyoul/django-backend-starter-template/archive/main.zip  hello_django_project
   ~~~

2. create virtualenv(venv) using poetry & install library
    ~~~shell
    poetry config virtualenvs.in-project true # if true .venv was created in PROJECT ROOT
    poetry shell
    poetry install
    ~~~

3. [Optional] install pre-commit config
   * if you want always run black&isort before commit
   ~~~shell
   pre-commit install
   ~~~
   * pre-commit run (reformatting)
   ~~~shell
   pre-commit run --files apps/**/**
   ~~~

4. [Optional] if you want to use not only sqlite3
   ~~~shell
   docker compose -f docker/compose.yaml up -d
   ~~~

5. django migration
    ~~~shell
    python apps/manage.py migrate
    ~~~

6. create superuser for test
   ~~~shell
   python apps/manage.py createsuperuser --username=root --email=kimsoungryoul@gmail.com
   ~~~

7. django runserver
    ~~~shell
    python apps/manage.py runserver 8000
    ~~~

8. you can see default API Docs in http://localhost:8000/docs

   <img src="./docs/img/hello_django_backend_template.png" width="60%" height="50%">


   8-1. get JWT Token with Login API

   <img src="docs/img/login_example.png" width="60%" height="50%">

   8-2. set JWT Token to API Docs

   <img src="docs/img/sample_auth.png" width="60%" height="50%">

   8-3. you can use other APIs

   <img src="docs/img/api_with_auth.png" width="60%" height="50%">


## build
* install docker first [install docker desktop](https://www.google.com/search?q=docker+desktop&sourceid=chrome&ie=UTF-8)
1. docker build
   ~~~shell
   docker build -f docker/application.dockerfile -t django-backend-starter-application:1.0.0 .
   ~~~
2. docker run
   ~~~shell
   docker run -d -p "8000:8000" --rm --name django-backend-application django-backend-starter-application:1.0.0
   ~~~
