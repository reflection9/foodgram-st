# Foodgram — «Продуктовый помощник»

## Описание проекта

**Foodgram** — это веб-приложение, позволяющее искать рецепты, сохранять любимые блюда и автоматически формировать список покупок на основе выбранных рецептов.  
Пользователь может:
- Просматривать ленту рецептов и информацию о каждом из них.
- Добавлять рецепты в «Избранное» и подписываться на авторов.
- Формировать единый файл со списком продуктов для закупки.

## Технологический стек

- **Backend**: Python 3.11, Django 4.x, Django REST Framework  
- **Frontend**: React, JavaScript (ES6+)  
- **База данных**: PostgreSQL  
- **Сервер**: Nginx  
- **Контейнеризация**: Docker, Docker Compose

## Требования

- Установлены Docker и Docker Compose (версия ≥ 1.29.0).
- Git (для клонирования репозитория).

## Быстрый старт

1. **Клонировать репозиторий**  
   ```bash
   git clone https://github.com/ArtSharifullin/foodgram-st.git
   cd foodgram-st/foodgram-st
2. **Скопировать и при необходимости отредактировать файл окружения**
   ```bash
   cp .env .env.local
3. **Запустить сервисы через Docker Compose**
   ```bash
   cd infra
   docker-compose up --build -d
4. **Выполнить миграции**
   ```bash
   docker-compose exec backend python manage.py migrate
5. **Создать суперпользователя (опционально)
   ```bash
   docker-compose exec backend python manage.py createsuperuser
6. **Собрать статику**
   ```bash
   docker-compose exec backend python manage.py collectstatic --no-input
7. **Загрузить тестовые данные**
   ```bash
   docker-compose exec backend python manage.py import_data

## Переменные окружения

В корне проекта создайте файл `.env` со следующим содержимым:

```dotenv
# Секретный ключ Django
SECRET_KEY=<ваш_секретный_ключ>

# Включить/выключить отладочный режим
DEBUG=True

# Настройки базы данных
DB_ENGINE=django.db.backends.postgresql
DB_NAME=foodgram           # при необходимости подставьте свои значения
DB_USER=postgres           # при необходимости подставьте свои значения
DB_PASSWORD=postgres       # при необходимости подставьте свои значения
DB_HOST=db
DB_PORT=5432