## Kittygram - сервис для любителей кошек и не только!


## 🛠 Используемые технологии:

![Python](https://img.shields.io/badge/Python-blue?style=for-the-badge&logo=python)
![Django](https://img.shields.io/badge/Django-green?style=for-the-badge&logo=django)
![Django Rest Framework](https://img.shields.io/badge/DRF-blue?style=for-the-badge&logo=django)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-blue?style=for-the-badge&logo=postgresql)
![NGINX](https://img.shields.io/badge/Nginx-brightgreen?style=for-the-badge&logo=nginx)
![React](https://img.shields.io/badge/React-blue?style=for-the-badge&logo=react)
![Docker Compose](https://img.shields.io/badge/Docker_Compose-blue?style=for-the-badge&logo=docker)

## Последний action:

[![Main Kittygram workflow](https://github.com/warior-d/kittygram_final/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/warior-d/kittygram_final/actions/workflows/main.yml)

## Установка в вашем окружении:

Склонируйте репозиторий и перейдите в корень проекта:

```bash
git clone git@github.com:warior-d/kittygram_final.git

cd kittygram_final
```

Настройте переменные окружения среды в файле .env в корне проекта:

```bash
POSTGRES_DB=<БД>
POSTGRES_USER=<имя_тех_пользователя>
POSTGRES_PASSWORD=<пароль_тех_пользователя>
DB_HOST=<хост_БД>
DB_PORT=<порт_БД>
```

В рамках простого деплоя приложения вам достаточно будет запустить docker-compose из файла docker-compose.yml:

```bash
docker-compose up --build
```

Не забудьте собрать статику и скопировать ее в volume:

```bash
docker compose exec backend python manage.py collectstatic
docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
docker compose exec backend python manage.py migrate 
```

Данные действия "поднимут" проект на localhost, для настройки HTTPS, доступа по доменному имени, вам следует установить подходящий web-server и настроить его самостоятельно :)

