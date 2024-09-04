---
layout: single
title: Cadena de ataque cibernético (Cyber Kill Chain)
excerpt: "El marco de trabajo de la cadena de ataque cibernético está diseñado para identificar y prevenir intrusiones en la red. Aprenderá lo que los adversarios deben hacer para lograr sus objetivos."
date: 2024-08-25
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Cadena-Ataque.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Portada.png">

## Introducción

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Cadena-Ataqu3.png">


El término Kill Chain es un concepto militar relacionado con la estructura de un ataque. Consiste en la identificación del objetivo, le decisión y orden de atacar el objetivo y, finalmente, la destrucción del objetivo.

Gracias a Lockheed Martin, una empresa aeroespacial y de seguridad global, que estableció el marco Cyber Kill Chain para la industria de la ciberseguridad en 2011 basado en el concepto militar. El marco define los pasos utilizados porr adversarios o actores maliciosos en el ciberespacio. Para tener éxito, un adversario debe pasar por todas las fases de Kill Chain. Pasaremos por las fases de ataque y te ayudaremos a comprender mejor a los adversarios y sus técnicas utilizadas en el ataque para defenderte.

Entonces, ¿por qué es importante entender cómo funciona Cyber Kill Chain? Cyber Kill Chain lo ayudará a comprender y protegerse contra ataques de ransomware, violaciones de seguridad y amenazas persistentes avanzadas (APT). Puede utilizar Cyber Kill Chain para evaluar la seguridad de su red y sistema identificando controles de seguridad faltantes y cerrando ciertas brechas de seguridad según la infraestructura de su empresa.

Al comprender Kill Chain como analista de SOC, investigador de seguridad, cazador de amenazas o respondedor de incidentes, podrá reconocer los intentos de intrusión y comprender las metas y objetivos del intruso.

Exploraremos las siguientes fases de ataque en esta sala:

- Reconocimiento
- Armamento
- Entrega
- Explotación
- Instalación
- Comando y Control
- Acciones sobre objetivos

- `Objetivos de aprendizaje`: En esta sala, aprenderá sobre cada fase del Cyber Kill Chain Framework, las ventajas y desventajas de la Cyber Kill Chain tradicional.

- `Resultado`: Como resultado, estarás preparado para reconocer diferentes fases o etapas del ataque llevado a cabo por un adversario y podrás romper la "cadena de muerte".

### Responde las preguntas a continuación
1. Lea lo anterior

## Reconocimiento

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Reconocimiento.png">


Para saber quée es el reconocimiento desde la perspectiva del atacante, primero definamos el término reconocimiento. El reconocimiento consiste en descubrir y recopilar información sobre el sistema y la víctima. La fase de reconocimiento es la fase de planificación para los adversarios.

OSINT (Inteligencia de Código Abierto) también se incluye en el ámbito del reconocimiento. OSINT es el primer paso que debe completar un atacante para llevar a cabo las fases posteriores de un ataque. El atacante necesita estudiar a la víctima recopilando toda la información disponible sobre la empresa y sus empleados, como el tamaño de la empresa, las direcciones de correo electronico y los números de toléfono de recursos disponibles públicamente para determinar el mejor objetivo para el ataque.

