---
layout: post
title: "JakiBandit: Mi Framework para Dominar OverTheWire Bandit"
date: 2026-01-12 12:00:00 -0500
categories: [Herramientas]
tags: [bash, pentesting, opensource]
Author: "Jaki"
img: /assets/img/jakibandit.png
---

¡Hola a todos!

Hoy estoy emocionado de compartir con ustedes mi último proyecto: **JakiBandit Breaker Framework v1.0**. Este es un framework desarrollado en Bash que nace de mi propia experiencia y la de mis colaboradores al abordar los famosos *wargames* de [Bandit](https://overthewire.org/wargames/bandit/) de OverTheWire.

### ¿Por qué JakiBandit?

Como muchos en la comunidad de ciberseguridad, me he encontrado resolviendo una y otra vez los niveles de Bandit. Es una excelente base para aprender los fundamentos de Linux y la línea de comandos, pero el proceso puede ser repetitivo: `ssh`, pegar contraseña, buscar la flag, pasar al siguiente nivel...

Quería algo más eficiente, más *hacker*. Una herramienta que automatizara la parte tediosa para poder concentrarme en lo que realmente importa: **el aprendizaje y la resolución de problemas.**

Así nació JakiBandit, con la colaboración y el apoyo incondicional de:
- **Jaki infrastrucutures**
- **Korman studios**
- **Shadow**
- **Darkhub community**

Este proyecto es el resultado de un esfuerzo conjunto para crear una herramienta robusta y útil para nuestra comunidad.

### Características Clave del Framework

JakiBandit no es solo un script; es un asistente completo para tu viaje en Bandit:

* **⚡ Conexión Automatizada (One-Click SSH):** Olvídate de escribir `ssh banditXX@bandit.labs.overthewire.org -p 2220`. Con JakiBandit, un simple comando te conecta al nivel deseado utilizando la contraseña almacenada.

* **📚 Gestión de Credenciales Persistente:** Mantiene un archivo local (`passwords.txt`) con el progreso de tus contraseñas, asegurando que nunca pierdas dónde te quedaste.

* **📡 Web Scraping Integrado:** Extrae dinámicamente las descripciones de los niveles, los comandos sugeridos y las pistas directamente de la web oficial de OverTheWire, presentándolas de forma legible en tu terminal. ¡Todo sin salir del framework!

* **📖 Writeups Offline y a Demanda:** ¿Atascado en un nivel? JakiBandit puede generar y mostrar los *writeups* detallados de cada reto, permitiéndote aprender la solución sin la distracción de un navegador web.

* **🎨 Interfaz Optimizada (JakiKali-OS Style):** Una interfaz de usuario limpia y colorida, diseñada para Kali Linux, que hace que la navegación sea intuitiva y agradable.

### Instalación (¡Rápida y Sencilla!)

La instalación es muy sencilla y transforma `JakiBandit.sh` en un comando de sistema global, accesible desde cualquier lugar de tu terminal (Bash o Zsh).

```bash
git clone [https://github.com/JakiNet/JakiBandit.git](https://github.com/JakiNet/JakiBandit.git)
cd JakiBandit
sudo chmod +x install.sh
sudo ./install.sh
```
## ¿Cómo Funciona? Una Breve Demo

Una vez instalado, simplemente ejecuta jakibandit en tu terminal. Podrás:

    Navegar entre niveles usando s (siguiente), a (anterior) o introduciendo el número del nivel.

    Guardar contraseñas con la opción p.

    Conectarte a un nivel con c.

    Consultar el writeup con r.

-------------------------------------------

**Este framework no solo es una herramienta, sino también una demostración de mis habilidades en Bash scripting, automatización y desarrollo de herramientas para la comunidad. Espero que les sea de gran utilidad en su camino por el mundo de la ciberseguridad.**

**¡Gracias por leer y Happy Hacking!**
by Jaki
