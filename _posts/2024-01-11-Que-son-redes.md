---
layout: single
title: ¿Qué son las redes?
excerpt: "Empiece a aprender los conceptos básicos de las redes informáticas en este módulo interactivo y breve."
date: 2024-08-21
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/Red.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/Portada.png">

## ¿Qué es la creación de redes?
Las redes son simplemente cosas conectadas. Por ejemplo, tu círculo de amigos: todos están conectados debido a intereses, pasatiempos, habilidades y demás cosas similares.

Las redes se pueden encontrar en todos los ámbitos de la vida:

- El sistema de transporte público de una ciudad
- Infraestructura como la red eléctrica nacional para la electricidad
- Conocer y saludar a tus vecinos
- Sistemas postales para enviar cartas y paquetes

Pero más específicamente, en informática, la creación de redes es la misma idea, solo que dispersada en dispositivos tecnológicos. Tenemos como ejemplo tu teléfono; la razón por la que lo tienes es para acceder a cosas. Veremos cómo se comunican estos dispositivos entre sí y las reglas que se desprenden de ello.

En informática, una red puede estar formada por cualquier número de dispositivos, desde 2 hasta miles de millones. Estos dispositivos incluyen todo, desde tu computadora portátil y teléfono hasta cámaras de seguridad, semáforos e incluso agricultura.

Las redes están integradas en nuestra vida cotidiana. Ya sea para recopilar datos sobre el clima, suministrar electricidad a los hogares o incluso determinar quién tiene derecho de paso en una carretera. Debido a que las redes están tan arraigadas en la actualidad, la creación de redes es un concepto esencial que se debe comprender en materia de ciberseguridad.

Tomemos como ejemplo el diagrama que aparece a continuación: Alice, Bob y Jim han formado su red. Hablaremos de esto más adelante.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/Equipo.png">

Las redes vienen en todas las formas y tamaños, algo que también abordaremos a lo largo de este modulo.

### Responda las preguntas a continuación
- ¿Cuál es el término clave para los dispositivos que están conectados entre sí? `Network`

## ¿Qué es Internet?
Ahora que hemos aprendido qué es una red y cómo se define en informática (solo dispositivos conectados), exploremos Internet.

Internet es una red gigante que consta de muchas, muchas redes pequeñas dentro de sí misma. Usando nuestro ejemplo de la tarea anterior, imaginemos ahora que Alice hizo algunos nuevos amigos llamados Zayn y Toby a quienes quiere presentarles a Bob y Jim. El problema es que Alice es la única persona que habla el mismo idioma que Zayn y Toby. ¡Así que Alice tendrá que ser la mensajera!

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/Mensajera.png">

Como Alice puede hablar ambos idiomas, pueden comunicarse entre sí a través de Alice, formando una nueva red.

La primera iteración de Internet se produjo en el marco del proyecto ARPANET a finales de los años 60. Este proyecto fue financiado por el Departamento de Defensa de los Estados Unidos y fue la primera red documentada en funcionamiento. Sin embargo, no fue hasta 1989 cuando Tim Berners-Lee inventó Internet tal como la conocemos, con la creación de la World Wide Web (WWW). No fue hasta ese momento que Internet empezó a utilizarse como repositorio para almacenar y compartir información, tal como se hace hoy.

Relacionemos la red de amigos de Alice con los dispositivos informáticos. Internet parece una versión mucho más grande de este tipo de diagrama:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/Internet.png">

Como se dijo anteriormente, Internet está formada por muchas redes pequeñas unidas entre sí. Estas redes pequeñas se denominan redes privadas, mientras que las redes que conectan estas redes pequeñas se denominan redes públicas (o Internet). Por lo tanto, para recapitular, una red puede ser de dos tipos:

- Una red privada
- Una red pública

Los dispositivos utilizan un conjunto de etiquetas para identificarse en una red, que veremos en la siguiente tarea.

### Responde las preguntas a continuación
- ¿Quién inventó la World Wide Web? `Tim Berners-Lee`

## Identificación de dispositivos en una red
Para comunicarse y mantener el orden, los dispositivos deben ser identificables y al mismo tiempo identificables en una red. ¿De qué sirve si no sabes con quién estás hablando al final del día?

Los dispositivos en una red son muy similares a los humanos en el hecho de que tenemos dos formas de ser identificados:

- Nuestro Nombre
- Nuestras huellas dactilares

