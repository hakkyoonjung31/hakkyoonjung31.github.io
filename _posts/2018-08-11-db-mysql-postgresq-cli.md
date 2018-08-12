---
title: mysql과 postgresql 커맨드라인 비교
date: 2018-08-11
tags: db mysql postgresql
category: db
---


## DB접속

### mysql
```bash
$ mysql -p -h hostname -P port -u username dbname
```
### postgres
```bash
$ psql -h hostname -p port -U username dbname
```

## Database 일람 확인

### mysql
```
SHOW DATABASES;
```
### postgres
```bash
\l
```

## table 일람 확인

### mysql
```
SHOW TABLES;
```
### postgres
```
\d
```

## table 스키마 확인

### mysql
```
DESC table_name;
```
### postgres
```
\d table_name
```

## table CREATE문 확인

### mysql
```
SHOW CREATE TABLE table_name;
```
### postgres
```bash
$ pg_dump database_name -Uuser_name -s -t table_name
```

## 실행중인 프로세스를 확인

### mysql
```
SHOW processlist;
SHOW full processlist;
```
### postgres
```
SELECT * FROM pg_stat_activity;
```

## 실행중인 프로세스를 kill

### mysql
```bash
kill process_id;
```
### postgres
```
SELECT pg_cancel_backend(process_id);
```

## function 일람 확인

### mysql
```
SHOW FUNCTION STATUS;
```
### postgres
```
\df
```

## function 스키마 확인

### mysql
```
SHOW CREATE FUNCTION function_name;
```
### postgres
```
SELECT prosrc FROM pg_proc WHERE proname = 'function_name';
```

## SQL 실행계획 확인

### mysql
```
EXPLAIN sql;
```
### postgres
```
EXPLAIN ANALYZE sql;
```