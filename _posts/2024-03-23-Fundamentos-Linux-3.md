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

Un defecto de este modulo es que no tiene forma de indexar, por lo que debe de saber el nombre exacto y la ubicación del archivo que desea utilizar. Por eso prefiero utilizar [Updog](https://github.com/sc0tfree/updog), un servidor web mas avanzado pero liviano. Pero por ahora, sigamos utilizando el *"servidor HTTP"* de Python.

### Responda las preguntas a continuación
- Asegurese de estar conectado a la instancia implementada.
- Ahora, use el modulo *"HTTPServer"* de Python3 para iniciar el servidor web en el directorio de inicio del usuario *"tryhackme"* en la instancia implementada.
- Descargue el archivo `http://10.10.137.7:8000/.flag.txt` en TryHackMe AttackBox. recuerde, deberà hacer esto en una nueva terminal. ¿Cùal es el contenido del archivo? `THM{WGET_WEBSERVER}`
- Cree y descargue archivos para aplicar aùn màs su aprendizaje; vea como puede leer la documentacion en el modulo *"HTTPServer"* de Python3. Utilice `Ctrl + C` para detener el modulo HTTPServer de python3 una vez que haya terminado.

## Procesos 101
Los procesos son los programas que se ejecutan en la máquina. Son administrados por el kernel, donde cada proceso tiene un identificador único asociado tambièn conocido como (PID). El PID aumenta segùn el orden en que comienza el proceso. Es decir, el proceso 60 tendrà un PID de 60.

### Visualización de Procesos
Podemos utilizar el comando `ps` para proporcionar una lista de los procesos en ejecución, como la sesión de nuestro usuario y alguna información adicional como su código de estado, la sesión que lo está ejecutando, cuánto tiempo de uso de la CPU está usando y el nombre del programa o comando real que se está ejecutando.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/ps.png" width="50%"> 
</center>

Observe cómo en la captura de pantalla anterior, el segundo proceso *ps* tiene un PID de 204, y luego, en el comando debajo, este se incrementa a 205.

Para ver los procesos ejecutados por otros usuarios y aquellos que no se ejecutan desde una sesión (procesos del sistema), debemos proporcionar *aux* al comando *ps* así: `ps aux`.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/ps-aux.png" width="50%"> 
</center>

Tenga en cuenta que podemos ver un total de *5 procesos*; observe que ahora tenemos *"root"* y *cmnatic"*.

Otro comando muy útil es el comando `top`; *top* le brinda estadísticas en tiempo real de los procesos que se ejecutan en el sistema en lugar de una vista única. Estas estadísticas se actualizarán cada *10 segundos*, pero también se actualizarán cuando utilice las teclas de flecha para explorar las distintas filas.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/top.png" width="50%"> 
</center>

### Gestión de Procesos
Puede enviar señales que finalicen procesos; hay una variedad de tipos de señales que se correlacionan exactamente con qué tan *"limpiamente"* el núcleo maneja el proceso. Para eliminar un comando, podemos utilizar el comando *"kill"* con el nombre apropiado y el *PID asociado* que deseamos eliminar, es decir, para eliminar el PID 1337, usaríamos `kill 1337`.

A continuación se muestran algunas de las señales que podemos enviar a un proceso cuando se elimina:
- SIGTERM: Elimina el proceso, pero permite que realice algunas tareas de limpieza de antemano.
- SIGKILL: Elimina el proceso, no realiza ninguna limpieza después del hecho.
- SIGSTOP: Detiene/Suspende un proceso.

### ¿Cómo comienzan los procesos?
Comencemos hablando de espacios de nombres. El sistema operativo (SO) utiliza espacios de nombres para, en última instancia, dividir los recursos disponibles en la computadora en procesos (CPU, RAM y prioridad). Piense en ello como dividir su computadora en porciones, similar a un pastel. Los procesos dentro de ese segmento tendrán acceso a una cierta cantidad de potencia informática; sin embargo, será una pequeña porción de lo que realmente está disponible para cada proceso en general.

Los espacios de nombres son excelentes para la seguridad, ya que son una forma de aislar procesos de otros: solo aquellos que están en el mismo espacio de nombres podrán verse entre sí.

Anteriormente hablamos de cómo funciona el PID y aquí es donde entra en juego. El proceso con un ID de 0 es un proceso que se inicia cuando se inicia el sistema. Este proceso es el inicio del sistema en Ubuntu, como `systemd`, que se utiliza para proporcionar una forma de administrar los procesos de un usuario y se ubica entre el sistema operativo y el usuario.

Por ejemplo, una vez que un sistema arranca e inicia, *systemd* es uno d elos primeros procesos que s einicia. Cualquier programa o pieza de software que queramos iniciar comenzará como lo que s econoce como *un proceso hijo de systemd*. Esto significa que está controlado por systemd, pero se ejecutará como su propio proceso (aunque compartiendo los recursos de systemd) para que nos sea más fácil identificarlo y similares.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/systemd.png" width="50%"> 
</center>

### Cómo hacer que los procesos/servicios se inicien al arrancar
Algunas aplicaciones se pueden iniciar durante el arranque del sistema que poseemos. Por ejemplo, *servidores web* *servidores de bases de datos* o *servidores de transferencia de archivos*. Este software suele ser fundamental y los administradores suelen indicarle qee se inicie durante el arranque del sistema.

En este ejemplo, le indicaremos al servidor web Apache que inicie Apache manualmente y luego le indicaremos al sistema que inicie Apache2 durante el arranque.

Utilizaremos el comando `systemctl`, este comando nos permite interactuar con el proceso/demonio systemd. Continuando con nuestro ejemplo, *systemctl* es un comando fácil de usar que toma el siguiente formato: `systemctl (option) (service)`.

Por ejemplo, para indicarle a Apache que inicie, usaremos `systemctl start apache2`. Parece bastante simple, lo mismo ocurre si quisiéramos detener Apache, simplemente reemplazaríamos la (opción) con *stop* (en lugar de iniciar como proporcionamos).

Podemos hacer 4 opciones con *systemctl*:

- Start
- Stop
- Enable
- Disable

### Introducción a la ejecución en segundo plano y en primer plano en Linux
Los procesos pueden ejecutarse en dos estados: en primer y segundo plano. Por ejemplo, los comandos que ejecuta en su terminal, como **echo**, o cosas por el estilo, se ejecutarán en primer plano de su terminal, ya que es el único comando proporcionado que no se le ha indicado que se ejecute en segundo plano. *"echo"* es un gran ejemplo, ya que la salida regresará a usted en primer plano, pero no en segundo plano; tome la captura de pantalla a continuación, por ejemplo.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-3/echo.png" width="50%"> 
</center>

Aquí estamos ejecutando `echo "Hi THM"`, donde esperamos que nos devuelvan el resultado como al principio. Pero después de agregar el operador `&` al comando, en lugar de la salida real, solo se nos da el ID del proceso *echo*, ya que se está ejecutando en segundo plano.

