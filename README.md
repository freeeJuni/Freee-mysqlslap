# Freee-mysqlslap
Freee-mysqlslap

### prerequisites
```
1. you need to create a user to execute these queries.
2. you need to install the mysql client to execute the mysqlslap.
3. the target table of "alter table" is "titles" table, if you want to conduct any schema changes.
```

### Preparation
```
git clone git@github.com:freeeJuni/Freee-mysqlslap.git

cd Freee-mysqlslap

tar -zxvf employees.tar.gz

export HOST=XXX
export USER=XXX
export PASSWORD=XXX
export PORT=XXX

cat employees.sql | mysql -v -h${HOST} -u${USER} -p${PASSWORD} -P${PORT}
```

### Execution
```
export CONCURRENCY=XXX
export ITERATIONS=XXX
export HOST=XXX
export USER=XXX
export PASSWORD=XXX
export PORT=XXX

mysqlslap --concurrency=${CONCURRENCY} --iterations=${ITERATIONS} --create-schema=employees --query="./test_query.sql" --verbose --delimiter=";" -h${HOST} -u${USER} -p${PASSWORD} -P${PORT}
```

### Alter table (optional)
```
ALTER TABLE titles ADD level int NOT NULL DEFAULT 1;
ALTER TABLE titles MODIFY COLUMN level bigint NOT NULL DEFAULT 1;
ALTER TABLE titles DROP COLUMN level ;
```
