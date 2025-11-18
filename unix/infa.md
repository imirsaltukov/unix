    probuem izmenit
	Пакеты: установка дополнительного софта



     * Сетевой установщик пакетов в Linux * 



    ZYPPER - сетевой менеджер пакетов



      Работа с репозиториями:
zypper lr   # ar, rr, nr (addrepo, removerepo, renamerepo)
zypper pa -ir "filesystems"   # list packages in repo

      Работа с пакетами:
zypper search   packetname
zypper install  packetname  # поставить/проапгрейдить
zypper remove   packetname
zypper update               # проапгрейдить все пакеты

    DNF aka YUM - сетевой менеджер пакетов


В RedHat yum был заменен на свою проапгрейженную версию dnf

      Работа с репозиториями:
dnf    repolist
dnf    config-manager   --add-repo   file:///path/to/reponame
dnf    config-manager   --set-enabled   reponame
dnf    config-manager   --set-disabled  reponame
rm     /etc/yum.repos.d/reponame.repo

      Работа с пакетами:
dnf search   packetname
dnf list     packetname
dnf install  packetname  # поставить/проапгрейдить
dnf remove   packetname


    APT


sudo apt install packetname
sudo apt remove  packetname

     * Linux RPM - локальное управление пакетами * 



    rpm -i filesystem-1.2-1.i386.rpm  # Поставить пакет
    rpm --erase filesystem-1.2-1      # Удалить пакет
    rpm -qa                           # Список всех пакетов
    rpm -qf /usr/bin/locate           # Какому пакету принадлежит файл
    rpm -ql   nfs-server-2.2beta16-5  # Файлы, входящие в установленный пакет
    rpm2cpio < packetname.i386.rpm | cpio -it # файлы в rpm-пакете
    rpm -Uvh samba-1.9.8p7-0.i386.rpm # Установка апдейта

     * Как устанавливать пакеты в Solaris 2.5 * 



    Администрирование программного обеспечения




       Этот  вопрос  очень  важен  для  поддержки  и обновления
программного  обеспечения.  Для  этой   цели   в   ОС   Solaris
предусмотрен  специальный  механизм,  поддерживаемый  с помощью
утилит  "pkgadd"  и  "pkgrm",  соответственно   добавляющих   и
удаляющих   пакеты   из   системы.   Чтобы  эти  утилиты  могли
оперировать  с  пакетами,  они  должны  быть   представлены   в
соответствующем  виде,  или формате. К сожалению, далеко не все
программные  продукты  доступны  непосредственно   в   формате,
пригодном  для  "pkgadd". Подавляющее большинство продуктов для
Unix, доступных  через  Internet,  находятся  в  виде  исходных
текстов,  которые  надо  откомпилировать и скопировать в нужные
места. Это имеет место, т.к. ОС Unix установлена на  машинах  с
различными типами процессоров и различной архитектурой.

Original is here

    Ручная установка



                         Глава подготовлена Сергеем Богомоловым

Здесь  описана  только  установка  пакета  для себя (standalone
sysтем), если вам нужно установить пакет в режиме
server/dataless/diskless - читайте другие книжки (делать это надо
только с большой тоски).


1. Станьте суперпользователем
2. введите:
	/usr/sbin/pkgadd -d имя_директории_где_лежит_пакет имя_пакета

    например:
        /usr/sbin/pkgadd -d /cdrom/solaris_2_5/s0/Solaris_2.5 SUNWpkgA

    можно установить несколько пакетов сразу (укажите их имена через пробелы).

Имя пакета можно узнать из инструкции или с помощью команды:
         /usr/sbin/pkginfo -d имя_директории_где_лежит_пакет

Внимание: Solaris не очень хорошо отслеживает взаимозависимость между
     пакетами, так что вы сами должны позаботиться о порядке установки.
Многие пакеты любят задавать всякие вопросы во время установки (куда
      все это поместить, весь ли пакет установить и т.д.), так что
      будьте готовы. Например, при установке тома AnswerBook спрашивается,
      что копировать на жесткий диск: описание или весь том.
      Если вы копируете только описание, то исходный CD-ROM должен
      быть установлен каждый раз, когда вы запускаете AnswerBook, иначе
      ненайденный том будет помечен как "неживой" и его придется
      восстанавливать. Кстати, тома разбросаны по 7 дискам!!!

-----------------------------------------------------------------

    Проверка установки пакета.



/usr/sbin/pkgchk <имя_пакета>

-----------------------------------------------------------------

    Получение информации о пакете:



/usr/bin/pkginfo -l <имя_пакета>

