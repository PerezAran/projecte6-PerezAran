# T06: Projecte Nexus - Implantació de PKI i Signatura Digital Corporativa

## 📝 Descripció del Projecte
El **Projecte Nexus** ha detectat una necessitat crítica: garantir la integritat, l'autenticitat i el no repudi dels seus documents interns i contractes amb proveïdors. L'objectiu d'aquesta tasca és modernitzar el sistema de signatures en paper mitjançant una **Prova de Concepte (PoC)**.

S'ha implementat una infraestructura de clau pública (PKI) pròpia perquè els empleats puguin obtenir certificats digitals corporatius i signar documents PDF de manera oficial per a ús intern, sense dependre de tercers.

---

## 🚀 Fases de l'Activitat
El projecte s'ha realitzat col·laborativament entre un **Administrador de Nexus** (Servidor) i un **Treballador de Nexus** (Client) dividit en:

1.  **Fase 1:** Desplegament de l'Autoritat de Certificació (CA) a Ubuntu Server.
2.  **Fase 2:** Sol·licitud i emissió de certificats des de la màquina client.
3.  **Fase 3:** Signatura digital de documents i verificació mitjançant Acrobat Reader.

---

## 📂 Contingut del Repositori
Dins d'aquesta carpeta trobareu els següents elements:

* **`memoria.md`**: Memòria tècnica detallada amb les captures de pantalla i el procediment pas a pas.
* **`document_signat.pdf`**: Evidència del fitxer PDF de prova signat digitalment.
* **`ca_nexus.cer`**: Certificat arrel de la nostra Autoritat de Certificació (Clau pública de la CA).

---

## 🛠️ Resum de la Memòria Tècnica
La memòria inclou els següents punts clau:
* **Instal·lació de la CA:** Procés de configuració a Ubuntu Server.
* **Gestió de Certificats:**
    * Procediment de sol·licitud i creació del certificat client.
    * Instal·lació de la clau de la CA al client per establir confiança.
    * Instal·lació del certificat personal del treballador.
* **Signatura Digital:** Guia sobre com signar un PDF i verificar la validesa de la signatura.
* **Conceptes Teòrics:** Explicació de la diferència entre **Clau Pública** (distribuïble per verificar) i **Clau Privada** (secreta per signar).



---

## 📚 Material de Suport
* Continguts de Seguretat Informàtica: RA3 (Signatura electrònica i Certificats).
* Guia de l'activitat de l'assignatura.

---
**Realitzat per:** [Nom de la Parella 1] i [Nom de la Parella 2]  
**Data:** 2026
