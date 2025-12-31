---
layout: post
title: "JakiScanner: El nuevo estándar de herramientas para Kali Linux"
date: 2025-12-30 12:00:00 -0000
categories: [Herramientas]
tags: [python, hacking, pentesting]
Author: "Jaki"
image: /assets/img/portada.png
---

# 🚀 Potencia, Orden y Estética Neon

En el ecosistema de **JakiNet**, creemos que una herramienta de ciberseguridad no solo debe ser potente, sino también estar perfectamente integrada en el sistema. Hoy presentamos oficialmente **JakiScanner**, un escáner diseñado para usuarios exigentes de Kali Linux.

![Banner JakiScanner](/assets/img/term.png)

## 🔍 Filosofía de Diseño

Muchos scripts de seguridad terminan perdidos en carpetas de descargas o generan errores de permisos al ejecutarse. JakiScanner rompe con eso mediante una arquitectura de instalación profesional.

### Puntos Clave de la Ingeniería:

| Característica | Descripción |
| :--- | :--- |
| **Directorio /opt** | Alojamiento limpio y seguro fuera de las carpetas de usuario. |
| **Global Path** | Acceso instantáneo escribiendo solo `jakiscanner`. |
| **UI Dinámica** | Barras de progreso y spinners para una instalación visual. |
| **Python 3 Optimized** | Ejecución fluida sin necesidad de llamar al intérprete manualmente. |

---

## 🛠️ Instalación Profesional

Hemos simplificado el despliegue para que sea una experiencia de "un solo paso". El instalador se encarga de todo: desde la limpieza de versiones antiguas hasta la configuración de dependencias.

```bash
git clone [https://github.com/JakiNet/jakiscanner](https://github.com/JakiNet/jakiscanner)
cd jakiscanner
chmod +x install.sh
sudo ./install.sh
```

**Nota: El instalador inyecta automáticamente el shebang necesario y crea un enlace simbólico en /usr/local/bin, garantizando que la herramienta funcione en cualquier máquina aislada.**

## 💻 Uso de la Herramienta

Una vez instalado, JakiScanner se convierte en una extensión de tu terminal. No más ./jakiscanner.py. Simplemente lanza:
$>**jakiscanner**

## 🌐 El Futuro: JakiNet Infrastructure

Este proyecto marca el inicio de una serie de herramientas que compartirán esta misma temática visual y estructural. Queremos elevar la calidad del software open-source para la comunidad de habla hispana, priorizando la facilidad de uso y la estética profesional.

¡Te invitamos a probarlo y a dejar tu ⭐ en el repositorio!
