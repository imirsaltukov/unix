
                                                      *lekciya 1 ssh
 Komaidu
*  id mc ps
sudo apt install mc (mind nait komander)
sudo up update обновили до решений команды
контрл аль т запуск терминала
ctrl o jnrhsnm  
f9 perekluchenie
sudo apt install openssh-server
Подключаем сетьевой адаптер
192.168.1.108
inet 192.168.1.108/24 brd 192.168.1.255
ip a
systemctl status ssh команда прадназначенная для проверки статусов
ssh kiber@ адресс сетьевого айпиыы aaa второй вариант
ssh -p 8022 порт хоста db@localhost
Сетьевые режимы VirtualBox
Most(bridge) - BM в локальной сети, прямой доступ к BM по IP
NAT -BM в своей сети, доступ к машине только через проброс портов
Установка гостевых дополнений виртуальной машины в Убунту
  sudo apt update - обновить список пакетов
  sudo apt install perl gcc make     -установить пакеты
  Запуск установки
                                                           *lekciya 2
kiber@kiber:~$()
~ tekushii katalog ~ v nachem sluchae domachnii
$ eto obuchnui tip polzovatelya
#   superpolzovatel
    sudo su -vhod v direkturiu superpolzovatelya

/home/ {user} -sam za sebya govorit
/etc (nastroiki sistemu)
cd cd/  cd ~ perehod v domachnii katalog
exit
ls -alhi - spisok failov
/dev -ustroistva
/proc - processu i sostoyaniya os
  *   /proc/cpuinfo -processor
285228


      /proc/version -versia os
/sys - informacia o sisteme
/run - vremennue failu sostoyaniya

cat cpuinfo -raspechatat katalog
     ls - a skratue failu
     ls -al vse parametru
     ls -help
     ll -psevdonim
     man ls
pwd - tekychaya direktoriya udobno vusuvat direktoriu
mkdir - sozdanie kataloga
  mkdir -p 1/2/3/4/5 sozdanie katalogov
  cd ~ /test perehodim v domawnuu direktoriu
  cat > testfile vhod v fail i rabota v nem
cp testfile test2 kopirovanie faila v fail
cp -r test test2 eto kopirivanie papok -r eto rekyrsia
cp -r /home/kiber/Документы/Code/linux /home/kiber/glagol
cp - kopirovanie
rm - udalenie
 rm test2
 v drugih sistemah flag -f test2 budet udalyat bez dop voprosov
 rm -rf test2 mogno bez zaprosa bustro udalit bolche strukturu
 rm -rf /home/db/test2 bolee tochnui hod udaleniya
mv - peremeinovanie/perenos
  mv test v test3 peremichaem test v test3 prichem test ischezaet
touch - sozdanie pustogo faila
    touch testt sozdanie novogo faila
cat - vuvod faila, skleika, sozdanie
  cat >testfile (dalee zapisuvaem v fail infu)
  cat testfile test2 > test_all
  vuhod ctrl D
sozdanie absolutnogo puti
  cd /home/glagol

cd ../..

!otkrutue voprosu dla ponimaniya
Otnositelnue ssulki i absolutnue
geskie ssulki  inod - ideksnui diskriptor

ln test2 test_ln

ls -ali vidim ainod v pervom stolbce
u geskih ssulok est ogranichenie odna failovaya sistema na vsex

cat >> test_ln dozapisat chto nibut vuhod ctrl_d

v itoge test2 toge izmenilsya vot kak rabotaut gestkie ssulki
toest mogno sohranyat bekapu tak vremya opizaniya 1.08


simvolichnue ssulki

ln -s

ll

ln -s test2 test _lns

proveryaem ll potom - ls-ali

 drugoi variant
 mv test_lns test3/
 cd test3
 ////test_lns_abs -> /home/db/test3/test2
 cat >> test_lns
 ln -s test3 test_ln_dir

 *redaktoru
  redaktor Vim
  komainnui regim - Esc
  regim redaktirovaniya  -I, A, O insert
  regim poslednei stroki : Q prosto vuhod, Q! vuhod s redakta (dvoetoche)
   manual po vimtutor  




   nano test_all

   tekstovui redaktor Mcedit

   spravka -f1
   sohranenie failav f2
   vuhod f10 ili esc+Esc
   vkluchenie nomerov strok alt+n
   poisk f7
   vudilenie bloka f3
   menu f9
   kopirovat v fail ctrl+f
   vstavit fail shift+5




                                                            *seminar

