# 🛡️ T08: Vigilància i Auditoria de Sistemes

## 📌 1. Introducció
Un cop desplegada la infraestructura bàsica de **TransLògic S.A.**, la direcció ha expressat la necessitat de garantir la **integritat de les dades** i detectar possibles **intrusions** 🔐.

En el sector logístic, la informació és tan crítica com la mercaderia. Per això, s’han implementat mecanismes de **monitorització** i **auditoria**, que funcionen com les “caixes negres” del sistema 📦.

---

## 🎯 2. Objectius
- 📊 Monitoritzar els recursos del servidor  
- 🔍 Configurar l’auditoria de seguretat  
- 🧪 Simular intents d’intrusió  
- 🕵️ Analitzar evidències amb eines forenses  

---

## 💻 3. Monitorització de Recursos

### ⚙️ Procediment
S’ha utilitzat el **Gestor de Tasques** o **Monitor de Rendiment** per analitzar:
- CPU 🧠  
- Memòria RAM 🧮  

### 📈 Resultats (exemple)
- CPU: 15%  
- RAM: 45%  

### 🧠 Interpretació
El servidor funciona **sense estrès** ✅ i disposa de recursos suficients.

📸 *(Inserir captura aquí)*

---

## 🔐 4. Configuració d’Auditoria de Seguretat

### ⚙️ Ruta de configuració

### ✅ Configuració aplicada
- Auditar èxits ✔  
- Auditar fracassos ✔  

### 🎯 Objectiu
- Saber **qui accedeix correctament**  
- Detectar **intents no autoritzats** 🚨  

📸 *(Inserir captura aquí)*

---

## 🧪 5. Simulació d’Incidents (Hacking Ètic)

### ⚙️ Procediment
1. 🔒 Tancar sessió  
2. ❌ Intentar iniciar sessió amb contrasenya incorrecta  
3. 🔁 Repetir 3-4 vegades  
4. 🔑 Accedir correctament com administrador  

### 🎯 Objectiu
Generar registres reals per validar el sistema d’auditoria.

---

## 🕵️ 6. Anàlisi Forense (Event Viewer)

### ⚙️ Procediment
- Obrir **Visor d’Esdeveniments**  
- Accedir a:

### 🔍 Anàlisi
Buscar esdeveniments amb:
- Usuari 👤  
- Hora ⏰  
- IP 🌐 (si disponible)  

### 📊 Resultats
S’han detectat correctament els intents fallits simulats 🚨

📸 *(Inserir captura aquí)*

---

## 🧾 7. Resposta Tècnica

### ❗ Event ID dels errors d’inici de sessió:
## 👉 4625

📌 Indica un:
- Intent d’inici de sessió **fallit**  
- Possible atac de **força bruta**  

---

## ✅ 8. Conclusions
- 🟢 El servidor funciona correctament  
- 🔐 L’auditoria està ben configurada  
- 🧪 La simulació ha generat registres correctes  
- 🕵️ El sistema permet una bona traçabilitat  

📌 Aquest sistema garanteix una millor **seguretat i control** dins de TransLògic S.A.
