---
layout: single
title: Servicios de red
excerpt: "Conozca, enumere y aproveche una variedad de servicios de red y configuraciones incorrectas."
date: 2024-08-20
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red/Servicios-Red.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red/Portada.png">

En esta sala se explotarán las vulnerabilidades y configuraciones incorrectas más comunes de los servicios de red, pero para ello, primero tendremos que hacer algunas cosas.

Para esta sala se requieren conocimientos básicos de Linux y de cómo navegar por el sistema de archivos de Linux. Si necesita ayuda con esto, intenta completar el módulo ***Conceptos básicos de Linux***:

- [Fundamentos de Linux, Parte 1]()
- [Fundamentos de Linux, Parte 2]()
- [Fundamentos de Linux, Parte 3]()

Conéctate al servidor [OpenVPN]() de TryHackMe; asegúrate de estar sentado cómodamente y ten una taza de té, café o agua cerca. ¡Ahora, sigamos adelante!

**N.B.** Esta no es una sala sobre piratería o secuestro de acceso WiFi, sino sobre cómo obtener acceso no autorizado a una máquina mediante la explotación de los servicios de red. Si te interesa hackear redes WiFi, te sugiero que consultes [WiFi Hacking 101]() de NinjaJc01.

### Responde las preguntas a continuación
- ¿Listo? ¡Comencemos!

