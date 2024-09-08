---
layout: single
title: Servicios de red 2
excerpt: "Enumeración y explotación de servicios de red y configuraciones erróneas más comunes."
date: 2024-08-19
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red-2/Servicios.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red-2/Portada.png">

Esta sala es una secuela de la primera sala de servicios de red. De manera similar, explotará algunas vulnerabilidades y configuraciones incorrectas más comunes de los servicios de red que probablemente encuentres en los CTF y algunos escenarios de pruebas de penetración.

Te recomiendo que completes la primera sala de [servicios de red]() antes de intentar esta. Al igual que con la sala anterior, definitivamente vale la pena tener un conocimiento básico de Linux antes de intentar esta sala. Si necesita ayuda con esto, intenta completar el módulo ***Conceptos básicos de Linux***:

- [Fundamentos de Linux, Parte 1]()
- [Fundamentos de Linux, Parte 2]()
- [Fundamentos de Linux, Parte 3]()

Conéctate al servidor [OpenVPN]() de TryHackMe; asegúrate de estar sentado cómodamente y ten una taza de té, café o agua cerca. ¡Comencemos!

**N.B.** Esta no es una sala sobre piratería o secuestro de acceso WiFi, sino sobre cómo obtener acceso no autorizado a una máquina mediante la explotación de los servicios de red. Si te interesa hackear redes WiFi, te sugiero que consultes [WiFi Hacking 101]() de NinjaJc01.

¿Listo? ¡Comencemos!

## NFS
NFS (Sistema de archivos de red) y permite que un sistema comparta directorios y archivos con otros a través de una red. Al utilizar NFS, los usuarios y los programas pueden acceder a archivos en sistemas remotos casi como si fueran archivos locales. Esto se logra montando todo o parte de un sistema de archivos en un servidor. Los clientes pueden acceder a la parte del sistema de archivos que se monta con los privilegios que se les asignen a cada archivo.