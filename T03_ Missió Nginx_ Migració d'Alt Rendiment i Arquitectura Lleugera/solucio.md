## GUIA D'INSTAL·LACIÓ - NGINX AMB MÚLTIPLES SITES

1. INSTAL·LACIÓ NGINIX (Imatge 1.png, 2.png, 3.png)

* sudo apt install nginx -y

* sudo systemctl status nginx (comprovar que està actiu)

Comprovar des del client: http://IP_SERVIDOR:

![foto](t03/1.png)
![foto](t03/2.png)
![foto](t03/3.png)

## 2. PREPARACIÓ CARPETES 

* ls -la /var/www/ (veure estrucrura existent)

* Carpeta projectenexus.test i academia.test ja creades 

![foto](t03/4.png)

## 3. CONFIGURACIÓ SERVER BLOCKS (Imatges 5.png, 6.png)
Crear fitxer projectenexus.test, per tal de crear-los hem de posar el text que es veu a l´imatge.
![foto](t03/5.png)

Al mateix farem amb academia.test:
![foto](t03/6.png)

## 4. ACTIVAR ELS SITES

Aixo ho farem de la seguent manera:
* sudo ln -s /etc/nginx/sites-available/projectenexus.test /etc/nginx/sites-enabled/

* sudo ln -s /etc/nginx/sites-available/academia.test /etc/nginx/sites-enabled/

![foto](t03/10.png)
![foto](t03/11.png)

## 5. CONFIGURACIÓ CLIENT

Hem d´editar els hosts del client tal i com es veu a l´imatge:

![foto](t03/12.png)

## 6. PROVA INICIAL 

Ara farem la prova tal i com es pot veure a l´imatge:

![foto](t03/13.png)

## 7. CORREGIR PERMISOS 

![foto](t03/4.png)
![foto](t03/7.png)

## 8. PERSONALITZAR ERROR 404

Crearem la pagina, modificarem configuracions i farem les comprovacions.
A les imatges es pot veure el procés complet.

![foto](t03/14.png)
![foto](t03/15.png)
![foto](t03/16.png)
![foto](t03/17.png)
![foto](t03/18.png)
![foto](t03/19.png)

## 9. HTTPS - CREAR CERTIFICATS

Ara crearem els certficats, primer haurem de crear les carpetes, i després generarem els certficats.

![foto](t03/20.png)
![foto](t03/21.png)

## 10. HTTPS - CONFIGURAR SERVER BLOCKS SSL

Crear fitxer per projectenexus.test SSL 

![foto](t03/22.png)
![foto](t03/23.png)

## 11. COMPROVACIONS FINALS 

Tal i com podem veure a les imatges funciona l´ultima comprovació.

![foto](t03/24.png)
