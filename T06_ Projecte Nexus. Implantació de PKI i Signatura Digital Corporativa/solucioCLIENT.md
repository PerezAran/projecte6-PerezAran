## T06: Projecte Nexus. Implantació de PKI i Signatura Digital Corporativa

![foto](img_T06clientcarlos/1.png)

Entrem a la maquina del client i activem a IPV4 i posem la nostre ip 


![foto](img_T06clientcarlos/26.png)

Obrim configuració anem a network & internet, entrem a ethernet - edit ip assigment seleccionem manual i activem al IPV4 i posem la ip la mascara la porta d’enllaç i el DNS.


![foto](img_T06clientcarlos/2.png)

Obrim C:\Windows\System32\drivers\etc\hosts

![foto](img_T06clientcarlos/3.png)

I quan obrim el hosts abaix de tot afegim la ip del servidor ubuntu que ha fet al meu company amb la seva ip.

![foto](img_T06clientcarlos/4.png)

I com podem veure ja ens podem veure amb el servidor. 

![foto](img_T06clientcarlos/5.png)

Entrem a la terminal i posem ssh usuari@192.168.2.20 que es la ip del servidor posem yes i ja estarem conectats ssh desde el servidor. 

![foto](img_T06clientcarlos/6.png)

Entrem al navegador i ens connectem al apache2 del servidor posan a al navegador la seva ip que en el cas del servidor es 192.168.2.20.

![foto](img_T06clientcarlos/7.png)

Ara a la hora que en al servidor fem el certificat si reinciem la pàgina podem veure els certificats que podem descarrega, descarreguem al CRT i al PFX. 

![foto](img_T06clientcarlos/8.png)

I podem veure com s’ens descarrega el certificat crt

![foto](img_T06clientcarlos/9.png)

I podem veure com s’ens ha descarregat el certificat pfx. 

![foto](img_T06clientcarlos/10.png)

Anem al navegador i ens instal·lem al acrobat reader. 

![foto](img_T06clientcarlos/11.png)

Fem windows + R i posem certmgr.msc i aceptar.

![foto](img_T06clientcarlos/12.png)

Ens entrà en aquesta pàgina busquem certificados en los que no se puede… fem click dret i li donem a importar. 

![foto](img_T06clientcarlos/13.png)

li donem a examinar i posem al format crt i la nostre ruta.

![foto](img_T06clientcarlos/14.png)

Posem la segona opcio li donem a examinar i posem la opcio de entidades de certificación raíz de confianza.

![foto](img_T06clientcarlos/15.png)

![foto](img_T06clientcarlos/16.png)

Ja tenim la importació feta correctament. 

![foto](img_T06clientcarlos/17.png)

Ara obrim al certificat pfx i li donem a examinar i posem el certificat pfx. 

![foto](img_T06clientcarlos/18.png)

Posem la contrasenya que ha posat al servidor en al meu cas es usuari. 

![foto](img_T06clientcarlos/19.png)

Posem la segona casella, examinar i entidades de certificación raíz de confianza.

![foto](img_T06clientcarlos/20.png)

S’ha fet correctament la importació

![foto](img_T06clientcarlos/21.png)

Busquem en al navegador una mostra de pdf la obrim a l’acrobat i seleccionem el lloc del pdf on volem que estigui la nostra firma. 

![foto](img_T06clientcarlos/22.png)

Agafem al arxiu de pfx posem la contrasenya que hem posat a la hora de importar al certificat. 

![foto](img_T06clientcarlos/23.png)

I ens surt aquesta firma per defecte que es la ip del servidor. 

![foto](img_T06clientcarlos/24.png)

Li donem a crear fem la firma posem la contrasenya de abans i li donem a firmar. 

![foto](img_T06clientcarlos/25.png)

I ja tindrem firmat al pdf amb la nostre firma.