например:
   pkginfo -l SUNWcar

   PKGINST:  SUNWcar
      NAME:  Core Architecture, (Root)
  CATEGORY:  system
      ARCH:  sparc.sun4m
   VERSION:  11.5.1,REV=94.07.15.22.10
   BASEDIR:  /
    VENDOR:  Sun Microsystems, Inc.
      DESC:  Core Architecture, (Root)
    PSTAMP:  fourstar940718191413
  INSTDATE:  Aug 16 1995 03:39
   HOTLINE:  Please contact your local service provider
    STATUS:  completely installed
     FILES:     51 installed pathnames
                16 shared pathnames
                 7 directories
                29 executables
              3794 blocks used (approx)

---------------------------------------------------------------

    Удаление пакета:



    /usr/sbin/pkgrm <имя_пакета>

---------------------------------------------------------------

    Работа с пакетами в графическом интерфейсе



 (swmtool для 2.4 или admintool для 2.5)
не надо устанавливать AnswerBook с их помощью.

                       SWMTOOL

запуск:

1. станьте суперпользователем
2. перейдите в графический режим, если вы еще не перешли в него
3. введите:
   /usr/sbin/swmtool &

 На экране возникает новое окно, программа долго-долго собирает
информацию об уже инсталлированных пакетах, затем  переходит  в
режим    установки    (режим    INSTALL/REMOVE    переключается
соответствующими кнопочками) и, скорее всего, сообщает вам, что
"устройство  не  готово, поменяйте установки (property)" Дело в
том, что swmtool  по  умолчанию  считает,  что  устанавливаемый
пакет  лежит  на  CD-ROM  и  менеджер  томов выключен. Если это
действительно так, то вставьте CD-ROM перед  запуском  swmtool.
Иначе  нажмите кнопку Props... (установки), возникает бланк, на
странице (категории) Source  Media  которого  вам  надо  задать
устройство или директорию, где лежит пакет.

 Например,  меняем  Media  Type на Mounted Directory, Directory
Name устанавливаем в  /cdrom/cdrom0  (установка  с  CD-ROM  при
включенном  менеджере  томов)  и  нажимаем кнопку Apply. Если в
указанной вами директории есть пакеты,  то  их  описания  будут
перечислены   в   главном  окне  swmtool.  Для  каждого  пакета
указывается: иконка (один ящик  -  простой  пакет  -  на  такую
иконку  можно жать два раза, и появляется подробное описание, 3
ящика - составной пакет - на такую иконку можно жать два раза, и
она   раскрывается   в  список  внутренних  пакетов  -  уровень
вложенности не ограничен), описание пакета и его предполагаемый
размер.  Выбираете  необходимые  вам  пакеты и нажимаете кнопку
Begin  Installation  (начать  установку).  Далее  весь   диалог
происходит в а/ц режиме как при установке pkgadd. Кстати, бланк
установок имеет большое количество  кнопочек,  менюшек  и  пр.:
есть с чем поиграться...

 Для  того,  чтобы  удалить  пакет,  нажимаете  кнопку  Remove,
выбираете  пакет  (пакеты),  который  вы  хотите  удалить,   и
нажимаете кнопку Begin Removal.

    Изготовление собственного пакета



Чтобы  легче  администрировать  этот разрозненный набор файлов, получающийся
после  компиляции,  их   можно   привести   к   формату   утилиты   "pkgadd"
самостоятельно.  Легче  всего этот вопрос рассмотреть на конкретном примере.
Пусть у нас есть пакет, состоящий из 3х программ: "MyProg.bin", "Myprog.lib"
и  "MyProg.man",  которые  должны  храниться  в  каталогах "/usr/local/bin",
"/usr/local/lib" и "/usr/local/man" соответственно.  Чтобы  сделать  из  них
пакет, надо проделать следующие простые шаги:

     а)  Создадим  директорию, где  будут  храниться  исходные
данные для утилиты "pkgmk", которая и делает собственно  пакет.
Пусть в нашем примере это будет директория "~/tmp/MyPackage".

     б)  Создадим  под  ним  систему  директорий,  где  должны
располагаться файлы пакета, и затем скопируем эти файлы на свои
места.  Т.о.  в  результате  у  нас  должны  получиться  файлы:

~/tmp/MyPackage/bin/MyProg.bin, ~/tmp/MyPackage/lib/MyProg.lib
и ~/tmp/MyPackage/man/MyProg.man

     в)  Затем  надо создать файлы "pkginfo" и "prototype". Они
должны выглядеть примерно так (более  подробную  информацию  об
этих  файлах вы можете получить, набрав команды

    man -s4 pkginfo
    man -s4 prototype

Файл "prototype":

!PROJDIR=/usr/local
1 i pkginfo=pkginfo
1 d none bin 0755 root other
1 f none bin/MyProg.bin 0644 root other
1 d none lib 0755 poul insects
1 f none lib/MyProg.lib 0644 root other
1 d none man 0755 poul insects
1 f none man/MyProg.man 0644 root other


Файл "pkginfo":

PKG=MyProg
NAME=MyPackage
ARCH=sparc
VERSION=Version 1.0
CATEGORY=application
VENDOR=Pavel K. Klodin
EMAIL=webmaster@reksoft.ru
PSTAMP=Pstamp
BASEDIR=/usr/local
CLASSES=none


     г)  После  того,  как  файлы  сделаны,  выполним следующие
