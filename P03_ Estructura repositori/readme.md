Per tancar l'estructura perfecta del teu repositori de GitHub per al **Projecte Nexus**, he preparat l'apartat **P03: Estructura del Repositori**.

Aquest text el pots posar directament al teu `README.md` principal com a guia de control (Checklist) per a tu i en **Ferran**, assegurant-vos que no us deixeu cap fitxer ni carpeta abans del lliurament final a GitHub Classroom.

---

## 📁 P03: Estructura i Organització del Repositori

Per complir amb els estàndards professionals de lliurament i control de versions amb **Git**, el repositori està organitzat de forma modular. Cada tasca (`TXX`) i cada producte (`PXX`) compta amb la seva pròpia carpeta independent i la documentació homogeneïtzada en format Markdown.

### 🗺️ Arbre de Directoris del Projecte

L'estructura de fitxers del repositori segueix el següent patró estricte:

```text
📂 projecte-nexus-nom-de-grup/
├── 📄 README.md                 <-- (Aquest fitxer: Índex global de la proposta)
│
├── 📂 P01_Memoria_Tecnica/
│   ├── 📄 README.md             <-- Enunciat resumit de la proposta professional
│   └── 📄 solucio.md            <-- Document final de la Memòria Tècnica
│
├── 📂 P02_Maquines_Client/
│   ├── 📄 README.md             <-- Enunciat de configuració de clients (Win11)
│   ├── 📄 solucio.md            <-- Documentació de les VM, xarxa bridge i script winget
│   └── 📂 img/                  <-- Captures de pantalla (pings, punts de restauració)
│
├── 📂 P03_Presentacio_Client/
│   ├── 📄 README.md             <-- Criteris d'avaluació de la defensa oral (12 minuts)
│   └── 📄 solucio.md            <-- Enllaç a les diapositives (PDF/PowerPoint) i guió
│
├── 📂 T04_Apache_vs_Nginx/
│   ├── 📄 README.md             <-- Enunciat del duel de servidors web
│   ├── 📄 solucio.md            <-- Quadre comparatiu, mètrics i conclusions
│   └── 📂 img/                  <-- Captures de configuracions i errors reals
│
└── 📂 T11_Moodle_vs_Canvas/
    ├── 📄 README.md             <-- Enunciat de la comparativa de LMS
    └── 📄 solucio.md            <-- Anàlisi funcional, experiència d'ús i elecció final

```

---

## 📑 Criteris Obligatoris de Format per a cada Carpeta

A totes i cadascuna de les carpetes del projecte s'han d'aplicar els següents requeriments de lliurament:

1. **`README.md` (Nom exacte):** Conté la descripció de l'activitat o l'enunciat resumit estructurat correctament en seccions mitjançant encapçalaments de Markdown (`#`, `##`, `###`).
2. **`solucio.md` (Nom exacte):** Conté la resolució tècnica, memòries de configuració, enllaços externs o scripts de codi resultants de la tasca.
3. **📂 Carpeta `img/` interna:** Cap imatge o captura de pantalla pot estar dispersa a l'arrel de la carpeta. Totes s'han d'emmagatzemar dins d'aquest directori i enllaçar-se des del document `.md` amb la sintaxi: `![Descripció de la imatge](img/captura.png)`.

---

## 🚀 Validació del Lliurament (GitHub Classroom)

* **Entorn Oficial:** El lliurament es realitza exclusivament mitjançant les branques assignades al repositori oficial generat per **GitHub Classroom**.
* **Sincronització:** Abans de la data límit, s'ha de comprovar mitjançant la interfície web de GitHub que tots els fitxers `.md` es renderitzen correctament i que no hi ha enllaços trencats a les imatges.
