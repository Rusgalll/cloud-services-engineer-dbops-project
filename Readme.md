# dbops-project

## 1) Первичные настройки
### 1.1) Для успешного выполнения запросов вставки в миграции V003, необходимо в postgresql.conf изменить значение statement_timeout
```
statement_timeout = 0
```

### 1.2) Подключитесь к PostgreSQL под пользователем с правами создания БД: <br>
```sql
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

## 2) Запрос, который покажет, какое количество сосисок было продано за каждый день предыдущей недели  
```sql
SELECT o.date_created, SUM(op.quantity) FROM orders AS o
JOIN order_product AS op ON o.id = op.order_id
WHERE o.status = 'shipped' AND o.date_created > NOW() - INTERVAL '7 DAY'
GROUP BY o.date_created;  
```
