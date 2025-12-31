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

## Guía de Usuario

JakiScanner es una potente herramienta de auditoría de red escrita en Python, diseñada para realizar escaneos de puertos TCP de forma rápida y eficiente. Utiliza técnicas de multihilo (multithreading) y reconocimiento pasivo para identificar servicios y sistemas operativos.
🚀 Características Principales

    Escaneo Multihilo: Capacidad de lanzar hasta 500 hilos simultáneos para cubrir los 65,535 puertos en segundos.

    Detección de SO: Identifica si el objetivo es Linux o Windows analizando el TTL (Time To Live) de los paquetes ICMP.

    Banner Grabbing: Intenta extraer la versión del software que corre en los puertos abiertos (ej. Apache, OpenSSH).

    Base de Datos Masiva: Diccionario integrado con más de 100 servicios comunes y especializados.

    Reportes Automáticos: Opción para guardar los resultados en formato de texto plano para documentación.

    Control de Velocidad: 3 perfiles de intensidad ajustables según la estabilidad de la red.

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
git clone https://github.com/JakiNet/jakiscanner
cd jakiscanner
chmod +x install.sh
sudo ./install.sh
```

**Nota: El instalador inyecta automáticamente el shebang necesario y crea un enlace simbólico en /usr/local/bin, garantizando que la herramienta funcione en cualquier máquina aislada.**

## 💻 Uso de la Herramienta

Una vez instalado, JakiScanner se convierte en una extensión de tu terminal. No más ./jakiscanner.py. Simplemente lanza:
$>**jakiscanner**

Opciones del Menú:

    Rápido (Top 100): Escanea los puertos más críticos para un reconocimiento veloz.

    Estándar (Top 1024): Cubre todos los puertos conocidos y servicios de sistema.

    Full (65535): Escaneo completo de todo el rango de puertos TCP.

    Personalizado: Permite definir un rango específico (ej: 80,443,8080 o 1-5000).

Perfiles de Velocidad:

Al elegir el escaneo Full o Personalizado, podrás seleccionar la intensidad:

    Lento (50 hilos): Ideal para redes inestables o para ser más sigiloso.

    Normal (200 hilos): El equilibrio perfecto entre velocidad y precisión.

    Rápido (500 hilos): Máxima potencia para redes locales o servidores robustos.

## 🌐 El Futuro: JakiNet Infrastructure

Este proyecto marca el inicio de una serie de herramientas que compartirán esta misma temática visual y estructural. Queremos elevar la calidad del software open-source para la comunidad de habla hispana, priorizando la facilidad de uso y la estética profesional.

¡Te invitamos a probarlo y a dejar tu ⭐ en el repositorio!
