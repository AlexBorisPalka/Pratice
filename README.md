# Pratice by Егоров Александр
# 1. Установка CentOS на VMware
VMware Wokstation создает полностью изолированные безопасные виртуальные машины. Уровень виртуализации VVMware сопоставляет ресурсы физического оборудования с ресурсами виртуальной машины. Таким образом, каждая виртуальная машина получает собственные ЦП, память, диски и устройства ввода-вывода и является полным эквивалентом стандартного компьютера x86. Centos является дистрибутивом GNU/Linux, основанном на свободных исходных текстах коммерческого дистрибутива Red Hat Enterprise Linux компании Red Hat.

1) Скачиваем VMware и CentOS, CentOS можно найти на оффициальном сайте https://www.centos.org/

2) Установка VMware
![](http://i.imgur.com/rshRqtg.png)

3) Создание Виртуальной машины с помощью VMware
![](http://i.imgur.com/uyYJuNf.png)

4)В процессе установки выбираем логин и пароль для входа в систему, далее выделяем следующие ресурсы для CentOS:

![](http://i.imgur.com/p7MkqVX.png)

5) Завершаем установку виртуальной машины запускаем CentOs и авторизуемся с помощью ранее заданных логина и пароля

![](http://i.imgur.com/BU3RSWH.png)

# 2. Основные команды
Рассмотрим несколько основных команд, не зная которых было бы крайне сложно взаимодействовать с системой:

1) "su" данная команда наделяет правами суперпользователя и позволяет выполнять любые команды, для ее активации необходимо ввести пароль

![](http://i.imgur.com/Sbk3EP1.png)

2) Для смены каталога используется команда "cd". Если вы введете эту команду без аргументов, вы попадете в свой домашний каталог; чтобы попасть в любой другой каталог, необходимо указать путь к нему.

![](http://i.imgur.com/yyvj5uN.png)

3) Команда "ls" показывает список файлов текущей папки, с ключом -l показывает дополнительные сведения о файлах.
Вот что будет если использовать эту команду в директории /usr/bin

![](http://i.imgur.com/cQVS5Lt.png)

4) "vi" - открывает текстовый редактор

  "cp" - копирование файла
  
  cp file1 file2 сопировать файл file1 в файл file2
  
  cp dir/* . копировать все файлы директории dir в текущую директорию
  
  cp -a /tmp/dir1 . копировать директорию dir1 со всем содержимым в текущую директорию
  
  "cat" - показывает содержимое текстовых файлов, а также "cat" можно использовать для реализации следующих инструкций:
  
  cat /proc/cpuinfo -	отобразить информацию о процессоре
  
  cat /proc/interrupts -	показать прерывания
  
  cat /proc/meminfo -	проверить использование памяти
  
  cat /proc/swaps -	показать файл(ы) подкачки
  
  cat /proc/version -	вывести версию ядра
  
  cat /proc/net/dev -	показать сетевые интерфейсы и статистику по ним
  
  cat /proc/mounts -	отобразить смонтированные файловые системы
  
  ![](http://i.imgur.com/P3KCcu0.png)
  
# Права суперпользователя
  
  Активация команды "su" дает нам доступ к некоторым командам доступным только для "root"
  
  Например:
  
  1) "poweroff" - выключение компьютера
  
  2) "reboot" - перезагрузка системы
  
  3) "dir" - показывает список файлов в директории, отсортированных вертикально по столбцам, эквивалентно команде “ls –C –b”
  
  4) "mkdir" и "rmdir" - создать и удалить директорию соответственно
  
  ![](http://i.imgur.com/MBZEkEu.png)
  
