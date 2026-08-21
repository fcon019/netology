Disaster recovery и Keepalived

## Задание 1
![alt text](https://github.com/fcon019/netology/blob/main/img/HSRP.jpg)

## Задание 2

Срипт проверки

#!/bin/bash
# Проверяем доступность порта 80 на localhost
if nc -z -w 2 localhost 80; then
    # Если порт доступен, проверяем существование index.html
    if [ -f /var/www/html/index.html ]; then
        exit 0  # Всё хорошо
    else
        exit 1  # Файл отсутствует
    fi
else
    exit 1  # Порт недоступен
fi

vrrp_script chk_web {
    script "/usr/local/bin/check_web.sh"
    interval 3             # Запуск каждые 3 секунды
    timeout 2
    fall 2                 # 2 неудачи → переход в FAULT
    rise 1                 # 1 успех → возврат в норму
}

vrrp_instance VI_1 {
    state MASTER
    interface eth0         # Замените на ваш интерфейс (enp0s3, ens33 и т.д.)
    virtual_router_id 51
    priority 100           # Выше, чем у бэкапа
    advert_int 1

    authentication {
        auth_type PASS
        auth_pass secret123
    }

    virtual_ipaddress {
        192.168.1.100/24 dev eth0 label eth0:vip
    }

    track_script {
        chk_web
    }
}
