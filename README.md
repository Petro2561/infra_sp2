# Проект YaMDb

Проект "YaMDb" собирает отзывы пользователей на произведения.
Сами произведения в "YaMDb" не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку.
На основе пользовательских оценок формируется усреднённая оценка произведения — рейтинг.

Проект подготовлен для изучения базовых принципов построения
API на основе фреймворка [DRF]

## Примеры работы с api проекта:

Получение списка произведений

```
GET api/v1/titles/
```

Получение списка отзывов на произведение

```
 GET api/v1/titles/{title_id}/reviews/
```

Получение списка комментариев к отзывам

```
GET /api/v1/titles/{title_id}/reviews/{review_id}/comments/
```

Подробное описание api в формате ReDoc доступно [тут]

[DRF]: <https://www.django-rest-framework.org/>
[тут]: <http://127.0.0.1:8000/redoc/>

## Используемые технологии
  -Python 3.7.9 https://docs.python.org/3.7/
  -Django 2.2.16 https://docs.djangoproject.com/en/4.1/
  -DRF 3.12.4 https://www.django-rest-framework.org/topics/documenting-your-api/
  -Docker 20.10.16 https://www.docker.com/
  -nginx 1.21.3 http://nginx.org/en/docs/
  -gunicorn 20.0.4 https://docs.gunicorn.org/en/stable/

# Docker
  Для запуска контейнера необходимо скачать, установить и запустить Docker.
  https://www.docker.com/

# Склонирйте репозитарий
  git clone SSH-адрес_вашего_форка

## Создайте и заполните по образцу .env-файл
  DB_ENGINE=<...>
  DB_NAME=<...>
  POSTGRES_USER=<...>
  POSTGRES_PASSWORD=<...>
  DB_HOST=<...>
  DB_PORT=<...>
  SECRET_KEY=<...>
## Соберите и запустите контейнер с помощью Docker-compose
  docker-compose build
  docker-compose up
## Выполните миграции через Docker-compose
  docker-compose exec web python manage.py makemigrations --noinput
  docker-compose exec web python manage.py migrate --noinput
## Соберите через Docker-compose статику
  docker-compose exec web python manage.py collectstatic --no-input
## Создайте суперпользователя
  docker-compose exec web python manage.py createsuperuser
## Заполнить базу начальными данными
  docker-compose exec web python manage.py loaddata fixtures.json

## Авторы проекта
  Андреев Петр https://github.com/Petro2561
  Бобко Сергей https://github.com/nentron
  Федотов Алексей https://github.com/uyngruynd

