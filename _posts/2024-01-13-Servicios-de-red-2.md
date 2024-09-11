---
layout: single
title: Servicios de red 2
excerpt: "Enumeración y explotación de servicios de red y configuraciones erróneas más comunes."
date: 2024-08-19
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red-2/Servicios.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red-2/Portada.png">

Esta sala es una secuela de la primera sala de servicios de red. De manera similar, explotará algunas vulnerabilidades y configuraciones incorrectas más comunes de los servicios de red que probablemente encuentres en los CTF y algunos escenarios de pruebas de penetración.

Te recomiendo que completes la primera sala de [servicios de red]() antes de intentar esta. Al igual que con la sala anterior, definitivamente vale la pena tener un conocimiento básico de Linux antes de intentar esta sala. Si necesita ayuda con esto, intenta completar el módulo ***Conceptos básicos de Linux***:

- [Fundamentos de Linux, Parte 1]()
- [Fundamentos de Linux, Parte 2]()
- [Fundamentos de Linux, Parte 3]()

Conéctate al servidor [OpenVPN]() de TryHackMe; asegúrate de estar sentado cómodamente y ten una taza de té, café o agua cerca. ¡Comencemos!

**N.B.** Esta no es una sala sobre piratería o secuestro de acceso WiFi, sino sobre cómo obtener acceso no autorizado a una máquina mediante la explotación de los servicios de red. Si te interesa hackear redes WiFi, te sugiero que consultes [WiFi Hacking 101]() de NinjaJc01.

¿Listo? ¡Comencemos!

## NFS
NFS (Sistema de archivos de red) y permite que un sistema comparta directorios y archivos con otros a través de una red. Al utilizar NFS, los usuarios y los programas pueden acceder a archivos en sistemas remotos casi como si fueran archivos locales. Esto se logra montando todo o parte de un sistema de archivos en un servidor. Los clientes pueden acceder a la parte del sistema de archivos que se monta con los privilegios que se les asignen a cada archivo.

### ¿Cómo funciona NFS?

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red-2/NFS.png">

