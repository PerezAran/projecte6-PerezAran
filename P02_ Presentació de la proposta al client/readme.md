# 📢 P02: Presentació de la Proposta Final al Client

## Defensa de la Infraestructura, Decisions Arquitectòniques i Viabilitat Econòmica

Aquest directori conté els materials, el guió de defensa i la documentació de suport per a la presentació final del **Projecte Nexus**. Com a consultors i tècnics de sistemes, el nostre objectiu és defensar davant la directiva (CEO i CTO) de *Nexus e-learning* que la nostra arquitectura de servidors i entorn LMS és la més segura, escalable, rendible i compromesa amb la sostenibilitat (*GreenIT*).

---

## ⏱️ Condicions i Format de l'Exposició

* **Durada:** 12 minuts concrets d'exposició + 5 minuts de preguntes per part del tribunal (CEO/CTO).
* **Codi de vestimenta:** Casual professional (estil entrevista de feina, evitant roba esportiva).
* **Suport Visual:** Diapositives netes, corporatives, prioritzant diagrames de xarxa propis i taules de mètriques per sobre del text excessiu.

---

## 🗺️ Estructura del Guió i Continguts de la Presentació

La presentació s'articula al voltant d'una lògica professional: **Entendre el problema ➔ Analitzar alternatives reals ➔ Prendre decisions basades en mètriques ➔ Presentar la solució viable.**

### 1. Context i Anàlisi de Requisits del Client

* **El Repte:** Dissenyar i desplegar un entorn *e-learning* d'alt rendiment per a *Nexus*.
* **Pilars Clau:** Rendiment òptim, costos controlats de l'infraestructura, sostenibilitat energètica i facilitat en el manteniment rutinari del sistema.

### 2. 🔀 T04: Duel de Titans (Apache vs Nginx)

Defensa de la capa de servidor web utilitzant l'experiència real adquirida en els desplegaments previs:

* **Comparativa Tècnica:** Consum de recursos (RAM/CPU), escalabilitat davant de peticions concurrents i simplicitat de configuració de fitxers d'host virtual.
* **Experiència Real i Mètriques:** Detall dels errors reals trobats a les pràctiques, dificultat en la gestió dels mòduls i una estimació del temps de resposta percebut i la lleugeresa del servei en segon pla.
* **Decisió Final Justificada:** Elecció en ferm d'una de les dues tecnologies d'acord amb les necessitats crítiques del client.

### 3. 🎓 T11: Elecció de l'LMS (Moodle vs Canvas LMS)

Defensa de la plataforma educativa contrastant el programari desplegat tradicionalment amb l'alternativa analitzada:

* **Anàlisi Funcional i Arquitectura:** Processos de desplegament (paquets natius vs. imatges preconfigurades com TurnKey Linux), facilitat d'ús de la interfície i dependències de mòduls externs.
* **Experiència d'Ús Real:** Valoració de la corba d'aprenentatge del panell d'administració, la agilitat per crear un curs de zero, la gestió de la base de dades i els rols de professor/alumne.
* **Decisió Final Justificada:** Posicionament tancat per l'LMS que millor s'ajusta al model de negoci de *Nexus*.

### 4. 🧩 Integració Global i Viabilitat (Econòmica i Tècnica)