## Entender SMB
[SMB](https://www.techtarget.com/searchnetworking/definition/Server-Message-Block-Protocol) `(Server Message Block Protocol)` es un protocolo de comunicación entre *cliente* y *servidor* que se utiliza para compartir el acceso a archivos, impresoras, puertos serie y otros recursos de una red.

Los servidores ponen a disposición de los clientes de la red sistemas de archivos y otros recursos (impresoras, canales con nombre, API). Los equipos cliente pueden tener sus propios discos duros, pero también desean acceder a los sistemas de archivos e impresoras compartidos en los servidores.

El protocolo SMB se conoce como *protocolo de solicitud de respuesta*, lo que significa que transmite varios mensajes entre el cliente y el servidor para establecer una conexión. Los clientes se conectan a los servidores mediante TCP/IP (en realidad NetBIOS sobre TCP/IP, como se especifica en RFC1001 y RFC1002), NetBEUI o IPX/SPX.

### ¿Cómo funciona SMB?

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red/SMB.png">

Una vez que han establecido una conexión, loc lientes pueden enviar comandos (SMB) al servidor que les permiten acceder a recursos compartidos, abrir archivos, leer y escribir arrchivos y, en general, hacer todo tipo de cosas que se pueden hacer con un sistema de archivos. Sin embargo, en el caso de SMB, estas cosas se hacen a través de la red.

### ¿Qué ejecuta SMB?
Los sistemas operativos Microsoft Windows desde Windows 95 han incluido compatibilidad con el protocolo SMB de cliente y servidor. Samba, un servidor de código abierto que admite el protocolo SMB, se lanzó para sistemas Unix.

### Responda las preguntas siguientes
- ¿Qué significa SMB? `Server Message Block`
- ¿Qué tipo de protocolo es SMB? `response-request`
- ¿Qué utilizan los clientes para conectarse a los servidores? `TCP/IP`
- ¿En qué sistemas se ejecuta Samba? `Unix`

## Enumeración de SMB
Antes de comenzar, asegúrese de implementar la sala y esperar un tiempo para que arranque. Tenga en cuenta que esto puede llevar hasta 5 minutos, así que tenga paciencia.

### Enumeración
La enumeración es el proceso de recopilación de información sobre un objetivo para encontrar posibles vectores de ataque y ayudar en la explotación.

Este proceso es esencial para que un ataque tenga éxito, ya que perder tiempo con exploits que no funcionan o pueden bloquear el sistema puede ser un desperdicio de energía. La enumeración se puede utilizar para recopilar nombres de usuario, contraseñas, información de red, nombres de host, datos de aplicaciones, servicios o cualquier otra información que pueeda ser valiosa para un atacante.

### SMB
Normalmente, hay unidades compartidas SMB en un servidor a las que se pueede conectar y utilizar para ver o transferir archivos. SMB a menudo puede ser un gran punto de partida para un atacante que busca descubrir información confidencial; le sorprendería saber lo que a veces se incluye en estos recursos compartidos.

### Escaneo de puertos
El primer paso de la enumeración es realizar un escaneo de puertos para obtener la mayor cantidad de información posible sobre los servicios, las aplicaciones, la estructura y el sistema operativo de la máquina de destino.

Si aún no ha visto el escaneo de puertos, le recomiendo que visite la sala de [Nmap]().

### Enum4Linux
Enum4Linux es una herramienta que se utiliza para enumerar recursos compartidos SMB en sistemas Windows y Linux. Básicamente, es un contenedor de las herramientas del paquete Samba y facilita la extracción rápida de información del destino relacionada con SMB. Ya está instalado en AttackBox, sin embargo, si necesita instalarlo en su propia máquina atacante, puede hacerlo desde el [github](https://github.com/CiscoCXSecurity/enum4linux) oficial.

La sintaxis de Enum4Linux es agradable y simple: `enum4linux [opciones] ip`.

`Opciones`
- `-U`: Obtener lista de usuarios
- `-M`: Obtener lista de máquinas
- `-N`: Obtener lista de nombres (diferente de -U y -M)
- `-S`: Obtener lista de recursos compartidos
- `-P`: Obtener información de política de contraseñas
- `-G`: Obtener lista de miembros y grupos
- `-a`: Todas las anteriores (enumeración básica completa)

Ahora que entendemos nuestras herramientas de enumeración, ¡comencemos!

### Responda las preguntas a continuación
- Realice un escaneo de nmap de su elección, ¿cuantos puertos están abiertos? `3`
- ¿En qué puertos se está ejecutando SMB? `139/445`
- Comencemos con Enum4Linux, realice una enumeración básica completa. Para empezar, ¿cuál es el nombre del grupo de trabajo? `WORKGROUP`
- ¿Cuál aparece como nombre de la máquina? `POLOSMB`
- ¿Qué versión del sistema operativo se está ejecutando? `6.1`
- ¿Qué recurso compartido se destaca como algo que podríamos querer investigar? `profiles`

## Explotación de SMB
### Tipos de explotación de SMB
Si bien existen vulnerabilidades como [CVE-2017-7494]() que pueden permitir la ejecución remota de código mediante la explotación de SMB, es más probable que se encuentre con una situación en la que la mejor manera de ingresar a un sistema sea debido a configuraciones incorrectas en el sistema. En este caso, vamos a explotar el acceso anónimo a un recursos compartido SMB, una configuración incorrecta común que puede permitirnos obtener información que conducirá a un shell.

### Desglose del método
Entonces, desde nuestra etapa de enumeración, sabemos:
- La ubicación del recurso compartido SMB
- El nombre de un recurso compartido SMB interesante

### SMBClient
Como estamos tratando de aaceder a un recurso compartido SMB, necesitamos un cliente para acceder a los recursos en los servidores. Usaremos `SMBClient` porque es parte de la suite samba predeterminada. Si bien ya está instalado oen AttackBox, si necesita instalarlo en su propia máquina atacante, puede encontrar la documentación [aquí](https://www.samba.org/samba/docs/current/man-html/smbclient.1.html).

Podemos acceder de forma remota al recurso compartido SMB mediante la sintaxis: `smbclient //IP/[Share]`.

Seguido de las etiquetas:
- `-U [nombre]`: Para especificar el usuario
- `-p [puerto]`: Para especificar el puerto

¿Entendido? ¡Bien, hagámoslo!

### Responda las preguntas a continuación
- ¿Cuál sería la sintaxis correcta para acceder a un recurso compartido SMB llamado (secret) como usuario (suit) en una máquina con la IP (10.10.10.2) en el puerto predeterminado? `smbclient //10.10.10.2/secret -U suit -p 445`

¡Genial! Ahora que ya domina la sintaxis, intentemos explotar esta vulnerabilidad. Tiene una lista de usuarios, el nombre del recurso compartido (smb) y una vulnerabilidad sospechosa.

Veamos si nuestro recurso compartido interesante se ha configurado opara permitir el acceso anónimo, es decir, no requiere autenticación para ver los archivos. Podemos hacer esto fácilmente:
- Usando el nombre de usuario "Anonymous"
- Conectándonos al recurso ocompartido que encontramos durante la etapa de enumeración
- Y sin proporcionar una contraseña.

- ¿El recurso compartido permite el acceso anónimo? (Y/N) `Y`

¡Genial! Eche un vistazo para ver si hay documentos interesantes que puedan contener información valiosa.

- ¿A quién podemos suponer que pertenece esta carpeta de perfil? `John Cactus`

```text
Para poder saber el nombre del usuario de la carpeta utilizamos el comando:

smb: \> more "Working From Home Information.txt"

John Cactus,

As you're well aware, due to the current pandemic most of POLO inc. has insisted that, wherever 
possible, employees should work from home. As such- your account has now been enabled with ssh
access to the main server.

If there are any problems, please contact the IT department at it@polointernalcoms.uk

Regards,

James
Department Manager
```

- ¿Qué servicio se ha configurado para permitirle trabajar desde casa? `ssh`

¡Bien! Ahora que sabemos esto, ¿en qué directorio del recurso compartido deberíamos buscar? `.ssh`

- Este directorio contiene claves de autenticación que permiten a un usuario autenticarse y luego acceder a un servidor. ¿Cuál de estas claves nos resulta más útil? `id_rsa`

Descargue este archivo a su máquina local y cambie los permisos a "600" usando `chmod 600 id_rsa`.

```text
Para descargar las claves se usan los siguientes comandos:

smb: \.ssh\> get id_rsa
smb: \.ssh\> get id_rsa.pub
```
```text
Para cambiar los permisos se utiliza el comando:

$ chmod 600 id_rsa
```

Ahora, use la información que ya ha reunido para averiguar el nombre de usuario de la cuenta. Luego, use el servicio y la clave para iniciar sesión en el servidor.

```text
Para averiguar el nombre de usuario de la cuenta debemso leer el archivo id_rsa.pub

┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ cat id_rsa.pub                
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDb7OaL8zLZ5Z8OU3wZPSIQHaoyI8Yc3I/8/Y6faWgYTZbfNPexli0jxdAeTeGy2X3XACWcB4HFejbiNsMYLjy517gwWKPBvN865i8uIQ0Gqayq/KmBHpuBbR0yX/SpyfyvzR3VD16pg/D+WT8hLaNHSYm6FNYLsmVnWDSJDBhS179czftuoW55mw/OqzWVr5ln9cKeeuXlNV1lqCjBqF3ClzEBvN4JW8GS/riLTeHcXeMIMUTuIpr4XovN/VivIlLqTYy7lHuUh6L2RqAfw5+FSr4QZW1zHCMoS6FooTomq/03EGJCGcp80/fT0e04n+7+PxnmvZQkOwe1A1hUG6C/ cactus@polosmb

Nos damos cuenta que el usuario es "cactus"
```
```text
Para acceder al servicio se utiliza el comando:

┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ ssh -i id_rsa cactus@10.10.58.9

Ingresando listamos archivos (ls) y leemos el archivo smb.txt con el comando (cat smb.txt) y nos imprime la última bandera.
```

- ¿Qué es el indicador smb.txt? `THM{smb_is_fun_eh?}`

## Telnet

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red/Telnet.png">

Telnet es un protocolo de aplicación que le permite, mediante el uso de un cliente Telnet, conectarse y ejecutar comandos en una máquina remota que aloja un servidor Telnet.

El cliente Telnet establecerá una conexión con el servidor. El cliente se convertirá entonces en una terminal virtual, lo que le permitirá interactuar con el host remoto.

### Reemplazo
Telnet envía todos los mensajes en texto sin formato y no tiene mecanismos de seguridad específicos. Por lo tanto, en muchas aplicaciones y servicios, Telnet ha sido reemplazado por SSH en la mayoría de las implementaciones.

### ¿Cómo funciona Telnet?
El usuario se conecta al servidor mediante el protocolo Telnet, lo que significa ingresar "telnet" en un símbolo del sistema. Luego el usuario ejecuta comandos en el servidor mediante comandos Telnet específicos en el símbolo del sistema. Puede conectarse a un servidor Telnet con el comando: `telnet [ip] [puerto]`.

### Responda las preguntas a continuación
- ¿Qué es Telnet? `application protocol`
- ¿Qué ha reemplazado lentamente a Telnet? `SSH`
- ¿Cómo se conectaría a un servidor Telnet con la IP (10.10.10.3) en el puerto (23)? `telnet 10.10.10.3 23`
- ¿La falta de qué significa que toda la comunicación Telnet se realiza en texto sin formato? `Encryption`

## Enumeración de Telnet
Antes de comenzar, asegúrese de implementar la sala y darle un tiempo para que arranque. Tenga en cuenta que esto puede tardar hasta 5 minutos, así que tenga paciencia.

### Enumeración
Ya hemos visto lo importante que puede ser la enumeración para explotar un servicio de red mal configurado. Sin embargo, las vulnerabilidades que podrían ser potencialmente tribviales de explotar no siempre están a la vista. Por esa razón, especialmente cuando se trata de enumerar servicios de red, debemos ser minuciosos en nuestro método.

### Escaneo de puertos
Comencemos de la misma manera que lo hacemos habitualmente, un escaneo de puertos, para encontrar la mayor cantidad de información posible sobre los servicios, las palicaciones, la estructura y el sistema operativo de la máquina de destino. Escanee la máquina con nmap.

### Salida
Veamos qué está sucediendo en el servidor de destino...

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ sudo nmap -A -Pn -T4 -p- 10.10.217.91

Nmap scan report for 10.10.217.91
Host is up (0.19s latency).
Not shown: 65534 closed tcp ports (reset)

PORT     STATE SERVICE VERSION
8012/tcp open  unknown
| fingerprint-strings: 
|   DNSStatusRequestTCP, DNSVersionBindReqTCP, FourOhFourRequest, GenericLines, GetRequest, HTTPOptions, Help, Kerberos, LANDesk-RC, LDAPBindReq, LDAPSearchReq, LPDString, NCP, NULL, RPCCheck, RTSPRequest, SIPOptions, SMBProgNeg, SSLSessionReq, TLSSessionReq, TerminalServer, TerminalServerCookie, X11Probe: 
|_    SKIDY'S BACKDOOR. Type .HELP to view commands
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port8012-TCP:V=7.94SVN%I=7%D=9/8%Time=66DD9344%P=x86_64-pc-linux-gnu%r(
SF:NULL,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20comma
SF:nds\n")%r(GenericLines,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20t
SF:o\x20view\x20commands\n")%r(GetRequest,2E,"SKIDY'S\x20BACKDOOR\.\x20Typ
SF:e\x20\.HELP\x20to\x20view\x20commands\n")%r(HTTPOptions,2E,"SKIDY'S\x20
SF:BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20commands\n")%r(RTSPReques
SF:t,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20commands
SF:\n")%r(RPCCheck,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20vi
SF:ew\x20commands\n")%r(DNSVersionBindReqTCP,2E,"SKIDY'S\x20BACKDOOR\.\x20
SF:Type\x20\.HELP\x20to\x20view\x20commands\n")%r(DNSStatusRequestTCP,2E,"
SF:SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20commands\n")%r
SF:(Help,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20comm
SF:ands\n")%r(SSLSessionReq,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x2
SF:0to\x20view\x20commands\n")%r(TerminalServerCookie,2E,"SKIDY'S\x20BACKD
SF:OOR\.\x20Type\x20\.HELP\x20to\x20view\x20commands\n")%r(TLSSessionReq,2
SF:E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20commands\n"
SF:)%r(Kerberos,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\
SF:x20commands\n")%r(SMBProgNeg,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HEL
SF:P\x20to\x20view\x20commands\n")%r(X11Probe,2E,"SKIDY'S\x20BACKDOOR\.\x2
SF:0Type\x20\.HELP\x20to\x20view\x20commands\n")%r(FourOhFourRequest,2E,"S
SF:KIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20commands\n")%r(
SF:LPDString,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20
SF:commands\n")%r(LDAPSearchReq,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HEL
SF:P\x20to\x20view\x20commands\n")%r(LDAPBindReq,2E,"SKIDY'S\x20BACKDOOR\.
SF:\x20Type\x20\.HELP\x20to\x20view\x20commands\n")%r(SIPOptions,2E,"SKIDY
SF:'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20commands\n")%r(LAND
SF:esk-RC,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\x20to\x20view\x20com
SF:mands\n")%r(TerminalServer,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x20\.HELP\
SF:x20to\x20view\x20commands\n")%r(NCP,2E,"SKIDY'S\x20BACKDOOR\.\x20Type\x
SF:20\.HELP\x20to\x20view\x20commands\n");
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.94SVN%E=4%D=9/8%OT=8012%CT=1%CU=30278%PV=Y%DS=2%DC=T%G=Y%TM=66D
OS:D93F3%P=x86_64-pc-linux-gnu)SEQ(SP=104%GCD=1%ISR=104%TI=Z%CI=Z%II=I%TS=A
OS:)OPS(O1=M508ST11NW7%O2=M508ST11NW7%O3=M508NNT11NW7%O4=M508ST11NW7%O5=M50
OS:8ST11NW7%O6=M508ST11)WIN(W1=F4B3%W2=F4B3%W3=F4B3%W4=F4B3%W5=F4B3%W6=F4B3
OS:)ECN(R=Y%DF=Y%T=40%W=F507%O=M508NNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+
OS:%F=AS%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)
OS:T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A
OS:=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%D
OS:F=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=4
OS:0%CD=S)

Network Distance: 2 hops

TRACEROUTE (using port 5900/tcp)
HOP RTT       ADDRESS
1   201.75 ms 10.9.0.1
2   201.76 ms 10.10.217.91

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 1379.97 seconds
```

### Responda las preguntas a continuación
- ¿Cuantos puertos están abiertos en la máquina de destino? `1`
- ¿Qué puerto es este? `8012`
- Este puerto no está asignado, pero aún así enumera el protocolo que está utilizando, ¿qué protocolo es este? `tcp`
- Ahora, vuelva a ejecutar el escaneo de nmap, sin la etiqueta (-p-), ¿cuantos puertos aparecen como abiertos? `0`

Aquí, vemos que al asignar telnet a un puerto no estándar, no forma parte de la lista de puertos comunes, o de los 1000 puertos principales, que escanea nmap. Es importante probar todos los ángulos al enumerar, ya que la información que recopile aquí le informará sobre su etapa de explotación.

- Según el título que nos devolvieron, ¿para qué creemos que se podría usar este puerto? `a backdoor`
- ¿A quién podría pertenecer? Recopilar posibles nombres de usuario es un paso importante en la enumeración. `Skidy`

Siempre tome nota de la información que encuentre durante su etapa de enumeración,de modo que pueda volver a consultarla cuando continúe para probar exploits.

## Explotando Telnet