# dbops-project

## 1) Первичное окружение
Подключитесь к PostgreSQL под пользователем с правами создания БД: <br>
```
# Создание базы данных
CREATE DATABASE store;

# Создаём пользователя с логином и паролем
CREATE USER dbops_user WITH PASSWORD 'your_password';

# Выдача прав для новой БД и для схемы public
GRANT ALL PRIVILEGES ON DATABASE store TO dbops_user;
GRANT ALL PRIVILEGES ON SCHEMA public TO dbops_user;

ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON TABLES TO dbops_user;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON SEQUENCES TO dbops_user;


```

## 2)   