Ahora podemos cambiar nuestro nombre mediante un voto en la escritura, pero no podemos cambiar nuestras huellas dactilares. Cada humano tiene un conjunto individual de huellas dactilares, lo que significa que incluso se cambia su nombre, sigue habiendo una identidad detrás de él. Los dispositivos tienen lo mismo: dos medios de idntificación, uno de los cuales es permeable. Estos son:

- Una dirección IP
- Una dirección de control de acceso al medio (MAC): piense en esto como algo similar a un número de serie.

### Direcciones IP
En pocas palabras, una dirección IP (o dirección de protocolo de Internet) se puede utilizar como una forma de identificar un host en una red durante un período de tiempo, donde esa dirección IP se puede asociar con otro dispositivo sin que cambie la dirección IP. Primero, desglosemos con presición qué es una dirección IP en el siguiente diagrama:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/Direccion-IP.png">

Una dirección IP es un conjunto de números que se dividen en cuatro octetos. El valor de cada octeto se resume en la dirección IP del dispositivo en la red. Este número se calcula mediante una técnica conocida como direccionamiento y subredes IP, pero eso es para otro día. Lo que es importante entender aquí es que las direcciones IP pueden cambiar de un dispositivo a otro, pero no pueden estar activas simultáneamente más de una vez dentro de la misma red.

Las direcciones IP siguen un conjunto de estándares conocidos como protocolos.. Estos protocolos son la columna vertebral de la red y obligan a muchos dispositivos a comunicarse en el mismo idioma, algo que veremos en otra ocasión. Sin embargo, debemos recordar que los dispositivos pueden estar tanto en una red pública como privada. Dependiendo de dónde se encuentren, determinará que tipoo de dirección IP tienen: una dirección IP pública o privada.

Una dirección pública se utiliza para identificar el dispositivo en Internet, mientras que una dirección privada se utiliza para identificar un dispositivo entre otros dispositivos. Tome la tabla y la captura de pantalla a continuación como ejemplo. Aquí tenemos dos dispositivos en una red privada:

<table align="center">
    <tr>
        <th>Nombre del Dispositivo</th>
        <th>Dirección IP</th>
        <th>Tipo de dirección IP</th>
    </tr>
    <tr>
        <td>DESKTOP-KJE57FD</td>
        <td>192.168.1.77</td>
        <td>Privada</td>
    </tr>
    <tr>
        <td>DESKTOP-KJE57FD</td>
        <td>86.157.52.21</td>
        <td>Pública</td>
    </tr>
    <tr>
        <td>CMNatic-PC</td>
        <td>192.168.1.74</td>
        <td>Privada</td>
    </tr>
    <tr>
        <td>CMNatic-PC</td>
        <td>86.157.52.21</td>
        <td>Pública</td>
    </tr>
</table>

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/MAC.png">

Estos dos dispositivos podrán utilizar sus direcciones IP privadas para comunicarse entre sí. Sin embargo, cualquier dato enviado a Internet desde cualquiera de estos dispositivos será identificado por la misma dirección IP pública. Las direcciones IP públicas las proporciona su proveedor de servicios de Internet (o ISP) a cambio de una tarifa mensual (¡su factura!).

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/IP-Publica.png">

