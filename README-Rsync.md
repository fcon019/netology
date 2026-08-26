## Задание 1
rsync -av --delete --exclude '.*' --checksum ~/ /tmp/backup
## Задание 2

#!/bin/bash

LOG="/tmp/backup.log"

echo "$(date): Starting backup" >> "$LOG"

if rsync -av --delete ~/ /tmp/backup >> "$LOG" 2>&1; then
    echo "$(date): SUCCESS - Backup completed" >> "$LOG"
else
    echo "$(date): ERROR - Backup failed" >> "$LOG"
fi


0 18 * * * /home/vboxuser/backup.sh
