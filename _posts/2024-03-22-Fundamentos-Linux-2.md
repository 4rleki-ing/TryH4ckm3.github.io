---
layout: single
title: Fundamentos de Linux Parte 2
excerpt: "."
date: 2024-06-29
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/Linux.png
  teaser_home_page: true
categories:
  - Lectura
tags:
  - Linux
---

![Portada](https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/Portada.png)

## Introducción
Bienvenidos a la segunda parte de la serie *"Fundamentos de Linux"*. Aplicaremos los conocimientos de la primera entrega de esta serie, por lo que se recomienda completar la sala anterior antes de continuar.

En la segunda parte, dejaremos de lado la funcionalidad del navegador y los ayudaremos a comenzar con una habilidad fundamental para poder iniciar sesión y controlar las terminales de máquinas remotas. No solo eso, sino que en la sala también podrán:

- Desbloquear el potencial de sus primeros comandos al presentarles el uso de indicadores y argumentos.
- Avanzar en su conocimiento del sistema de archivos para ejecutar algunos comandos más útiles, como copiar y mover archivos.
- Descubrir cómo se administra el acceso a archivos y carpetas y cómo podemos determinar nuestro acceso.

¡Ejecutar sus primeros scripts y ejecutables!

## Acceder a su máquina Linux mediante SSH
La funcionalidad en el navegador se utilizó en *"fundamentos de Linux, parte 1"*, para que pueda conectarse directamente a su primera máquina Linux sin ningún problema. De hecho, la funcionalidad en el navegador utiliza el mismo protocolo que vamos a utilizar hoy. Este protocolo se denomina `Secure Shell (SSH)`, es el medio común para conectarse e interactuar con la línea de comandos de una máquina Linux remota.

Implementaremos 2 máquinas en esta sala:
- Nuestra máquina Linux
- TryHackMe AttackBox

### ¿Qué es SSH y cómo funciona?
`Secure Shell (SSH)` es simplemente un protocolo entre dispositivos en formato cifrado. Mediante criptografía, cualquier entrada que enviemos en un formato legible para humanos se cifra para viajar a través de una red, donde luego se descifra una vez que llega a la máquina remota, como en el siguiente diagrama:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/Encriptado.jpeg" width="50%"> 
</center>

Puede obtener más información sobre los distintos tipos de cifrado en una sala de TryHackMe. Pero por ahora, solo necesitamos entender que:

- SSH nos permite ejecutar comandos de forma remota en otro dispositivo.
- Todos los datos enviados entre dispositivos se cifran cuando se envían a través de una red como Internet.

### Implementación de la máquina Linux
Presione el botón verde *"Iniciar máquina"* en la parte superior derecha de esta tarea y luego desplácese hasta la parte superior de la página para ver la información de implementación de la siguiente manera:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/Implementacion.png" width="50%"> 
</center>

La dirección IP que se muestra es la dirección de la máquina Linux en la que iniciará sesión mediante SSH. Tome nota de esto por ahora.

### Implementación de TryHackMe AttackBox
En la parte superior de la página, presione el botón *"Iniciar AttackBox"* con el que interactuaremos. TryHackMe AttackBox es una máquina **Ubuntu Linux** que está alojada en línea en la nube y se puede interactuar con ella a través de su navegador. La usará para interactuar con la máquina que implemente en esta tarea.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/AttackBox.png" width="50%"> 
</center>

### Uso de SSH para iniciar sesión en su máquina Linux
La sintaxis para usar SSH es muy simple. Sólo necesitamos proporcionar 2 cosas:

- La dirección IP de la máquina remota.
- Las credenciales correctas de una cuenta válida para iniciar sesión en la máquina remota.

Para esta sala, iniciaremos sesión como `tryhackme`, cuya contraseña es `tryhackme`. Usemos la dirección IP de la máquina que se muestra en la tarjeta en la parte superior de la sala como la dirección IP y este usuario, para construir un comando para iniciar sesión en la máquina remota usando SSH. El comando para hacerlo es `ssh` y luego el nombre de usuario de la cuenta, `@` la dirección de la máquina.