A medida que se conectan más y más dispositivos, resulta cada vez más difícil obtener una dirección pública que no esté en uso. Por ejemplo, Cisco, un gigante en la industria en el mundo de las redes, estimó que habría aproximadamente 50 mil millones de dispositivos conectados a Internet para fines de 2021 [(Cisco, 2021)](https://www.cisco.com/c/dam/en_us/about/ac79/docs/innov/IoT_IBSG_0411FINAL.pdf). Aquí es donde aparecen las versiones de direcciones IP. Hasta ahora, solo hemos analizado una versión del esquema de direccionamiento del Protocolo de Internet conocido como IPv4, que utiliza un sistema de numeración de 2^32 direcciones IP (4,290 millones), ¡así que puede ver por qué hay tanta escasez!

IPv6 es una nueva iteración del esquema de direccionamiento del protocolo de Internet para ayudar a abordar este problema. Aunque parece más abrumador, cuenta con algunas ventajas:

- Admite hasta 2^128 direcciones IP (más de 340 billones), lo que resuelve los problemas que enfrenta IPv4
- Es más eficiente debido a las nuevas metodologías

La siguiente captura de pantalla compara una direccion IPv6 e IPv4.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/IPv6.png">

### Direcciones MAC
Todos los dispositivos de una red tienen la interfaz de red física, que es una placa de microchip que se encuentra en la placa madre del dispositivo. A esta interfaz de red se le asigna una dirección única en la fábrica en la que se fabricó, llamada dirección MAC (Media Access Control). La dirección MAC es un número hexadecimal de doce caracteres (un sistema de numeración de base dieciséis utilizado en informática para representar números) dividido en dos y separado por dos puntos. Estos dos puntos se consideran separadores. Por ejemplo, `a4:c3:f0:85:ac:2d`. Los primeros seis caracteres representan la empresa que fabricó la interfaz de red y los últimos seis son un número único.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/Estructura-MAC.png">

Sin embargo, una cosa interesante con las direcciones MAC es que pueden ser falsificadas en un proceso conocido como suplantación de identidad. Esta suplantación de identidad ocurre cuando un dispositivo en red pretende identificarse como otro utilizando su dirección MAC. Cuando esto ocurre, a menudo puede romper diseños de seguridad mal implementados que asumen que los dispositivos que se comunican en una red son confiables. Considere el siguiente escenario: un firewall está configurado para permitir cualquier comunicación que vaya hacia y desde la dirección MAC del administrador. Si un dispositivo pretendiera o "falsificara" esta dirección MAC, el firewall pensaría que está recibiendo comunicación del administrador cuando no es así.

Lugares como cafés, cafeterías y hoteles por igual a menudo usan el control de direcciones MAC cuando usan su Wi-Fi "Público" o "Invitado". Esta configuración podría ofrecer mejores servicios, es decir, una conexión más rápida por un precio si está dispuesto a pagar la tarifa por dispositivo. ¡El laboratorio interactivo adjunto a esta tarea se ha creado para replicar este escenario!

### Práctica
Los laboratorios interactivos simulan una red Wi-Fi de hotel en la que hay que pagar por el servicio.. Notarás que el enrutador no permite que los paquetes de Bob (Azul) ingresen al sitio web TryHackMe y los coloca en la papelera, pero los paquetes de Alice (verde) pasan bien porque ella pagó por el Wi-Fi. Intenta cambiar la dirección MAC de Bob por la misma que la de Alice para ver que sucede.

Implementa el laboratorio interactivo y procede a responder las siguientes preguntas.

### Responde las preguntas a continuación
- ¿Qué significa el término "IP"? `Internet Protocol`
- ¿Cómo se llama cada sección de una dirección IP? `Octet`
- ¿Cuántas secciones (en dígitos) tiene una dirección IP? `4`
- ¿Qué significa el término "MAC"? `Media Access Control`
- Implementa el laboratorio interactivo usando el botón "Ver Sitio" y falsifica tu dirección MAC para acceder al sitio. ¿Qué es la bandera? `THM{YOU_GOT_ON_TRYHACKME}`

## Ping (ICMP)
Ping es una de las herramientas de red más fundamentales que tenemos a nuestra disposición. Ping utiliza paquetes ICMP (Internet Control Message Protocol) para determinar el rendimiento de una conexión entre dispositivos, por ejemplo, si la conexión existe o es confiable.

El tiempo que tardan los paquetes ICMP en viajar entre dispositivos se mide mediante ping, ,como se muestra en la siguiente captura de pantalla. Esta medición se realiza utilizando el paquete de eco de ICMP y luego la respuesta de eco de ICMP del dispositivo de destino.

Los pings se pueden realizar contra dispositivos en una red, como su red doméstica o recursos como sitios web. Esta herramienta se puede utilizar fácilmente y viene instalada en sistemas operativos (OS) como Linux y Windows. La sintaxis para hacer in ping simple es `ping dirección IP o URL del sitio web`. Veamos esto en acción en la siguiente captura de pantalla.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Que-son-Redes/ping.png">

Aquí estamos haciendo ping a un dispositivo que tiene la dirección privada `192.168.1.254`. Ping nos informa que hemos enviado seis paquetes ICMP, todos los cuales se recibieron con un tiempo promedio de 4,16 milisegundos.

Ahora va a hacer lo mismo para hacer ping a la dirección `8.8.8.8` en el sitio web implementable en esta tarea. Hacer ping a la dirección correcta revelará un indicador para responder la siguiente pregunta,

### Responda las preguntas a continuación
- ¿Qué protocolo utiliza ICMP? `ICMP`
- ¿Cuál es la sintaxis para hacer ping a 10.10.10.10? `ping 10.10.10.10`
- ¿Qué indicador obtiene cuando hace ping a 8.8.8.8? `THM{I_PINGED_THE_SERVER}`

## Continúe su aprendizaje; Introducción a LAN
Continúe su aprendizaje uniéndose a la sala "Introducción a LAN".

### Responda las preguntas a continuación
- Únase a la sala [Introducción a LAN]().