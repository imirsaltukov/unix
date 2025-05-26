	web prilogeniya


utilitu                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               


curl -L https://ya.ru/


wget https://yastatic.net/jquery/2.1.4/jquery.min.js


sudo apt install nginx


ss -ntlp proveryarm naliche soketa

ps afx   master processov

curl localnost - prosmotr host parametrov

cd /etc/nginix - prosmotr konfiguracii

curl localhost

cd /etc/nginx

nano nginx.conf

sudo ngnix -t proverka rabotu konfiguracionnogo faila

systemctl reload nginx - perezagruzka nginx

cd sites-enabled/
nano default 
cd /var/www/html
cd ~- preduduchi direktoriya
nano defalut

apache

sudo apt install apache2

test configa - sudo apachectl -t

Primenit : sudo systemctl reload apache2

konfiguraciya /etc/apache2/*

osnovnoi fail /etc/apache2/apache2.conf

bloki <VirtualHost></VirtualHost>

Direktivu : ServerName site.ru

Dokumentaciya : https:/httpd.apache.org/docs/2.4/en/


apachectl -t prosmotr konfigov

systemctl start apache2  - zapusk v ruchnuu 

systemctl status apache2 - podborka ochibok

zahodim v konfig cd /etc/apache2


cd sites-enabled

apachectl -t proverka

systemctl reload apache2

curl lockalhost:8080

cd /var/www/html smotrim gde nahoditsya stranica


Primer konfiguracii chtoba kakto mogno balo ispolzovat na storone apache


nginx reserve proxy

# dinamicheskie zaprosu

location / {
	proxy_pass http://localhost:8000
	proxy_set_header Host Shots:
	proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	proxy_set_header X-Real-IP $remote_add:
	}
	
# staticheskie zaprosu

location ~* >.+.(jpg|jpeg|gif|png|ico|css|zip|pdf|txt|tar|js)$ {
root /var/www/html; 
}

konfiguraciya sistemu

cd /etc/nginx
cd sites-enabled/


location ~*  sohranaem
