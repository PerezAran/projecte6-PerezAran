# 🚀 T02: Missió Apache — Desplegament Multidomini i Segur (Nexus Mataró)

Aquest document recull el resum executiu de l'encàrrec rebut per part de **Nexus**, la nova empresa de formació de Mataró. Com a tècnics especialistes, l'objectiu és dissenyar i validar una infraestructura web local sòlida, eficient i segura sobre **Ubuntu Server** abans de fer el salt definitiu al núvol (VPS).

---

## 📋 Resum de l'Encàrrec i Objectius

El projecte neix de la necessitat d'optimitzar els recursos de la consultora i del client, allotjant múltiples llocs web sota un mateix servidor sense comprometre ni la seguretat ni el rendiment.

### Requisits Clau del Client:

1. **Multidomini (VirtualHosts):** Allotjar el portal de l'agència de disseny (`projectenexus.test`) i el de l'acadèmia de formació (`academia.test`) en un únic servidor Apache.
2. **Seguretat Avançada:** Implementar xifratge d'extrem a extrem amb certificats SSL/TLS (HTTPS).
3. **Rendiment Òptim:** Activar protocols de transferència moderns per garantir la màxima velocitat de càrrega.

---

## 🛠️ Desglossament de les Tasques Tècniques

L'ordre de desplegament i configuració per a la Prova de Concepte (PoC) s'estructura en 5 fases crítiques:

### 1. Instal·lació i Configuració Base

* Desplegament del servidor web **Apache** a Ubuntu Server.
* Verificació de l'estat del servei amb `apachectl`.
* Gestió del sistema de fitxers: verificació de l'usuari de l'entorn web (`www-data`) i assignació correcta de permisos a la ruta `/var/www/`.

### 2. Desplegament de VirtualHosts (Multidomini)

* Creació de l'estructura de directoris independent per a cada lloc web a `/var/www/`.
* Creació i edició dels fitxers de configuració dins de `/etc/apache2/sites-available/`.
* Activació dels llocs web amb `a2ensite` i simulació de la resolució de noms local modificant el fitxer `/etc/hosts` de les màquines clientes.

### 3. Personalització d'Errors

* Substitució de la pantalla genèrica d'Apache per una **pàgina d'error 404 (Not Found)** corporativa i personalitzada, millorant l'experiència d'usuari (UX) de l'acadèmia o l'agència.

### 4. Seguretat i Certificats (HTTPS)

* Activació del mòdul SSL d'Apache (`a2enmod ssl`).
* Generació d'un certificat xifrat autosignat (RSA de 2048 bits, validesa de 365 dies) mitjançant **OpenSSL** per als dos dominis.
* Configuració dels VirtualHosts al port `443` i creació d'una **redirecció forçada automàtica** de HTTP (port 80) a HTTPS per garantir que totes les connexions siguin segures.

### 5. Optimització amb HTTP/2

* Activació del protocol d'alta velocitat **HTTP/2** al servidor per minimitzar la latència.
* Configuració de la directiva `Protocols` als fitxers de configuració.
* Verificació tècnica del protocol mitjançant eines de diagnòstic com `curl` o l'inspector de xarxa del navegador.

---

## 📦 Requisits del Lliurament

Per donar per tancada la tasca, caldrà presentar una **Memòria Tècnica** formalment redactada en Markdown.

> ⚠️ **Criteri de Qualitat:** El document no pot ser només un recull de captures de pantalla. Ha d'incloure explicacions conceptuals clares, detallades i professionals perquè qualsevol perfil del client (encara que no sigui expert en IT) pugui comprendre la infraestructura desplegada.
