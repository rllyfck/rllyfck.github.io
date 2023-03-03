## Host Discovery - SCRIPT

---
layout: single
title: Hdiscovery - Mi primera herramienta
excerpt: "Delivery is a quick and fun easy box where we have to create a MatterMost account and validate it by using automatic email accounts created by the OsTicket application. The admins on this platform have very poor security practices and put plaintext credentials in MatterMost. Once we get the initial shell with the creds from MatterMost we'll poke around MySQL and get a root password bcrypt hash. Using a hint left in the MatterMost channel about the password being a variation of PleaseSubscribe!, we'll use hashcat combined with rules to crack the password then get the root shell."
date: 2023-03-03
classes: wide
header:
  teaser: /assets/images/htb-writeup-delivery/delivery_logo.png
  teaser_home_page: true
  icon: /assets/images/hackthebox.webp
categories:
  - hackthebox
  - tryhackme
tags:  
  - script
  - mysql
  - mattermost
  - hashcat
  - rules
---


Descripción: Script creado por @rllyfc4 en bash. Es una herramienta muy sencilla y útil de utilizar.

Dato importante: Para su correcto funcionamiento se debe pasar una dirección IP. ya que si pasas el nombre del servidor puede dar fallo. 

