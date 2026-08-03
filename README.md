# Домашнее задание к занятию "`Zabbix Часть 1`" - `Соколов М.И.`


## Задание 1
sudo apt update

sudo apt upgrade

sudo apt install postgresql

wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb

sudo dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb

sudo apt update

sudo apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent

sudo -u postgres createuser --pwprompt zabbix
sudo -u postgres createdb -O zabbix zabbix

sudo nano /etc/zabbix/zabbix_server.conf

DBPassword=password

sudo systemctl restart zabbix-server zabbix-agent apache2

sudo systemctl enable zabbix-server zabbix-agent apache2

![alt text](https://github.com/fcon019/zabbix/blob/main/img/Login%20admin.jpg)

### Задание 2

### Задание 3

### Задание 4

