# Kittygram - социальная сеть для размещения фотографий котиков

## Описание проекта

Учебный проект от Яндекс.Практикума
Пользователи могут регистрироваться, загружать фотографии своих котиков с кратким описанием,
добавлять котикам достижения, выбирать цвет и смотреть фотографии котиков других пользователей. 
В рамках проекта проходило обучение деплою проекта на сервер, контейнеризации, CI/CD. 

## Ссылка на задеплоенный проект
elijah-kittygram.sytes.net (будет работать месяц после сдачи)

## Как развернуть

1. Скачайте docker-compose.yml из репозитория
   
2. Создайте файл .env
```
touch .env
```

3. Создайте файл с переменными окружения
```
POSTGRES_DB=<БазаДанных>
POSTGRES_USER=<имя пользователя>
POSTGRES_PASSWORD=<пароль>
DB_NAME=<имя БазыДанных>
DB_HOST=db
DB_PORT=5432
SECRET_KEY=<ключ Django>
DEBUG=<DEBUG True/False>
ALLOWED_HOSTS=<разрешенные хосты>
```

4. Запустите Dockercompose
```
sudo docker compose -f docker-compose.yml pull
sudo docker compose -f docker-compose.yml down
sudo docker compose -f docker-compose.yml up -d
```

5. Сделайте миграции и соберите статику
```
sudo docker compose -f docker-compose.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
```

## Автодеплой на Git Hub Action
Добавьте переменные в Secrets
```
DOCKER_PASSWORD - пароль от Docker Hub
DOCKER_USERNAME - имя пользователя Docker Hub
HOST - ip сервера
SSH_KEY - ключ ssh для доступа к удаленному серверу
SSH_PASSPHRASE - пароль ssh
TELEGRAM_TO - id пользователя TELEGRAM
TELEGRAM_TOKEN - TELEGRAM токен
USER - имя пользователя сервера
```

## Технологии
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/python-3.9-blue)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/django-4.2-green)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/DRF-3.14-red)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/nginx-1.23-green)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/gunicorn-20.1-orange)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-adge&logo=javascript&logoColor=%23F7DF1E)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/react-18-blueviolet)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-adge&logo=docker&logoColor=white)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/CI%2FCD-brightgreen)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-adge&logo=githubactions)</span>

<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/certbot-green?style=for-the-badge&logo=certbot&logoColor=white)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/dotenv-blue?style=for-the-badge&logo=dotenv&logoColor=white)</span>
<span style="display: inline-block; margin-right: 5px;">![alt text](https://img.shields.io/badge/docker%20hub-2496ED?style=for-the-badge&logo=docker&logoColor=white)</span>


## Автор
ILYA OLEYNIKOV
GitHub:	https://github.com/Elijah-iSO
E-mail: oleynikovis@yandex.ru
