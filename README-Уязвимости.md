## Задание1

![alt text](https://github.com/fcon019/netology/blob/main/img/1.Nmap.JPG)
![alt text](https://github.com/fcon019/netology/blob/main/img/2.ftp.JPG)
![alt text](https://github.com/fcon019/netology/blob/main/img/3.smtp.JPG)
![alt text](https://github.com/fcon019/netology/blob/main/img/4.http.JPG)

## Задание2

SYN (-sS) — шлём SYN. Открыт → сервер отвечает SYN+ACK (Nmap шлёт RST). Закрыт → RST. Быстро, трафика мало.

FIN (-sF) — шлём только FIN. Открыт → сервер молчит. Закрыт → RST. 

Xmas (-sX) — шлём FIN+PSH+URG («ёлка» из флагов). Открыт → молчит. Закрыт → RST. 

UDP (-sU) — шлём UDP-датаграммы. Открыт → ответ данными или тишина. Закрыт → ICMP «port unreachable».
