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

<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Portada.jpg">

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

<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Iniciar-maquina.png">

Una vez desplegada, aparecerá una tarjeta en la parte superior de la sala:

<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Maquina-Desplegada.png">

Contiene toda la información de la máquina implementada en la sala, incluida la `dirección IP` y el `temporizador de expiración`, junto con los botones para administrar la máquina. Recuerde `Terminar` la máquina una vez que haya terminado con la sala. Puede encontrar más información sobre esto en la sala [tutoriales](https://tryhackme.com/r/room/tutorial).

Por ahora, presione *Iniciar Máquina* donde podrá interactuar con su propia máquina Linux dentro de su navegador mientras sigue esta sala:

<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Linux-1/Interactuar.png">

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
| whoami  | ¡Descubre con qué usuario estamos conectados actualmente    |