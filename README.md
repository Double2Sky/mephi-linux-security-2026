# Домашнее задание №1 — Защита в GNU/Linux

| Пункт | Основные команды |
|---|---|
| 1. Создание пользователя | `groupadd students`<br>`useradd -m -u 1234 -G students user1`<br>`passwd user1`<br>`chage -M 90 user1` |
| 2. Мониторинг файлов и процессов | `find / -type f -perm -4000 2>/dev/null`<br>`ps -eo pid,ruid,euid,user,comm \| awk '$2>=1000 && $3==0'` |
| 3. Изучение механизма set-UID | `cp /usr/bin/cat /home/user1/cat-su`<br>`chown root:root /home/user1/cat-su`<br>`chmod 4755 /home/user1/cat-su` |
| 4. Изучение механизма привилегий | `cp /usr/bin/chown /home/user1/chown-su`<br>`chown root:root /home/user1/chown-su`<br>`chmod 755 /home/user1/chown-su`<br>`setcap cap_chown+ep /home/user1/chown-su` |
| 5. Изучение механизма sudo | `echo 'user1 ALL=(root) /usr/bin/date -s *' > /etc/sudoers.d/user1-time`<br>`chmod 440 /etc/sudoers.d/user1-time` |