sudo apt instell gcc make perl
-y togda bez voprosov

zapusk faila  sudo ./VBoxL
```
sudo apt install openssh-server

ip -c a

sudo apt install mc


les3


cat /etc/passwd fail polzovatelya
cat /etc/group fail grup
sudo cat /etc/shadow paroli dostupa

upravlenie polzovatelyami

useradd - sozdanie polzovatelya

adduser - sozdanie polzovatelya (skript)

usermod - izmenenie polzovatelya

userdel - udalenie polzovatelya

passwd - izmenenie parolya

chage -izmenenie svoistv parolya

groupadd -sozdanie gruppu

groupdel - udalenie gruppu



sudo useradd -s /bin/bash -m -d /home/testuser testuser (sozdanie usera)

tail /etc/passwd  prosmotr

sudo adduser testuser2  drugoi variant sozdanaya user

sudo tail /etc/shadow

passwd -odnakomanda oznachaet smena parolya dla raznogo polzovatelya


sudo usermod -aG adm testuser dobavlenie usera v gruppu

id - prasto prosmotr v kakih gruppah user

sudo id testuser - infa gde user chilit

sudo usermod -g www-data testuser - dobavili usera v druguu gruppu po drugomu

man usermod -instrukciya

sudo userdel  testuser2 - udalenie usera

sudo ls -al /home/testuser2  -proveryaem i vse ostalos

man userdel

rm -rf tochnoe udalenie !!!!


                                                                   *sem2

ls --help
ls --alh
ls -- i -aynod  
mkdir less

perechli v papku sozdali fail 1

touch file1

mkdir folder

cp copy file1
sudo apt install tree -y proga dla prosmotra direktorii

rm -udalenie
 cat vhod dla redaktirovaniya

 vuhod ctrl_d
 cat > file1
 zozdaem i odnovremenno zapisuvaem

 esli pishem cat file1 on prosto napishet shto tem v faile

 esli cat file1 > file2 sozdatsya fail i odnovremenno zapishetsa v nego

 cat >>file1 eto dosapisat esli s odnoi ni sotret staroe i zapishet novoe

 takge cat file1 >> file2

 tekge konkotinaciya failov ...

 cat file1 file2 > file3

 mv filed1 file4 eto pereimenovanie failov

 mv file2 v dir1 peremeshenie faila v druguu papku


 sozdanie ssulok

 ssulka simvolicheskaya eto kak yaruk v vinde

 ln file3 link  obuchnaya ssulka sozdanie

 ln -s file3 slink simvolichnaya ssulka

 ls -alhi

 prosmotr cat linc

          cat slink

          cat file3

udaliv fail geskaya ssulka budel pomnit a slink pri zapisi
novogo takovoge fail budet vasproizvodot ego

                                                  *les3

  hranenie

cat  /etc/passwd - spisok polzovatelei
  /etc/group -gruppu polzovatelei
  /etc/shadow -paroli polzovatelei


useradd -sozdanie polzovatelia
adduser - sozdanie polzovatelya (skript)
usermod - izmenenie polzovatelya
userdell - udalenie palzovatelya
passwd - izmenenie parolya
change - izmenenie svoistv parolya
groupadd -sozdanie gruppu
groupdel - udalenie gruppu




suzdanie polzovatelya sudo useradd -s /bin/bash -m -d /home/testuser testuser  

tail /etc/passwd   prosmotr userov

ewe sozdanie polzovatelya

sudo adduser testuser2

sudo tail /etc/shadow prosmotr infu o polzovatelyah
izmenenie parolya userad

sudo passwd testuser2

sudo tail /etc/shadow

sudo ls -al /home/testuser prismotr kataloga userad

ls -al /etc/skel  proverka skeletona usera


radaktirovanie polzovatelya

sudo urermod -aG adm testuser zaglavnaya G oznochet spisok anazer group
 id mu smotrim v kakih we group and how group we haw to and activ

 sudo id testuser - inf abaut anather usera
