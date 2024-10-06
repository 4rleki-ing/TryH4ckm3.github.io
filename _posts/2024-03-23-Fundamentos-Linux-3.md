---
layout: single
title: Fundamentos de Linux Parte 3
excerpt: "¡Potencie sus habilidades de Linux y póngase manos a la obra con algunas utilidades comunes que probablemente usará ddía a día!."
date: 2024-06-28
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/Linux.jpg
  teaser_home_page: true
categories:
  - Lectura
tags:
  - Linux
---

<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/Portada.jpg">

Bienvenidos a la tercera parte (y al final) del módulo de *Fundamentos de Linux*. Hasta ahora, a lo largo de la serie, te has puesto manos a la obra con algunos conceptos fundamentales y has utilizado algunos comandos importantes. Esta sala mostrará algunas utilidades y aplicaciones útiles que probablemente utilizará en el día a día. También vas a mejorar tus habilidades de Linux aprendiendo sobre automatización, gestión de paquetes y registro de servicios / aplicaciones.

## Implemente su máquina Linux
Presione el botón verde *"Iniciar máquina"* en la parte superior de la página para ver la información de implementación de la siguiente manera:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/Implementacion.png" width="50%"> 
</center>

La dirección IP que se muestra es la dirección de su máquina Linux en la que iniciará sesión mediante SSH. Toma nota de esto por ahora.

### Implementación de TryHackMe AttackBox
Mirando en la parte superior de la página, presione el botón *"Iniciar AttackBox"* para desplegar el TryHackMe AttackBox con el que interactuaremos. TryHackMe AttackBox es una máquina Ubuntu Linux que está alojada en línea en la nube y con la que se puede interactuar a través de su navegador. Lo usará para interactuar con la máquina que implemente en esta tarea.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/AttackBox.png" width="50%"> 
</center>

Utilice las siguientes credenciales:
- *Dirección IP*: `MACHINE_IP`
- *Nombre de Usuario*: `tryhackme`
- *Contraseña*: `tryhackme`

## Editores de texto de terminal
A lo largo de la serie hasta ahora, solo hemos almacenado texto en archivos utilizando una combinación del comando `echo` y los operadores `>` y `>>`. Esta no es una forma eficaz de manejar datos cuando se trabaja con archivos con varias líneas y los ordenes.

### Presentación de editores de texto de terminal
Hay algunas opciones que puede usar, todas con una variedad de amabilidad y utilidad. Esta tarea te va a presentar `nano`, pero también te va a mostrar una alternativa llamada `VIM` (¡a la que TryHackMe tiene una sala dedicada!).

### Nano
¡Es fácil empezar con Nano! Para crear o editar un archivo usando nano, simplemente usamos `nano filename` reemplazando *"filename"* con el nombre del archivo que desea editar.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/nano-myfile.png" width="50%"> 
</center>

Una vez que pulsemos "enter" para ejecutar el comando `nano`, este se lanzará; donde apenas podemos empezar a introducir o modificar nuestro texto. Puede navegar por cada línea usando las teclas de flecha *arriba (up)* y *abajo (down)* o comenzar una nueva línea usando la tecla "Enter" en su teclado.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/nano-myfile-2.png" width="50%"> 
</center>

Nano tiene algunas características que son fáciles de recordar y cubre las cosas más generales que querría de un editor de texto, que incluyen:

- Búsqueda de texto
- Copiar y pegar
- Saltar a un número de línea
- Averiguar en qué número de línea se encuentra

Puede utilizar estas características de nano presionando la tecla `Ctrl` (que se representa como un `^` en Linux) y una letra correspondiente. Por ejemplo, para salir, querríamos presionar `Ctrl + X` para salir de nano.

### VIM
VIM es un editor de texto mucho más avanzado. Si bien no se espera que conozca todas las funciones avanzadas, es útil mencionarlo para potenciar sus habilidades de Linux.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/VIM.png" width="50%"> 
</center>

Algunos de los beneficios de VIM, aunque lleva mucho más tiempo familiarizarse, incluyen:

- `Personalizable`: Puedes modificar los atajos de teclado para que sean de tu elección.
- `Resaltado de sintaxis`: Esto es útil si se está escribiendo o manteniendo código, lo que lo convierte en una opción popular para los desarrolladores de software
- VIM funciona en todos los terminales en los que no se puede instalar nano.
- Hay muchos recursos, como [hojas de trucos](https://vim.rtorr.com/), tutoriales y los tipos disponibles para usar.

¡TryHackMe tiene una sala que muestra [VIM](https://tryhackme.com/r/room/toolboxvim), si desea obtener más información sobre este editor!

### Responda las preguntas a continuación
- Edite *"task3"* ubicado en el directorio de inicio de *"tryhackme"* usando Nano. ¿Qué es la bandera? ``