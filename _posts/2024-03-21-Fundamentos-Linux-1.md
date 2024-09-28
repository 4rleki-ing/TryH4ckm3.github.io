---
layout: single
title: Fundamentos de Linux Parte 1
excerpt: "."
date: 2024-06-30
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Linux.png
  teaser_home_page: true
categories:
  - Lectura
tags:
  - Linux
---

![Portada](https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Portada.jpg)

Bienvenidos a la primera parte de la serie de salas `Fundamentos de Linux`. Probablemente esté usando una máquina *Windows* o *Mac*, ambas son diferentes en diseño visual y en su funcionamiento. Al igual que Windows, iOS y MacOS, **Linux** es solo otro sistema operativo y uno de los más populares del mundo que impulsa autos inteligentes, dispositivos Android, supercomputadoras, electrodomésticos, servidores empresariales y más.

Cubriremos parte de la historia detrás de Linux y, finalmente, comenzaremos su viaje para convertirse en un experto en Linux. En esta sala:

- Ejecutarán sus primeros comandos en una máquina Linux interactiva en su navegador.
- Le enseñarán algunos comandos esenciales que se usan para interactuar con el sistema de archivos.
- Le demostrarán cómo puede buscar archivos y presentar operadores de shell.

## ¿Donde se utiliza Linux?
Es justo decir que `Linux` es mucho más intimidante de abordar que los sistemas operativos (OS) como Windows. Ambas variantes tienen sus propias *ventajas* y *desventajas*. Por ejemplo, Linux es considerablemente más liviano y te sorprendería saber que es muy probable que hayas usado Linux de una forma u otra todos los días. Linux impulsa cosas como:

- Sitios web que visitas.
- Paneles de control/entretenimiento de automóviles
- Sistemas de punto de venta (PoS) como cajas registradoras y cajas registradoras en tiendas.
- Infraestructuras críticas como controladores de semáforos o sensores industriales.

## Variedades de Linux
El nombre `Linux` es en realidad un término general para varios SO que se basan en `UNIX` (otro sistema operativo). Gracias a que Linux es de código abierto, las variantes de Linux vienen en todas las formas y tamaños, las más adecuadas para el uso que se le da al sistema.

Por ejemplo, `Ubuntu` y `Debian` son algunas de las distribuciones más comunes de Linux porque son muy extensibles. Es decir, se pueden ejecutar *Ubuntu* como un servidor (como sitios web y aplicaciones web) o como un escritorio completo.

```text
Nota:
   Ubuntu Server puede ejecutarse en sistemas con solo 512 MB de RAM.
```

De manera similar a cómo existen diferentes versiones de Windows (7, 8 y 10), existen muchas versiones (distribuciones) diferentes de Linux.

### Responda las preguntas a continuación
- (Investigación): ¿En qué año se lanzó por primera vez el sistema operativo Linux? `1991`

## Interacción con su primera máquina Linux
```text
Nota:
   Esta sala tiene una máquina Linux Ubuntu con la que puede interactuar desde su navegador mientras 
   sigue el material de esta sala.
```

Para comenzar la máquina de la sala, simplemente localice el botón verde `Iniciar máquina` en la parte superior derecha de la tarea y presionelo.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Iniciar-maquina.png">
</center>

Una vez desplegada, aparecerá una tarjeta en la parte superior de la sala:

![Máquina Desplegada](https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Maquina-Desplegada.png)

