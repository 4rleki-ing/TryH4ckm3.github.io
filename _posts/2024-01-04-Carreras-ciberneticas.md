---
layout: single
title: Carreras en Ciberseguridad
excerpt: "Conozca las diferentes carreras en ciberseguridad."
date: 2024-08-28
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/Defensa.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/Portada.png">
</p>

## Introducción a la Seguridad Defensiva

La seguridad ofensiva se centra en una sola cosa: *entrar en los sistemas*. Para entrar en los sistemas se puede aprovechar la explotación de errores, el abuso de configuraciones inseguras y el aprovechamiento de políticas de control de acceso no aplicadas, entre otras cosas. Los *Equipos Rojos* y los *evaluadores de penetración* se especializan en **Seguridad Ofensiva**.

La ***Seguridad Defensiva*** es en cierto modo lo opuesto a la seguridad ofensiva, ya que se ocupa de 2 tareas principales:

1. Prevenir que se produzcan intrusiones.
2. Detectar intrusiones cuando se producen y responder adecuadamente.

Los **Equipos Azules** son parte del panorama de la seguridad defensiva.

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/Blue-team.png">
</p>

Algunas de las tareas relacionadas con la seguridad defensiva incluyen:

- `Concientización sobre la ciberseguridad del usuario`: Capacitar a los usuarios sobre la ciberseguridad ayuda a protegerse contra diversos ataques que tienen como objetivo sus sistemas.
- `Documentar y administrar activos`: Se necesita conocer los tipos de sistemas y dispositivos que se tienen que administrar y proteger adecuadamente.
- `Actualizar y aplicar parches a los sistemas`: Garantizar que las computadoras, servidores y dispositivos de red estén correctamente actualizados y parcheados contra cualquier vulnerabilidad (debilidad) conocida.
- `Configurar dispositivos de seguridad preventiva`: Los Firewalls y los sistemas de prevención de intrusiones (IPS) son componentes críticos de la seguridad preventiva. Los Firewalls controlan qué tráfico de red puede ingresar y qué puede salir del sistema o la red. Los IPS bloquean cualquier tráfico de red que coincida con las reglas y las firmas de ataques actuales.
- `Configurar dispositivos de registro y monitoreo`: Sin un registro y monitoreos adecuados de la red, no será posible detectar actividades e intrusiones maliciosas. Si aparece un nuevo dispositivo no autorizado en nuestra red, deberíamos poder saberlo.

La seguridad defensiva implica mucho más y la lista anterior solo cubre algunos temas comunes.

En esta sala, abodamos:
- Centro de Operaciones de Seguridad (SOC).
- Inteligencia de Amenazas.
- Análisis Forense Digital y Respuesta a Incidentes (DFIR).
- Análisis de Malware.

### Responda las preguntas a continuación
1. ¿Qué equipo se centra en la seguridad defensiva? `Blue Team`

## Áreas de Seguridad Defensiva
En esta tarea, cubriremos 2 temas principales relacionados con la seguridad defensiva:

- `Centro de Operaciones de Seguridad (SOC)`: Donde cubrimos Inteligencia de Amenazas.
- `Análisis Forense Digital y Respuesta a Incidentes (DFIR)`: Donde también cubrimos análisis de malware.

### Centro de Operaciones de Seguridad (SOC)
Un *Centro de Operaciones de Seguridad (SOC)* es un equipo de profesionales de seguridad cibernética que monitorea la red y sus sistemas para detectar eventos de seguridad cibernética maliciosos. Algunas de las principales áreas de interés para un SOC son:

- `Vulnerabilidades`: Siempre que se descubre una vulnerabilidad (debilidad) del sistema, es esencial corregirla instalando una actualización o parche adecuado. Cuando no hay una solución disponible, se deben tomar las medidas necesarias para evitar que un atacante la explote. Aunque remediar las vulnerabilidades es de vital interés para un SOC, no necesariamente se les asigna.
- `Violaciones de Políticas`: Podemos pensar en una política de seguridad como un conjunto de reglas necesarias para la protección de la red y los sistemas. Por ejemplo, podría ser una violación de política si los usuarios comienzan a cargar datos confidenciales de la empresa a un servicio de almacenamiento en línea.
- `Actividad no autorizada`: Considere el caso en el que se roban el nombre de usuario y la contraseña de un usuario y el atacante los usa para iniciar sesión en la red. Un SOC debe detectar un evento de este tipo y bloquearlo lo antes posible antes de que se produzcan más daños.
- `Intrusiones en la red`: No importa lo buena que sea su seguridad, siempre existe la posibilidad de una intrusión. Una intrusión puede ocurrir cuando un usuario hace clic en un enlace malicioso o cuando un atacante explota un servidor público. De cualquier manera, cuando ocurre una intrusión, debemos detectarla lo antes posible para evitar más daños.

