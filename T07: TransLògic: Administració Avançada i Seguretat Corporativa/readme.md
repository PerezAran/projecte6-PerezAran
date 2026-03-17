# T08: Vigilància i auditoria de sistemes

## Breu descripció
Un cop la infraestructura bàsica de **TransLògic S.A.** està operativa, la direcció de l'empresa ha expressat la seva preocupació per la integritat de les dades i la possibilitat d'intrusions no detectades. En el món de la logística, la informació és tan crítica com la mercaderia física.

Com a consultors de confiança, se us ha encarregat una nova tasca crítica: establir mecanismes de vigilància activa. L'objectiu no és només assegurar que el servidor té prou recursos per treballar, sinó també configurar les "caixes negres" del sistema (els logs) per poder rastrejar qualsevol activitat sospitosa o intent d'accés no autoritzat.

---

## Descripció de l'activitat

### 1. Monitorització de Recursos
El client vol assegurar-se que el nou servidor dimensionat suporta la càrrega de treball.

- Accediu al **Monitor de Rendiment** o al **Gestor de Tasques** del servidor.
- Realitzeu una captura on es vegi clarament l'estat actual de la CPU i la Memòria RAM disponible.
- Interpreteu breument les dades:  
  > El servidor està saturat o treballa sense estrès?

---

### 2. Configuració d'Auditoria de Seguretat
Per detectar possibles atacs de força bruta (intents d'endevinar contrasenyes), heu d'activar el registre d'accessos.

- Configureu la política d'auditoria (via **GPO** o política local del servidor) per auditar els successos d'inici de sessió.
- És imprescindible activar:
  - ✔️ Èxits (per saber qui entra)
  - ❌ Fracassos (per saber qui intenta entrar sense permís)

---

### 3. Simulació d'Incidents (Hacking Ètic)
Ara posareu a prova el sistema que acabeu de configurar.

1. Tanqueu la sessió actual.
2. Intenteu iniciar sessió amb un usuari existent (ex: usuari de magatzem) introduint una contrasenya incorrecta.
3. Repetiu aquest procés **3 o 4 vegades seguides**.
4. Finalment, inicieu sessió correctament amb l'administrador.

---

### 4. Anàlisi Forense (Event Viewer)
Actueu com a pèrits informàtics per trobar proves de l'intent d'intrusió.

- Obriu el **Visor d'Esdeveniments (Event Viewer)**.
- Aneu al registre de **Seguretat**.
- Busqueu els esdeveniments recents relacionats amb intents fallits.
- Feu clic en un esdeveniment i reviseu:
  - Usuari implicat
  - Hora
  - IP d'origen (si està disponible)

#### Tasca d'investigació
- Localitzeu l'**Event ID** corresponent a un intent d'inici de sessió fallit.

---

## Què cal lliurar

### 📄 Informe d'Auditoria

- Captura dels recursos del sistema amb interpretació.
- Captura de la configuració de la política d'auditoria activada.
- Evidència forense:
  - Captura clara del **Visor d'Esdeveniments** amb errors d'inici de sessió.

### 🧠 Resposta tècnica

- Indiqueu quin és el número d'**Event ID** que Windows assigna als errors d'inici de sessió.

---

## Material de suport

- **0224 SOX. Material UD7: AA3**  
  _(Disponible al Moodle de l’assignatura)_
