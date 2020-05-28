# Практика Загрузка Linux

## Попадаем в систему без пароля.

### Способ 1. init=/bin/sh

+ ul В конце строки начинающейся с linux16 добавляем init=/bin/sh и нажимаем сtrl-x для загрузки в систему.
![initbinsh1.png](initbinsh1.png)
![initbinsh2.png](initbinsh2.png)

### Способ 2. rd.break

+ ul В конце строки начинающейся с linux16 добавляем rd.break и нажимаем сtrl-x для загрузки в систему.
![rdbreak1.png](rdbreak1.png)
![rdbreak2.png](rdbreak2.png)

###Способ 3. rw init=/sysroot/bin/sh

+ ul В строке начинающейся с linux16 заменяем ro на rw init=/sysroot/bin/sh и нажимаем сtrl-x для загрузки в систему.
![sysrootbinsh1.png](sysrootbinsh1.png)
![sysrootbinsh2.png](sysrootbinsh2.png)

## Установить систему с LVM, после чего переименовать VG

+ ul Посмотрим текущее состояние системы и переименуем centos в OtusRoot:
![vgrename1.png](vgrename1.png)

+ul Далее правим /etc/fstab, /etc/default/grub, /boot/grub2/grub.cfg. Везде заменāем старое название на новое.
![vgrename2.png](vgrename2.png)
![vgrename3.png](vgrename3.png)
![vgrename4.png](vgrename4.png)

+ul Пересоздаем initrd image, чтобý он знал новое название Volume Group.
![vgrename5.png](vgrename5.png)

+ul После чего можем перезагружаться и, если всё сделано правильно, то успешно грузимся с новым именем Volume Group и проверяем:
![vgrename6.png](vgrename6.png)

## Добавить модуль в initrd

+ul Результат на скриншоте:
![moduleinitrd.png](moduleinitrd.png)
