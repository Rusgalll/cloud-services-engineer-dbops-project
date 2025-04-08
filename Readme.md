# dbops-project

## 1) Создание базы данных
Подключитесь к PostgreSQL под пользователем с правами создания БД: <br>
`CREATE DATABASE store;`

Создаём пользователя с логином и паролем: <br>
`CREATE USER dbops_user WITH PASSWORD 'your_password';`

Выдаем пользователю все права на созданную базу данных: <br>
`GRANT ALL PRIVILEGES ON DATABASE store TO dbops_user;`

Создаем схему (если используется отдельная схема) и выдаём права: <br>
`GRANT ALL PRIVILEGES ON SCHEMA public TO dbops_user;`

## 2)   
