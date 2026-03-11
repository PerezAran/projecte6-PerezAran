# Guia d’implementació – TransLògic S.A.

## Introducció
Aquesta guia descriu els passos necessaris per completar l’activitat de configuració de l’entorn de TransLògic S.A., basant-se en les captures d’imatge realitzades durant el procés. Per a cada apartat s’indiquen les accions a realitzar i, just a sota de l’explicació, el nom de la imatge que s’ha d’adjuntar com a evidència.

---

## 1. Polítiques de Seguretat i Contrasenyes

### 1.1 Política global (Default Domain Policy)
**Acció:** Modificar la política per defecte del domini per establir una longitud mínima de contrasenya de 8 caràcters.

**On es fa:** Group Policy Management → Default Domain Policy → Edit → Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies → Password Policy → “Minimum password length”.

Tal com es veu a la imatge:
![foto](IMG/1.png)

### 1.2 Política específica per a Gerència (VIP)
**Acció:** Crear una GPO anomenada POL_Contrasenyes_Gerencia i configurar els paràmetres següents:

* **Longitud mínima:** 18 caràcters
* **Caducitat:** 28 dies
* **Complexitat:** Deshabilitada
* Activar l’opció “Relax minimum password length limits”

**Passos detallats:**

1. Crear la GPO des de l’OU gerencia → New GPO → nom POL_Contrasenyes_Gerencia.

Tal com es veu a la imatge:
![foto](IMG/2.jpg)

2. Editar la GPO i accedir a la configuració de la política de contrasenyes.

Tal com es veu a la imatge:
![foto](IMG/3.jpg)

3. Activar l’opció “Relax minimum password length limits” (Enabled).

Tal com es veu a la imatge:
![foto](IMG/4.jpg)

4. Definir “Minimum password length = 18”.

Tal com es veu a la imatge:
![foto](IMG/5.jpg)

5. Definir “Maximum password age = 28 dies”.

Tal com es veu a la imatge:
![foto](IMG/6.jpg)

6. Deshabilitar “Password must meet complexity requirements” (Disabled).

Tal com es veu a la imatge:
![foto](IMG/7.jpg)

7. Comprovar que l’enllaç a l’OU gerencia està habilitat: a l’OU gerencia, pestanya “Linked Group Policy Objects”, la GPO ha de tenir Link Enabled = Yes.

Tal com es veu a la imatge:
![foto](IMG/image.jpg)

### 1.3 GPO Bonus – Bloqueig de pantalla per a Magatzem
**Acció:** Crear una GPO POL_Bloqueig_Pantalla_Magatzem per a l’OU magatzem que activi el protector de pantalla amb contrasenya després de 5 minuts d’inactivitat.

**Justificació:** En un entorn de magatzem, els equips queden sovint desatesos; aquesta mesura evita accessos no autoritzats.

**Passos detallats:**

1. Crear la GPO des de l’OU magatzem.

Tal com es veu a la imatge:
![foto](IMG/8.jpg)

2. Configurar “Enable screen saver” = Enabled.

Tal com es veu a la imatge:
![foto](IMG/9.jpg)

3. Configurar “Screen saver timeout” = Enabled, segons = 300.

Tal com es veu a la imatge:
![foto](IMG/10.jpg)

4. Configurar “Password protect the screen saver” = Enabled.

Tal com es veu a la imatge:
![foto](IMG/11.jpg)

5. Vista general de les polítiques aplicades.

Tal com es veu a la imatge:
![foto](IMG/12.jpg)

---

## 2. Desplegament Automatitzat de Programari

### 2.1 Preparació de la carpeta compartida i fitxers MSI
**Acció:** Assegurar que els fitxers 7z2600-x64.msi i Firefox Setup 148.0.msi es troben en una carpeta compartida accessible des dels equips clients.

**Passos detallats:**

1. Localitzar els fitxers a C:\Programari\MSI.

Tal com es veu a la imatge:
![foto](IMG/13.jpg)

2. Seleccionar els usuaris o grups per compartir la carpeta.

Tal com es veu a la imatge:
![foto](IMG/14.jpg)

3. Assignar permisos de lectura als usuaris del domini.

Tal com es veu a la imatge:
![foto](IMG/15.jpg)

4. Confirmar la ruta compartida \\DC20\Programari.

Tal com es veu a la imatge:
![foto](IMG/16.jpg)

### 2.2 GPO per a Gestió (7-Zip assignat)
**Acció:** Crear una GPO POL_Software_Gestio enllaçada a l’OU gestio que desplegui 7-Zip en mode Assigned (instal·lació automàtica).

**Passos detallats:**

1. Crear la GPO i editar-la.
2. Anar a Computer Configuration → Policies → Software Settings → Software installation.
3. Nou paquet → seleccionar \\DC20\Programari\7z2600-x64.msi → triar Assigned.

Tal com es veu a la imatge:
![foto](IMG/17.jpg)

### 2.3 GPO per a Gerència (Firefox publicat)
**Acció:** Crear una GPO POL_Firefox_Gerencia enllaçada a l’OU gerencia que desplegui Firefox en mode Published.

---

## 3. Mobilitat d’Usuaris (Perfils Mòbils)

### 3.1 Creació de la carpeta compartida perfils
**Acció:** Crear una carpeta al servidor (ex. C:\perfils) i compartir-la amb permisos adequats.

**Passos detallats:**

1. Crear la carpeta.
2. Compartir-la amb nom perfils i permisos de compartir: Usuaris del domini amb Canvi (o Control total).
3. Configurar permisos NTFS: Usuaris del domini amb Modificació.

Tal com es veu a les imatges:
![foto](IMG/18.jpg)
![foto](IMG/19.jpg)
![foto](IMG/20.jpg)

---

## 4. Seguretat de Dades (Redirecció de Carpetes)

### 4.1 Configuració de la redirecció de Documents
**Acció:** Crear o modificar una GPO enllaçada a l’arrel del domini per redirigir la carpeta “Documents” a la carpeta personal de l’usuari (home folder).

**Passos detallats:**

1. Editar la GPO.
2. Anar a User Configuration → Policies → Windows Settings → Folder Redirection → Documents.
3. Propietats → Setting = “Basic - Redirect everyone’s folder to the same location” → Target folder location = “Redirect to the user’s home directory”.

Tal com es veu a la imatge:
![foto](IMG/21.jpg)

---

## 5. Delegació de Funcions (Helpdesk)

### 5.1 Creació de l’usuari adminOU
**Acció:** Crear un usuari dins l’OU Users amb nom adminOU i contrasenya que no caduqui.

**Passos detallats:**

1. Active Directory Users and Computers → New → User → omplir les dades.

Tal com es veu a la imatge:
![foto](IMG/23.jpg)

2. Configurar la contrasenya marcant “Password never expires”.

Tal com es veu a la imatge:
![foto](IMG/24.jpg)

### 5.2 Delegació de control sobre l’OU principal
**Acció:** Atorgar a l’usuari adminOU permisos per reiniciar contrasenyes i modificar la pertinença a grups.

**Passos detallats:**

1. Fer clic dret sobre l’OU → Delegar control.
2. Afegir l’usuari adminOU i triar tasques comunes.

Tal com es veu a la imatge:
![foto](IMG/25.jpg)

3. Crear una tasca personalitzada i seleccionar objectes d’usuari.

Tal com es veu a la imatge:
![foto](IMG/26.jpg)

4. Seleccionar objectes de grup.

Tal com es veu a la imatge:
![foto](IMG/27.jpg)

5. Atorgar permisos de lectura/escriptura.

Tal com es veu a la imatge:
![foto](IMG/28.jpg)