Las operaciones de seguridad cubren varias tareas para garantizar la protección; una de ellas es la inteligencia de amenazas.

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/SOC.png">
</p>

### Inteligencia Sobre Amenazas
En este contexto, la inteligencia se refiere a la información que se recopila sobre enemigos reales y potenciales. Una amenaza es cualquier acción que pueda interrumpir o afectar negativamente a un sistema.

La inteligencia sobre amenazas tiene como objetivo recopilar información para ayudar a la empresa a prepararse mejor contra posibles adversarios. El objetivo sería lograr una defensa basada en amenazas.

Diferentes empresas tienen diferentes adversarios. Algunos adversarios pueden intentar robar datos de clientes de un operador móvil; sin embargo, otros adversarios están interesados en detener la producción en una refinería de petróleo.

Algunos ejemplos de adversarios incluyen un *ejército cibernético de un estado-nación* que trabaja por razones políticas y un *grupo de ransomware* que actúa con fines financieros. Según la empresa (objetivo), podemos esperar adversarios.

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/Inteligencia-Amenazas.png">
</p>

La inteligencia necesita datos. Los datos deben recopilarse, procesarse y analizarse.

- La **recopilación de datos** se realiza a partir de fuentes locales (registros de red), y fuentes públicas (foros).
- El **procesamiento de los datos** tiene como objetivo organizarlos en un formato adecuado para el análisis.
- La **fase de análisis** busca encontrar más información sobre los atacantes y sus motivos; además, tiene como objetivo crear una lista de recomendaciones y pasos a seguir.

Conocer a sus adversarios le permite conocer sus tácticas, técnicas y procedimientos. Como resultado de la inteligencia de amenazas, identificamos al actor de la amenaza (adversario), predecimos su actividad y, en consecuencia, podremos mitigar sus ataques y preparar una estrategia de respuesta.

### Informática Forense Digital y Respuesta a Incidentes (DFIR)
Esta sección trata sobre la informática forense digital y la respuesta a incidentes (DFIR) y cubriremos:

- Informática Forense Digital.
- Respuesta a Incidentes.
- Análisis de Malware.

#### Ciencia Forense Digital
La Ciencia Forense es la aplicación de la ciencia para investigar delitos y establecer hechos. Con el uso la difusión de los sistemas digitales, como las computadoras y los teléfonos inteligentes, nació una nueva rama de la ciencia forense para investigar delitos relacionados: la ciencia forense informática, que luego evolucionó hacia la ***ciencia forense digital***.

En Seguridad Defensiva, el enfoque de la ciencia forense digital se desplaza hacia el análisis de evidencia de un ataque y sus perpetradores y otras áreas como el *robo de propiedad intelectual*, el *espionaje cibernético* y la *posesión de contenido no autorizado*. En consecuencia, la ciencia forense digital se centrará en diferentes áreas como:

- `Sistema de Archivos`: El análisis de una imagen forense digital (copia de bajo nivel) del almacenamiento de un sistema revela mucha información, como programas instalados, archivos creados, archivos parcialmente sobrescritos y archivos eliminados.
- `Memoria del sistema`: Si el atacante está ejecutando su programa malicioso en la memoria sin guardarlo en el disco, tomar una imagen forense (copia de bajo nivel) de la memoria del sistema es la mejor manera de analizar su contenido y obtener información sobre el ataque.
- `Registros del Sistema`: Cada computadora cliente y servidor mantiene diferentes archivos de registro sobre lo que está sucediendo. Los archivos de registro brindan mucha información sobre lo que sucedió en un sistema. Algunos rastros quedarán incluso si el atacante intenta borrar sus rastros.
- `Registros de red`: Los registros de los paquetes de red que han atravesado una red ayudarían a responder más preguntas sobre si se está produciendo un ataque y qué implica.

#### Respuesta a Incidentes
Un incidente suele hacer referencia a una violación de datos o un ciberataque; sin embargo, en algunos casos, puede ser algo menos crítico, como una configuración incorrecta, un intento de intrusión o una violación de políticas.

Algunos ejemplos de un ciberataque incluyen un atacante que hace que nuestra red o sistemas sean inaccesibles, desfigura (cambia) el sitio web público y una violación de datos (roba datos de la empresa).

`¿Cómo respondería a un ciberataque?` La respuesta a incidentes especifica la metodología que se debe seguir para manejar un caso de este tipo. El objetivo es reducir el daño y recuperarse en el menor tiempo posible. Lo ideal sería desarrollar un plan listo para la respuesta a incidentes.

Las 4 fases principales del proceso de respuesta a incidentes son:

