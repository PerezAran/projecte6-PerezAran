# Guia tècnica del servidor: Implementació de la PKI corporativa (Administrador)
Aquesta guia descriu el treball realitzat per l’administrador per posar en marxa l’Autoritat de Certificació (CA) corporativa sobre un Ubuntu Server, publicar els certificats i fer-los accessibles als clients.

### Configuració inicial de xarxa:

Em de posar el primer adaptador en xarxa NAT i el segon en adaptador pont per tal de poder fer la conexió correcta amb al client. Tal i com veiem a la imatge es veu pefectament. :)

![foto](t06/0.0.png)
![foto](t06/0.1.png)

Aqui com podem veure configuro al netplan per personalitzar la ip i també cambio al domini com es pot veure a la imatge ja que la activitat ho requereix.

![foto](t06/1.png)
![foto](t06/2.png)
![foto](t06/3.png)

### Preparació de l’entorn de l’Autoritat de Certificació i configuració  OPENSSL:

Es va crear l’estructura de directoris que OpenSSL utilitzarà per emmagatzemar la base de dades de certificats, els certificats emesos, les llistes de revocació i la clau privada.

![foto](t06/5.png)
![foto](t06/7.png)
### Generació del certificat arrel (CA)

Ara em de generar els certficats per al client tal i com es veu a les  imatges:

![foto](t06/8.png)

![foto](t06/9.png)

![foto](t06/10.png)

### Permisos

Ara hem de posar els permisos correctes, perque el client pugui entrar sense cap problema.

![foto](t06/12.png)

### Publicació dels certificats a través d’un portal web

Hem d´instalar o apache o nginx per fer un portal web que serà on al client entrara atraves de la ip del servidor per poguer descarregar els certficats que hem creat anteriorment.
Com podeu veure a la imatge:

![foto](t06/11.png)