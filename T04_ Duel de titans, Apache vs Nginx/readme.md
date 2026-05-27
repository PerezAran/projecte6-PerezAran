# 🚀 T04: Duel de Titans — Apache vs Nginx (Benchmarking de Servidors Web)

Aquest document conté el resum executiu de la pràctica d'auditoria de sistemes per al projecte de **Nexus**. L'objectiu és sotmetre ambdós servidors a proves d'estrès realistes des d'un client Zorin OS per analitzar quin gestiona millor les connexions sota pressió abans de presentar la proposta definitiva al client.

---

## 📋 Resum de l'Encàrrec i Entorn de Proves

Deixem de banda la configuració pura i ens posem el barret d'**Auditors de Sistemes** per avaluar el rendiment real d'Apache i Nginx utilitzant l'eina de benchmarking `ab` (ApacheBench).

### 🛠️ Preparació de l'Entorn:

1. **Contingut Realista:** Optimització dels llocs web de Nexus amb estils, imatges i codi més professional (generat amb suport d'IA) per simular una càrrega real de servidor.
2. **Distribució del Treball:** Un membre de l'equip auditarà el rendiment sobre Apache i l'altre sobre Nginx, assegurant que només el servei corresponent estigui actiu en cada màquina virtual.
3. **Equip Client:** Una màquina virtual amb **Zorin OS** des de la qual s'instal·larà l'eina de test mitjançant la terminal:
```bash
sudo apt update && sudo apt install apache2-utils -y

```



```

---

## 📊 Escenaris de Proves (Benchmarking)

Les proves es realitzaran llançant peticions concurrents mitjançant la sintaxi de la comanda `ab`:
`ab -n [Total_Peticions] -c [Usuaris_Concurrents] http://[IP_SERVIDOR]/`

### 🔹 Escenari 1: Prova de Càrrega Lleugera
Simulació de trànsit normal i diari a la web de l'acadèmia o l'agència de Nexus.
* **Usuaris concurrents (`-c`):** 10 usuaris simultanis.
* **Total de peticions (`-n`):** 1.000 peticions en total.
* **Comanda:** `ab -n 1000 -c 10 http://[IP_SERVIDOR]/`

### 💥 Escenari 2: La Prova d'Estrès (Límit)
Simulació d'un pic de trànsit massiu (efecte viral) o d'un petit atac de denegació de servei.
* **Usuaris concurrents (`-c`):** 100 usuaris simultanis colpejant el servidor alhora.
* **Total de peticions (`-n`):** 10.000 peticions en total.
* **Comanda:** `ab -n 10000 -c 100 http://[IP_SERVIDOR]/`
* *Nota:* Es documentarà si algun dels servidors experimenta caigudes, bloquejos o errors de tipus *Connection timed out*.

---

## 📦 Què cal lliurar (Estructura de la Taula Comparativa)

Els resultats de les mètriques obtingudes a la terminal del Zorin OS s'hauran de recollir i lliurar en una **taula comparativa** detallada com la següent:

| Mètrica | Apache (Prova Lleugera) | Nginx (Prova Lleugera) | Apache (Prova d’Estrès) | Nginx (Prova d’Estrès) |
| :--- | :---: | :---: | :---: | :---: |
| **Time taken for test** *(Temps total)* | | | | |
| **Transfer rate** *(Velocitat de transferència)* | | | | |
| **RPS** *(Requests per second - Més alt és millor)* | | | | |
| **Time per request** *(Temps mitjà - Més baix és millor)* | | | | |
| **Completed requests** *(Peticions completades)* | | | | |
| **Failed requests** *(Peticions fallides / Errors)* | | | | |

---
> 💡 **Consell d'Auditoria:** Fixeu-vos bé en la diferència de comportament en la prova d'estrès. Nginx sol destacar en la gestió d'esdeveniments asíncrons amb molts usuaris concurrents, mentre que Apache utilitza un model basat en processos o fils que pot augmentar el temps de resposta en situacions límit. Anoteu aquestes conclusions per a la memòria final!

```
