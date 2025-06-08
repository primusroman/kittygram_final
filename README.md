# Kittygram - социальная сеть для любителей котиков

## Описание приложения
Kittygram - это социальная платформа для публикации фотографий кошек. Основные возможности:
- Публикация фотографий с описанием
- Просмотр ленты публикаций
- Регистрация и авторизация пользователей
- Личный кабинет для управления своими публикациями

Доступ к контенту имеют только авторизованные пользователи. Приложение реализовано как микросервисная архитектура, работающая в Docker-контейнерах.

## Необходимые инструменты
Для работы с проектом потребуется:
- Docker 20.10+
- Docker Compose 1.29+
- Python 3.9+
- Node.js 18+
- Git

## Установка и запуск

### Локальная разработка
1. Клонировать репозиторий:
   
   git clone https://github.com/primusroman/kittygram_final.git
       
  cd kittygram
   
2. Создать и заполнить .env файлы:

cp
 .env.example .env
cp 
frontend/.env frontend/.env
3.
 Запустить контейнеры:

dock
er-compose up -d --build

4.
 Применить миграции:
docke
r-compose exec backend python manage.py migrate

5. 
Собрать статику:
docker
-compose exec backend python manage.py collectstatic

Прил
ожение будет доступно по адресу: http://localhost:80

### Продакшен-развертывание
Для развертывания на сервере используется CI/CD pipeline:

При push в ветку main автоматически запускаются тесты

Успешное прохождение тестов инициирует сборку Docker-образов

Образы публикуются в Docker Hub

Происходит автоматический деплой на сервер

Развернутая версия приложения доступна по адресу:
https://primkittygram.duckdns.org/
# Используемые технологии
Backend
- Python 3.9
- Django 3.2
- Django REST Framework 3.12
- Djoser 2.1 (аутентификация)
- PostgreSQL 13
- Gunicorn
- Nginx (gateway)

Frontend
- React
- Bootstrap

Инфраструктура
- Docker
- Docker Compose
- GitHub Actions (CI/CD)

Автор
Проект разработан primusroman

Лицензия
MIT License
