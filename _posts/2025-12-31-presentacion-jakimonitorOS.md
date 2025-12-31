---
layout: post
title: "Lanzamiento de JakiMonitor OS: El Monitor Definitivo para Kali Linux"
date: 2025-12-31 12:00:00 -0500
categories: [Herramientas]
tags: [python, hacking, pentesting]
image: /assets/img/jakimonitorOS.png
---

¡Hola a todos! Hoy tengo el placer de presentarles **JakiMonitor OS**, una herramienta en la que he estado trabajando para mejorar la experiencia de monitoreo en entornos de seguridad, específicamente diseñada para **Kali Linux**.

## ¿Qué es JakiMonitor OS?

JakiMonitor OS es una suite de monitoreo avanzada basada en Conky, inspirada en la estética de sistemas como Kodachi. No es solo un monitor de hardware; es un centro de comando visual que te permite tener el control total de tu máquina y tu privacidad mientras trabajas en auditorías o laboratorios.

![JakiMonitor Preview](https://github.com/JakiNet/jakimonitor-os/raw/main/screenshots/banner.png)

## Características Principales 🛡️

El monitor está dividido en secciones clave para cualquier analista de seguridad:

* **Estado de Privacidad:** Visualización en tiempo real del estado de **Tor** y **VPN (tun0)**, además de tu IP pública actual.
* **Networking Avanzado:** Seguimiento de conexiones TCP/UDP activas y analítica de tráfico (subida/bajada).
* **Hardware en Vivo:** Gráficas detalladas para los 4 núcleos de la CPU, carga de RAM y uso de Swap.
* **Gestión de Procesos:** Un "Top 5" automático de los procesos que más recursos están consumiendo en tu sistema.

## ¿Cómo funciona? ⚙️

He diseñado un script de instalación que automatiza todo el proceso, desde la instalación de dependencias hasta la configuración de los alias en tu terminal (Bash o Zsh).

### Instalación rápida

Solo necesitas clonar el repositorio y ejecutar el instalador:

```bash
git clone https://github.com/JakiNet/jakimonitor-os.git
cd jakimonitor-os
chmod +x install.sh
sudo ./install.sh
```
[Video de Youtube](https://www.youtube.com/watch?v=7eGRjIj67Hg)
