---
layout: post
title: "Identificando Sistemas Operativos mediante TTL: Presentando JakiTTL"
date: 2026-01-09 12:00:00 -0000
categories: [ciberseguridad, python]
tags: [hacking, ttl, herramienta]
Author: "Jaki"
image: /assets/img/ttl.png
---

En el mundo del reconocimiento (recon), la discreción es clave. A veces no necesitamos lanzar un escaneo de puertos agresivo para saber a qué nos enfrentamos. Un simple paquete ICMP puede decirnos mucho más de lo que parece a través de un valor fundamental: el **TTL**.

## ¿Qué es el TTL?

El **TTL (Time To Live)** es un valor en el encabezado del protocolo IP que indica cuántos "saltos" (hops) puede dar un paquete antes de ser descartado por un router. Sin embargo, lo interesante para nosotros es que cada Sistema Operativo tiene un valor inicial predeterminado.



### Valores comunes de TTL
Al recibir una respuesta (ICMP Echo Reply), podemos inferir el SO basado en el número:

| Sistema Operativo | TTL Inicial |
| :--- | :--- |
| **Linux / Unix** | 64 |
| **Windows** | 128 |
| **Dispositivos de Red (Cisco)** | 255 |

> **Nota:** Si el valor que recibes es 63 o 127, significa que el paquete ha pasado por un router antes de llegar a ti (64 - 1 = 63).

## Presentando JakiTTL

Para automatizar este análisis, he desarrollado **JakiTTL**, un script en Python que no solo extrae este valor, sino que lo interpreta y lo muestra con una interfaz limpia y estética en la terminal.

### ¿Por qué usar JakiTTL?
- **Pasivo:** No alerta a la mayoría de los sistemas de detección de intrusos.
- **Sin Dependencias:** Escrito puramente en Python usando librerías nativas.
- **Instalación Local:** Diseñado para ejecutarse como un comando global sin ensuciar los archivos del sistema.

## Instalación y Uso

Si quieres probar la herramienta, puedes clonarla directamente desde mi repositorio de GitHub:

```bash
git clone https://github.com/JakiNet/JakiTTL.git
cd JakiTTL
chmod +x install.sh
./install.sh
```

Una vez instalado, identificar un host es tan sencillo como:
```Bash

jakittl 8.8.8.8
```
## Conclusión

El análisis del TTL es una técnica clásica de "fingerprinting" que todo entusiasta de la ciberseguridad debe conocer. Es la base de herramientas más complejas y una forma elegante de entender cómo se comunican las máquinas.

Puedes ver el código completo y contribuir en mi GitHub.

**Escrito por Jaki. Explora, aprende y rompe las reglas (en entornos controlados claro xd).**
