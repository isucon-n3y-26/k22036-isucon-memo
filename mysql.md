# mysql

## スロークエリログ

```sql
SET GLOBAL slow_query_log = ON;
SET GLOBAL slow_query_log_file = '/var/log/mysql/slow.log';
SET GLOBAL long_query_time = 0.1
```

## コネクションプール

```go
db.SetMaxOpenConns(100)
db.SetMaxIdleConns(100)
db.SetConnMaxLifetime(2 * time.Minute)
```
