# Домашнее задание к занятию "`Zabbix Часть 2`" - `Соколов М.И.`


## Задание 1
![alt text](https://github.com/fcon019/zabbix/blob/main/img/Templates.jpg)

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


## Задание 2
![alt text](https://github.com/fcon019/zabbix/blob/main/img/ZabbixConf%20agents2.jpg)

wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb

sudo dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb

sudo apt update

sudo apt install zabbix-agent

sudo systemctl restart zabbix-agent

sudo systemctl enable zabbix-agent

## Задание 3
![alt text](https://github.com/fcon019/zabbix/blob/main/img/SokolovMI1)
![alt text](https://github.com/fcon019/zabbix/blob/main/img/SokolovMI2)