1. `Preparación`: Esto requiere un equipo capacitado y listo para manejar incidentes. Lo ideal es que se implementen varias medidas para evitar que ocurran incidentes en primer lugar.
2. `Detección y análisis`: El equipo tiene los recursos necesarios para detectar cualquier incidente; además, es esencial analizar más a fondo cualquier incidente detectado para conocer su gravedad.
3. `Contención, Erradicación y Recuperación`: Una vez que se detecta un incidente, es fundamental evitar que afecte a otros sistemas, eliminarlo y recuperar los sistemas afectados. Por ejemplo, cuando notamos que un sistema está infectado con un virus informático, nos gustaría detener (contener) la propagación del virus a otros sistemas, limpiarlo (erradicarlo) y garantizar una recuperación adecuada del sistema.
4. `Actividad Posterior al Incidente`: Después de una recuperación exitosa, se elabora un informe y se comparte la lección aprendida para evitar incidentes similares en el futuro.

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/Incidente.png">
</p>

#### Análisis de Malware
Malware significa **Software Malicioso**. El software se refiere a programas, documentos y archivos que se pueden guardar en un disco o enviar a través de la red. El malware incluye muchos tipos como:

- Un `virus` es un fragmento de código (parte de un programa) que se adjunta a un programa. Está diseñado para propagarse de un equipo a otro; además, funciona modificando, sobrescribiendo y eliminando archivos una vez que infecta un equipo. El resultado varía desde que el equipo se vuelve lento hasta que queda inutilizable.
- Un `troyano` es un programa que muestra una función deseable pero oculta una función maliciosa por debajo. Por ejemplo, una víctima puede descargar un reproductor de video de un sitio web sospechoso que le da al atacante control total sobre su sistema.
- Un `ransomware` es un programa malicioso que encripta los archivos del usuario. El cifrado hace que los archivos sean ilegibles sin conocer la contraseña de cifrado. El atacante ofrece al usuario la contraseña de cifrado si el usuario está dispuesto a pagar un *"rescate"*.

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/Ransomware.png">
</p>

El análisis de malware tiene como objetivo conocer estos programas maliciosos mediante diversos medios:

- El `análisis estático` funciona inspeccionando el programa malicioso sin ejecutarlo. Por lo general, esto requiere un conocimiento sólido del lenguaje ensamblador (el conjunto de instrucciones del procesador, es decir, las instrucciones fundamentales de la computadora).

- El `análisis dinámico` funciona ejecutando el malware en un entorno controlado y monitoreando sus actividades. Le permite observar cómo se comporta el malware cuando se ejecuta.

### Responda las preguntas a continuación
1. ¿Cómo llamaría a un equipo de profesionales de seguridad cibernética que monitorea una red y sus sistemas para detectar eventos maliciosos? `Security Operations Center`

2. ¿Qué significa DFIR? `Digital Forensics and Incident Response`

3. ¿Qué tipo de malware requiere que el usuario pague dinero para recuperar el acceso a sus archivos? `ransomware`

## Ejemplo práctico de Seguridad Defensiva
¿Cuál sería una tarea típica que se realizaría como analista de seguridad? Haga clic en *"Ver Sitio"* para seguir hasta que obtenga la bandera. (Si es la primera vez que obtiene banderas, una bandera puede verse como una cadena de texto que recibe una vez que completa una tarea. Un ejemplo de bandera es `FLAG{WORDS_AND_MORE}`.)

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Defensiva/Ejercicio.png">
</p>

Formas parte de un centro de operaciones de seguridad (SOC) responsable de proteger un banco. El SOC de este banco utiliza un sistema de gestión de eventos e información de seguridad (SIEM).

Un SIEM recopila información y eventos relacionados con la seguridad de varias fuentes y los presenta a través de un sistema.

Por ejemplo, se te notificaría si hay un intento de inicio de sesión fallido o un intento de inicio de sesión desde una ubicación geográfica inesperada. Además, con la llegada del aprendizaje automático, un SIEM podría detectar un comportamiento inusual, como un usuario que inicia sesión a las 03:00 Hrs cuando normalmente inicia sesión solo durante el horario laboral.

En este ejercicio, interactuaremos con un SIEM para monitorear los diferentes eventos en nuestra red y sistemas en tiempo real. Algunos de los eventos son típicos e inofensivos; otros pueden requerir una mayor intervención de nuestra parte. Encuentra el evento marcado en rojo, anótalo y haz clic en él para inspeccionarlo más a fondo.

A continuación, queremos obtener más información sobre la actividad o el evento sospechoso. El evento sospechoso podría haber sido activado por un evento, como un usuario local, una computadora local o una dirección IP remota.

Para enviar y recibir correo postal, se necesita una dirección física; de manera similar, se necesita una dirección IP para enviar y recibir datos a través de Internet. Una dirección IP es una dirección lógica que le permite comunicarse a través de Internet.

Inspeccionamos la causa del desencadenante para confirmar si el evento es realmente malicioso. Si es malicioso, debemos tomar las medidas correspondientes, como informar a otra persona en el SOC y bloquear la dirección IP.

### Responde las preguntas a continuación
1. ¿Cuál es la bandera que obtuvo al seguir el procedimiento? `THM{THREAT-BLOCKED}`