Pero primero, necesitamos abrir una terminal en *"TryHackMe AttackBox"*. Hay un ícono ubicado en el escritorio llamado *"Terminal"*. Y ahora, podemos proceder a ingresar comandos.

Por ejemplo, `ssh tryhackme@IP`. Reemplace la dirección IP con la dirección IP de su máquina Linux destino. Una vez ejecutado, se nos solicitará que confiemos en el host y luego proporcionemos una contraseña para la cuenta `tryhackme`, que también es `tryhackme`.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/SSH-tryhackme.png" width="50%"> 
</center>

Ahora que estamos conectados, cualquier comando que ejecutemos se ejecutará en la máquina remota, no en la nuestra.

```text
Nota:
  Cuando escribe una contraseña en un mensaje de sesión de SSH, no hay respuesta visible; no podrá ver ningún texto ni símbolo que aparezca a medida que escribe la contraseña.

  Sin embargo, sigue funcionando, así que solo escriba la contraseña y presione "Enter" para iniciar sesión.
```

## Introducción a los indicadores y conmutadores
La mayoría de los comandos permiten proporcionar argumentos. Estos argumentos se identifican con un guión y una palabra clave determinada conocida como **indicadores** o **conmutadores**.

Mas adelante analizaremos cómo podemos identificar qué comandos permiten proporcionar argumentos y comprender qué hacen exactamente. Al utilizar un comando, a menos que se especifique lo contrario, realizará su comportamiento predeterminado.

Por ejemplo, `ls` enumera el contenido del directorio de trabajo. Sin embargo, no se muestran los archivos *ocultos*. Podemos utilizar indicadores y conmutadores para ampliar el comportamiento de los comandos.

Utilizando nuestro ejemplo de *ls*, `ls` nos informa que solo hay una carpeta llamada `folder1`, como se destaca en la siguiente captura de pantalla. Tenga en cuenta que el contenido de las capturas de pantalla son solo ejemplos.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/SSH-ls.png" width="50%"> 
</center>

Sin embargo, después de usar el argumento `-a` (abreviatura de *-all*), ahora tenemos una salida con algunos archivos y carpetas más, como `.hiddenfolder`. Los archivos y carpetas con `.` son archivos ocultos.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/SSH-ls-a.png" width="50%"> 
</center>

Los comandos que las aceptan también tendrán una opción `--help`. Esta opción enumerará las posibles opciones que acepta el comando, proporcionará una breve descripción y un ejemplo de cómo utilizarlas.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/SSH-ls-help.png" width="50%"> 
</center>

Esta opción es, de hecho, una salida formateada de lo que se denomina la página `man` (abreviatura de *manual*), que contiene documentación para los comandos y aplicaciones de Linux.

### Página man
Las páginas del manual son una gran fuente de información tanto para los comandos del sistema como para las aplicaciones disponibles en una máquina Linux, a la que se puede acceder desde la propia máquina y en línea.

Para acceder a esta documentación, podemos utilizar el comando `man` y luego proporcionar el comando para el que queremos leer la documentación. Utilizando nuestro ejemplo *ls*, utilizaríamos `man ls` para ver las páginas del manual de *ls* de la siguiente manera:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/SSH-ls-man.png" width="50%"> 
</center>

### Responda las preguntas a continuación
- Explore la página del manual del comando ls.
-¿Qué tecla de flecha direccional usaríamos para navegar hacia abajo en la página del manual? `down`
- ¿Qué bandera usaríamos para mostrar la salida de una manera "legible para humanos"? `-h`

## Interacción con el sistema de archivos (Continuación)
Abordamos algunos de los comandos más fundamentales al interactuar con el sistema de archivos en la máquina Linux. Por ejemplo, abordamos cómo enumerar y buscar el contenido de las carpetas mediante `ls` y cómo buscar y navegar por el sistema de archivos mediante `cd`.

En esta tarea, aprenderemos algunos comandos más para interactuar con el sistema de archivos que nos permitan:

- Crear archivos y carpetas
- Mover archivos y carpetas
- Eliminar archivos y carpetas

Más específicamente, los siguientes comandos:

