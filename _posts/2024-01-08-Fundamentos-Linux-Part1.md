---
layout: single
title: Fundamentos de Linux, Parte 1
excerpt: "Embárcate en el viaje de aprendizaje de los conceptos básicos de Linux. Aprende a ejecutar algunos de los primeros comandos esenciales en una terminal interactiva."
date: 2024-08-24
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Linux.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Portada.png">

## Introducción

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Fundamentos-Linux.png">

Bienvenidos a la primera parte de la serie de salas "Fundamentos de Linux". Probablemente estén usando una máquina Windows o Mac, ambas son diferentes en diseño visual y en su funcionamiento. Al igual que Windows, iOS y MacOS, Linux es solo otro sistema operativo y uno de los más populares del mundo que impulsa autos inteligentes, dispositivos Android, supercomputadoras, electrodomésticos, servidores empresariales y más.

¡Cubriremos parte de la historia detrás de Linux y luego, eventualmente, comenzaremos su viaje para convertirse en un experto en Linux! En esta sala:

- Ejecutaremos sus primeros comandos en una máquina Linux interactiva en su navegador.
- Le enseñaremos algunos comandos esenciales que se usan para interactuar con el sistema de archivos.
- Le demostraremos cómo puede buscar archivos e introducir operadores de shell.

### Responda las preguntas a continuación
1. ¡Comencemos!

## Un poco de Historia sobre Linux
`¿Dónde se utiliza Linux?` Es justo decir que Linux es mucho más intimidante de abordar que los sistemas operativos (OS) como Windows. Ambas variantes tienen sus propias ventajas y desventajas. Por ejemplo, Linux es considerablemente más liviano y te sorprendería saber que es muy probable que hayas usado Linux de una forma u otra todos los días. Linux impulsa cosas como:

- Sitios web que visitas
- Paneles de control/entretenimiento de automóviles
- Sistemas de punto de venta (PoS) como cajas registradoras y cajas registradoras en tiendas
- Infraestruccturas críticas como controladores de semáforors o sensores industriales.

### Variedades de Linux
El nombre "Linux" es en realidad un término general para varios SO que se basan en UNIX (otro sistema operativo). Gracias a que Linux es de código abierto, las variantes de Linux vienen en todas las formas y tamaños, las más adecuadas para el uso que se le da al sistema.

Por ejemplo, Ubuntu y Debian son algunas de las distribuciones más comunes de Linuxx porque son muy extensibles. Es decir, puedes ejecutar Ubuntu como un servidor (como sitios web y aplicaciones web) o como un escritorio completo. Para esta serie, usaremos Ubuntu.

```text
Ubuntu Server puede ejecutarse en sistemas con solo 512 MB de RAM.
```

De manera similar a cómo existen diferentes versiones de Windows (7, 8 y 10), existen muchas versiones/distribuciones diferentes de Linux.

### Responde las preguntas a continuación
1. Investigación: ¿En qué año se lanzó por primera vez un sistema operativo Linux? `1991`

## Interacción con su primera máquina Linux (Desde el Navegador)

Esta sala cuenta con una máquina Linux Ubuntu con la que puedes interactuar desde tu navegador mientras sigues el material de esta sala.

Sin embargo, para comenzar, simplemente presiona el botón verde "Iniciar máquina" en la parte superior derecha de esta tarea indicada por la flecha a la derecha:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Inicio-Sala.png">

Una vez desplegada, aparecerá una tarjeta en la parte superior de la sala:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Sala.png">

