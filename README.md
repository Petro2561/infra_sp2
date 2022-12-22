# Проект YaMDb

Проект "YaMDb" собирает отзывы пользователей на произведения.
Сами произведения в "YaMDb" не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку.
На основе пользовательских оценок формируется усреднённая оценка произведения — рейтинг.

Проект подготовлен для изучения базовых принципов построения
API на основе фреймворка [DRF]

## Используемые технологии:
- Python 3.7.9
- Django 2.2.16
- DRF 3.12.4

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