Contiene toda la información de la máquina implementada en la sala, incluida la `dirección IP` y el `temporizador de expiración`, junto con los botones para administrar la máquina. Recuerde `Terminar` la máquina una vez que haya terminado con la sala. Puede encontrar más información sobre esto en la sala [tutoriales](https://tryhackme.com/r/room/tutorial).

Por ahora, presione *Iniciar Máquina* donde podrá interactuar con su propia máquina Linux dentro de su navegador mientras sigue esta sala:

![Interactuar con la máquina](https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Interactuar.png)

## Ejecutar los primeros comandos
Como ya hemos comentado, uno de los puntos fuertes de los sistemas operativos como *Ubuntu* es su ligereza. Por supuesto, esto no está exento de desventajas, como por ejemplo que, a menudo, no existe una ***interfaz gráfica de usuario (GUI)*** o lo que también se conoce como entorno de escritorio que podamos utilizar para interactuar con la máquina (a menos de que esté instalada). Una gran parte de la interacción con estos sistemas consiste en utilizar la **Terminal**.

La `Terminal` se basa exclusivamente en texto y, al principio, resulta intimidante. Sin embargo, si analizamos algunos de los comandos, después de un tiempo, ¡rápidamente te familiarizarás con el uso de la terminal!

  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Comandos.png" width="50%"> 

Necesitamos poder realizar funciones básicas como navegar hasta los archivos, mostrar su contenido y crear archivos. Los comandos para hacerlo se explican por sí solos (una vez que sepas qué son, por supuesto ...)

Comencemos con 2 de los primeros comandos que he desglosado en la siguiente tabla:

| Comando | Descripción                                                 |
|---------|-------------------------------------------------------------|
| echo    | Muestra cualquier texto que le proporcionemos               |
| whoami  | ¡Descubre con qué usuario estamos conectados actualmente!   |

Vea los fragmentos a continuación para ver un ejemplo de cómo se utiliza cada comando:

- `echo`
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/echo.png" width="50%"> 

- `whoami`
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/whoami.png" width="45%"> 

### Responda las preguntas a continuación
- Si quisiéramos mostrar el texto "TryHackMe", ¿cuál sería nuestro comando? `echo TryHackMe`
- ¿Cuál es el nombre de usuario con el que inició sesión en su máquina Linux implementada? `tryhackme`

## Interacción con el sistema de archivos
Hasta ahora, solo hemos cubierto los comandos `echo` y `whoami`. No son tan útiles si tenemos en cuenta las cosas que tenemos que hacer, como navegar por el sistema de archivos, leer y escribir en él.

En esta tarea, aprenderemos los comandos para poder hacer precisamente eso. Al igual que en la tarea anterior, se mostrará los comandos en la tabla del siguiente encabezado y se mostrará ejemplos de su uso.

### Interacción con el sistema de archivos
Como se mencionó anteriormente, poder navegar por la máquina en la que ha iniciado sesión sin depender de un entorno de escritorio es bastante importante. Después de todo, *¿qué sentido tiene iniciar sesión si no podemos ir a ningún lado?*

| Comando | Nombre Completo                                              |
|---------|--------------------------------------------------------------|
|   ls    | Listado (listing)                                            |
|   cd    | Cambiar directorio (change directory)                        |
|   cat   | Concatenar (concatenate)                                     |
|   pwd   | Directorio de Trabajo de Impresión (print working directory) |

### Listado de archivos (ls)
Antes de poder hacer algo como averiguar el contenido de cualquier archivo o carpeta, necesitamos saber qué existe en primer lugar. Esto se puede hacer usando el comando `ls`.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/ls.png" width="55%"> 
</center>

En la captura de pantalla anterior, podemos ver que hay los siguientes directorios (carpetas):

- Archivos importantes (Important Files)
- Mis documentos (My Documents)
- Notas (Notes)
- Imagenes (Pictures)

¡Genial! Probablemente puedas adivinar qué información o archivos esperar que contenga una carpeta según su nombre.

```text
Consejo:
  Puedes enumerar el contenido de un directorio sin tener que navegar hasta él usando ls y el nombre del directorio.
  
  Por ejemplo: ls Pictures
```

### Cambiar directorio (cd)
Ahora que sabemos qué carpetas existen, necesitamos usar el comando `cd` para cambiar a ese directorio. Digamos que queremos abrir el directorio *Pictures*, usaría `cd Pictures`. Nuevamente, queremos averiguar el contenido de este directorio *(Pictures)* y para ello usaríamos `ls` nuevamente:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/cd.png" width="70%"> 
</center>

¡En este caso, parece que hay 4 fotos de perros!

### Mostrar contenido de un archivo (cat)
Si bien conocer la existencia de archivos es genial, no es tan útil a menos que podamos ver su contenido. Más adelante, analizaremos algunas de las herramientas disponibles que nos permiten transferir archivos de una máquina a otra. Pero por ahora, vamos a hablar simplemente sobre cómo ver el contenido de archivos de texto mediante el comando **cat**.

`cat` es una forma fantástica de mostrar el contenido de archivos (¡no solo archivos de texto!). En la captura de pantalla a continuación, puede ver cómo se combinó el uso de `ls` para enumerar los archivos dentro de un directorio llamado *"Documents"*.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/cat.png" width="50%"> 
</center>

Hemos aplicado algunos conocimientos adquiridos anteriormente en esta tarea para hacer lo siguiente:

1. Utilizamos `ls` para informarnos qué archivos están disponibles en la carpeta *"Documents"* de esta máquina. En este caso, se llama *"todo.txt"*.
2. Luego, hemos utilizado `cat todo.txt` para concatenar (mostrar) el contenido del archivo *"todo.txt"*, donde el contenido es *"¡Aquí hay algo importante que debo hacer más tarde!"*.

```text
Consejo:
  Puede utilizar "cat" para mostrar el contenido de un archivo dentro de directorios sin tener que navegar hasta él 
    utilizando cat y el nombre del directorio.

  Por ejemplo: cat /home/ubuntu/Documents/todo.txt
```

A veces, elementos como nombres de usuario, contraseñas, indicadores o ajustes de configuración se almacenan dentro de archivos donde se puede utilizar `cat` para recuperarlos.

### Averiguar la ruta completa de un directorio (pwd)
A medida que avanza en la navegación de su máquina Linux, notará que el nombre del directorio en el que está trabajando actualmente aparecerá en su terminal. Es fácil perder la pista de dónde se encuentra exactamente en el sistema de archivos, para solucionar este problema existe el comando `pwd`. Esto significa *"imprimir directorio de trabajo"*.

Usando la máquina del ejemplo anterior, actualmente se encuentra en la carpeta *"Documents"*, pero ¿dónde está exactamente en el sistema de archivos de la máquina Linux?; Podemos averiguarlo usando el comando `pwd` como aparecerá en la siguiente captura de pantalla:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/pwd.png" width="50%"> 
</center>

Analicemos esto:
1. Ya sabemos que estamos en *"Documents"* gracias a nuestra terminal, pero en este momento no tenemos idea de donde está almacenado *"Documents"* para que podamos volver a él fácilmente en el futuro.
2. Se ha utilizado el comando `pwd` para encontrar la ruta completa del archivo de esta carpeta.
3. Linux nos informa que el directorio *"Documents"* está almacenado en `/home/ubuntu/Documents` en la máquina. ¡Es bueno saberlo!
4. Ahora, en el futuro, si nos encontramos en una ubicación diferente, podemos simplemente utilizar `cd /home/ubuntu/Documents` para cambiar nuestro directorio de trabajo al directorio *"Documents"*.

### Responda las preguntas a continuación
- En la máquina Linux que implementa, ¿cuántas carpetas hay? `4`
- ¿Qué directorio contiene un archivo? `folder 4`
- ¿Cuál es el contenido de este archivo? `Hello World`
- Use el comando **cd** para navegar hasta este archivo y averiguar el nuevo directorio de trabajo actual. ¿Cuál es la ruta? `/home/tryhackme/folder4`

## Búsqueda de archivos
Aunque no lo parezca hasta ahora, una de las características positivas de Linux es lo eficiente que puede ser con él. Dicho esto, solo puede ser tan eficiente como lo conozca, por supuesto. A medida que interactúe con sistemas operativos como *Ubuntu* con el tiempo, los comandos esenciales como los que ya se cubrieron comenzarán a convertirse en *memoria muscular*.

Una forma fantástica de mostrar cuán eficiente puede ser con sistemas como este es usar un conjunto de comandos para buscar rápidamente archivos en todo el sistema al que nuestro usuario tiene acceso. No es necesario usar constantemente `cd` y `ls` para averiguar qué está en cada lugar. En cambio, podemos usar comandos como `find` para automatizar cosas como esta para nosotros.

Aquí es donde Linux comienza a volverse un poco más *intimidante* de abordar, pero lo desglosaremos y lo haremos más fácil.

### Uso de find
El comando `find` es fantástico en el sentido de que se puede usar de manera muy simple o *bastante compleja* según lo que desee hacer exactamente. Sin embargo, centrémonos primero en los aspectos básicos.

Observe el fragmento que aparece a continuación; podemos ver una lista de directorios disponibles:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/find.png" width="60%"> 
</center>

1. Escritorio (Desktop)
2. Documentos (Documents)
3. Imagenes (Pictures)
4. Carpeta 1 (folder 1)

Ahora bien, los directorios pueden contener incluso más directorios dentro de sí mismos. Se convierte en un dolor de cabeza cuando tenemos que buscar en cada uno de ellos solo para intentar encontrar archivos específicos. ¡Podemos usar `find` para que haga exactamente esto por nosotros!

Comencemos de manera sencilla y supongamos que ya sabemos el nombre del archivo que estamos buscando, ¡pero no podemos recordar dónde está exactamente! En este caso, estamos buscando `passwords.txt`.

Si recordamos el nombre del archivo, podemos simplemente usar `find -name passwords.txt` donde el comando buscará en cada carpeta de nuestro directorio actual ese archivo específico de la siguiente manera:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/find-passwords.png" width="55%"> 
</center>

`find` ha logrado encontrar el archivo, resulta que se encuentra en `folder1/passwords.txt`, genial. Pero digamos que no sabemos el nombre del archivo o que queremos buscar todos los archivos que tengan una extensión como `.txt`; ¡*find* también nos permite hacer eso!

Podemos simplemente usar lo que se conoce como `comodín (*)` para buscar cualquier cosa que tenga *.txt* al final.En nuestro caso, queremos encontrar todos los archivos *.txt* que se encuentran en nuestro directorio actual.

Construiremos el comando `find -name *.txt`, donde *"find"* ha podido encontrar todos los archivos .txt y luego nos ha dado la ubicación de cada uno:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/find-all.png" width="50%"> 
</center>

find a logrado encontrar:
- `passwords.txt` ubicado dentro de *"folder1"*
- `todo.txt` ubicado dentro de *"Documents"*

### Uso de Grep
Otra gran utilidad que vale la pena aprender es el uso de `grep`. El comando *grep* nos permite buscar en el contenido de los archivos valores específicos que estamos buscando. Tomemos como ejemplo el registro de acceso de un servidor web. En este caso, el archivo `access.log` de un servidor web tiene 244 entradas.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/grep.png" width="50%"> 
</center>

Usar el comando `cat`no funcionará como esperamos en esta situación. Digamos, por ejemplo, si queremos buscar en este archivo de registro para ver los sitios que visitó una determinada *dirección de usuario/IP*. Mirar a través de 244 entradas no es tan eficiente teniendo en cuenta que queremos encontrar un valor específico.

Podemos usar `grep` para buscar dentro del contenido completo de este archivo cualquier entrada del valor que estamos buscando. Con el ejemplo del registro de acceso de un servidor web, queremos ver todo lo que ha visitado la dirección IP `81.143.211.90`.

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/grep-access.png" width="50%"> 
</center>

`Grep` ha buscado a través de este archivo y nos ha mostrado cualquier entrada que coincida con los valores que hemos proporcionado y que está contenido en este archivo de registro para la IP.

### Responda las preguntas a continuación
- Use *"grep"* en **"Access.log"** para encontrar la bandera que tiene un prefijo de *"THM"*. ¿Cuál es el contenido de la bandera? `THM{ACCESS}`

## Introducción a los operadores Shell
Los operadores de Linux son una forma fantástica de alimentar su conocimiento de trabajar con Linux. Hay algunos operadores importantes que vale la pena señalar. Cubriremos los conceptos básicos y los desglosaremos en consecuencia en trozos del tamaño de un bocado.

En una visión general, voy a mostrar los siguientes operadores:

| Símbolo/Operador | Descripción                                                                                          |
|------------------|------------------------------------------------------------------------------------------------------|
|        &         | Este operador le permite ejecutar comandos en el fondo de su terminal                                |
|        &&        | Este operador le permite combinar múltiples comandos en una línea de su terminal.                    |
|        >         | Este operador es un redirector, lo que significa que podemos tomar la salida de un comando (como usar "cat" para emitir un archivo) y dirigirlo en otro lugar. |
|        >>        | Este operador hace la misma función del operador ">" pero agrega la salida en lugar de reemplazar (lo que significa que no se sobrescribe nada). |

### Operador "&"
Este operador nos permite ejecutar comandos en segundo plano. Por ejemplo, supongamos que queremos copiar un archivo grande. Obviamente, esto llevará bastante tiempo y nos dejará incapaz de hacer nada más hasta que el archivo se copie con éxito.

¡El operador `&` nos permite ejecutar un comando y hacer que se ejecute en segundo plano (como esta copia del archivo), lo que nos permite hacer otras cosas!

### Operador "&&"
Este operador es un poco engañoso en el sentido de cuán familiar es para su compañero `&`. A diferencia del operador *"&"*, podemos usar *"&&"* para hacer una lista de comandos para ejecutar; por ejemplo, `Command1 && Command2`. Sin embargo, vale la pena señalar que *Command2* solo se ejecutará si *Command1* fue exitoso.

### Operador ">"
Este operador es lo que se conoce como un redireccionador de salida. Básicamente, esto significa que tomamos la salida de un comando que ejecutamos y enviamos esa salida a otro lugar. Un gran ejemplo de esto es redirigir la salida del comando `echo` que aprendimos en la *tarea 4*. Por supuesto, ejecutar algo como `echo howdy` devolverá *"howdy"* a nuestra terminal, lo que no es muy útil. Lo que podemos hacer en cambio es redirigir *"howdy"* a algo como un nuevo archivo.

Digamos que queremos crear un archivo llamado *"welcome"* con el mensaje *"hey"*. Podemos ejecutar `eccho hey > welcome` donde queremos que see cree el archivo con el contenido *"hey"* de la siguiente manera:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/echo-1.png" width="50%"> 
</center>

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/cat-welcome.png" width="50%"> 
</center>

```text
Nota:
  Si el archivo "welcome" ya existe, el contenido se sobrescribirá.
```

### Operador ">>"
Este operador también es un redireccionador de salida como el operador anterior *">"* que analizamos. Sin embargo, lo que hace que este operador sea diferente es que en lugar de sobrescribir cualquier contenido dentro de un archivo, por ejemplo, simplemente coloca la salida al final.

Siguiendo con nuestro ejemplo anterior donde tenemos el archivo *"welcome"* que tiene el contenido de *"hey"*. Si usáramos **echo** para agregar *"hello"* al archivo usando el operador `>`, el archivo ahora solo tendrá *"hello"* y no *"hey"*.

El operador `>>` permite agregar la salida al final del archivo, en lugar de reemplazar el contenido de la siguiente manera:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/echo-2.png" width="50%"> 
</center>

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/cat-welcome-2.png" width="50%"> 
</center>

### Responda las preguntas a continuación
- Si quisiéramos ejecutar un comando en segundo plano, ¿Qué operador usaríamos? `&`
- Si quisiera reemplazar el contenido de un archivo llamado *"passwords"* con la palabra *"password123"*, ¿Cuál sería el comando? `echo password123 > passwords`
- Ahora bien, si quisiera agregar *"tryhackme"* a este archivo llamado *"passwords"* pero también conservar *"password123"*, ¿Cuál sería el comando' `echo tryhackme >> passwords`

## Conclusiones
¡Buen trabajo al llegar a esta etapa! Hemos cubierto bastante para sus primeras interacciones con Linux. Sin embargo, estas son las funciones más esenciales que usará cada vez que interactúe con una máquina Linux.

Espero que esta sala no haya sido demasiado abrumadora para que pueda comenzar. Como mencioné anteriormente, se familiarizará con estas cosas muy rápidamente debido a la frecuencia con la que las usará.

Para resumir rápidamente, hemos cubierto lo siguiente:

- Comprender por qué Linux es tan común hoy en día.
- ¡Interactuar con su primera máquina Linux!
- Ejecutar algunos de los comandos más fundamentales.
- Recibir una introducción sobre cómo navegar por el sistema de archivos y cómo podemos usar comandos como *find* y *grep* para hacer que la búsqueda de datos sea aún más eficiente.
- Mejore sus comandos aprendiendo sobre algunos de los operadores de shell importantes.

Tómese un tiempo para jugar un poco en esta sala. Cuando se sienta un poco más cómodo, avance a la `Parte 2 de Fundamentos de Linux`.