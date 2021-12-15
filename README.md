# OHW8bts
Booting Linux
# Three entrances
Исходные параметры загрузки:

![Исходные параметры загрузки:](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1200.png)

рекомендация по методичке не cработала - вставлял init=/bin/bash, после чего загрузка зависала очень надолго, пока не сделал так:

![second image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1202.png)

То есть плюсом к рекомендации удалены упоминания консолей, вуаля:

Далее перемонтирую корневую ФС в режиме записи и сбрасываю пароль root-а.
Создаю в корне файл /.autorelabel указывающий Selinux перемаркировать корневую фс с новым паролем root

![8 image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1208.png)


![15 image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1215.png)

Второй вариант:

Параметр rd.break вызывает прерывание загрузки до перехода управления к ядру. Меняется пароль root и далее загрузка осуществлена с примонтированным sysroot вместо /, для доступа к корню основной фс применён chroot. А после создания .autorelabel при reboot происходит перемаркировка системных файлов.

![18 image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1218.png)


![24 image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1224.png)

Вошёл с новым паролем:

![28 image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1228.png)

Перед третьим вариантом оставил консоли, опять виснет, запускается только без них, далее всё ОК:

![33 image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1233.png)

![36 image](https://github.com/terentyfox/OHW8bts/blob/main/ThreeEntrcs/1236.png)




# Renaming VG in LVM

  Процесс отображён в логе - файл LVMor
  
# Adding initrd module

Всё, что касается этой задачи - в каталоге AddInitrdMod
Чтобы увидеть птицу счастья снова пришлось убрать упоминание консоли в параметрах:

![44 image](https://github.com/terentyfox/OHW8bts/blob/main/AddInitrdMod/1244.png)

![45 image](https://github.com/terentyfox/OHW8bts/blob/main/AddInitrdMod/1245.png)

лог действий - в файле AdMod в том же каталоге.