Contiene toda la información de la máquina implementada en la sala, incluida la dirección IP y el temporizador de expiración, junto con los botones para administrar la máquina. Recuerde "Terminar" una máquina una vez que haya terminado con la sala. Puede encontrar más información sobre esto en la sala de [Tutoriales](https://tryhackme.com/r/room/tutorial).

Por ahora, presione "Iniciar máquina" donde podrá interactuar con su propia máquina Linux dentro de su navegador mientras sigue esta sala.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Ejecucion-Sala.png">

### Responda las preguntas a continuación
1. ¡He implementado mi primera máquina Linux!

## Ejecutar los primeros comandos
Como ya hemos comentado, uno de los puntos fuertes de los sistemas operativos como Ubuntu es su ligereza. Por supuesto, esto no está exento de desventajas, como por ejemplo que, a menudo, no existe una interfaz gráfica de usuario (GUI) o lo que también se conoce como entorno de escritorio que podamos utilizar para interactuar con la máquina (a menos que esté instalada). Una gran parte de la interacción con estos sistemas consiste en utilizar la **"Terminal"**.

La `Terminal` se basa exclusivamente en texto y, al principio, resulta intimidante. Sin embargo, si analizamos algunos de los comandos, después de un tiempo, ¡rápidamente te familiarizarás con el uso de la terminal!

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Terminal.png">

Necesitamos poder realizar funciones básicas como navegar hasta los archivos, mostrar su contenido y crear archivos. Los comandos para hacerlo se explican por sí solos (una vez que sepas qué son, por supuesto ...)

Comencemos con dos de los primeros comandos que he desglosado en la siguiente tabla:

<table align="center">
    <tr>
        <th>Comando</th>
        <th>Descripción</th>
    </tr>
    <tr>
        <td>echo</td>
        <td>Imprime cualquier texto que le proporcionemos.</td>
    </tr>
    <tr>
        <td>whoami</td>
        <td>¡Descubre con qué usuario estamos conectados actualmente!</td>
    </tr>
</table>

Vea los fragmentos a continuación para ver un ejemplo de cómo se utiliza cada comando ...

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/echo.png">

¡Pruebe esto en su máquina Linux ahora!

### Responda las preguntas a continuación
1. Si quisiéramos mostrar el texto **"TryHackMe"**, ¿cuál sería nuestro comando? `echo TryHackMe`
2. ¿Cuál es el nombre de usuario con el que inició sesión en su máquina Linux implementada? `tryhackme`


## Interacción con el Sistema de Archivos
Hasta ahora, solo hemos cubierto los comandos **"echo"** y **"whoami"**. No son tan útiles si tenemos en cuenta las cosas que debemos hacer, como navegar por el sistema de archivos, leer y escribir en él.

En esta tarea, aprenderemos los comandos para poder hacer precisamente eso. Al igual que en la tarea anterior, mostraré los comandos en la tabla del siguiente encabezado y mostraré ejemplos de su uso.

Como se mencionó anteriormente, poder navegar por la máquina en la que está conectado sin depender de un entorno de escritorio es bastante importante. Después de todo, ¿qué sentido tiene iniciar sesión si no podemos ir a ninguna parte?

<table align="center">
    <tr>
        <th>Comando</th>
        <th>Nombre Completo</th>
    </tr>
    <tr>
        <td>ls</td>
        <td>Listado (listing)</td>
    </tr>
    <tr>
        <td>cd</td>
        <td>Cambiar Directorio (change directory)</td>
    </tr>
    <tr>
        <td>cat</td>
        <td>Concatenar (concatenate)</td>
    </tr>
    <tr>
        <td>pwd</td>
        <td>Directorio de Trabajo de Impresión (print working directory)</td>
    </tr>
</table>

### Listado de Archivos en nuestro Directorio Actual (ls)
Antes de poder hacer algo como averiguar el contenido de cualquier archivo o carpeta, necesitamos saber qué existe en primer lugar. Esto se puede hacer usando el comando `ls` (abreviatura de listing).

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/ls.png">

En la captura de pantalla anterior, podemos ver que hay los siguientes directorios/carpetas:

- Archivos Importantes
- Mis documentos
- Notas
- Imagenes

¡Genial! Probablemente puedas adivinar qué esperar que contenga una carpeta según su nombre.

`Consejo Profesional`: Puedes enumerar el contenido de un directorio sin tener que navegar hasta él usando ***(ls)*** y el nombre del directorio. Es decir, ***(ls imagenes)***

### Cambiar Nuestro Directorio Actual (cd)
Ahora que sabemos qué carpetas existen, necesitamos usar el comando `cd` abreviatura de cambiar directorio, para cambiar a ese directorio. Digamos que quiero abrir el directorio **"Pictures"** (Imágenes), usaría `cd Pictures`. Nuevamente, queremos averiguar el contenido de este directorio **"Pictures"** y para ello usaríamos `ls Pictures` nuevamente:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/cd.png">

¡En este caso, parece que hay 4 fotos de perros!

### Mostrar el contenido de un archivo (cat)
Si bien conocer la existencia de archivos es genial, no es tan útil a menos que podamos ver su contenido. Más adelante, analizaremos algunas de las herramientas disponibles que nos permiten transferir archivos de una máquina a otra. Pero por ahora, vamos a hablar simplemente sobre cómo ver el contenido de archivos de texto mediante un comando llamado `cat`.

"Cat" es la abreviatura de concatenación y es una forma fantástica de mostrar el contenido de archivos (¡no solo archivos de texto!).

En la captura de pantalla a continuación, puede ver como combiné el uso de "ls" para enumerar los archivos dentro de un directorio llamado "Documentos":

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/cat.png">

Hemos aplicado algunos conocimientos adquiridos anteriormente en esta tarea para hacer lo siguiente:

- Usamos `ls` para informarnos qué archivos están disponibles en la carpeta "Documentos" de esta máquina. en este caso, se llama (todo.txt)
- Luego usamos `cat todo.txt` para concatenar/mostrar el contenido de este archivo, donde el contenido es: "¡Aquí hay algo importante que debo hacer más tarde!".

**Consejo Profesional**: puedes usar *cat* para mostrar el contenido de un archivo dentro de directorios sin tener que navegar hasta él usando cat y el nombre del directorio. Es decir, `cat /home/ubuntu/Documents/todo.txt`.

A veces, cosas como nombres de usuario, contraseñas (sí, en serio...), indicadores o ajustes de configuración se almacenan dentro de archivos donde se puede usar "cat" para recuperarlos.

### Cómo averiguar la ruta completa a nuestro directorio de trabajo actual (pwd)
A medida que avanza en la navegación de su máquina Linux, notará que el nombre del directorio en el que está trabajando actualmente aparecerá en su terminal.

Es fácil perder la pista de dónde estamos exactamente en el sistema de archivos, por eso quiero presentar `pwd`. Esto significa imprimir directorio de trabajo.

USando la máquina de ejemplo anterior, actualmente estamos en la carpeta "Documents", pero ¿dónde está exactamente en el sistema de archivos de la máquina Linux? Podemos averiguarlo usando este comando `pwd` como en la captura de pantalla siguiente:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/pwd.png">

Analicemos esto:

1. Ya sabemos que estamos en "Documents" gracias a nuestra terminal, pero en este momento no tenemos idea de dónde está almacenado "Documents" para que podamos volver a él fácilmente en el futuro.
2. He utilizado el comando `pwd` (imprimir directorio de trabajo) para encontrar la lruta completa del archivo de la carpeta "Documents".
3. Linux nos informa amablemente que este directorio "Documents" está almacenado en `/home/ubuntu/Documents` en la máquina. ¡Es genial saberlo!
4. Ahora, en el futuro, si no encontramos en una ubicación diferente, podemos simplemente utilizar `cd /home/ubuntu/Documents` para cambiar nuestro directorio de trabajo a este direcctorio "Documents".

### Responda las preguntas a continuación
1. En la máquina Linux que implementa, ¿cuántas carpetas hay? `4`
2. ¿Qué directorio contiene un archivo? `folder4`
3. ¿Cuál es el contenido de este archivo? `Hello World`
4. Utilice el comando cd para navegar a este archivo y averiguar el nuevo directorio de trabajo actual. ¿Cuál es el camino? `/home/tryhackme/folder4`

## Búsqueda de Archivos
Aunque no lo parezca hasta ahora, una de las características positivas de Linux es lo eficiente que puede ser con él. Dicho esto, solo puede ser tan eficiente como lo conozca, por supuesto. A medida que interactúe con sistemas operativos como Ubuntu con el tiempo, los comandos esenciales como los que ya cubrimos comenzarán a convertirse en memoria muscular.

Una forma fantástica de mostrar cuán eficiente puede ser con sistemas como este es usar un conjunto de comandos para buscar rápidamente archivos en todo el sistema al que nuestro usuario tiene acceso. No es necesario usar constantemente `cd`y `ls` para averiguar qué está en cada lugar. En cambio, podemos usar comandos como `find` para automatizar cosas como esta para nosotros.

Aquí es donde Linux comienza a volverse un poco más intimidante de abordar, pero lo desglosaremos y lo haremos más fácil.

### Uso de Find
El comando `find` es fantástico en el sentido de que se puede usar de manera muy simple o bastante compleja según lo que desee hacer exactamente. Sin embargo, centrémonos primero en los aspectos básicos.

Observe el fragmento que aparece a continuación; podemos ver una lista de directorios disponibles:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/find.png">

1. Desktop
2. Documents
3. Images
4. Folder1

Por supuesto, los directorios pueden contener incluso más directorios dentro de sí mismos. Se conviente en un dolor de cabeza cuando tenemos que buscar en cada uno de ellos solo para intentar buscar archivos específicos. ¡Podemos usar `find` para que haga exactamente esto por nosotros!

Comencemos de manera simple y supongamos que ya sabemos el nombre del archivo que estamos bsucando, ¡pero no podemos recoradr dónde está exactamente! En este caso, estamos buscando "contraseñas.txt"

Si recordamos el nombre del archivo,, podemos simplemente usar `find -name contraseñas.txt` donde el comando buscará en cada carpeta en nuestro directorio actual ese archivo específico de la siguiente manera:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/password.png">

`Find` ha logrado encontrar el archivo; resulta que se encuentra en `folder1/contraseñas.txt`; genial. Pero digamos que no sabemos el nombre del arcxhivo o queremos buscar todos los archivos que tienen una extensión como `.txt`. ¡Find también nos permite hacer eso!

Podemos simplemente usar lo que se conoce como `comodín (*)` para buscar cualquier cosa que tenga ".txt" al final. En nuestro caso, queremos encontrar todos los archivos (.txt) que se encuentran en nuestro directorio actual. Construiremos un comando como `find -name *.txt`. Donde "find" ha podido encontrar todos los archivos .txt y luego nos ha dado la ubicación de cada uno:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/txt.png">

Find ha logrado encontrar:
1. `passwords.txt` ubicado dentro de (folder1)
2. `todo.txt` ubicado dentro de (Documents)

¡Eso no fue tan defícil, eh!

### Uso de Grep
Otra gran utilidad que vale la pena aprender es el uso de **grep**. El comando `grep` nos permite buscar en el contenido de los archivos valores específicos que estamos buscando.

Tomemos como ejemplo el regisstro de acceso de un servidor web. En este caso, el archivo (access.log) de un servidor web tiene 244 entradas.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Grep.png">

Usar un comando como `cat` no será muy útil en este caso. Digamos, por ejemplo, que queremos buscar en este archivo de registro para ver las cosas que visitó un determinado usuario o dirección IP. Buscar en 244 entradas no es tan eficiente teniendo en cuenta que queremos encontrar un valor específico.

Podemos usar `grep` para buscar en todo el contenido de este archivo cualquier entrada del valor que estamos buscando. Siguiendo con el ejemplo del registro de acceso de un servidor web, queremos ver todo lo que ha visitado la dirección IP (81.143.211.90) "tenga en cuenta que esto es ficticio".

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Access.png">

`Grep` ha buscado en este archivo y nos ha mostrado todas las entradas que le hemos proporcionado y que están contenidas en este archivo de registro para la IP.

### Responda las preguntas a continuación
1. Utilice grep en "access.log" para encontrar la bandera que tiene el prefijo "THM". ¿Cuál es la bandera? `THM{ACCESS}`
2. ¡Y todavía no hee encontrado lo que estoy buscando!

## Introducción a los Operadores de Shell
Los operadores de Linux son una forma fantástica de mejorar sus conocimientos sobre cómo trabajar con Linux. Hay algunos operadores importantes que vale la pena mencionar. Cubriremos los conceptos básicos y los desglosaremos en fragmentos pequeños.

En una descripción general, mostraré los siguientes operadores:

<table align="center">
    <tr>
        <th>Simbolo/Operador</th>
        <th>Descripción</th>
    </tr>
    <tr>
        <td>&</td>
        <td>Este operador le permite ejecutar comandos en segundo plano en su terminal.</td>
    </tr>
    <tr>
        <td>&&</td>
        <td>Este operador le permite combinar varios comandos een una línea de su terminal.</td>
    </tr>
    <tr>
        <td>></td>
        <td>Este operador es un redirector, lo que significa que podemos tomar la salida de un comando (como usarr cat para generar un archhivo) y dirigirla a otro lugar.</td>
    </tr>
    <tr>
        <td>>></td>
        <td>Este operador realiza la misma función del operador (>) pero agrega la salida en lugar de reemplazarla (lo que significa que no se sobrescribe nada).</td>
    </tr>
</table>

Analicemos esto con un poco más de detalle.

### Operador "&"
Este operador nos permite ejecutar comandos en segundo plano. .Por ejemplo, digamos que queremos copiar un archivo grande. Obviamente, esto llevará bastante tiempo y no podremos hacer nada más hasta que el archivo se ccopie correctamente.

El operador de Shell `&` nos permite ejecutar un comando y que se ejecute en segundo plano (como esta copia de archivo), lo que nos permite hacer otras cosas.

### Operador "&&"
Este operador de Shell es un poco engañoso en el sentido de lo familiar que es con su compañero "&". A diferencia del operador `&`, podemos usar `&&` para hacer una lista de comandos para ejecutar, por ejemplo, `command1 && command2`. Sin embaargo, vaale la pena señalar que `command2` solo se ejecutará si `command1` tuvo éxito.

### Operador ">"
Este operador es lo que se conoce como un redirector de salida. Lo que esto significa esencialmente es que tomamos la salidda de un comando que ejecutamos y enviamos esa salida a otro lugar.

Un buen ejemplo de esto es redirigir la salida del comando `echo` que aprendimos en la "tarea 4". Por supuesto, ejecutar algo como `echo howdy` devolverá "howdy" a nuestra terminal, lo cual no es muy útil. Lo que podemos hacer es redirigir "howdy" a algo como un nuevo archivo.

Digamos que queremos crear un archivo llamado "welcome" con el mensaje "hey". Podemos ejecutar `echo hey > welcome` donde queremos que se cree el archivo con el contenido "hey" de la siguiente manera:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Operador-Simple.png">

Nota: Si el archivo, es decir, "welcome", ya existe, se sobrescribirá el contenido.

### Operador ">>"
Este operador también es un redireccionador de salida como el operador anterior `>` que analizamos. Sin embargo, lo que hace que este operador sea diferente es que, en lugar de sobrescribir cualquier contenido dentro de un archivo, por ejemplo, simplemente coloca la salida al final.

Siguiendo con nuestro ejemplo anterior donde tenemos el archivo "welcome" que tiene el contenido de "hey". Si usáramos `echo` para agregar "hola" al archivo usando el operador `>`, el archivo ahora solo tendrá "hola" y no "hey".

El operador `>>` permite agregar la salida al final del archivo, en lugar de reemplazar el contenido de esta manera:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-Parte1/Operador-doble.png">

### Responda las preguntas a continuación
1. Si quisiéramos ejeccutar un comando en segundo plano, ¿qué operador usaríamos? `&`
2. Si quisiera reemplazar el contenido de un archivo llamado "contraseñas" con la palabra "password123", ¿cuál sería mi comando? `echo password123 > passwords`
3. Ahora, si quisiera agregar "tryhackme" a este archivo llamado "contraseñas" pero también conservar "passwords123", ¿cuál sería mi comando? `echo tryhackme >> passwords`
4. Ahora, use la máquina Linux implementada para poner esto en práctica.

## Conclusiones y Resúmenes
¡Buen trabajo al llegar a esta etapa! Hemos cubierto bastante para sus primeras interacciones con Linux. Sin eembargo, estas son las funciones más esenciales que usará cada vez qye interactúe con una máquina Linux.

Espero que esta sala no haya sido demasiado abrumadora para que pueda comenzar. Como mencioné anteriormente, se familiarizará con estas cosas muy rápidamentedebido a la frecuencia con la que las usará.

Para resumir rápidamente, hemos cubierto lo siguiente:

- Entender por qué Linux es tan común hoy en día
- Interactuar con su primera máquina Linux.
- Eejecutar algunos de los comandos más fundamentales
- Recibir una introducción sobre cómo navegar por el sistema de archivos y cómo podemos usar los comandos como "find" y "grep" para hacer que la búsqueda de datos sea aún más eficiente.
- Mejore sus comandos aprendiendo sobre algunos de los operadores de shell importantes.

Tómese un tiempo para jugar un poco en esta sala. Cuando te sientas un poco más cómodo, pasa a la [segunda parte]() de Fundamentos de Linux.

### Responde las preguntas a continuación
- ¡Intentaré un poco!

## Fundamentos de Linux, Parte 2
¡Visita la segunda parte de la serie Fundamentos de Linux [aquí](https://tryhackme.com/jr/linuxfundamentalspart2)!

### Responde las preguntas a continuación
1. Termina la máquina implementada en esta sala de la tarea 3
2. ¡Únete a la segunda parte de Fundamentos de Linux!