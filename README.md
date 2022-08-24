[![.github/workflows/yamdb_workflow.yml](https://github.com/Lexxar91/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)](https://github.com/Lexxar91/yamdb_final/actions/workflows/yamdb_workflow.yml)

# Yamdb
Описание проекта:

Проект YaMDb - это сервис собирающий отзывы пользователей на книги, фильмы, музыку. Список категорий может быть расширен администратором сервиса. У произведения есть жанр, который можно выбрать из списка предустановленных(например, «Сказка», «Детектив» и т.п). Жанры создаются администратором сервиса. Пользователи могут оставить свой отзыв на произведение, но не более одного раза.

### Стэк технологий:

[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)

### Подготовка.

Необходимо установить Docker:

- выполните команду docker --version и проверьте , что Docker установлен.
Если Docker отсутствует необходимо зайти на официальный сайт и скачать установочный файл Docker Desktop для вашей операционной системы. Далее необходимо следовать инструкциям по установке в зависимости от Вашей операционной системы.

### Запуск приложения.

Клонируйте репозиторий:
**https://github.com/Lexxar91/yamdb_final**

Создайте виртуальное:
**python -m venv venv**

Активируйте виртуальное окружение и запустите установку пакетов из requirements.txt:
**venv\Scripts\activate**

**pip install -r requirements.txt**

### Выполните команду:

**docker-compose up -d --build**

После успешной сборки и запуска контейнеров нужно выполнить миграции:

**docker-compose exec web python manage.py migrate --noinput**

Установите статику:
**docker-compose exec web python manage.py collectstatic --no-input**

Заполните базу данных:
**docker-compose exec web python3 manage.py loaddata fixtures.json**

Создайте суперпользователя:
**docker-compose exec web python manage.py createsuperuser**