También puede obtener más información sobre OSINT en este artículo de Varonis, [¿Qué es OSINT?](https://www.varonis.com/blog/what-is-osint). Veámoslo desde la perspectiva del atacante, que inicialmente no sabe qé empresa quiere atacar.

Este es el escenario: un atacante malicioso que se hace llamar "Megatron" decide llevar a cabo un ataque muy sofisticado que ha estado planeando durante años; Ha estado estudiando e investigando diferentes herramientas y técnicas que podrían ayudarlo a llegar a la última fase de Cyber Kill Chain. Pero primero necesita empezar desde la fase de Reconocimiento.

Para operar en esta fase, el atacante necesitaría realizar OSINT. Echemos un vistazo a la recolección de correo electrónico.

La recolección de correo electrónico es el proceso de obtener direcciones de correo electrónico de servicios públicos, pagos o gratuitos. Un atacante puede utilizar la recolección de direcciones de correo electrónico para un ataque de phishing (un tipo de ataque de ingeniería social utilizado para robar datos confidenciales, incluidas credenciales de inicio de sesión y números de tarjetas de crédito). El atacante dispondrá de un gan arsenal de herramientas con fines de recconocimiento. Éstos son algunos de ellos:

- `theHarvester`: Además de recopilar correos electrónicos, esta herramienta también es capaz de recopilar nombres, subdominios, IP y URL utilizando múltiples fuentes de datos públicos.
- `Hunter.io`: Esta es una herramienta de búsqueda de correo electrónico que le permitirá obtener información de contacto asociada con el dominio.
- `OSINT Framework`: OSINT Framework proporciona una colección de herramientas OSINT basadas en varias categorias.

Un atacante también utilizaría sitios web de redes sociales como Linkedin, Facebook, Twitter e Instagram para recopilar información sobre una víctima específica a la que le gustaría atacar o sobre la empresa. La información encontrada en las redes sociales puede resultar beneficiosa para que un atacante lleve a cabo un ataque de phishing.

### Responde las preguntas a continuación
1. ¿Cuál es el nombre de Intel Gathering Tool, que es una interfaz basada en web para herramientas y recursos comunes para inteligencia de código abierto? `OSINT Framework`

2. ¿Cuál es la definición del proceso de recopilación de correos electrónicos durante la etapa de reconocimiento? `email harvesting` -> Cosecha de correo electrónico

## Arma (Weaponization)

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Arma.png">

Después de una exitosa etapa de reconocimiento, "Megatron" trabajaría para crear un "arma de destrucción". Preferiría no interactuar con la víctima directamente y, en cambio, creará un "armamento" que, según Lockheed Martin, combina malware y se explotará en una carga útil entregable. La mayoría de los atacantes generalmente usan herramientas automatizadas para generar el malware o se refieren a Darkweb paara comprar el malware. Actores más sofisticados o APT patrocinados por la nación (grupos de amenazas persistentes avanzados) escribirían su malware personalizado para hacer que la muestra de malware sea única y evadir la detección del objetivo.

Primero definamos algo de terminología antes de analizar la fase de armas.

- El `malware` es un programa o software diseñado para dañar, interrumpir u obtener acceso no autorizado a una computadora.
- Un `exploit` es un programa o código que aprovecha la vulnerabilidad o la falla en la aplicación o el sistema.
- Una `carga útil (payload)` es un código malicioso que el atacante ejecuta en el sistema.

Continuando con nuestro adversario, "Megatron" elige...

"Megatron" elige comprar una carga útil ya escrita de otra persona en Darkweb, para que pueda pasar más tiempo en las otras fases.

En la fase de armas, el atacante:

- Cree un documento de Microsoft Office infectado que contenga scripts macro o VBA (Visual Basic para aplicaciones). Si desea aprender sobre Macro y VBA, consulte el artículoo [Introducción a Macros y VBA para Script Kiddies](https://www.trustedsec.com/blog/intro-to-macros-and-vba-for-script-kiddies) de TrustedSec.
- Un atacante puede crear una carga útil maliciosa o un gusano muy sofisticado, implantarlo en las unidades USB y luego distribuirlos en público. Un ejemplo del virus.
- Un atacante elegiría técnicas de comando y control (C2) para ejecutar los comandos en la máquina de la víctima o entregar más cargas útiles. Puede leer más sobre las técnicas C2 en [Mitre ATT & CK](https://attack.mitre.org/tactics/TA0011/).
- Un atacante seleccionaría un implante de puerta trasera (backdoor), la forma de acceder al sistema informático, que incluye evitar los mecanismos de seguridad.

### Responda las preguntas a continuación
1. Este término se conoce como un grupo de comandos que realizan una tarea específica. Puede pensar en ellas como subrutinas o funciones que contienen el código qye la mayoría de los usuarios usan para automatizar tareas de rutina. Pero los actores maliciosos tienden a usarlos para fines maliciosos e incluyen los documentos de Microsoft Office. ¿Puede proporcionar el término? `Macro`

## Entrega (Delivery)

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Entrega.png">


La fase de entrega es cuando "Megatron" decide elegir el método para transmitir la carga útil o el malware. Tiene muchas opciones para elegir:

- `Correo electrónico de Phishing`: Después de realizar el reconocimiento y determinar los objetivos para el ataque, el actor malicioso elaboraba un correo electrónico malicioso que se dirigiría a una persona específica (ataque de pezing) o a varias personas en la empresa. El correo electrónico contendría una carga útil o malware. Por ejemplo, "Megatron" aprendería que Nancy del departamento de ventas de la compañía A constantemente les gustará las publicaciones en Linkedin de Scott, un gerente de entrega de servicios de la Compañía B. Le daría una segunda suposicción de que ambos se comunican entre sí mediante correos electrónicos de trabajo. "Megatron" elaboraría un correo electrónico con el nombre y el apellido de Scott, haciendo que el dominio se vea similar a la compañía en el que Scott está trabajando. Luego, un atacante enviaría un correo electrónico falso de "factura" a Nancy, que contiene la carga útil.
- `Distribuir unidades USB infectadas` en lugares públicos como cafeterías, estacionamientos o en la calle. Un atacante podría decidir llevar a cabo un sofisticado ataque de caída USB imprimiendo el logotipo de la compañía en las unidades USB y enviándolas por correo a la compañía mientras pretende ser un cliente que envía los dispositivos USB como regalo. Puede leer sobre uno de estos ataques similares en CSO en línea [CyberCriminal Group](https://www.csoonline.com/article/569163/cybercriminal-group-mails-malicious-usb-dongles-to-targeted-companies.html) envía dongles USB maliciosos a empresas dirigidas.
- `Ataque de Agujero`: Un atacante de agujero de riego es un ataque objetivo diseñado para apuntar a un grupo específico de personas al comprometer el sitio web que generalmente están visitando y luego redirigirlos al sitio web malicioso de la elección de un atacante. El atacante buscaría una vulnerabilidad conocida para el sitio web e intentaría explotarlo. El atacante alentaría a las víctimas a visitar el sitio web enviando correos electrónicos "inofensivos" que señalen la URL maliciosa para que el ataque funcione de manera más eficiente. Después de visitar el sitio web, la víctima descargaría involuntariamente malware o una aplicación maliciosa a su computadora. Este tipo de ataque se llama descarga de manejo. Un ejemplo puede ser una ventana emergente maliciosa para descargar una extensión de navegador falso.

### Responda las preguntas a continuación
1. ¿Cuál es el nombre del ataque cuando se realiza contra un grupo específico de personas, y el atacante busca infectar el sitio web de que el grupo de personas mencionado eestá constantemente de visita? `Watering hole attack` -> Ataque de Agujero.

## Explotación (Exploitation)

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Explotacion.png">


Para obtener acceso al sistema, un atacante necesita explotar la vulnerabilidad. En esta fase, "Megatron" se volvió un poco creaativo: creó dos correos electrónicos de phishing, uno que contiene un enlace de phishing a una página de inicio de sesión de Office 365 falsa y otra que contiene un archivo adjunto macro que ejeccutaría ransomware cuando la víctima lo abre. "Megatron" entregó con éxito sus hazañas y consiguió dos víctimas para hacer clic en el enlace malicioso y abrir el archivo malicioso.

Después de obtener acceso al sistema, el actor malicioso podría explotar las vulnerabilidades basadas en software, sistema o servidor para intensificar los privilegios o moverse lateralmente a través de la red. Según [CrowdStrike](https://www.crowdstrike.com/cybersecurity-101/lateral-movement/), el movimiento lateral se refiere a las técnicas que un actor malicioso utiliza después de obtener acceso ainicial a la máquina de la víctima para avanzar más profundamnete en una red para obtener datos confidenciales.

Si desea obtener más información sobre las vulnerabilidades basadas ens ervidor o basadas en la web, consulte el [TreyHackMe Room OWASP Top 10](https://tryhackme.com/r/room/owasptop10).

El atacante también podría aplicar un "exploit de día cero" en esta etapa.. Según [FireEye](https://www.trellix.com/security-awareness/cybersecurity/what-is-a-zero-day-exploit/), el "exploit de día cero" o vulnerabilidad de día cero es un exploit desconocido en la naturaleza qye expone una vulnerabilidad en el software o el hardware y puede crear problemas complicados mucho antes de que alguien se dé cuenta de que algo está mal. Se deja mal. No hay oportunidad de detección al principio.

Estos son ejemplos de cómo un atacante lleva a cabo la explotación:

- La víctima desencadena el exploit abriendo el archivo adjunto del correo electrónico o haciendo clic en un enlace malicioso.
- USando un exploit de día cero.
- Explotar el software, el hardware o incluso las vulnerabilidades humanas.
- Un atacante desencadena un exploit para las vulnerabilidades basadas en servidores.

### Responda las preguntas a continuación
1. ¿Puede proporcionar el nombre para un ataque cibernético dirigido a una vulnerabilidad de software que se descompone para el antivirus o los proveedores de software? `Zero-day` -> Ataque de día cero.

## Instalación (Installation)

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Instalacion.png">


Como has aprendido de la fase de armas, la puerta trasera permite que un atacante pase por alto las medidas de seguridad y oculte el acceso. Una puerta trasera (backdoor) también se conoce como punto de acceso.

Una vez que el atacante obtiene acceso al sistema, querría reaccionar el sistema si pierde la conexión a él o si se detectó y se eliminó el acceso inicial, o si el sistema está paercheado más tarde. Ya no tendrá acceso a ello. Es entonces cuando el atacante necesita instalar una [puerta trasera persistente](https://www.offsec.com/metasploit-unleashed/persistent-backdoors/). Una puerta trasera persistente permitirá al atacante acceder al sistema que comprometió en el pasado. Puede consultar la sala de persistencia de Windows en [tryHackme](https://tryhackme.com/room/windowslocalpersistence) para aprender como un atacante puede lograr la persisntencia en las ventanas.

La persisntencia se puede lograr a través de:

- `Instalación de un Shell Web en el servidor web`: Un shell web es un script malicioso escrito en lenguajes de programación de desarrollo web como ASP, PHP o JSP utilizado por un atacante para mantener el acceso al sistema comprometido. Debido a la simplicidad del shell web y el formato de archivo (.php, .asp, .aspx, .jsp, etc.) puede ser difícil de detectar y puede clasificarse como benigna. Puede ver este gran artículo publicado por Microsoft en varios [ataques de Shell Web](https://www.microsoft.com/en-us/security/blog/2021/02/11/web-shell-attacks-continue-to-rise/).
- `Instalar un backdoor en la máquina víctima`: Por ejemplo, el atacante puede usar Meterpreter para instalar un backdoor en la máquina víctima. [Meterpreter](https://www.offsec.com/metasploit-unleashed/meterpreter-backdoor/) es una carga útil del marco de MetaSploit que proporciona un caparazón interactivo del cual un atacante puede interactuar con la máquina víctima de forma remota y ejecutar el código malicioso.
- `Creación o modificación de los servicios de Windows`: Esta tecnica se conoce como [T1543.003](https://attack.mitre.org/techniques/T1543/003/) en Miter ATT & CK (Miter ATT & CK es una base de conocimiento de tácticas y técnicas adversas basadas en escenarios del mundo real). Un atacante puede crear o modificar los servicios de Windows para ejecutar los scripts maliciosos o las cargas útiles regularmente como parte de la persistencia. Un atacante puede usar las herramientas como SC.EXE (SC.EXE le permite crear, iniciar, detener, consultar o eliminar cualquier servicio de Windows) y [Reg](https://attack.mitre.org/software/S0075/) para modificar las configuraciones de servicio. El atacante también puede [disfrazar la carga útil](https://attack.mitre.org/techniques/T1036/) maliciosa utilizando un nombre de servicio que se sabe que está relacionado con el sistema operativo o el software legítimo.
- `Agregar la entrada a las "Claves de ejecución" para la carga útil maliciosa en el registro o en la carpeta de inicio`: Al hacer eso, la carga útil se ejecutará cada vez que el usuario inicie sesión en la computadora. Según Miter ATT & CK, hay una ubicación de carpeta de inicio para cuentas de usuario individuales y una carpeta de inicio de todo el sistema que se verificará sin importar qué cuenta de usuario inicie sesión.

Puede leer más sobre las claves de ejecución del registro / carpeta de inicio en una de las técnicas [MITER ATT & CK](https://attack.mitre.org/techniques/T1547/001/).

En esta fase, el atacante también puede usar la [técnica de tiempo]() para evitar la detección del investigador forense y también para que el malware aparezca como parte de un programa legítimo. La técnica de tiempo permite a un atacante modificar las marcas de tiempo del archivo, incluidas los tiempos de modificar, acceso, crear y cambiar.

### Responda las preguntas a continuación.
1. ¿Puede proporcionar la técnica utilizada para modificar los atributos de tiempo de archivo para ocultar nuevos o cambios en los archivos existentes? ` Timestomping`

2. ¿Puede nombrar el guión malicioso plantado por un atacante en el servidor web para mantener el acceso al sistema comprometido y permitir que el servidor web se acceda de forma remota? `web shell`

## Comando y Control (Command & Control)

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Comando-Control.png">


Después de obtener la persistencia y ejecutar el malware en la máquina víctima, "Megatron" abre el canal C2 (Comando y Control) a través del malware para controlar y manipular de forma remota a la víctima. Este término también se conoce como C&C o C2 Beaconing como un tipo de comunicación maliciosa entre un servidor C&C y malware en el host infectado. El host infectado se comunicará constantemente con el servidor C2; de ahí también proviene el término beaconing.

El punto final comprometido se comunicará con un servidor externo configurado por un atacante para establecer un canal de comando y control. Después de establecer la conexión, el atacante tiene control total de la máquina de la víctima. Hasta hace poco, IRC (Internet Relay Chat) era el canal C2 tradicional utilizado por los atacantes. Esto ya no es así, ya que las soluciones de seguridad modernas pueden detectar fácilmente el tráfico IRC malicioso.

Los canales C2 más comunes que utilizan los adversarios en la actualidad:

- Los `protocolos HTTP` en el puerto 80 y HTTPS en el puerto 443: Este tipo de señalización combina el tráfico malicioso con el legítimo y puede ayudar al atacante a evadir los firewalls.
- `DNS (Servidor de Nombres de Dominio)`: La máquina infectada realiza solicitudes DNS constantes al servidor DNS que pertenece a un atacante; este tipo de comunicación C2 también se conoce como tunelización DNS.

Es importante tener en cuenta que un adversario u otro host comprometido puede ser el propietario de la infraestructura C2.

### Responda las preguntas a continuación
1. ¿Qué es la comunicación C2 en la que la víctima realiza solicitudes DNS regulares a un servidor DNS y un dominio que pertenecen a un atacante? `DNS Tunneling`

## Acciones sobre Objetivos (Exfiltración)

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Exfiltracion.png">

Después de pasar por 6 fases del ataque, "Megatron" puede finalmente lograr sus objetivos, lo que significa tomar medidas sobre los objetivos originales. Con acceso directo al teclado, el atacante puede lograr lo siguiente:

- Recopilar las credenciales de los usuarios.
- Realizar una escalada de privilegios (obtener acceso elevado como el acceso de administrador de dominio desde una estación de trabajo explotando la configuración incorrecta).
- Reconocimiento interno (por ejemplo, un atacante puede interactuar con el software interno para encontrar sus vulnerabilidades).
- Movimiento lateral a través del entorno de la empresa.
- Recopilar y exfiltrar datos confidenciales.
- Eliminar las copias de seguridad y las instantáneas. Shadow Copy es una tecnología de Microsoft que puede crear copias de seguridad, instantáneas de archivos de la computadora o volúmenes.
- Sobrescribir o corromper datos.

### Responda las preguntas a continuación
1. ¿Puede proporcionar una tecnología incluida en Microsoft Windows que pueda crear copias de seguridad o instantáneas de archivos o volúmenes en la computadora, incluso cuando están en uso? `Shadow Copy`

## Análisis de Práctica

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Analisis-Practica.png">


Esperamos que hayas disfrutado de esta sala. Para fortalecer tus conocimientos, hagamos un análisis de práctica. A continuación, te presentamos el escenario del mundo real que debes abordar:

El infame ciberataque a Target, que provocó una de las mayores violaciones de datos de la historia, tuvo lugar el 27 de noviembre del 2013. El 19 de diciembre del 2013, Target publicó una [declaración](https://corporate.target.com/news-features/article/2013/12/important-notice-unauthorized-access-to-payment-ca) que confirmaba la violación, y afirmaba que aproximadamente 40 millones de cuentas de tarjetas de crédito y débido se vieron afectadas entre el 27 de noviembre y el 15 de diciembre de 2013. Target tuvo que pagar la multa de 18.5 millones de dólares según los [términos del acuerdo](https://www.attorneygeneral.gov/taking-action/settlement-reached-with-target-following-major-consumer-data-breach/) de conciliación multiestatal. Este se considera el acuerdo de conciliación de datos más grande de la historia.

### ¿Cómo se produjo la violación de datos?
Implementa el sitio estático adjunto a esta tarea y aplica tus habilidades para crear la Cyber Kill Chain de este escenario. Aquí hay algunos consejos para ayudarlo a completar la práctica:

1. Agregue cada elemento de la lista en el formulario de entrada de Kill Chain correcto en el laboratorio de sitio estático:
    - Explotar la Aplicación Pública
    - Datos del Sistema Local
    - PowerShell
    - Secuestro de enlazador dinámico
    - Adjunto de Phishing Selectivo
    - Canales de Respaldo

2. Use el botón "Verificar Respuestas" para verificar si las respuestas son correctas (las respuestas incorrectas estarán subrayadas en rojo).

### Responda las preguntas a continuación
1. ¿Cuál es la bandera después de completar el sitio estático? `THM{7HR347_1N73L_12_4w35om3}`

## Conclusión

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Cadena-Ataque/Conclusion.png">


Cyber Kill Chain puede ser una gran herramienta para mejorar la defensa de la red. ¿Es perfecta y puede ser la única herramienta en la que confiar? No.

La Cyber Kill Chain tradicional o Lockheed Martin Cyber Kill Chain se modificó por última vez en 2011, que, si recuerdas, es la fecha de su creación. La ausencia de actualizaciones y modificaciones crea brechas de seguridad.

La Cyber Kill Chain tradicional fue diseñada para proteger el perímetro de la red y proteger contra amenazas de malware. Pero las amenazas de ciberseguridad se han desarrollado drásticamente en la actualidad, y los adversarios están combinando múltiples TTP (tácticas, técnicas y procedimientos) para lograr su objetivvo. Los adversarios son capaces de derrotar la inteligencia de amenazas modificando los hashes de archivos y las direcciones IP. Las empresas de soluciones de seguridad están desarrollando tecnologías como IA (Inteligencia Artificial) y diferentes algoritmos para detectar incluso cambios leves y sospechosos.

Dado que el enfoque principal del marco está en la distribución de malware y la seguridad de la red, la Cyber Kill Chain tradicional no podrá identificar amenazas internas. Según la CISA, "la amenaza interna es la posibilidad de que un miembro de la organización utilice su acceso autorizado o su conocimiento de una organización para dañarla".

Recomendamos no solo confiar en el modelo tradiccional Cyber Kill Chain, ,sino también consultar MITRE ATT&CK y Unified Kill Chain para aplicar un enfoque más integral a sus metodologías de defensa.

### Responda las preguntas a continuación
- Lea lo anterior.