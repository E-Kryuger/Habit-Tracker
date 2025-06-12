# Habit-Tracker

## Описание
**Habit-Tracker** – это серверная часть SPA веб-приложения для отслеживания полезных привычек, 
основанная на концепции, изложенной в книге Джеймса Клира «Атомные привычки». 
Проект позволяет пользователям добавлять, редактировать и удалять привычки, получать напоминания в Telegram.

## Зависимости
- celery 5.4.0 
- coverage 7.6.11
- Django 5.1.5 
- django-celery-beat 2.7.0
- django-cors-headers 4.6.0
- djangorestframework 3.15.2
- djangorestframework_simplejwt 5.4.0
- drf-yasg 1.21.8
- flake8 7.1.1
- ipython 8.32.0
- pillow 11.1.0
- psycopg2-binary 2.9.10
- python-dotenv 1.0.1
- redis 5.2.1
- requests 2.32.3

## Установка
1. Клонируйте репозиторий:
   ```shell
   https://github.com/E-Kryuger/Habit-Tracker.git
   ```
2. Установите зависимости:
   ```shell
   pip install -r requirements.txt
   ```

## Подключение БД
1. Создайте БД
2. Создайте файл `.env` из файла `.env.sample`

## Применение миграций
```shell
python manage.py migrate
```

## Наполнение проекта данными
```shell
python manage.py fill_project
```

## Запуск
1. Запустите сервер Django:
   ```shell
   python manage.py runserver
   ```
2. Запустите брокер Redis:
   ```shell
   redis-server
   ```
3. Запустите Celery worker с планировщиком Celery beat:
   ```shell
   celery -A config worker --beat --scheduler django --loglevel=info
   ```

## Тестирование
Создание текстового отчёта:
```shell
coverage run --source='.' --omit='*/migrations/*','*/management/*','*/__init__.py' manage.py test
```
```shell
coverage report
```