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
- Edite *"task3"* ubicado en el directorio de inicio de *"tryhackme"* usando Nano. ¿Qué es la bandera? `THM{TEXT_EDITORS}`

## Utilidades Generales / Útiles
### Descarga de archivos (wget)
Una caracteística bastante fundamental de la informática es la capacidad de transferir archivos. Por ejemplo, es posible que desee descargar un programa, un script o incluso una imagen. Afortunadamente para nosotros, hay varias formas en las que podemos recuperar estos archivos.

Vamos a cubrir el uso de `wget`. Este comando nos permite descargar archivos de la web a través de HTTP, como si estuvieras accediendo al archivo en el navegador. Simplemente tenemos que proporcionar la dirección del recurso que deseamos descargar. Por ejemplo, si quisiera descargar un archivo llamado *"myfile.txt"* en mi máquina, suponiendo que supiera la dirección web, se vería así: `wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt`

### Transferencia de archivos desde su host - SCP (SSH)
La copia segura, o SCP, es solo eso: un medio para copiar archivos de forma segura. A diferencia del comando *cp* normal, este comando le permite transferir archivos entre dos computadoras utilizando el protocolo SSh para proporcionar autenticación y cifrado.

Trabajando en un modelo de ORIGEN y DESTINO, SCP te permite:

- Copie archivos y directorios de su sistema actual a un sistema remoto.
- Copie archivos y directorios de un sistema remoto a su sistema actual.

Siempre que conozcamos los nombres de usuario y las contraseñas de un usuario en su sistema actual y un usuario en el sistema remoto. Por ejemplo, copiemos un archivo de ejemplo de nuestra máquina a una máquina remota, que he expuesto cuidadosamente en la siguiente tabla:

| Variable                                                            | Valor           |
|---------------------------------------------------------------------|-----------------|
| La dirección IP del sistema remoto                                  | 192.168.1.30    |
| Usuario en el sistema remoto                                        | ubuntu          |
| Nombre del archivo en el sistema local                              | important.txt   |
| Nombre en el que deseamos almacenar el archivo en el sistema remoto | transferred.txt |

Con esta información, vamos a crear el comando `scp` (recordando que el formato de SCP es solo ORIGEN y DESTINO) `scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt`. Y ahora invirtamos esto y diseñemos la sintaxis para usar *scp* para copiar un archivo de una computadora remota en la que no hemos iniciado sesión.

| Variable                                                           | Valor         |
|--------------------------------------------------------------------|---------------|
| Dirección IP del sistema remoto                                    | 192.168.1.30  |
| Usuario en el sistema remoto                                       | ubuntu        |
| Nombre del archivo en el sistema remoto                            | documents.txt |
| Nombre con el que deseamos almacenar el archivo en nuestro sistema | notes.txt     |

El comando ahora tendrá el siguiente aspecto `scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt`

### Sirviendo archivos desde su host - WEB
Las máquinas Ubuntu vienen preempaquetadas con *python3*. Python proporciona un módulo ligero y fácil de usar llamado `HTTPServer`. Este módulo convierte su computadora en un servidor web rápido y fácil que puede usar para servir sus propios archivos, donde luego pueden ser descargados por otra computadora usando comandos como `curl` y `wget`.

*"HTTPServer"* de Python3 servirá los archivos en el directorio donde ejecuta el comando, pero esto se puede cambiar proporcionando opciones que se pueden encontrar en las páginas del manual. simplemente, todo lo que tenemos que hacer es correr `python3 -m http.server` en la terminal para iniciar el módulo. En la siguiente captura de pantalla, se aprecia como se está sirviendo desde un directorio llamado *"webserver"*, que tiene un solo nombre *"file"*.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/webserver.png" width="50%"> 
</center>

Ahora, usemos `wget` para descargar el archivo utilizando la dirección IP y el nombre del archivo. Recuerde, debido a que el servidor *python3* está ejecutando el puerto 8000, deberá especificar esto dentro de su comando *wget*. Por ejemplo: 

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/wget-myfile.png" width="50%"> 
</center>

Tenga en cuenta que deberá abrir una nueva terminal para usar `wget` y deje el servidor web en el que ha iniciado el servidor web Python3. Esto se debe a que, una vez que inicies el servidor web Python3, se ejecutará en esa terminal hasta que lo canceles.
Echemos un vistazo a la siguiente captura de pantalla como ejemplo:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/wget-file.png" width="50%"> 
</center>

**Recuerde**, deberá ejecutar el comando *wget* en otra terminal (mientras mantiene activo el terminal que ejecuta el servidor Python3). A continuación se muestra un ejemplo de esto en TryHackMe AttackBox:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/webserver-exec.png" width="50%"> 
</center>

