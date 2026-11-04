## 1 Задание

Восстановление полного архива
Восстановление полного архива и всех инкрементальных до часа перед аварией
Возможен при ваинте репликации мастер-мастер

## 2 Задание

pg_dump -Fc mydb > db.dump

pg_restore -d postgres --clean --create db.dump

или
pg_dump mydb > db.sql

psql mydb < db.sql

## 3 Задание

mysqldump -u root -p --all-databases > full_backup.sql

mysqladmin flush-logs

mysqlbinlog binlog.000001 binlog.000002 | mysql -u root -p

