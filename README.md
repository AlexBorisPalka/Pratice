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

# 2.1 Основные команды
Рассмотрим несколько основных команд, не зная которых было бы крайне сложно взаимодействовать с системой:

1) "su" данная команда наделяет правами суперпользователя и позволяет выполнять любые команды, для ее активации необходимо ввести пароль

![](http://i.imgur.com/Sbk3EP1.png)

2) Для смены каталога используется команда "cd". Если вы введете эту команду без аргументов, вы попадете в свой домашний каталог; чтобы попасть в любой другой каталог, необходимо указать путь к нему.

![](http://i.imgur.com/yyvj5uN.png)

3) Команда "ls" показывает список файлов текущей папки, с ключом -l показывает дополнительные сведения о файлах.
Вот что будет если использовать эту команду в директории /usr/bin

![](http://i.imgur.com/cQVS5Lt.png)

4) "vi" - открывает текстовый редактор

Вот описание некоторых команд:

![](http://i.imgur.com/Yb2onqw.png)

![](http://i.imgur.com/Ylxkfc8.png)

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
  
# 2.2 Настройка сети
  используем команду "dhclient -v" для подключения к сети, а далее с помощью "ping 8.8.8.8" проверяем подключение
 
  ![](http://i.imgur.com/71IcGXp.png)
  
  ![](http://i.imgur.com/Kvu2d8U.png)

# 2.3 Установка ПО

  Установка дополнительного ПО производится с помощью плагина “yum” входящей в CentOS. Для установки необходимо быть пользователем “root”
  
  1) Текстовый редактор "nano"; для его установки необходимо ввести "yum install nano"
  
  ![](http://i.imgur.com/UWw7dVm.png)
  
  2) Браузер "elinks"; для его установки необходимо ввести "yum install elinks"
  
  ![](http://i.imgur.com/5KIFAfN.png)
 
  3) Файловй менеджер "mc" (midnight commander); для его установки необходимо ввести "yum install mc"
  
  ![](http://i.imgur.com/ZbZMv5c.png)
  
  А вот список "горячих клавиш":
  
  ![](http://i.imgur.com/2wwPssc.png)
  
# 3.1 SSH
  SSH (от англ. secure shell -- безопасная оболочка) это набор программ, которые позволяют регистрироваться на компьютере по сети, удаленно выполнять на нем команды, а также копировать и перемещать файлы между компьютерами. SSH организует защищенное безопасное соединение поверх небезопасных каналов связи.

SSH предоставляет замены традиционным r-командам удаленного доступа с тем отличием, что они обладают повышенной безопасностью. Они выполняются поверх защищенных зашифрованных соединений, которые не позволяет прослушивать или подменять трафик. Кроме того, SSH может обеспечивать безопасное соединение для передачи любого другого трафика: например, почтовых сообщений или файлов.

Чтобы получить доступ к серверу посредством протокола SSH необходимо программное обеспечение, которое обеспечит шифрование сеанса связи по сети. Именно таковым программным обеспечением и является оболочка OpenSSH которая является самой популярной из прочих программных продуктов на сегодняшний день.

# 3.2 Настройка SSH-сервера
 "yum -y install openssh-server openssh-clients" - С помощью данной команды мы производим установку серверной и клиентской части OpenSSH.
 
 "chkconfig sshd on" - Чтобы OpenSSH загружался автоматом, при загрузке системы, добавляем его в автозагрузку.
 
 "service sshd start" - Запуск OpenSSH
 
 "netstat -tulpn | grep :22" - Проверка порта по умолчанию
 
 ![](http://i.imgur.com/D4QhNZz.png)
 
 Настройка конфигурации OpenSSH:
 
 Конфигурационный файл OpenSSH называется sshd_config, и расположен по пути указанному ниже. Вся основная конфигурация OpenSSH производиться посредством этого файла. После того, как какие-либо изменения будут внесены в файл, следует перезапустить сервер, чтобы настройки вступили в силу.
 
 "vi /etc/ssh/sshd_config" - Файл конфигурации OpenSSH
 
 ![](http://i.imgur.com/AAm0yCM.png)
 
 Первый параметр – Port. По умолчанию используется 22 порт. Изменим его на нестандартный порт 2203 – это избавит наш сервер от сетевых роботов, которые автоматически сканируют интернет в поиске открытых портов и пытаются через них подключиться. 
 
"ListenAddress 0.0.0.0 "

 "ListenAddress : :"
 
Эти строки отвечают за настройку разграничений по сетевым интерфейсам, сетевому адресу или имени компьютера. По умолчанию сервер «слушает» (принимает подключения) на всех сетевых интерфейсах. 

Следующий параметр "Protocol" отвечает за версию протокола SSH. Значение по умолчанию 2. Его и оставляем. Не добавляем единичку ни при каких обстоятельствах. Первая версия протокола SSH не безопасна.

Строки HostKey необходимы для второй версии протокола SSH и отвечают за названия файлов ключей и их расположение. Первая строка отвечает за пару ключей RSA, вторая соответственно за пару ключей DSA. К названиям открытых (публичных) ключей добавляется .pub. Эти ключи используются при аутентификации с ключом хоста. Можно поменять слово host в названии ключей на имя нашего сервера, но мы сделаем это в части, посвященной генерации ключей. Сейчас же отключим ключи DSA, так как будем пользоваться только RSA:

HostKey /etc/ssh/ssh_host_rsa_key

#HostKey /etc/ssh/ssh_sunup_dsa_key

Следующие строки отвечают за временный ключ и его длину при работе с первой версией протокола SSH. Мы не используем SSH-1, поэтому пока закомментируем эти строки.

 # KeyRegenerationInterval 1h

 # ServerKeyBits 1024

Далее следует группа параметров, отвечающая за журналирование. События, связанные с доступом по SSH записываются в журнал /var/log/auth

Первый параметр определяет, список каких событий администратор хочет видеть в журнале. Доступны следующие значения: DAEMON, USER, AUTH, LOCAL0, LOCAL1, LOCAL2, LOCAL3, LOCAL4, LOCAL5, LOCAL6, LOCAL7. Нас интересует авторизация, поэтому оставляем AUTH.

Второй параметр определяет уровень детализации событий. Доступны следующие события: SILENT , QUIET, FATAL, ERROR, INFO, VERBOSE, DEBUG, DEBUG1, DEBUG2, DEBUG3. Оставляем уровень детализации по умолчанию, если возникнут ошибки, то всегда можно увеличить детализацию журнала.

Следующая группа параметров относится к аутентификации. Первый параметр означает, что соединение будет разорвано через указанное количество секунд, если пользователь не войдёт в систему. Уменьшим это время в два раза.

LoginGraceTime 1m

Второй параметр разрешает или запрещает вход по SSH под суперпользователем.

PermitRootLogin yes

Третий параметр включает проверку демоном ssh прав и владение домашним каталогом пользователя, который пытается получить удалённый доступ к компьютеру. Оставляем yes.

StrictModes yes

