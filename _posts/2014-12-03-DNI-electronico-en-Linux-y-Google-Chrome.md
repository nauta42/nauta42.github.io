---
layout: post
title: Google Chrome (Linux): soporte para DNI electrónico (España) 
---

## (2014-12) DNIe EN GOOGLE CHROME BAJO LINUX

Esta pequeña guía es para conseguir que el DNIe FUNCIONE en Google Chrome bajo Linux.
Los pasos a añadir a esta [excelente guía de juanetel][1] son bastante simples.
Que yo sepa *NO* he encontrado ninguna otra guía que explique cómo hacerlo.

### ENTORNO
* Linux Mint 17 (64bits) - basado en UBUNTU 14.04
* Google Chrome v39 - posiblemente funcione en otras versiones
* Smartcard reader C3PO LTC31

### PASOS
1. Usar [esta guía][1] hasta conseguir que funcione el DNIe en FIREFOX
2. Los pasos adicionales que he añadido se basan en [esto][2] y son:
  1. Instalar NSS tools
        sudo apt-get install libnss3-tools
  2. CERRAR todos los navegadores (IMPORTANTE!)
  3. Añadir el módulo DNIe_Module (se puede poner otro nombre)
        modutil -dbdir sql:.pki/nssdb/ -add "DNIe_Module" -libfile /usr/lib/opensc-pkcs11.so
  4. Comprobar que se ha añadido a la lista
        modutil -dbdir sql:.pki/nssdb/ -list

Con esto ya debería estar; para comprobarlo insertar el DNI, abrir el Chrome y
dentro de la configuración ir a avanzado, HTTPS/SSL gestionar certificados.
Pedirá la clave y deberían aparecer los certificados del DNIe.

Este documento puede usarse libremente.

### REFERENCIAS
[1]: http://www.ubuntu-guia.com/2014/04/instalar-dni-electronico-en-ubuntu.html#
[2]: https://help.ubuntu.com/community/CommonAccessCard#Google_Chrome.2BAC8-Chromium_Setup