| Comando | Nombre Completo                   | Objetivo                          |
|---------|-----------------------------------|-----------------------------------|
| touch   | Tocar (touch)                     | Crear archivo                     |
| mkdir   | Crear Directorio (make directory) | Crear una carpeta                 |
| cp      | Copiar (copy)                     | Copiar un archivo o una carpeta   |
| mv      | Mover (move)                      | Mover un archivo o  una carpeta   |
| rm      | Eliminar (remove)                 | Eliminar un archivo o una carpeta |
| file    | Archivo (file)                    | Determinar el tipo de un archivo  |

```text
Consejo:
  De manera similar al uso de cat, podemos proporcionar rutas de archivo completas, es decir, (directorio1/directorio2/nota) para todos estos comandos.
```

### Creación de archivos y carpetas (touch, mkdir)
Crear archivos y carpetas en Linux es un proceso sencillo. Primero, veremos cómo crear un archivo.

El comando `touch` toma exactamente un argumento: *el nombre que queremos darle al archivo que creamos*. Por ejemplo, podemos crear el archivo **note** usando `touch note`. Vale la pena señalar que *touch* simplemente crea un archivo en blanco. Necesitarás usar comandos como `echo` o editores de texto como `nano` para agregar contenido al archivo en blanco.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/touch-note.png" width="50%"> 
</center>

Este es un proceso similar al de crear una carpeta, que solo implica usar el comando  `mkdir` y proporcionar el nombre del directorio que queremos crear. Por ejemplo, crear el directorio *"mydirectory"*  se puede hacer con `mkdir mydirectory`.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/mkdir-mydirectory.png" width="50%"> 
</center>

### Eliminar archivos y  carpetas (rm)
De todos los comandos que hemos visto  hasta ahora, `rm` es el más peligroso. Puedes eliminar archivos simplemente usando `rm`. Sin embargo, debes proporcionar el modificador `-R` junto con el nombre del directorio que deseas eliminar.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/rm-note.png" width="50%"> 
</center>

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/rm-mydirectory.png" width="50%"> 
</center>

### Copiar y mover archivos y  carpetas (cp, mv)
Copiar y mover archivos es una función importante en una máquina Linux. Este comando, que comienza con `cp` toma 2 argumentos:

- El archivo o carpeta que deseas copiar.
- El nombre del archivo o carpeta destino.

`cp` copia todo el contenido del archivo existente en el nuevo archivo. En la siguiente captura de pantalla, se aprecia como copiamos *"note"* a *"note2"*.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/cp-note.png" width="50%"> 
</center>

Para mover un archivo se necesitan 2 argumentos, al igual que con el comando `cp`. Sin embargo, en lugar de copiar o crear un archivo nuevo, `mv` fusionará o modificará el segundo archivo que proporcionamos como argumento. No solo puede usar `mv` para mover un archivo a una nueva carpeta, sino que también puede usar *mv* para **cambiar el nombre de un archivo o carpeta**. Por ejemplo, en la siguiente captura de pantalla, estamos cambiando el nombre del archivo *"note2"* para que se llame *"note3"*. **"note3"** ahora tendrá el contenido de *"note2"*.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/mv-note2.png" width="50%"> 
</center>

### Determinación del tipo de archivo
Lo que suele ser engañoso y suele pillar desprevenidos a los usuarios es hacer suposiciones a partir de los archivos sobre su propósito o contenido. Los archivos suelen tener loq ue se conoce como extensión para facilitar esta tarea. Por ejemplo, los archivos de texto suelen tener la extensión `".txt"`. Pero esto no es necesario.

Hasta ahora, los archivos que hemos utilizado en nuestros ejemplos no tenían extensión. Sin conocer el contexto de por qué el archivo está ahí, no sabemos realmente su propósito. Introduzca  el comando `file`. Este comando toma 1 argumento. Por ejemplo, utilizaremos *file* para confirmar si el archivo *"note"* en nuestros ejemplos es o no un archivo de texto, como `file note`.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/file-note.png" width="50%"> 
</center>

