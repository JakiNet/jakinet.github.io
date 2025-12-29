---
layout: post
title: "🚀 JakiSnippets: El fin de las cheatsheets infinitas en el Pentesting"
date: 2025-12-29 10:00:00 -0000
categories: [Herramientas]
tags: [python, hacking, pentesting, opensource]
Author: "Jaki"
image: /assets/img/unnamed.jpg
---

# JakiSnippets: Tu Arsenal de Comandos en la Terminal

¿Cuántas veces has perdido el hilo de una intrusión por tener que buscar el comando exacto de una **Reverse Shell** o los parámetros de **Nmap** para evadir un firewall? Como pentesters, la eficiencia es nuestra mejor arma, y perder tiempo en Google no es eficiente.

Por eso he desarrollado **JakiSnippets**, una herramienta CLI diseñada para centralizar comandos críticos y ejecutarlos (o copiarlos) en segundos.

---

## 🛠️ ¿Qué hace especial a JakiSnippets?

A diferencia de un simple archivo de texto, **JakiSnippets** ofrece una interfaz interactiva directamente en tu Bash o Zsh.

### Principales Funcionalidades:

| Función | Beneficio |
| :--- | :--- |
| **🔍 Búsqueda Inteligente** | Filtra por categorías (sqli, ad, wifi) o palabras clave. |
| **📋 Copiado al Portapapeles** | Integración con `pyperclip` para pegar comandos al instante. |
| **📂 Extensible** | Base de datos en JSON totalmente editable. |
| **🚀 Instalador Global** | Un solo script para tener el comando `jaki` en todo el sistema. |

---

## 📥 Guía de Instalación

Para desplegar el arsenal en tu sistema Linux/Kali, ejecuta los siguientes comandos:

```bash
# Clonar el repositorio oficial
git clone https://github.com/JakiNet/JakiSnippets.git

# Entrar al directorio
cd JakiSnippets

# Dar permisos y ejecutar el instalador
chmod +x install.sh
sudo ./install.sh
```

# 🚀 Uso Diario: De la Teoría a la Práctica

La herramienta está pensada para ser minimalista. Aquí te muestro cómo integrarla en tu flujo de trabajo:
1. Buscar comandos de una categoría

Si estás auditando una base de datos, simplemente escribe: jaki sqli
2. Búsqueda por palabra clave

¿Necesitas una shell? jaki buscar revshell
3. Alimentar el Arsenal

Puedes añadir tus propios comandos personalizados que vayas descubriendo en tus auditorías: sudo jaki agregar

    Pro Tip: Si usas una terminal con soporte de colores, verás el banner ASCII y los resultados resaltados para una mejor lectura en entornos oscuros.

🤝 Contribuciones y Open Source

Este proyecto es personal y para la comunidad. Si tienes "one-liners" potentes o quieres mejorar el código del motor de búsqueda, los Pull Requests son más que bienvenidos.
🔗 Enlaces de Interés:

   Repositorio: <https://github.com/JakiNet/JakiSnippets>

   Reportar Bugs: Issues de JakiSnippets

¡Gracias por leer! Si te ha sido útil, no olvides dejar una ⭐ en el repositorio. ¡Happy Hacking! :)
