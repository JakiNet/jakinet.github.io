---
layout: post
title: "Anatomía de un Ataque Informático: La Cyber Kill Chain"
date: 2026-08-10
Author: Jaki
categories: [Ciberseguridad]
tags: [pentesting, killchain]
image: /assets/img/killchain.png
---

Un ciberataque no es un evento instantáneo, sino un proceso metódico por fases.<br> 
Entender el modelo **Cyber Kill Chain** permite comprender cómo operan los atacantes y cómo frenarlos: **romper un solo eslabón frustra el ataque completo.**

---

### Las 5 Fases de un Ataque

1. **Reconocimiento (Pasivo)**
   * **Objetivo:** Recopilar información pública sobre la víctima (correos, IPs, subdominios).
   * **Técnicas:** OSINT, Google Hacking, verificación de registros DNS.

2. **Escaneo (Activo)**
   * **Objetivo:** Identificar vías de entrada directas, servicios activos y vulnerabilidades.
   * **Técnicas:** Escaneo de puertos, análisis de fallos en servicios web.

3. **Explotación**
   * **Objetivo:** Aprovechar un fallo de software, mala configuración o credenciales débiles para ganar acceso.
   * **Técnicas:** Ejecución de exploits, phishing, inyecciones (SQLi, RCE).

4. **Post-Explotación**
   * **Objetivo:** Consolidar la presencia dentro de la red objetivo.
   * **Técnicas:** Escalación de privilegios (`root`/`SYSTEM`), movimiento lateral y persistencia.

5. **Limpieza (Borrado de Huellas)**
   * **Objetivo:** Ocultar rastros para evitar ser detectado por administradores o equipos de seguridad.
   * **Técnicas:** Limpieza de archivos de registro (`/var/log`) e historial de comandos.

---

### Recursos para Aprender y Practicar

* **Plataformas de Práctica (CTFs):**
  * [TryHackMe](https://tryhackme.com/) — Salas guiadas sobre redes, Linux y Kill Chain.
  * [Hack The Box](https://www.hackthebox.com/) — Laboratorios prácticos de pentesting.
* **Herramientas Clave:**
  * `Nmap` / `Shodan` (Reconocimiento y Escaneo).
  * `Metasploit` / `Searchsploit` (Explotación).
* **Documentación:**
  * [Lockheed Martin - Cyber Kill Chain](https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html)

*Nota: Este artículo tiene fines estrictamente educativos para promover la concienciación y la ciberseguridad defensiva.*<br>
Gracias por leer :D<br>
Atte: Jaki