### Responde las preguntas a continuación
- ¿Cómo crearías el archivo llamado *"newnote"*? `touch newnote`
- En la máquina implementable, ¿Cuál es el tipo de archivo *"unknown1"* en el directorio de inicio de *"tryhackme"*? `ASCII text`
- ¿Cómo movemos el archivo *"myfile"* al directorio *"myfolder"*? `mv myfile myfolder`
- ¿Cuál es el contenido de este archivo? `THM{FILESYSTEM}`

## Permisos 101
Como ya habrás descubierto, ciertos usuarios no pueden acceder a determinados archivos o carpetas. Anteriormente hemos explorado algunos comandos que se pueden utilizar para determinar qué acceso tenemos y a dónde nos lleva.

En nuestras tareas anteriores, aprendimos a ampliar el uso de comandos a través de indicadores y modificadores. Tomemos, por ejemplo, el comando **ls**, que enumera el contenido del directorio actual. Al utilizar el modificador `-l`, podemos ver diez columnas como se muestra en la siguiente captura de pantalla. Sin embargo, solo nos interesan las primeras 3 columnas:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/ls-l.png" width="50%"> 
</center>

Aunque parezacan intimidantes, estas 3 columnas son muy importantes para determinar ciertas características de un archivo o carpeta y si tenemos o no acceso a él. Un archivo o carpeta puede tener un par de características que determinan qué acciones están permitidas y qué usuario o grupo tiene la capacidad de realizar la acción dada, como las siguientes:

- Lectura (Read)
- Escritura (Write)
- Ejecución (Execute)

Uso de `su` para cambiar a *user2*:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/su-user2.png" width="50%"> 
</center>

Utilicemos el archivo `cmnatic.pem` en nuestra captura de pantalla inicial en la parte superior de esta tarea. Tiene el indicador `-` que resalta que es un archivo y luego `rw` seguido. Esto significa que solo el propietario del archivo puede leer y escribir en este archivo *cmnatic.pem*, pero no puede ejecutarlo.

### Brevemente: Diferencias entre usuarios y grupos
Lo bueno de Linux es que los permisos pueden ser tan granulares que, si bien un usuario técnicamente es el propietario de un archivo, si se han establecido los permisos, un grupo de usuarios también puede tener el mismo conjunto de permisos o uno diferente para el mismo archivo exacto sin afectar al propietario del archivo en sí.

Pongamos esto en un contexto del mundo real; el usuario del sistema que ejecuta un servidor web debe tener permisos para leer y escribir archivos para una aplicación web efectiva. Sin embargo, las empresas como las de alojamiento web, tendrán que permitir que sus clientes carguen sus propios archivos para su sitio web sin ser el usuario del sistema del servidor web, lo que comprometería la seguridad de todos los demás clientes.

Aprenderemos los comandos necesarios para cambiar entre usuarios a continuación.

### Cambiar entre usuarios
Cambiar entre usuarios en una instalación Linux es una tarea sencilla gracias al comando `su`. A menos que sea el usuario ***root*** (o utilice permisos *root* a través de `sudo`), deberá saber 2 cosas para facilitar esta transición de cuentas de usuario:

1. El nombre de usuario al que desea cambiar
2. La contraseña del usuario al que desea cambiar

El comando `su` requiere un par de opciones que pueden ser relevantes para usted. Por ejemplo, ejecutar un comando una vez que inicia sesión o especificar un shell específico para usar. Se recomienda leer la página del manual de `su` para obtener más información. Sin embargo, cubriré el parámetro `-l` o `--login`.

Simplemente, al proporcionar el parámetro `-l` a `su`, iniciamos un shell que es mucho más similar al usuario real que inicia sesión en el sistema: heredamos muchas más propiedades del nuevo usuario, es decir, variables de entorno y similares.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/su-user2.png" width="50%"> 
</center>

Por ejemplo, al usar `su` para cambiar a *"user2"*, nuestra nueva sesión nos lleva al directorio de inicio de nuestro usuario anterior.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/su-l-user2.png" width="50%"> 
</center>

Ahora, después de usar `-l`, nuestra nueva sesión nos ha llevado automáticamente al directorio de inicio de *"user"*

