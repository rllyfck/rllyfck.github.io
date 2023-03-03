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
# Herramienta

Como se pude apreciar en la imágen, para que la herramienta funcione se debe poner ``` ./hdiscovery -h {ip} ```. Como salida del comando nos mostrará la IP previamente escrita y el sistema operativo al cual le pertenece.

# Código

```
#!/bin/bash

# Created by @rllyfck on instagram and @rllyfc4 on twitter

if [[ $1 == "-h" || $1 == "--host" ]]; then
        ping=$(ping -c1 $2 | awk '{print $6}' | grep "ttl" | cut -c 5,6,7)
        if [[ $ping -ge 128 ]]; then
	        echo -e "\n\t[+] Internet Protocol: $2 | Operative Sistem: Windows"
        else
                echo -e "\n\t[+] Internet Protocol: $2 | Operative Sistem: Linux"
        fi
else
	echo -e "\n\t[*] AYUDA: Debes introducir el parametro '-h' o '--host' seguido de la dirección IP."
fi
```
Para el reconocimiento del sistema operativo jugamos con el TTL, si el TTL tiene un número igual o inferior a 70 nos encontraremos ante un sistema Linux, mientras que si es mayor a 70 será un sistema Windows.
