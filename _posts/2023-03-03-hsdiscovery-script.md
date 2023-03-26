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

As you can see in the image, for the tool to work you must put ``` ./hdiscovery -h {ip} ```. As output of the command it will show us the IP previously written and the operating system to which it belongs.

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
For the recognition of the operating system we play with the TTL, if the TTL has a number equal to or less than 70 we will find a Linux system, while if it is greater than 70 it will be a Windows system.
