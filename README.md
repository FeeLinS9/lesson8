# Загрузка системы
## Цели:
- Попасть в систему без пароля несколькими способами
- Установить систему с LVM, после чего переименовать VG
- Добавить модуль в initrd

Первым спопособом, добавив `init=/bin/sh` в загрузчик, всё сработало так, как описано в методичке, без всяких нюансов.\
Вторым способом, добавив в загрузчик `rd.break`, пришлось перемонтировать всю файловую систему - `mount -o remount,rw /`, так как каталога `sysroot` не было.\
Третий способ для меня показался самым удобным. В загрузчике изменил `ro` на `rw` и дописал `init=/bin/sh`

Следующие шаги по переименованию VolumeGroup я записал утилитой `script`, log файлы можете посмотреть в репозитории.\
В итоге всё получилось, с небольшими правками.\
![Скрин](https://github.com/FeeLinS9/lesson8/blob/master/img.png)