* **Arquitectura Unificada:** Com enllacen la capa del servidor web triat i l'LMS seleccionat en una solució final cohesionada.
* **Proposta de Producció:** Estructuració del sistema sobre un entorn de **VPS (Virtual Private Server)** real, desglossant:
* Costos de posada en marxa (temps de configuració de l'equip tècnic).
* Costos mensuals de manteniment i allotjament de la infraestructura.
* Recursos humans i materials implicats.



### 🌿 5. Qualitat, Manteniment i Sostenibilitat (GreenIT)

* **Polítiques de Qualitat:** Estratègia de còpies de seguretat periòdiques (p. ex., mitjançant Duplicity), monitoratge de logs d'error i actualitzacions de seguretat del sistema operatiu base.
* **Compromís GreenIT:** Justificació de com l'arquitectura triada estalvia cicles de CPU, redueix el consum elèctric del servidor i garanteix un desplegament digital net i eficient.

---

## 📂 Recursos de la Presentació en aquest Directori

Per mantenir l'ordre del repositori segons la normativa de qualitat de l'equip, els fitxers es distribueixen de la següent manera:

* **`README.md`:** (Aquest fitxer) Índex, contextualització, estructura de la defensa i guia d'objectius de la tasca.
* **`presentacio_nexus.pdf`:** Document de diapositives final utilitzat durant l'exposició davant del tribunal (versió corporativa i neta).
* **`memoria_defensa.md`:** Resum executiu de suport amb la taula comparativa final de mètriques (Apache/Nginx i Moodle/Canvas) i l'estudi econòmic detallat del VPS que s'entregarà imprès al client.
* **`img/`:** Carpeta local que allotja els diagrames de xarxa i l'esquema d'infraestructura cloud creats expressament per a la proposta.

## 🚀 4. Automatització del Programari amb Winget

Per optimitzar el temps de desplegament de l'oficina, la instal·lació del programari es realitza mitjançant un script automatitzat amb la CLI de **Winget**.

L'equip del tècnic (`it`) es deixa net d'aplicacions. Per als equips `treballador` i `adviser`, s'executa el següent script (instal·lació silenciosa i sense interrupció):

```cmd
@echo off
:: Script d'automatització d'aplicacions - P02
echo Instal·lant aplicacions requerides...

:: 1. Paquet ofimàtic LibreOffice
winget install --id DocumentFoundation.LibreOffice --silent --accept-source-agreements --accept-package-agreements

:: 2. Lector de PDF (Adobe Acrobat Reader o alternatives segons necessitat)
winget install --id Adobe.Acrobat.Reader.64-bit --silent --accept-package-agreements

:: 3. Navegador Opera
winget install --id Opera.Opera --silent --accept-package-agreements

:: 4. Aplicació Canva
winget install --id Canva.Canva --silent --accept-package-agreements

echo Instal·lació completada amb èxit.
pause

```

---

## 🌐 5. Configuració de Xarxa i Connectivitat

Es canvia el tipus de xarxa de les VM de **NAT** a **Adaptador en pont (Bridged)**. L'adreçament IP s'estructura segons el grup de treball.

> **Paràmetres base del grup:**
> * `c` = *(Indicar `1` per a 1r A o `3` per a 1r B)*
> * `x` = *(Indicar el número del teu grup de pràctiques)*
> 
> 

### Taula de Configuració IP Estàtica

| Paràmetre | Equip Treballador (`treballador`) | Equip Assessor (`adviser`) |
| --- | --- | --- |
| **Adreça IP** | `192.168.c.x` | `192.168.c.100+x` |
| **Màscara de xarxa** | `255.255.255.0` | `255.255.255.0` |
| **Porta d'enllaç** | `192.168.c.254` | `192.168.c.254` |
| **Servidor DNS 1** | `172.0.2.2` | `172.0.2.2` |
| **Servidor DNS 2** | `8.8.8.8` | `8.8.8.8` |

### Proves de Connectivitat (Ping)

Un cop configurades les IP, es realitzen les següents verificacions des de la línia de comandes (`cmd`):

* **Comprovació d'Internet:** `ping 8.8.8.8`
* **Connexió entre màquines (LAN):** Executar un `ping` creuat des de la IP del treballador cap a la de l'assessor i viceversa per verificar la comunicació interna.

---

## 🛡️ 6. Eines de Recuperació (Punt de Restauració)

Com a mesura de seguretat abans del lliurament o futurs canvis en l'entorn de producció:

1. S'activa la *Protecció del Sistema* a la unitat principal `C:`.
2. Es crea un **Punt de Restauració** manual a cadascuna de les màquines virtuals.
3. **Nomenclatura utilitzada:** *(Indicar aquí el codi o criteri exacte de la guia de classe, per exemple: `P02_GrupX_PostInstalacio`)*.

## Disseny i Desplegament d’una Solució E-learning Sostenible

Aquest repositori conté la **Memòria Tècnica de Proposta** formal per al desplegament de la plataforma de formació online de l'empresa client. Aquest document no és un resum d'activitats acadèmiques, sinó una proposta professional estructurada que justifica la viabilitat tècnica, econòmica i ambiental del projecte per passar del concepte de *"configurar per practicar"* al de *"dissenyar per donar servei"*.

---

## 👥 Equip Consultor (Tècnics SMX)

* **Aran Perez** - *Consultor de Sistemes i Infraestructura Cloud*
* **Ferran** - *Consultor de Sistemes i Infraestructura Cloud*

---

## 🎯 El Repte Professional

L'objectiu d'aquesta memòria és respondre a una necessitat real del sector mitjançant:

* L'anàlisi crítica i de camp de tecnologies de servidor i plataformes educatives.
* L'estudi de la viabilitat econòmica orientada a una petita o myjana organització.
* El compromís amb la sostenibilitat (reducció del consum de recursos i eficiència energètica / *GreenIT*).
* La defensa i venda del projecte en una presentació executiva de **12 minuts**.

---

## 📂 Estructura del Document de Proposta i Defensa

La documentació i el guió de defensa s'estructuren en els següents blocs professionals per a la presentació formal davant la directiva de *Nexus E-learning*:

### 💼 1. Context, Objectius i Necessitats del Client

* **Definició del projecte:** Infraestructura de formació *online* de rendiment òptim per a perfils tècnics.
* **Criteris Clau de Nexus:** Rendiment, costos controlats, sostenibilitat ecològica i facilitat de manteniment operatiu.

### ⚔️ 2. T04 — Duel de Titans: Apache vs Nginx

* **Comparativa de Rendiment:** Anàlisi de consum de CPU/RAM, comportament davant la concurrència d'alumnes i escalabilitat de l'arquitectura.
* **Experiència de Camp (Evidències Reals):** Documentació dels errors reals de configuració trobats, dificultat real d'ús dels fitxers de configuració i facilitat d'administració observada a les pràctiques.
* **Mètriques i dades:** Mètriques orientatives de temps de resposta, nombre de línies de configuració modificades i optimització de recursos.
* **Decisió Executiva:** Triar el servidor web idoni basant-se estrictament en les dades i l'experiència en l'entorn real.

### 🎓 3. T11 — Comparativa LMS: Moodle vs Canvas LMS

* **Anàlisi Funcional:** Facilitat de desplegament, integració de continguts formatius per a informàtics i model de llicències (costos ocults).
* **Experiència d'Ús (Evidències Reals):** Complexitat del procés d'instal·lació, dependències de bases de dades o mòduls externs, i la sensació real d'usabilitat a l'hora de gestionar usuaris i crear un curs de prova.
* **Criteris Concrets:** Ràtio de passos necessaris per realitzar accions clau i consum estimat de recursos del servidor.
* **Decisió Executiva:** Triar el gestor d'aprenentatge òptim que millor resolgui el context del client.

### 🔌 4. Integració, Viabilitat Econòmica i Sostenibilitat

* **Visió Global del Sistema:** Com s'acoblen el Servidor Web i el LMS seleccionats dins la infraestructura final.
* **Estudi de Mercat del VPS (4 Alternatives):** Anàlisi comparativa d'infraestructures allotjades estrictament **dins de la Unió Europea (UE)** (garantia RGPD, baixa latència per proximitat i eficiència energètica).
* **Costos i Recursos:** Pressupost tancat que inclou el preu del VPS, els recursos humans/materials necessaris per a la posada en marxa i l'estimació de les hores de manteniment bàsic.
* **Green Computing:** Justificació de com la proposta final garanteix la reducció de la petjada ecològica mitjançant l'ús eficient del maquinari de la plataforma virtual.

---

## 📢 5. Planificació de la Defensa de la Proposta (Pitch de 12')

L'equip es prepara per a l'exposició executiva simulant un escenari de licitació empresarial real davant del tribunal (CEO i CTO):

* **Format del Lliurable:** Diapositives executives (PDF o PowerPoint) amb alt contingut visual (diagrames de xarxa propis) i text reduït.
* **Codi de Vestimenta:** Casual professional (estil entrevista de feina).
* **Control del Temps:** * **12 minuts:** Exposició conjunta dividida equitativament.
* **5 minuts:** Ronda de preguntes i defensa de decisions tecnològiques dures.



---

## 🛠️ Tecnologies i Criteris de Validació

* **Entorn de Prova de Client:** Màquines Windows 11 (Segons configuració P02 de proves de connectivitat interna i xarxa bridge).
* **Infraestructura de Servidor:** Servidors Virtuals Privats (VPS de la UE) + Stack d'aplicacions web seleccionat.
* **Format de Documentació:** GitHub Markdown (`.md`) com a índex i eix central de la memòria tècnica.