команды:

cd ~/tmp/MyPackage
pkgmk -o -d /tmp -r .


     После  этого  в директории "/tmp" будет создан пакет "MyPackage" в виде
структуры файлов  и  директорий.  С  ним  уже  можно  оперировать  утилитой
"pkgadd".   д)   Теперь,  наконец,  выполним  команды  (предварительно  став
суперпользователем с помощью команды "su -"):

cd /tmp
pkgadd -d .


     ПРИМЕЧАНИЕ:   Следует   помнить,  что  пакеты  могут  быть
представлены в двух равноправных формах:

    в виде структуры директорий (как уже было рассмотрено выше);
    в виде так называемых "потоковых пакетов" (stream packages).

     Они  представляют  собой  простой  файл,  как если бы были
записаны  на  стриммерной   кассете   или   каком-либо   другом
последовательном  устройстве  (отсюда,  возможно,  и название).
Обращаться с ними следует так же, как и с "обычными" пакетами  в
виде  структуры  директорий  и  файлов.  Эти  2  формы взаимно
преобразуются командой "pkgtrans".

              Советом поделился Павел Клодин

    Summary of pkg commands:



	    pkginfo {pkg}   - test for presents of package.
	    pkgadd -d /cdrom/Solaris_2.3 <pkg ...>
			    - add missing packages
	    pkgrm {pkg ...} - remove packages.
	    pkgchk -q {pkg} - test for existance of package
	    pkgchk {options} [pkg] - check installed packages for
	    integrity.

    Let's say your Solaris2 workstation is called "sol" and the
    4.1.x server is called "bertha" and you want the printer name
    to be "printer" (imaginative, eh?).

    sol# lpsystem -t bsd bertha             # says bertha is a bsd system
    sol# lpadmin -p printer -s bertha       # creates "printer" on "sol"
					    # to be printed on "bertha"
    sol# accept printer                     # allow queuing
    sol# enable printer                     # allow printing
    sol# lpstat -t                          # check the status

    sol# lpadmin -d printer       # default

    To get transparent mode, try this:

    lpadmin -I any -p printer

     * Пакеты в HP-UX 10.20 * 



Пакеты в HP-UX ставятся через подменюшку SAM.

Список всех пакетов

    swlist -l product

swpackage
/usr/sbin/swpackage -s $DEPOTDATA/$PSFFILE -x media_type=tape @ $DEPOTDIR/$DEPOTNAME.depot;

Делаешь файл psf (читать man 5 swpackage), запускаешь вышеупомянутую
коммандочку как тебе нужно и получаешь)
формат psf  приблизительно такой:

# PSF file which defines an example product.

depot
  layout_version   1.0

# Vendor definition:
vendor
  tag           AS
  title         Kaspersky Labs, Ashmanov & Partners
  description   AS Software Distributor
category
  tag           antivirus_sft
  title         Antiviral Sofware
  description   These are the aniviral software
  revision      1.0
end

# Product definition:
product
  tag            VSAPI
  revision       A.@VSAPI_VERSION@
  architecture   @OS@_@OS_RELEASE@_32/64
  vendor_tag     AS

  title          The aniviral software, HP OpenMail Kaspersky Labs VSAPI patch
  number         B2002A
  category_tag   openmail_path

  description    < data/descr.sd
  copyright      < data/copyr.sd
  readme         < data/README

  machine_type   *
  os_name        @OS@
  os_release     ?.@OS_NUMBER@.*
  os_version     ?

  directory      /
  is_locatable   false

  # Create a product script which executes during the swremove
  # analysis phase.  (This particular script returns an ERROR,
  # which prevents the removal of the VSAPI product.)

fileset
  tag    Files
  file    ./vsapi/libvsapi.@so_suffix@    /etc/iscan/libvsapi.@so_suffix@
  file    ./vsapi/vsapi.cfg      /etc/iscan/vsapi.cfg
  file    ./openmail_var/rules/ALL-ROUTES.VIR_2
/var/opt/openmail/rules/ALL-ROUTES.VIR
  file    ./openmail_var/rules/ndninfo.txt
/var/opt/openmail/rules/ndninfo.txt

#control_files
  postinstall ./data/postinstall
  postremove  ./data/postremove
end

Популярность: 39, Last-modified: Thu, 07 Mar 2024 07:27:58 GmT




