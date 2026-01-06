---
layout: post
title: "Bash Scripting: Fundamentos y Automatización para el Mundo Real"
date: 2026-01-05 12:00:00 
categories: [programación, linux, hacking]
tags: [bash, scripting, automatización]
Author: "Jaki"
image: /assets/img/bashscript.png
---

En el ecosistema Linux, **Bash (Bourne Again SHell)** no es solo una interfaz para ejecutar comandos; es un motor de automatización extremadamente potente. Aprender a programar en Bash es pasar de ser un usuario pasivo a un arquitecto de sistemas capaz de orquestar tareas complejas con simples archivos de texto.

Este post explora los conceptos pilares que todo profesional debe dominar para escribir scripts robustos y eficientes.

---

## 1. El Esqueleto de un Script: El Shebang

Todo script profesional debe comenzar con el **Shebang**. Esta línea le indica al kernel de Linux qué intérprete debe usar para procesar el resto del archivo.

```bash
#!/bin/bash
```

Sin esta línea, el sistema intentará ejecutar el script con el shell por defecto del usuario (que podría ser sh o zsh), lo que suele causar errores de compatibilidad.

## 2. Variables y Paso de Argumentos

A diferencia de otros lenguajes, en Bash no hay espacios alrededor del signo = al asignar variables. Además, es fundamental distinguir entre variables locales y argumentos posicionales.

    Asignación: NOMBRE="Servidor_Web"

    Uso: echo $NOMBRE

    Argumentos:

        $1, $2...: Primer y segundo argumento pasados al script.

        $#: Número total de argumentos.

        $?: Código de salida del último comando ejecutado (0 significa éxito).

## 3. Redirecciones y Pipes: La Filosofía Unix

El verdadero poder de Bash reside en su capacidad para conectar programas. La salida de un comando puede ser la entrada de otro.

    Pipes (|): Envía la salida de un comando a otro. Ejemplo: cat lista.txt | sort | uniq.

    Redirecciones (>, >>): Envía la salida a un archivo (sobrescribiendo o añadiendo).

    Manejo de Errores (2>): Redirige los errores a un archivo específico para auditoría.

## 4. Estructuras de Control y Lógica

La automatización requiere toma de decisiones. Bash utiliza corchetes [ ] para evaluar condiciones. Nota: Los espacios dentro de los corchetes son obligatorios.
Condicionales
```bash

if [ -f "/etc/passwd" ]; then
    echo "El archivo de usuarios existe."
else
    echo "Archivo no encontrado."
fi
```

*Bucles (Loops)*
 
Ideales para tareas repetitivas como renombrar archivos o escanear puertos.
```bash

for ip in {1..10}; do
    ping -c 1 192.168.1.$ip
done
```

## Aplicación Práctica: El Laboratorio de Bandit

Una vez comprendidos estos conceptos, la mejor forma de consolidarlos es mediante la práctica en entornos controlados. Un excelente punto de partida es Bandit, de la plataforma OverTheWire.

Bandit es un Wargame diseñado para enseñar comandos de Linux y lógica de scripting mediante retos que aumentan en dificultad. Es el "campo de entrenamiento" perfecto para aplicar lo aprendido sobre permisos de archivos, manipulación de texto y conexiones remotas.
Aprende Bandit en Video

Para complementar esta guía, he preparado una serie de tutoriales donde resolvemos estos retos paso a paso, aplicando los conceptos de scripting vistos anteriormente:

<https://www.youtube.com/watch?v=0Tj_G53rtBs&list=PLgvdZyIX3fRz_q682LzItYna6ezQapISd>

*Conclusión*

## ⚡ Bash Scripting: Cheat Sheet Essentials

**Esta guía rápida resume los comandos y estructuras más utilizados en la automatización con Bash.**

# 1. Variables y Argumentos Especiales

```bash
|Variable   |Descripción
_____________________________________________________________
|$0,        |Nombre del script
|$1 - $9,   |Argumentos posicionales
|$#,        |Número de argumentos pasados
|$@,        |Todos los argumentos como una lista
|$?,        |Estado de salida del último comando (0 = éxito)
|$$,        |PID (ID de proceso) del script actual
```
# 2. Pruebas de Condición (Tests)
 
Las condiciones se evalúan entre corchetes [ ]. ¡No olvides los espacios!
**Archivos**
```bash
    -f archivo: True si el archivo existe y es regular.

    -d carpeta: True si el directorio existe.

    -r / -w / -x: True si el archivo tiene permisos de lectura / escritura / ejecución.

**Cadenas (Strings)**

    z $var: True si la cadena está vacía.

    n $var: True si la cadena no está vacía.

    $var1 == $var2: Igualdad.

**Números**

    -eq: Igual a (equal)

    -ne: No igual (not equal)

    -lt: Menor que (less than)

    -gt: Mayor que (greater than)
```
# 3. Estructuras de Control
**Condicional If/Else**
```bash

if [ condition ]; then
    # código
elif [ condition ]; then
    # código
else
    # código
fi
```

**Bucle For**
```Bash

for item in {1..5}; do
    echo "Iteración: $item"
done
```

**Bucle While**
```Bash

while [ condition ]; do
    # código
done
```

# 4. Redirección y Flujos
```bash
|Operador	|Acción
_______________________________________________________________
| >	        |Redirige salida estándar (sobrescribe archivo)
|>>	        |Redirige salida estándar (añade al final)
|2>	        |Redirige errores estándar
|&>     	|Redirige tanto salida como errores
|/dev/null	|El "agujero negro" de Linux (descarta la salida)
```
**Gracias por leer, espero hayas aprendido al igual que yop :)**
**SaludOS de Jaki**