### Responda las preguntas a continuación
- En la máquina implementable, ¿Quién es el propietario de *"important"*? `user2`
- ¿Cuál sería el comando para cambiar al usuario *"user2"*? `su user2`
- Ahora cambie al usuario *"user2"* usando la contraseña **"user2"**; extraiga el contenido de *"important"*, ¿Cuál es el indicador? `THM{SU_USER2}`

## Directorios Comunes
### /etc
Este directorio raíz es uno de los más importantes de su sistema. La carpeta `etc` (Abreviatura de etcetera) es una ubicación común para almacenar archivos de sistema que utiliza su sistema operativo.

Por ejemplo, el archivo `sudoers` resaltado en la siguiente captura de pantalla contiene una lista de los usuarios y grupos que tienen permiso para ejecutar **sudo** o un conjunto de comandos como `usuario raíz`.

También se destacan a continuación los archivos `passwd` y `shadow`. Estos archivos son especiales para Linux, ya que muestran cómo su sistema almacena las contraseñas de cada usuario en un formato cifrado llamado `sha512`.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/etc-ls.png" width="50%"> 
</center>

### /var
El directorio `/var` (Abreviatura de Datos Variables), es una de las principales carpetas raíz que se encuentran en la instalación de Linux. Esta carpeta almacena datos a los que acceden o escriben con frecuencia los servicios o aplicaciones que se ejecutan en el siustema.

Por ejemplo, aquí se escriben los archivos de registro de los servicios y aplicaciones que se ejecutan `/var/log` u otros datos que no están necesariamente asociados con un usuario específico (es decir, bases de datos y similares).

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/var-ls.png" width="50%"> 
</center>

### /root
A diferencia del directorio `/home`, la carpeta `/root` es en realidad el directorio de inicio del usuario `root` del sistema. Esta carpeta no tiene nada más que ver con entender que es el directorio de inicio del usuario `root`. Sin embargo, vale la pena mencionarlo, ya que la suposición lógica es que este usuario tendría sus datos en un directorio como `/home/root` de manera predeterminada.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/root-ls.png" width="50%"> 
</center>

### /tmp
Este es un directorio raíz único que se encuentra en la instalación de Linux. El directorio `/tmp` (Abreviatura de Temporal), es volátil y se utiliza para almacenar datos a los que solo se debe acceder una o dos veces. De manera similar a la memoria de la computadora, una vez que se reinicia la computadora, se borra el contenido de esta carpeta.

Lo que nos resulta útil en las pruebas de penetración es que cualquier usuario puede escribir en esta carpeta de manera predeterminada. Esto significa que una vez que tenemos acceso a una máquina, sirve como un buen lugar para almacenar cosas como nuestros scripts de enumeración.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-2/tmp-ls.png" width="50%"> 
</center>

### Responde las preguntas a continuación
- ¿Cuál es la ruta del directorio en el que esperamos que se almacenen los registros? `/var/log`
- ¿Qué directorio raíz es similar a cómo funciona la memoria RAM en una computadora? `/tmp`
- Nombra el directorio de inicio del usuario root. `/root`

## Conclusiones y Resúmenes
¡Buen trabajo! Esta sala se centró en la teoría y cubrió una gran variedad de aspectos fundamentales para familiarizarse con Linux. Para resumir rápidamente, esta sala le enseñó:

- Cómo conectarse a una máquina Linux de forma remota usando SSH
- Avanzar en el uso de comandos proporcionando indicadores, modificadores y dónde puede ir para obtener información sobre estos para cada comando (manual)
- Algunos comandos más que usará con frecuencia para interactuar con el sistema de archivos y su contenido.
- Una breve introducción a los permisos de archivo y al cambio de usuarios
- Un párrafo de resumen de los directorios raíz más importantes en una instalación de Ubuntu Linux y cómo podemos usar los datos almacenados en estos.

Les animo a que vuelvan a pasar por esta sala una o dos veces para familiarizarse con los conceptos. Después de todo, ¡la práctica hace al maestro!

## Fundamentos de Linux - Parte 3
¡Visite la tercera parte de la serie de fundamentos de Linux [aquí](https://tryhackme.com/r/room/linuxfundamentalspart3).