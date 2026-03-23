# 🚀 T03: Missió Nginx – Migració d'Alt Rendiment i Arquitectura Lleugera

## 📌 Breu Descripció

La vostra implementació amb **Apache** ha estat satisfactòria, però el Projecte Nexus preveu un **pic de visites elevat** durant la propera campanya.  

Per garantir **escalabilitat i rendiment**, es decideix migrar a **Nginx**, un servidor amb arquitectura orientada a **esdeveniments**, capaç de gestionar milers de connexions concurrents amb un consum de memòria inferior 💨.

L’objectiu és replicar l’estructura Apache anterior, però amb **Nginx**, per comparar rendiment i tenir una alternativa d’altes prestacions.  

> ⚠️ Nota: Dos serveis no poden escoltar el mateix port (80/443) simultàniament a la mateixa IP. Assegureu-vos d’aturar Apache abans de començar.

---

## 🎯 Objectius

- Migrar la infraestructura web a **Nginx** sobre **Ubuntu Server**  
- Configurar **multidomini (server blocks)**  
- Personalitzar pàgines d’error  
- Configurar **HTTPS** amb certificats SSL  
- Habilitar **HTTP/2** per millorar rendiment  

---

## 💻 1. Preparació de l’Entorn i Instal·lació

### ⚙️ Procediment
1. Aturar i deshabilitar **Apache2**:
```bash
sudo systemctl stop apache2
sudo systemctl disable apache2