No necesitamos entender el intercambio técnico en demasiado detalle para poder explotar NFS de manera efectiva; sin embargo, si esto es algo que le interesa, le recomendaría este [recurso](https://docs.oracle.com/cd/E19683-01/816-4882/6mb2ipq7l/index.html).

Primero, el cliente solicitará montar un directorio desde un host remoto en un directorio local de la misma manera que puede montar un dispositivo físico. El servicio de montaje actuará entonces para conectarse al demonio de montaje relevante mediante RPC.

El servidor verifica si el usuario tiene permiso para montar cualquier directorio que se haya solicitado. Luego devolverá un identificador de archivo que identifica de manera única cada archivo y directorio que se encuentra en el servidor.

Si alguien desea acceder a un archivo mediante NFS, se realiza una llamada RPC a NFSD (el demonio NFS) en el servidor. Esta llamada toma parámetros como:

- El identificador del archivo
- El nombre del archivo al que se accederá
- El ID de usuario
- El ID de grupo del usuario

Estos se utilizan para determinar los derechos de acceso al archivo especificado. Esto es lo que controla los permisos de usuario, es decir, la lectura y escritura de archivos.

### ¿Qué ejecuta NFS?
Mediante el protocolo NFS, puede transferir archivos entre computadoras que ejecutan Windows y otros sistemas operativos que no son Windows, como Linux, MacOS o UNIX.

Una computadora que ejecuta Windows Server puede actuar como un servidor de archivos NFS para otras computadoras cliente que no sean Windows. Del mismo modo, NFS permite que una computadora basada en Windows que ejecuta Windows Server acceda a archivos almacenados en un servidor NFS que no sea Windows.

### Más información
A continuación, se incluyen algunos recursos que explican la implementación técnica y el funcionamiento de NFS con más detalle del que se ha cubierto aquí:

- [datto.com](https://www.datto.com/blog/what-is-nfs-file-share/)
- [sourceforge.net](https://nfs.sourceforge.net/)
- [archlinux.org](https://wiki.archlinux.org/title/NFS)
- [IBM](https://www.ibm.com/docs/es/aix/7.1?topic=management-network-file-system)
- [Wikipedia](https://en.wikipedia.org/wiki/Network_File_System)

### Responda las preguntas a continuación
- ¿Qué significa NFS? `Network File System`
- ¿Qué proceso permite que un cliente NFS interactúe con un directorio remoto como si fuera un dispositivo físico? `mounting`
- ¿Qué utiliza NFS para representar archivos y directorios en el servidor? `file handle`
- ¿Qué protocolo utiliza NFS para comunicarse entre el servidor y el cliente? `RPC`
- ¿Qué dos datos de usuario toma el servidor NFS como parámetros para controlar los permisos de usuario? (Formato: parámetro1 / parámetro 2) `user id / group id`
- ¿Puede un servidor NFS de Windows compartir archivos con un cliente Linux? (S/N) `Y`
- ¿Puede un servidor NFS de Linux compartir archivos con un cliente MacOS? (S/N) `Y`
- ¿Cuál es la última versión de NFS? [Publicada en 2016, pero aún está actualizada en 2020]; Esto requerirá una investigación externa. `4.2` 

## Enumeración de NFS
Antes de comenzar, asegúrese de implementar la sala y esperar un tiempo para que arranque. Tenga en cuenta que esto puede tardar hasta 5 minutos, así que tenga paciencia.

### ¿Qué es la enumeración?
La enumeración se define como "un proceso que establece una conexión activa con los hosts destino para descubrir posibles vectores de ataque en el sistema, y lo mismo se puede utilizar para una mayor explotación del sistema". - [Infosec Institute](https://www.infosecinstitute.com/resources/penetration-testing/what-is-enumeration/). Es una frase crítica al considerar cómo enumerar y explotar una máquina remota, ya que la información que utilizará para informar sus ataques provendrá de esta etapa.

### Requisitos
Para realizar una enumeración más avanzada del servidor NFS y los recursos compartidos, vamos a necesitar algunas herramientas. La primera de las cuales es clave para interactuar con cualquier recurso compartido NFS desde su máquina local: `nfs-common`

### NFS-Common
Es importante tener eeste paquete instalado en cualquier máquina que use NFS, ya sea como cliente o servidor. Incluye programas como: lockd, statd, showmount, nfsstat, gssd, idmapd y mount.nfs. Principalmente, nos interesan *showmount* y *mount.nfs*, ya que nos serán de gran utilidad a la hora de extraer información del recurso compartido NFS. Si desea más información sobre este paquete, no dude en leer: [packages.ubuntu.com](https://packages.ubuntu.com/jammy/nfs-common).

Puede instalar *nfs-common* utilizando `sudo apt install nfs-common`, es parte de los repositorios predeterminados para la mayoría de las distribuciones de Linux, como Kali Remote Machine o AttackBox, que se proporciona a TryHackMe.

### Escaneo de Puertos
El escaneo de puertos se ha tratado muchas veces antes, por lo que solo se cubrirá los conceptos básicos que necesita para esta sala. Si desea obtener más información sobre nmap con más detalle, eche un vistazo a la sala [nmap]().

El primer paso de la enumeración es realizar un escaneo de puertos para encontrar la mayor cantidad de información posible sobre los servicios, los puertos abiertos y el sistema operativo de la máquina destino. Puede profundizar tanto como desee en esto, sin embargo, le sugiero que utilice nmap con las etiquetas `-A` y `-p-`.

### Montaje de recursos compartidos NFS
El sistema de su cliente necesita un directorio donde se pueda acceder a todo el contenido compartido por el servidor host en la carpeta de exportación. Puede crear esta carpeta en cualquier parte de su sistema. Una vez que haya creado este punto de montaje, puede utilizar el comando `mount` para conectar el recurso compartido NFS al punto de montaje en su máquina de la siguiente manera:

```text
sudo mount -t nfs IP:share /tmp/mount/ -nolock
```

Desglosemos esto

<table align="center">
    <tr>
        <th>Etiqueta</th>
        <th>Función</th>
    </tr>
    <tr>
        <td>sudo</td>
        <td>Ejecutar como root</td>
    </tr>
    <tr>
        <td>mount</td>
        <td>Ejecutar el comando mount</td>
    </tr>
    <tr>
        <td>-t nfs</td>
        <td>Tipo de dispositivo a montar, luego especificar que es NFS</td>
    </tr>
    <tr>
        <td>IP:Share</td>
        <td>La dirección IP del servidor NFS y el nombre del recurso compartido que deseamos montar.</td>
    </tr>
    <tr>
        <td>-nolock</td>
        <td>Especifica que no se debe usar el bloqueo NLM</td>
    </tr>
</table>

Ahora qye entendemos nuestras herramientas, ¡comencemos!

### Responda las preguntas a continuación
- Realice un escaneo de puertos completos de su elección, ¿cuántos puertos están abiertos? ``

- ¿Qué puerto contiene el servicio que buscamos enumerar? ``

- Ahora, use `/usr/sbin/showmount -e [IP]` para enumerar los recursos compartidos NFS, ¿cuál es el nombre del recurso compartido visible? ``

¡Es hora de montar el recurso compartido en nuestra máquina local! primero, use `mkdir /tmp/mount` para crear un directorio en su máquina para montar el recurso compartido. Esta se encuentra en el directorio `/tmp`, así que tenga en cuenta que s eeliminará al reiniciar.

- Luego, use el comando `mount` que desglosamos anteriormente para montar el recurso compartido NFS en su máquina local. Cambie el directorio al lugar donde montó el recurso compartido, ¿cuál es el nombre de la carpeta que s eencuentra dentro? ``

- Eche un vistazo dentro de este directorio, mire los archhivos. Parece que estamos dentro del directorio de inicio de un usuario ...

- ¡Interesante! Investiguemos un poco ahora, echemos un vistazo a las carpetas. ¿Cuál de estas carpetas podría contener claves que nos darían acceso remoto al servidor? ``

- ¿Cuál de estas claves nos resulta más útil? ``

Copia este archivo en una ubicación diferente de tu máquina local y cambia los permisos a "600" usando `chmod 600 [archivo]`.

Suponiendo que estábamos en lo ciertosobre qué tipo de directorio es este, podemos averiguar fácilmente el nombre del usuario al que corresponde esta clave.

- ¿Podemos iniciar sesión en la máquina usando `ssh -i [archivo-de-claves] [nombre-de-usuario]@[IP]`? (S/N) ``