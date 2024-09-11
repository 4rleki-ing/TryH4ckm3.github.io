---
layout: single
title: HTTP en detalle
excerpt: "Obtenga más información sobre cómo solicitar contenido a un servidor web mediante el protocolo HTTP."
date: 2024-08-19
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/HTTP-Detalle/Detalle.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/HTTP-Detalle/Portada.png">

`HTTP (Protocolo de Transferencia de Hipertexto)`, es lo que se utiliza siempre que se visita un sitio web, desarrollado por Tim Berners-Lee y su equipo entre 1989 y 1991. HTTP es el conjunto de reglas que se utilizan para comunicarse con servidores web para la transmisión de datos de páginas web, ya sea HTML, imágenes, videos, etc.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/HTTP-Detalle/HTTP.png">

`HTTPS (Protocolo de Transferencia de Hipertexto Seguro)`, HTTPS es la versión segura de HTTP, Los datos HTTPS están encriptados, por lo que no solo evita que las personas vean los datos que está recibiendo y enviando, sino que también le garantiza que está hablando con el servidor web correcto y no con algo que lo suplanta.

### Responda las preguntas a continuación
- ¿Qué significa HTTP? `HyperText Transfer Protocol`
- ¿Qué significa la S en HTTPS? `Secure`
- En la página web simulada de la derecha hay un problema; una vez que lo haya encontrado, haga clic en él. ¿Qué es la bandera de desafío? `THM{INVALID_HTTP_CERT}`

## Solicitudes y respuestas
Cuando accedemos a un sitio web, su navegador deberá realizar solicitues a un servidor web para obtener recursos como HTML, imágenes y descargar las respuestas. Antes de eso, debe indicarle al navegador específicamente cómo y dónde acceder a estos recursos, y aquí es donde las URL serán de ayuda.

### ¿Qué es una URL?
Si ha utilizado internet, habrá utilizado una URL antes. Una URL (Localizador Unifforme de Recursos) es principalmente una instrucción sobre cómo acceder a un recurso en Internet. La siguiente imagen muestra cómo se ve una URL con todas sus características (no utiliza todas las caracteristicas en cada solicitud).

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/HTTP-Detalle/URL.png">

- `Scheme (Esquema)`: Indica qué protocolo utilizar para acceder al recurso, como HTTP, HTTPS, FTP (Protocolo de transferencia de archivos).
- `User (Usuario)`: Algunos servicios requieren autenticación para iniciar sesión; puede colocar un nombre de usuario y una contraseña en la URL para iniciar sesión.
- `Host`: El nombre del dominio o la dirección IP del servidor al que desea acceder.
- `Port (Puerto)`: El puerto al que se va a conectar, normalmente 80 para HTTP y 443 para HTTPS, pero puede estar alojado en cualquier puerto entre 1 y 65535.
- `Path (Ruta)`: El nombre del archivo o la ubicación del recurso al que intenta acceder.
- `Query String (Cadena de consulta)`: bits adicionales de información que se pueden enviar a la ruta solicitada. (Por ejemplo, /blog?id=1) le indicaría a la ruta del blog que desea recibir el artículo del blog con el id 1.
- `Fragment (Fragmento)`: Es una referencia a una ubicación en la página real solicitada. Esto se usa comúnmente para páginas con contenido extenso y puede tener una cierta parte de la página directamente vinculada a ella, de modo que sea visible para el usuario tan pronto como acceda a la página.

### Realizar una solicitud
Es posible realizar una solicitud a un servidor web con solo una línea `GET / HTTP/1.1`

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/HTTP-Detalle/Solicitud-GET.png">

Pero una experiencia web mucho más completa, también deberá enviar otros datos. Estos otros datos se envían en lo que se denomina encabezados, donde los encabezados contienen información adicional para proporcionar al servidor web con el que se está comunicando, pero profundizaremos más en esto en la tarea "Encabezado".

Ejemplo de solicitud: 

```text
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/

```

Para desglosar cada línea de esta solicitud:

- `Línea 1`: Esta solicitud envía el método GET (más sobre esto en la tarea "Métodos HTTP"), solicita la página de inicio con / y le dice al servidor web que estamos usando el protocolo HTTP versión 1.1.
- `Línea 2`: Le decimos al servidor web que queremos el sitio web tryhackme.com
- `Línea 3`: Le decimos al servidor web que estamos usando el navegador Firefox versión 87
- `Línea 4`: Le decimos al servidor web que la página web que nos refirió a esta es https://tryhackme.com
- `Línea 5`: Las solicitudes HTTP siempre terminan con una línea en blanco para informar al servidor web que la solicitud ha finalizado.

Ejemplo de respuesta:

```text
HTTP/1.1 200 OK
Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98

<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>
```

Para desglosar cada línea de la respuesta.

- `Línea 1`: HTTP 1.1 es la versión del protocolo HTTP que utiliza el servidor y luego sigue el código de estado HTTP, en este caso "200 Ok", nos indica que la solicitud se ha completado correctamente.
- `Línea 2`: Esto nos indica el software del servidor web y el número de versión
- `Línea 3`: La fecha, hora y zona horaria actuales del servidor web
- `Línea 4`: El encabezado Content-Type le indica al cliente qué tipo de información se va a enviar, como HTML, imágenes, videos, PDF, XML.
- `Línea 5`: Content-Length le indica al cliente la longitud de la respuesta, de esta manera podemos confirmar que no faltan datos.
- `Línea 6`: La respuesta HTTP contiene una línea en blanco para confirmar el final de la respuesta HTTP.
- `Líneas 7 a 14`: La información que se ha solicitado, en este caso la página de inicio.

### Responda las preguntas a continuación
- ¿Qué protocolo HTTP se está utilizando en el ejemplo anterior? `HTTP/1.1`
- ¿Qué encabezado de respuesta le indica al navegador cuántos datos esperar? `Content-Length`

## Métodos HTTP
Los métodos HTTP son una forma de que el cliente muestre la acción prevista al realizar una solicitud HTTP. Hay muchos métodos HTTP, pero cubriremos los más comunes, aunque principalmente tratará con los métodos GET y POST.

- `Solicitud GET`: Se utiliza para obtener información de un servidor web.
- `Solicitud POST`: Se utiliza para enviar datos al servidor web y potencialmente crear nuevos registros.
- `Solicitud PUT`: Se utiliza para enviar datos a un servidor web para actualizar información.
- `Solicitud DELETE`: Se utiliza para eliminar información/registros de un servidor web.

### Responda las preguntas a continuación
- ¿Qué método se utilizaría para crear una nueva cuenta de usuario? `POST`
- ¿Qué método se utilizaría para actualizar su dirección de correo electrónico? `PUT`
- ¿Qué método se utilizaría para eliminar una imagen que ha cargado en su cuenta? `DELETE`
- ¿Qué método se utilizaría para ver un artículo de noticias? `GET`

