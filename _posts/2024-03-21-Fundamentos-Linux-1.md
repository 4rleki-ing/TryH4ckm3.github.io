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

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Comandos.png" width="50%"> 
</center>

Necesitamos poder realizar funciones básicas como navegar hasta los archivos, mostrar su contenido y crear archivos. Los comandos para hacerlo se explican por sí solos (una vez que sepas qué son, por supuesto ...)

Comencemos con 2 de los primeros comandos que he desglosado en la siguiente tabla:

| Comando | Descripción                                                 |
|---------|-------------------------------------------------------------|
| echo    | Muestra cualquier texto que le proporcionemos               |
| whoami  | ¡Descubre con qué usuario estamos conectados actualmente!   |

Vea los fragmentos a continuación para ver un ejemplo de cómo se utiliza cada comando:

- `echo`
<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/echo.png" width="50%"> 
</center>

- `whoami`
<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/whoami.png" width="50%"> 
</center>

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
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/ls.png" width="50%"> 
</center>

En la captura de pantalla anterior, podemos ver que hay los siguientes directorios (carpetas):

- Archivos importantes (Important Files)
- Mis documentos (My Documents)
- Notas (Notes)
- Imagenes (Pictures)

¡Genial! Probablemente puedas adivinar qué información o archivos esperar que contenga una carpeta según su nombre.

```text
Consejo:
  Puedes enumerar el contenido de un directorio sin tener que navegar hasta él usando ls y el nombre del directorio, (por ejemplo: ls Pictures)
```

### Cambiar directorio (cd)
Ahora que sabemos qué carpetas existen, necesitamos usar el comando `cd` para cambiar a ese directorio. Digamos que queremos abrir el directorio *Pictures*, usaría `cd Pictures`. Nuevamente, queremos averiguar el contenido de este directorio *(Pictures)* y para ello usaríamos `ls` nuevamente:

<center>
  <img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/cd.png" width="50%"> 
</center>

¡En este caso, parece que hay 4 fotos de perros!

### Mostrar contenido de un archivo (cat)
