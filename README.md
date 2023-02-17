# ПРОЕКТ **YAMDB API**

[![API for YaMDB project workflow](https://github.com/mashka33/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

![python version](https://img.shields.io/badge/Python-3.9-green)
![django version](https://img.shields.io/badge/Django-2.2-green)
![Docker version](https://img.shields.io/badge/Docker-4.15-green)
![Djangorestframework version](https://img.shields.io/badge/Djangorestframework-3.12-green)
![PyJWT version](https://img.shields.io/badge/PyJWT-2.1-green)
![gunicornversion](https://img.shields.io/badge/gunicorn-12.7-green)



## *Инфраструктура социальной сети Yamdb*

### Описание проекта:

Социальная сеть позволяющая зарегестрированным пользователям создавать, редактировать и удалять постов.
Также Yatube позволяет просматривать и комментировать записи других авторов. Незарегистрированным пользователям
доступен просмотр чужих постов и комментариев.

Учебный проект 16 спринта факультета бэкенд-разработки [Яндекс.Практикума](https://practicum.yandex.ru/backend-developer)

## стек:
- Python
- Django
- Docker
- Nginx
- см. файл `api_yamdb/requirements.txt`

## руководство по установке Docker
можно найти [здесь](https://docs.docker.com/engine/install/)


---

### Запуск проекта на локальном компьютере:

#### Клонируйте репозиторий на свой компьютер и перейдите в корневую папку

`git clone https://github.com/Mashka33/infra_sp2.git`
`cd yatube_api`

#### Установить виртуальное окружение

```
python -m venv venv

# Активировать виртуальное окружение

# для Linux
source env/bin/activate

# для Windows
source venv\Scripts\activate

# деактивировать виртуальное окружение можно командой
deactivate
```

#### Установить зависимости

```
python -m pip install --upgrade pip
pip install -r requirements.txt
```

#### Запустить приложение в контейнерах:

*из директории `infra/`*
```bash
docker-compose up -d --build
```

#### Выполнить миграции:

*из директории `infra/`*
```bash
docker-compose exec web python manage.py migrate
```

#### Создать суперпользователя:

*из директории `infra/`*
```bash
docker-compose exec web python manage.py createsuperuser
```

#### Собрать статику:

*из директории `infra/`*
```bash
docker-compose exec web python manage.py collectstatic --no-input
```

#### Остановить приложение в контейнерах:

*из директории `infra/`*
```bash
docker-compose down -v
```

### Документация API с примерами:

```json
/redoc/
```

## Шаблон наполнения .env файла по пути ```./infra/.env```

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=username
POSTGRES_PASSWORD=password
DB_HOST=db
DB_PORT=5432
```

### описание команды для заполнения базы данными
```bash
cd api_yamdb && python manage.py loaddata ../infra/fixtures.json
```
### автор Степанова Мария https://github.com/Mashka33
