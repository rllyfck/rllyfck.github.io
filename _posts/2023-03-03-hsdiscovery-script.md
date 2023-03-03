---
layout: single
title: Hdiscovery - Mi primera herramienta
excerpt: "Hdiscovery es una herramienta muy sencilla y fácil de utilizar, util para saber a que sistema operativo nos vamos a enfrentar cuando tratemos de realizar una máquina en hackthebox, tryhackme o una auditoria."
date: 2023-03-03
classes: wide
header:
  teaser: /assets/images/htb-writeup-delivery/delivery_logo.png
  teaser_home_page: true
  icon: /assets/images/hackthebox.webp
categories:
    - Herramientas
    - Linux
tags:  
  - Utilidad
  - Scripting
  - Linux
---
## Código

```
#!/bin/bash
```
Para el reconocimiento del sistema operativo jugamos con el TTL, si el TTL tiene un número igual o inferior a 70 nos encontraremos ante un sistema Linux, mientras que si es mayor a 70 será un sistema Windows.

# Manual

Importante, esta herramienta a día de hoy únicamente funciona pasandole una dirección IP, ya que si se pasa el nombre del servidor nos podríamos encontrar con un fallo en la herramienta.

# Poniendola a prueba
