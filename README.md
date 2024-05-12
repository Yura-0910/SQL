**Данный проект создан, только чтоб создать БД "Postgres" средствами Docker-а.**

Установка учебной БД:
1. Качаем файл "demo-small.zip" вот отсюда https://postgrespro.ru/docs/postgrespro/10/demodb-bookings-installation
2. Разархивируем файл "demo-small.zip" и там будет SQL - скрипт:: "demo-small-20170815.sql"
3. Запускаем БД "Postgres" через Docker вот так::
* "sudo docker compose down --remove-orphans"
* "sudo docker compose up --no-start"
* "sudo docker compose up"
4. Запускаем "psql" из "Postgres"-а (в "Docker-е") и импортируем в БД(в Docker-е) 
необходимый SQL-скрипт и там(в БД, в Docker-е) выполняем этот SQL-скрипт, вот так::
* sudo docker exec -i postgres-dev-db-cnt psql  < /home/source/Документы/SQL-Prj/Наполнение-БД/demo-small-20170815.sql -U dev-usr -W demo
* Где "docker exec -it" - это:: выполнить команду в работающем контейнере
* Где "postgres-dev-db-cnt" - это:: имя контейнера с "Postgres"
* Где "psql" - это:: какую команду выполняем в контейнере
* Где "-U dev-usr" - это:: имя пользователя
* Где "-W" - это:: спросить пароль от БД "demo"
* Где "demo" - это имя БД в Docker-е