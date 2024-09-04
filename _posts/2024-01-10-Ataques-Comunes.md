---
layout: single
title: Ataques Comunes
excerpt: "Con ejercicios prácticos, descubre cómo se producen los ataques más comunes y mejora tu higiene cibernética para estar más seguro en Internet."
date: 2024-08-22
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Ataques.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Portada.png">

## (Información) Introducción
Nuestra existencia en un mundo digital hace que sea imperativo que entendamos y podamos proteger contra ataques comunes.

Esta sala discutirá algunas de las técnicas más comunes utilizadas por los atacantes para atacar a las personas en línea. También enseñará alfgunas de las mejores formas de prevenir el éxito de cada técnica.

Sin más preáambulos, ¡comencemos!

### Responda las preguntas a continuación
1. ¡Comencemos!

## (Ataques Comunes) Ingeniería Social
La `Ingeniería Social` es el término utilizado para describir cualquier ataque cibernético donde un humano (en lugar de una computadora) es el objetivo; Por esta razón, a veces se le conoce como `pirateo de personas`. Por ejemplo, si un atacante desea obtener la contraseña de una víctima, podría intentar adivinar o hacer una fuerza bruta, o simplemente [podrían preguntarle](https://www.youtube.com/watch?v=opRMrEfAIiI&t=42s).

Mientras que el ejemplo vinculado anteriormente es relativamente sencillo, los ataques de ingeniería social pueden volverse muy complejos y a menudo resulta en un atacante que gane un control significativo sobre la vida de un objetivo, tanto en línea como fuera de línea. Los ataques de ingeniería social a menudo son de varias capas y se intensifican debido al efecto de la bola de nieve. Por ejemplo, un atacante puede comenzar obteniendo una pequeña cantidad de información disponible en público de la presencia de las redes sociales de una víctima, que luego podrían usar para obtener más información de, por ejemplo, su teléfono o proveedor de banda ancha. La información obtenida de la segunda etapa podría usarse para obtener información más útil, luego aumentar el paso a paso a algo como la cuenta bancaria de la víctima.

¡La mejor manera de entender la ingeniería social es verla en accón! Estos videos de [DefCon23](https://www.youtube.com/watch?v=fHhNWAKw0bY&t=100s) una de las conferencias de piratería más grandes del mundo y [CNN](https://www.youtube.com/watch?v=PWVN3Rq4gzw) demuestran parte del inmenso poder en la ingeniería social. ¡Ambos valen la pena ver!

### Otras Formas de Ingeniería Social
Los piratas informáticos carismáticos que llaman a su compañía telefónica y toman posesión de su cuenta es una forma de ingeniería social; Sin embargo, la ingeniería social es un gran tema, que abarca cualquier ataque que se basa en engañar a los humanos para que le dé acceso al atacante, en lugar de atacar la tecnología directamente. Si bien la interacción directa con objetivos es el estilo más común de ingeniería social, otros ejemplos incluyen dejar caer dispositivos de almacenamiento USB en público (por ejemplo, en los aparcamientos de la compañía) con la esperanza de que alguien (a menudo un empleado de una empresa) lo recoja y lo enchufe a un computador sensible. En una línea similar, los atacantes pueden dejar un "cable de carga" conectado a un zócalo en un lugar público. En realidad, el cable contiene software malicioso como keyloggers o herramientas para tomar el control del dispositivo de la víctima.

```text
Caso práctico: Stuxnet

Stuxnet era el nombre que se le daba a un virus informático particularmente desagradable (supuestamente desarrollado por los gobiernos de los Estados Unidos e Israel) que se utilizó originalmente para atacar el programa nuclear de Irán en 2009. Debido a su capacidad como "gusano" de autorreplicarse (es decir, clonarse a sí mismo en distintas redes, incluida Internet), el virus escapó y se extendió mucho más de lo que se pretendía. Ahora también existen múltiples variantes, lo que convierte a Stuxnet en un arma particularmente contundente y notoria. Puede leer más sobre los antecedentes de Stuxnet aquí.

Lo que hace que Stuxnet sea particularmente interesante para esta sección es el método original de infección. El virus puede clonarse a sí mismo en distintas redes, pero eso no ayuda mucho cuando la red objetivo es una instalación de desarrollo de armas nucleares sin acceso a Internet. La pregunta era: ¿cómo se puede introducir un virus en una red que no deja entrar ni salir nada? La respuesta fue sencilla: dejar dispositivos USB maliciosos en lugares donde los trabajadores de las empresas que trabajaban con la instalación los pudieran encontrar y esperar que alguno de ellos los conectara a un ordenador de trabajo. En este caso, la apuesta funcionó: Stuxnet causó graves daños al programa nuclear iraní y destruyó de hecho muchas de las centrifugadoras nucleares.
```

En resumen, los límites de la ingeniería social están en los límites de la imaginación de un atacante. Un buen ingeniero social puede (y lo hará) utilizar una plétora de trucos psicológicos en cualquier contexto plausible para "hackear" a sus objetivos.

### Mantenerse a salvo de los ataques de Ingeniería Social
En muchos sentidos, es muy complicado mantenerse a salvo de la ingeniería social, ya que no siempre será usted con quién el atacante esté hablando, sino más bien alguien que puede darles lo que necesitan sin su consentimiento (por ejemplo, llamando a su banco haciendose pasar por usted, para así acceder a su cuenta bancaria). Dicho esto, todavía hay medidas que puede tomar para protegerse de los ataques de ingeniería social:

- Asegúrese siempre de configurar múltiples formas de autenticación y asegúrese de que los proveedores las respeten. Por ejemplo, configure respuestas difíciles de adivinar, o incorrectas, a las preguntas de seguridad (¡asegúrese de guardar las respuestas en un lugar seguro!) y asegúrese de que se le hagan estas preguntas cuando intente acceder a las cuentas por telefono.
- Nunca conecte dispositivos externos (por ejemplo, USB, CD, etc.) a una computadora que le importe o que esté conectada a otros dispositivos. Lo ideal es no conectar ningún dispositivo y, en su lugar, dárselo a la polícia local para que lo guarde.
- Insista siempre en que le muestren una prueba de identidad cuando un desconocido lo llame o le envíe un mensaje diciendo que trabaja para una emrpesa cuyos servicios usted utiliza. Siempre que sea posible, confirme con  un número de teléfono o una dirección de correo electrónico conocidos que la llamada o mensaje que recibieron eran legítimos (es decir, utilice un método de confianza para ponerse en contacto con la empresa para confirmarlo.) Recuerde que ningún empleado legítimo le pedirá nunca su contraseña ni ninguna otra información que proteja su cuenta.

### Responda las preguntas a continuación
1. Lea la información de la tarea y mire los videos adjuntos.
2. ¿Cuál era el objetivo original de Stuxnet? `the Iran nuclear programme (programa nuclear de Irán)`

## (Ataques Comunes) Ingeniería Social: Phishing
### Descripción General
El phishing es uno de los tipos de ataque cibernético más comunes empleados por estafadores y malos actores, dirigidos a individuos y empresas indiscriminadamente. En muchos casos, el phishing es el vector de ataque inicial utilizado para obtener acceso a la infraestructura de una empresa antes de realizar nuevos ataques contra la red corporativa. Si bien hay muchas herramientas automatizadas ahora disponibles para ayudar a combatir las amenazas de phishing, el phishing sigue siendo uno de los vectores de ataque más prolíficos.

### ¿Qué es el Phishing?

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Phishing.png">

El phishing es una subsección de la ingeniería social. Mientras que la ingeniería social es un término muy general utilizado para descubrir cualquier ataque que aproveche un sistema humano en lugar de un sistema informático, Phishing describe específicamente los ataques mediante los cuales un estafador u otro atacante engaña a una víctima para abrir una página web maliciosa enviándoles un mensaje de texto, correo electrónico u otra forma de correspondencia en línea. Tradicionalmente, el phishing simplemente se refería a los correos electrónicos; Sin embargo, en los días de mensajes instantáneos, mensajes de texto y videollamadas, el término ha evolucionado para cubrir estas otras categorías. Estas otras formas a veces se denominan individualmente como "amordazos" (phishing sobre SMS) y "salpicaduras" (phishing sobre chat de voz) respectivamente.

Estos ataques están muy extendidos (de hecho, ¡las posibilidades de que no hayan estado en el extremo receptor de tal ataque son escasas!) y con frecuencia se despliegan en escalas masivas utilizando listas de números de telefono y direcciones de correo electrónico filtradas o robadas.

Los mensajes de phishing generalmente implementan trucos psicológicos (por ejemplo, inducir un falso sentido de urgencia para que las víctimas actúen con precisión) y casi siempre implican que una víctima haga clic en un enlace a una aplicación web propiedad del atacante. A menudo se le pide a la víctima que ingrese información confidencial, por ejemplo, detalles de inicio de sesión o información de la tarjeta de crédito, momento en el que el sitio malicioso almacena la información y el ataque está completo. Alternativamente. la víctima puede instalar inadvertidamente malware desde la página maliciosa, lo que le da a un atacante un punto de entrada a su dispositivo y red.

Hay tres tipos principales de ataques de phishing:

<table align="center">
    <tr>
        <th>Tipo de Ataque</th>
        <th>Definición</th>
    </tr>
    <tr>
        <td>Phishing General</td>
        <td>Un ataque de phishing masivo simple que no se dirige a nadie en particular, aunque pueden apuntar a grandes grupos (por ejemplo, usuarios de PayPal o clientes de Amazon). Estas campañas a gran escala suelen ser simples y generalmente (pero no siempre) bastantes fáciles de detectar, ya que los mensajes y los sitios maliciosos a menudo no están muy bien elaborados y con frecuencia contienen muchos errores inmediatamente visibles. </td>
    </tr>
    <tr>
        <td>Espeluznante (Spearphishing)</td>
        <td>Más objetivos que el phishing general, los objetivos de Spearphishing para un grupo individual o pequeño (por ejemplo, empleados de una empresa específica). Las campañas de Spearphishing generalmente están mejor elaboradas que la correspondencia y los sitios maliciosos utilizados en el phishing general, ya que están diseñados para apuntar a un grupo en particular, a menudo como parte de una campaña más extensa contra el objetivo. </td>
    </tr>
    <tr>
        <td>Ballenero (Whaling)</td>
        <td>Aún más específico que Spearphishing, ballena apunta a individuos de alto valor (por ejemplo, un ejecutivo de C-suite en una empresa objetivo). Los mensajes generalmente están extremadamente bien elaborados y tienden a ser muy difíciles de detectar.</td>
    </tr>
</table>

Tenga en cuenta que es mucho más probable que encuentre un ataque de phishing general que un ataque de Spearphishing o Whaling en su vida cotidiana. Sin embargo, este puede no ser el caso en su vida laboral, especialmente si usted es un miembro de alto rango de una empresa.

Un ejemplo de un escenario de phishing general (o "pretexto") popular sería recibir un correo electrónico supuestamente de "Amazon", informándole que su cuenta se ha utilizado para comprar un artículo muy costoso (por ejemplo, el último iPad). Luego se le proporciona un enlace para ver su historial de compras. El enlace parece que va a `https://amazon.co.uk`, pero en realidad lo llevará a una aplicación web controlada por el atacante (que se ve idéntico a la página de inicio de sesión de Amazon), pidiéndole que ingrese sus credenciales de Amazon. Cuando ingresa sus credenciales, se le redirige a la página real de Ordenes de Amazon, donde se encuentra que no hay compras no autorizadas ... todavía. Luego, el atacante usará sus credenciales debidamente proporcionadas para pedir artículos costosos con su cuenta.

Este proceso se muestra en el siguiente diagrama:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Campaña-Phishing.png">

1. El atacante envía una campaña de correo electrónico de phishing malicioso.
2. Las posibles víctimas reciben los correos electrónicos: algunas de ellas abren el correo electrónico y hacen clic en el enlace.
3. Las víctimas ingresan a sus credenciales en la página web falsa del atacante.
4. La página web almacena las credenciales o las envía directamente al atacante.
5. El atacante usa las credenciales para acceder al sitio, asumiendo así las cuentas de las víctimas.

Los ataques de phishing funcionan mejor cuando la página web maliciosa imita una página web existente (generalmente conocida). Por esta razón, los atacantes/estafadores generalmente usarán una de las muchas herramientas disponibles gratuitamente para simplemente clonar una página existente, que luego se puede editar a su ocio.

El objetivo final de un ataque de phishing puede variar significativamente dependiendo de quién realice el ataque. Por ejemplo, un estafador de bajo nivel puede ser simplemente después de la información confidencial (por ejemplo, datos bancarios), mientras que un grupo de piratas informáticos maliciosos puede estar apuntando a una organización específica con la intención de causar más daños.

### Identificación de Ataques de Phishing
Muchos ataques genéricos de phishing son relativamente fáciles de detectar; con frecuencia tienen una gramática deficiente y a menudo no abordan a sus víctimas por su nombre (en cambio, dejando los saludos genéricos, por ejemplo, "querido cliente"). Dicho esto, otras instancias pueden ser extremadamente difíciles de detectar, y algunos ataques son lo suficientemente completos como para engañar a los profesionales de ciberseguridad.

Independientemente del tipo de ataque, en muchos casos, el pretexto será plausible, por ejemplo: la estafa de Amazon enumerada anteriormente, o un mensaje (falso) de su "banco" que le dice que ha habido una actividad inusual con su cuenta y para complacer inicie sesión para revisarlo. Esto es especialmente cierto para los ataques de lanza o ballena donde el pretexto se adaptará mucho al objetivo.

Igualmente, el nombre de dominio del sitio malicioso generalmente será similar (pero nunca idéntico) al nombre de dominio utilizado por el sitio web legítimo. Como ejemplo del mundo real de 2021, un grupo de estafadores envió una campaña de phishing masiva sobre SMS, imitando el servicio de correo real británico y utilizando el nombre de dominio `https://royalmai1.co.uk`(a diferencia de https://royalmail.co.uk). Al intercambiar la `l` final por el número uno, los estafadores pudieron registrar con éxito un nombre de dominio que parecía casi idéntico al nombre de dominio de su sitio web clonado; esta es una táctica muy común.

Además, tenga en cuenta que los correos electrónicos de HTML (efectivamente cualquier correo electrónico que se vea elegante y contenga formateo/gráficos) también se pueden usar para enmascarar el nombre de dominio real en uso. Por ejemplo, el texto en el correo electrónico puede ser `https://amazon.co.uk`; sin embargo, el enlace en realidad va a `https://am4zon.co.uk`. Puede ver esto al pasar el mouse sobre el enlace en una aplicación de escritorio: el anlace real debe aparecer en la parte inferior de la pantalla como en este gráfico:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/enlace.png">

¡Puedes probar esto por ti mismo con el siguiente enlace!

[https://tryhackme.com](https://shibes.xyz/)

En una línea similar, la dirección de correo electrónico "desde" en una campaña de phishing basada en el correo electrónico a menudo será sospechoso. Muchas campañas genéricas de phishing masivo simplemente usarán direcciones de `Gmail`, sin molestarse en usar un nombre de dominio asociado con la empresa que están falsificando. Este es un sorteo muerto que el correo electrónico es sospechoso.

La mejor manera de identificar un correo electrónico de phishing es simplemente mantener los ojos abiertos y buscar algo sospechoso, todo menos lo mejor tendrá un error en alguna parte.

### Mantenerse a salvo de los ataques de phishing
Hay una variedad de cosas que puedes (¡y debes!) hacer para mantenerte a salvo de los ataques de phishing:

1. Eliminar correos electrónicos desconocidos o no confiables sin abrirlos. Si puede ver algo sospechoso en el correo electrónico, también repórtelo como spam a su proveedor de correo electrónico o reenvíelo a su departamento de seguridad de TI si recibió el correo electrónico en el trabajo.
2. Nunca abra los archivos adjuntos de correos electrónicos no confiables: esto incluye cualquier archivo adjunto de un contacto legítimo que no esperaba.
3. No haga clic en enlaces incrustrados en correos electrónicos o mensajes. Siempre que sea posible, navegue al sitio web real en su navegador web y acceda al contenido de esa manera. Si debe hacer clic en el enlace, asegúrese de que el nombre de dominio sea correcto y que el enlace apunte a donde cree que lo hace.
4. Siempre asegúrese de que su dispositivo y software antivirus estén actualizados.
5. Evite hacer pública su informacción personal (por ejemplo, dirección de correo electrónico y número de teléfono) si es posible. Si debe publicar datos personales públicamente, cree una dirección de correo electrónico de "quemador (burner)" es una dirección temporal realizada para un propósito, luego destruida poco después, para la ocasión, luego destruya tan pronto como ya no sea necesario.

Vale la pena señalar en este punto que cualquiera puede caer en un ataque de phishing, especialmente uno complejo que se ha hecho que se vea muy realista. Si accidentalmente cae por uno, ¡no se asuste! Asegúrese de cambiar las contraseñas afectadas de inmediato y comuníquese con los servicios de TI si el ataque ocurre en el trabajo.

### Responda las preguntas a continuación
1. Haga clic en el botón verde "Ver Sitio" en la parte superior de esta tarea si aún no lo ha hecho.
2. El sitio estático mostrará una serie de correos electrónicos y mensajes de texto. Se le pedirá que identifique cuáles de estos mensajes son genuinos y cuáles son intentos de phishing. Una vez que haya identificado con éxito todos los mensajes, se le presentará una bandera para ingresar, aquí. ¡Buena suerte!
3. ¿Qué es la bandera? `THM{I_CAUGHT_ALL_THE_PHISH}`

## (Ataques Comunes) Malware y Ransomware
### Descripción General
A pesar del avance constante de las soluciones de software antivirus, el malware (y el ransomware en particular) es una amenaza cada vez mayor.

El malware (abreviatura de "software malicioso") se puede definir como cualquier software diseñado para realizar acciones maliciosas en nombre de un atacante. Hay muchos tipos diferentes de malware: nos centraremos en malware genérico y ransomware específicamente en esta tarea.

Una vez instalados, los atacantes comúnmente usan malware para robar información, causar daños o ejecutar comandos arbitrarios en el sistema infectado. El malware a menudo se usa para realizar un conjunto de tareas denominadas "comando y control" (o C2/C&C). El malware C2 se conecta a un servidor de espera y permite que un atacante controle el sistema infectado de forma remota, a menudo incorporando muchas tareas simples, como el `keylogging` como partes incorporadas del software malicioso.

### Ransomware
Una clase especializada de malware: el ransomware se usa para infectar tantos sistemas como sea posible, encriptando los datos en los dispositivos y manteniéndolo en rescate. Si las víctimas pagan a los atacantes dentro de un plazo establecido (generalmente a través de una criptomoneda como Bitcoin), los datos se devuelven teóricamente.

El ransomware generalmente se extiende explotando vulnerabilidades conocidas en el software comúnmente instalado (por ejemplo, el sistema operativo Microsoft Windows); puede ser muy rápido una vez que comience una infección, y puede exigir millones en el dinero del rescate. El objetivo de un ataque de ransomware es infectar tantos sistemas como sea posible, luego hacer tantos datos inaccesibles como sea posible encriptándolo con una clave conocida solo por el atacante. Una vez que se completa el ataque, el malware generalmente muestra una ventana que se parece a esto:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Ransomware.png">

Esta ventana ofrece a las víctimas el límite de tiempo y las instrucciones sobre cómo pagar, así como un resumen de lo que ha sucedido exactamente con sus datos. El ejemplo anterior es el infame ransomware [WannaCry](https://www.malwarebytes.com/es/wannacry).

Con el rescate pagado, el malware puede o no descifrar los datos y la autodestrucción, dependiendo completamente de cuán agradables son los atacantes.

### Métodos de Entrega
Hay varias formas en que un atacante puede infectar un objetivo con el malware, muchas de estas giran en torno a la ingeniería social o los ataques de phishing. Por ejemplo, un atacante puede enviar a una víctima un correo electrónico que contenga un archivo de Microsoft Word o Excel que contiene una macro maliciosa (código que está integrado dentro del documento que se ejecuta cuando un usuario abre el archivo). Estos no se ejecutarán de forma predeterminada a menos que el usuario haga clic en el botón "Habilitar Contenido" en la parte superior de la pantalla para habilitar macros:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Macros.png">

Sin embargo, hay situaciones en las que un usuario puede realmente desear ejecutar macros, y un buen atacante capitalizará estos pretextos para convencer a la víctima de hacer clic en el botón.

Del mismo modo, el atacante puede enviar el archivo como un `.exe` compilado, un `.pdf`, un script de PowerShell `.ps1` o un script de lotes `.bat`, un archivo de aplicación HTML `.hta` o incluso un archivo JavaScript `.js` para ser ejecutado por JavaScript intérprete integrado en Windows.

En resumen, hay muchas formas y formatos diferentes en los que un atacante puede enviar código a una víctima. Una vez que se ejecuta el código, comienza la infección.

Alternativamente, el atacante puede explotar una vulnerabilidad en la infraestructura pública en un entorno corporativo (por ejemplo, un servidor web), dándose así una apertura en la red interna y permitiéndoles comenzar un ataque más grande, facilitado por el malware.

### Mantenerse a Salvo
¡Mantenerse a salvo del malware (y el ransomware en particular) se hace mejor con una combinación de conciencia y manteniendo las cosas actualizadas!

- Siempre acepte actualizaciones y parches cuando se ofrecen, especialmente en software importante como los sistemas operativos. Las actualizaciones a menudo contienen soluciones a los defectos de seguridad, por lo que es importante ponerlos en su lugar lo antes posible.
- Nunca haga clic en enlaces sospechosos, especialmente en correos electrónicos. Intente no abrir archivos adjuntos si es posible. Si un mensaje parece sospechoso, elimínelo o reenvíelo al equipo apropiado si usa su cuenta de trabajo.
- Siempre esté buscando personas que intenten que descargue o ejecute archivos, especialmente por correo electrónico o mensajes instantáneos.
- Nunca conecte los dispositivos de medios desconocidos (por ejemplo, dispositivos USB) en computadoras importantes. Si encuentra un dispositivo en público ¡no lo conecte a su computadora portatil de trabajo!
- Siempre respalde datos importantes: esto se discutirá con más detalle más adelante en la sala y puede ser crucial para recuperarse de un ataque de ransomware.
- Asegúrese de que su software antivirus siempre esté actualizado y activado.

**Nota:** Si usted o su empresa se infectan con ransomware, no pague el rescate. En su lugar, llame a sus autoridades locales de inmediato e intente contener la infección deshabilitando su enrutador o evitando físicamente que el dispositivo infectado se conecte a cualquier otra cosa. No alimente el dispositivo infectado, ya que esto a veces puede destruir cualquier oportunidad potencial para descifrar los datos sin pagar.

### Responda las preguntas a continuación
1. (Investigación) ¿En qué moneda solicitó el pago los atacantes de WannaCry? `Bitcoin`

## (Ataques Comunes) Contraseñas y Autenticación
### Descripción General

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Seguridad.png">

Para bien o para mal, las contraseñas son una parte integral de la mayoría de los sistemas de autenticación. Utilizamos contraseñas para proteger todo, desde nuestras cuentas de redes sociales hasta nuestras aplicaciones bancarias. Desafortunadamente, a pesar de su importancia significativa, todavía es demasiado fácil crear y usar una contraseña insegura, e incluso más fácil tomar otras acciones que reducen la seguridad general del sistema. Por ejemplo, incluso la contraseña más robusta del mundo es inútil si se escribe en una pizarra a la vista de una cámara web, especialmente si se usa la misma contraseña para más de un servicio.

Esta tarea cubrirá la seguridad de la contraseña, así como otras medidas que puede tomar para fortalecer su seguridad general de autenticación.

### ¿Qué hace una contraseña segura?
Los consejos sobre lo que constituye una contraseña segura ha cambiado con el tiempo. En el pasado, se aconsejó a las personas que eligieran contraseñas complejas que fueran fáciles de recordar, por ejemplo: `@Ed1nburgh#1988-2000!`

La contraseña anterior es una colección de caracteres en minúsculas y mayúsculas, incluidos símbolos y dígitos numéricos. Tiene más de ocho caracteres (lo que hace que sea casi imposible ataacar por la furza bruta con nuestro nivel actual de tecnología) y se crea utilizando un conocimiento que es poco probable que sea retenido por alguien que no sea el propietario de la contraseña.

Es importante destacar que tampoco se ajusta a los patrones normales (usando símbolos inusuales, intercambiando solo algunos caracteres de L33T Speak, y que contiene un rango de fechas en lugar de una sola fecha), lo que dificulta la adivinación. Para todos los efectos, esta es una contraseña tradicionalmente segura. Dicho esto, la conexión personal significa que esta contraseña podría ser más débil a través de la ingeniería social o la recopilación de información en profundidad en un objetivo.

Las mejores prácticas actuales se inclinan más hacia la longitud que la complejidad. Por ejemplo: `¡Vim es_Obviosy_, indiscutiblemente el mejor editor de texto que existe!`.

Al usar una frase de contraseña en lugar de una contraseña tradicional, la contraseña es significativamente más larga mientras conserva algunos de los elementos más complejos, a pesar de no parecer tan ofuscados. Esto tiene la ventaja de ser más fácil de recordar, mientras que sigue siendo increíblemente díficil de la fuerza bruta.

Idealmente, sin embargo, debe usar contraseñas largas y completamente aleatorias. Por ejemplo: `w41 = v1) s7kijgpn, dii> cheh> frvqsj3m^] CB`.

Estos tardan millones de años en romperse y son objetivamente la opción más segura disponible. El inconveniente es la usabilidad; sin embargo, esto se mitiga en gran medida mediante el uso de un administrador de contraseñas, que se discutirá en la próxima tarea.

### ¿Qué hace una contraseña débil?
Las personas a menudo buscan contraseñas simples que significan algo para ellos, a menudo siguiendo uno de los pocos patrones "simples". Por ejemplo, un patrón de uso común es un nombre/ubicación, seguido de un año, seguido de un signo de exclamación. Por ejemplo: `Gareth2012!`

Esto es suficiente para satisfacer la mayoría de los requisitos de complejidad de contraseña (caracteres minúsculas y mayúsculas, más de ocho caracteres, contiene dígitos numéricos y un símbolo); sin embargo, es trivial adivinar si un atacante sabe que tienes un hijo llamado Gareth que nació en 2012. Este tipo de contraseña es inherentemente extremadamente inseguro.

En resumen, cualquier contraseña que pueda ser adivinada fácilmente por alguien que lo conozca relativamente bien (esto incluye a un atacante que mira sus redes sociales) ¡es una mala idea!

Igualmente, las contraseñas cortas (especialmente aquellas que no contienen caracteres no alfanuméricos) son débiles contra los ataques de fuerza bruta. Veremos esto con más profundidad más adelante en la tarea.

De igual importancia para la fuerza de la contraseña es la reutilización de contraseña. Puede tener la contraseña más sólida del mundo, pero si la usa en numerosas cuentas y se filtra, un atacante simplemente puede usar la misma contraseña segura en todas las cuentas afectadas. Igualmente, si descubre que su contraseña ha sido expuesta, ¡tendrá mucho trabajo para cambiar todas las contraseñas de su cuenta!

### Contraseñas Expuestas
Desafortunadamente, no todos los servicios almacenan contraseñas de forma segura (lo que hace que sea doblemente importante que no reutilice las contraseñas!).

```text
Información general: almacenamiento seguro de contraseñas

Cuando se registra para obtener una cuenta en línea, el proveedor debe almacenar una copia de su contraseña para validarla la próxima vez que inicie sesión; pero esto plantea un gran problema: ¿cómo se pueden almacenar las contraseñas de forma segura?

Almacenar las contraseñas como texto sin formato (por ejemplo, de la misma forma en que las envía) no es una opción, ya que todas las contraseñas se filtrarán instantáneamente si alguna vez se piratea la base de datos.
El cifrado de las contraseñas es una mejora, pero no mucho. Si las contraseñas se almacenan cifradas, también se pueden descifrar: un atacante simplemente tiene que obtener la clave y puede convertir todas las contraseñas cifradas nuevamente en texto sin formato. El cifrado de contraseñas fue parte de lo que hizo que la violación de Adobe de 2013 fuera tan grave.
El método de almacenamiento de contraseñas estándar de la industria se conoce como hash de contraseñas. El hash de contraseñas (o simplemente "hashing") implica el uso de algoritmos matemáticos complicados para tomar cualquier entrada y convertirla en una salida única de longitud fija de una manera que es imposible de revertir. Esto significa que cuando te registras, tu contraseña se codificará y almacenará en la base de datos de una manera que impida que todos (incluidos los administradores del servidor) puedan leerla.
Cuando intentas iniciar sesión, se aplica el mismo algoritmo a la contraseña que proporcionas: si el hash almacenado coincide con el hash de la contraseña con la que intentas iniciar sesión (recuerda que la misma entrada siempre creará la misma salida única), entonces se considera que te has autenticado correctamente.

Lo ideal sería que todos los servicios codificaran las contraseñas de los usuarios con un algoritmo seguro. Incluso si se filtrara toda la base de datos, los atacantes tendrían que perder tiempo valioso y potencia computacional intentando forzar los hashes (de otro modo inútiles) para encontrar las contraseñas en texto plano. Por eso es tan importante que las contraseñas sean largas y, preferiblemente, de un nivel decente de complejidad: cuanto más larga sea la contraseña y mayor sea la cantidad de caracteres potenciales involucrados, más potencia se necesita para adivinar de manera efectiva la entrada de contraseña utilizada para generar un hash.
```

Entonces, ¿qué sucede si un servicio es hackeado y su base de datos que contiene información de cuentas de usuario se filtra? En el mejor de los casos, el servicio ha utilizado un algoritmo de hash seguro y usted tiene una contraseña segura; en este caso, su contraseña está segura, pero su dirección de correo electrónico o nombre de usuario aún pueden filtrarse públicamente (así que espere algunos correos electrónicos spam).

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Cadena.png">

En el peor de los casos, su contraseña de texto simple está disponible de inmediato o es fácil para un atacante encontrarla. Si esto sucede, entonces tanto su nombre de usuario como su contraseña son conocidos por el atacante, lo que le permite tomar el control de su cuenta o realizar ataques de "relleno de credenciales", utilizando su par de nombre de usuario y contraseña robados contra otros servicios para ver si los reutilizó en otro lugar. Estas bases de datos filtradas que contienen credenciales aparecen con frecuencia en la red oscura, lo que nos lleva a nuestro punto final en esta sección: los servicios de cotificación de exposición de datos.

El verificador de exposición de datos más grande y conocido se llama [Have I Been Pwned?](https://haveibeenpwned.com/). Existe como un servicio gratuito en línea que analiza los datos recopilados y cataloga toda la información encontrada, lo que permite a los usuarios ingresar sus direcciones de correo electrónico para ver si han sido incluidos en alguna filtración de datos. Have I Been Pwned también le permite agregarse a una lista de notificaciones, lo que significa que recibirá un correo electrónico que le notificará si su dirección de correo electrónico aparece en alguna filtración de datos.

Si bien no es una defensa perfecta, los servicio de notificación le brindan una advertencia temprana vital para cambiar sus contraseñas (con suerte) antes de que lo pirateen.

### Ataques de Contraseñas
Un atacante tiene algunas opciones cuando se trata de atacar contraseñas y sistemas de autenticación. Algunos ataques son completamente locales (es decir, funcionan completamente en un dispositivo propiedad del atacante sin interactuar en absoluto con el servicio de destino), otros son ataques remotos que involucran al servidor original.

Los ataques locales requieren una copia robada de las credenciales en cuestión. El atacante tomará un archivo lleno de nombres de usuario/correos electrónicos robados y contraseñas codificadas, luego usará un software para intentar adivinar de manera efectiva la entrada que creó el hash, ya sea utilizando secuencias de caracteres generadas aleatoriamente (más lento pero más completo) o utilizando una lista de palabras pregenerada de posibles contraseñas (más rápido pero con muchas más probabilidades de pasar por alto cosas). Los tipos híbridos también se utilizan mucho; estos son cuando un atacante toma una lista de palabras existente y la muta para agregar nuevos caracteres, símbolos o elementos aleatorios. Los ataques de contraseñas locales se demostrarán en el elemento interactivo para esta tarea.

Los ataques remotos tienden a ser una de dos categorías o bien implican intentar forzar nombres de usuario conocidos enviando solicitudes al servidor y viendo con qué responde, o bien utilizan pares de nombres de usuario y contraseñas conocidos de infracciones anteriores para ver si son válidos en el sitio de destino: este es el robo de credenciales mencionado anteriormente.

### Responda las preguntas a continuación
- Póngase en el lugar de un hacker malintencionado. Ha logrado volcar la base de datos de contraseñas de un servicio en línea, ¡pero todavía tiene que descifrar esos hashes!, ¡Haga clic en el botón verde al comienzo de la tarea para implementar el forzado de hashes interactivo!
- Basándose en el contenido del sitio web, ha generado una lista de posibles contraseñas, que es la siguiente:

```text
TryH@ckMe
TryHackMe123
THM123456
qwertyuiop123
TryHackMe2021
TryHackMe123!
TryHackMe345
TryHackM3!
```

Copie la lista de contraseñas en el campo "Lista de contraseñas" del descifrador de hash y luego haga clic en "Ir".

- Observa la sección "Palabra actual / Hash" del descifrador de hash. Observa que, para cada palabra de la lista que ingresaste, el descifrador crea un hash MD5 de la palabra y luego lo compara con el hash de destino. Si los dos hashes coinciden, ¡se encontró la contraseña!

- El descifrador de hash debería encontrar la contraseña que coincide con el hash de destino muy rápidamente. ¿Cuál es la contraseña? `TryHackMe123!`

Este es un ejemplo muy simple basado en el naveegador; sin embargo, en realidad, el descifrado de hashes locales con una lista de palabras no es más complejo desde una perspectiva de alto nivel: es la misma técnica, pero con muchas más contraseñas potenciales.

Esperemos que este ejemplo ilustre por qué es tan importante elegir una contraseña segura, incluso si las contraseñas están codificadas correctamente.

En la siguiente tarea, veremos algunas de las medidas de protección de cuentas más comunes, así como también cómo generar contraseñas seguras.

## (Mantenerse a Salvo) Administradores de Autenticación y Contraseñas
### Descripción General
En la tarea anterior, analizamos algunos de los ataques más comunes contra las contraseñas y los sistemas de autenticación. También analizamos qué hace que una contraseña débil o fuerte. Esta tarea cubrirá algunos de los pasos adicionales que puede tomar para mejorar la seguridad de sus contraseñas mediante el uso de administradores de contraseñas y autenticación multifactor.

### Autenticación Multifactor
La autenticación multifactor (o MFA) es un término que se utiliza para describir cualquier proceso de autenticación en el que se necesita más de una cosa para iniciar sesión. El ejemplo más común de esto es cuando ingresa la contraseña de una cuenta y luego se le solicita un código de 6 dígitos que se envía a su teléfono y generalmente caduca después de 15 minutos aproximadamente. Este segundo factor de autenticación en particular se conoce como contraseña de un solo uso basada en el tiempo (o TOTP) y es uno de los segundos factores más comunes qe se utilizan actualmente.

```text
Antecedentes: Tres factores de autenticación

Hay tres factores principales que se pueden tener en cuenta al implementar la autenticación multifactor; estos son:

- Algo que usted tiene (por ejemplo, una tarjeta inteligente, un TOTP o un autenticador de hardware como un "YubiKey". También es posible que su banco le haya pedido que inserte su tarjeta en un lector de tarjetas e ingrese su código PIN antes de permitirle el acceso a los servicios bancarios en línea; este es el mismo principio)
- Algo que usted sabe (por ejemplo, una contraseña)
- Algo que usted es (es decir, datos biométricos como una huella digital o un escaneo de iris)

Una autenticación ideal utiliza los tres; por ejemplo, puede requerir una contraseña, una tarjeta inteligente y una huella digital antes de permitir que el usuario acceda al sistema.

Desafortunadamente, la mayoría de las personas no tienen acceso a un lector de tarjetas inteligentes, un autenticador de hardware costoso (por ejemplo, el mencionado YubiKey) o un escáner de huellas digitales. Sí tienen acceso a un teléfono inteligente que se puede usar para recibir o acceder a contraseñas de un solo uso basadas en tiempo. Como tal, la autenticación multifactor basada en dispositivos móviles es uno de los métodos de autenticación multifactor más comunes implementados para uso personal. Si bien no es ideal, dos factores son mejores que uno.
```

Siempre debe activar la autenticación multifactor cuando esté disponible. Hacerlo significa que un atacante debe obtener más de un factor si desea comprometer ccualquiera de sus cuentas; por ejemplo, debe tener tanto la contraseña como su telefono (o la capaccidad de interceptar sus mensajes de texto). Muchas personas lo ven como una "molestia innecesaria"; sin embargo, ¡vale la pena por la seguridad adicional!

Desafortunadamente, la autenticación TOTP basada en SMS (mensaje de texto), a pesar de ser la más utilizada, está lejos de ser la más segura, ya que ha habido casos documentados de atacantes que lograron redirigir los mensajes de texto de una víctima sin demasiada dificultad.

Entonces, si no es SMS, ¿qué? Las contraseñas de un solo uso basadas en tiempo siguen siendo la forma más accesible de autenticación de segundo factor para la mayoría de los usuarios; afortunadamente, ¡es posible generarlas usted mismo!

La mayoría de los servicios le brindarán una opción para usar una "Aplicación de autenticación" para MFA. Cuando seleccionas esta opción, se te presentará un código QR y una "clave secreta", que se puede escanear o importar a una aplicación como [Authy](https://authy.com/) o Google Authenticator ([Android](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=en_US&gl=US&pli=1)|[IOS](https://apps.apple.com/us/app/google-authenticator/id388497605)). Una vez que hayas añadido tu clave secreta a la aplicación, estas aplicaciones pueden generar códigos TOTP completamente en tu dispositivo sin necesidad de conectividad de red ni SMS interceptables.

### Gestores de contraseñas y generación de contraseñas seguras
Como se mencionó anteriormente, las contraseñas más seguras son simplemente cadenas largas y completamente aleatorias de caracteres, dígitos y símbolos. Desafortunadamente, estas contraseñas aleatorias son muy díficiles de memorizar; de hecho, memorizar una contraseña diferente de 60 dígitos, generada aleatoriamente para cada cuenta en línea, simplemente no es factible para la mayoría de las personas.

Aquí es donde entran en juego los gestores de contraseñas. En el nivel más básico, los gestores de contraseñas proporcionan un espacio seguro para almacenar sus contraseñas. Almacenan nlas contraseñas en "bovedas": almacenamiento cifrado, ya sea localmente en su propio dispositivo o como un servicio en línea (que también suele permitirle acceder a sus contraseñas desde cualquier dispositivo). Se accede a estas bóvedas utilizando una contraseña maestra (la única contraseña que necesita recordar) o (lo que es más común en los últimos años) datos biométricos como una huella digital. Algunos gestores de contraseñas son gratuitos, mientras que otros requieren una suscripción de paga. Dicho esto, las características y la facilidad de uso que ofrecen las ofertas pagas a menudo hacen que valga la pena el gasto.

Los gestores de contraseñas con más funciones suelen incluir también una serie de funciones adicionales, como el almacenamiento de otros tipos de datos (por ejemplo, imágenes, archivos, etc.), el rellenado automático de contraseñas para otros servicios y la generación segura de contraseñas. Disponer de estas funciones significa que puede generar contraseñas muy seguras de forma rápida y sencilla y almacenarlas automáticamente, para que luego se introduzcan automáticamente cuando intente iniciar sesión en una aplicación, todo ello dentro de la misma aplicación.

Los gestores de contraseñas son la forma recomendada de gestionar la autenticación de numerosas cuentas; sin embargo, conviene recordar que la seguridad de toda la estructura puede girar en torno a una única contraseñla maestra, así que asegúrese de que sea sólida.

Algunos gestores de contraseñas habituales son:
- [1Password](https://1password.com/es)
- [LastPass](https://www.lastpass.com/)
- [KeePass](https://keepass.info/)
- [Bittwarden](https://bitwarden.com/)

¡Existen muchos otros! Cada gestor de contraseñas tiene sus propias ventajas y desventajas, por lo que merece la pena investigar un poco para encontrar el que mejor se adapte a sus necesidades.

- https://krebsonsecurity.com/2021/03/can-we-stop-pretending-sms-is-secure-now/

### Responda las preguntas a continuación
- Si tiene la opción, ¿cuál debería usar como segundo factor de autenticación entre los TOTP basados en SMS o los TOTP basados en la aplicación de autenticación (SMS o App)? `App`

## [Mantenerse a Salvo] Seguridad de la Red Pública
### El problema
Internet desempeña un papel gigantesco en la vida moderna, ya que la mayoría de las personas están conectadas de algún modo prácticamente de forma constante. Por ello, la mayoría de los espacios públicos (por ejemplo, cafeterías, restaurantes, transporte público) están completamente equipados con WI-FI púbblico para que la gente pueda ponerse al día con el correo electrónico (o, con la misma probabilidad, jugar al último juego de móvil de moda). Lo que mucha gente no sabe es que esperar que haya Wi-Fi público disponible puede resultar muy peligroso.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/WiFi.png">

El Wi-Ffi público, aunque es increíblemente práctico, también ofrece a un atacante oportunidades ideales para atacar los dispositivos de otros usuarios o simplemente interceptar y registrarr el tráfico para robar información confidencial. Esta última técnica puede ser tan sencilla como explotar el hecho de que la mayoría de las personas esperan ver redes públicas disponibles. El atacante puede configurar rápidamente una red propia y controlar el tráfico de todos los que se conecctan; esto se conoce como un ataque de "man-in-the-middle" y es muy fácil de llevar a cabo. Por ejemplo, si te conectas a una red que pertenece a un atacante y luego inicias sesión en una cuenta de un sitio web que no utiliza una conexión cifrada (HTTPS), el atacante podría simplemente extraer tus credenciales del tráfico de la red y usarlas para iniciar sesión en tu cuenta. Este escenario se explorará con más detalle en el elemento interactivo de esta tarea; sin embargo, afortunadamente es mucho menos probable que ocurra con los sitios web modernos que implementan Transport Layer Security (TLS) para cifrar el tráffico entre sus servidores y usuarios como estándar.

Del mismo modo, estar conectado a cualquier red (independientemente de si confías en ella o no) hace que tu dispositivo sea visible para otros en la red, ¡Nunca sabes quién más está en una red pública o cuáles podrían ser sus intenciones!

### Las Soluciones
La solución ideal para este problema es simplemente no conectarse a redes que no sean de confianza. Aunque las conexiones inalámbricas públicas son beneficiosas, siempre será más seguro utilizar un punto de acceso móvil o una red privada. Lamentablemente, la solución ideal no siempre es factible; cuando este es el caso, debemos confiar en otros métodos para mantenernos seguros.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/VPN.png">

Las redes privadas virtuales (VPN) cifran todo el tráfico que sale y vuelve a entrar en su máquina, lo que hace que cualquier técnica de interceptación sea inútil, ya que los datos interceptados simplemente parecerán un galimatías. Si bien es posible alojar su propio servidor VPN de forma gratuita, la mayoría de las personas prefieren utilizar una de las muchas soluciones en línea. Algunas de estas soluciones comerciales son gratuitas, peo tenga cuidado: las VPN gratuitas tienden a no proporcionar la mejor seguridad y, a menudo, recopilan ssus datos para obtener ganancias. Dicho esto, el precio de una buena VPN vale la pena por la mayor seguridad al operar en redes que no son de confianza. Hay muchas buenas opciones disponibles, incluidas [ProtonVPN](https://protonvpn.com/) y [Mullvad VPN](https://mullvad.net/en), por nombrar dos.

### Seguridad de la conexión a sitios web
Además de las medidas que toma para protegerse, también es importante conocer las medidas que toman los servicios en línea para protegerlo.

Todos los sitios web ahora solo deben proporcionar información en la seguridad de una conexión cifrada. Al igual que con el uso de una VPN, esto evita que un atacante lea o modifique su tráfico web si lo intercepta. La conexión cifrada que se utiliza para crear HTTPS (Protocolo Seguro de Transferencia de Hipertexto) se conoce como TLS (Seguridad de la capa de transporte) y en la mayoría de los navegadores se representa con un candado a la izquierda de la barra de búsqueda, que indica que la conexión es segura:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/HTTPS.png">

Con esto en su lugar, su tráfico solo se puede descifrar en circunstancias muy selectas; es decir, si se trata de un dispositivo administrado por el trabajo o la escuela y está conectado a una red de trabajo o escuela.

Nota: La presencia del candado indica que la conexión es segura; no garantiza que el sitio web en sí sea seguro. En otras palabras, un sitio web malicioso puede tener fácilmente un certificado TLS (lo que significa que su tráfico con el servidor está cifrado), pero eso no impide que el sitio tenga un propósito malicioso.

Si accede a un sitio web sin el símbolo del candado, nunca ingrese credenciales ni información confidencial, especialmente se está utilizando una red que no es de confianza.

En algunos casos, también puede ver un candado con una cruz o un signo de exclamación sobre él; esto indica que la conexión es teóricamente segura, pero que hay algo incorrecto con el certificado que usa el servidor. La presencia de este ícono de candado alterado puede significar cualquier cosa, desde que el administrador del servidor simplemente dejó que el certificado caduque hasta que un atacante interfiera activamente con la seguridad de su conexión. En otras palabras: si el icono es cualquier cosa que no sea un candado normal, no conffie en que la conexión sea segura.

También puede encontrar errores de página completa relacionados con la seguridad del certificado al intentar acceder a páginas web; estos pueden verse así:

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Ataques-Comunes/Error-Certificado.png">

Como regla general, si ve un error como este, debe hacer clic en el botón "Volver" (o equivalente en otros navegadores); generalmente significa que hay un problema con la conexión cifrada, lo que podría dejar su tráfico expuesto a ser robado.

### Responda las siguientes preguntas a continuación
- Implemente el contenido interactivo haciendo clic en el botón verde en la parte superior de la tarea.
- El contenido interactivo de esta tarea demuestra lo que puede suceder si se envía información a través de una red potencialmente insegura con varios tipos de cifrado (o falta de ellos). No hay ninguna bandera para esta tarea, pero se le recomienda que pruebe cada uno de los siguientes escenarios, mezclando y combinando las opciones proporcionadas en el cuadro de control en la parte inferior derecha de la pantalla.

## [Mantenerse a Salvo] Respaldos
### Descripción General
Las copias de seguridad son, sin duda, la medida defensiva más importante que puede adoptar para proteger sus datos. Pase lo que pase, si ha tomado las medidas adecuadas para realizar copias de seguridad de su información, siempre podrá recuperarla, casi independientemente de la gravedad del daño.

Tanto si se trata de datos empresariales de vital importancia en el trabajo como de fotos familiares en casa, las copias de seguridad son una medida sencilla que se amortiza con creces en caso de que ocurra lo peor.

Según los datos en cuestión, realizar copias de seguridad y restaurarlas puede ser tan sencillo como arrastrar y soltar carpetas en Google Drive. Dicho esto, también hay muchas soluciones de software disponibles para ayudar a automatizar las copias de seguridad y simplificar la restauración.

### La regla de oro 3, 2, 1
La regla de oro para realizar copias de seguridad es relativamente simple y suele denominarse "regla 3,2,1". Dicha regla especifica que:

- Siempre debe conservar al menos tres copias actualizadas de sus datos; esto puede incluir la copia original, pero todas las copias deben conservarse.
- Las copias de seguridad deben almacenarse en al menos dos medios de almacenamiento diferentes; por ejemplo: una copia de seguridad en la nube y un dispositivo USB. Esto puede incluir un disco duro en su PC.
- Una (o más) copias de seguridad deben almacenarse "fuera de las instalaciones". Los servicios en la nube como Google Drive son ideales para uso personal en este sentido.

Sus copias de seguridad deberían estar seguras si se cumplen las tres condiciones de la regla 3,2,1; pero es igualmente importante la frecuencia con la que realiza las copias de seguridad. ¡No tiene sentido mantener sus copias de seguridad almacecnadas de forma segura si todas tienen un año de antigüedad!

La frecuencia con la que realiza copias de seguridad de sus datos depende de usted y, por lo general, depende de la confidencialidad de los datos, en comparación con el riesgo de que se vean comprometidos y la cantidad de espacio de copia de seguridad disponible. Por ejemplo, una corporación multimillonaria que maneja datos confidenciales corre un alto riesgo de sufrir un ataque de ransomware y es posible que desee realizar copias de seguridad completas dos o tres veces al día. En comparación, un usuario doméstico puede sentir la necesidad de realizar copias de seguridad solo una o dos veces por semana.

### Responda las preguntas a continuación
- ¿Cuál es la cantidad mínima de copias de seguridad actualizadas que debe realizar? `3`
- De estos, cuántos (como mínimo) deberían almacenarse en otra ubicación? `1`

## [Mantenerse a Salvo] Actualizaciones y Parcheos
### Actualizaciones de software
Las actualizaciones son una parte esencial del ciclo de vida del desarrollo de software; permiten a los desarrolladores agregar nuevas funciones, corregir errores y, de otro modo, modificar aspectos del producto. Cuando se descubren vulnerabilidades en el software, los desarrolladores suelen publicar actualizaciones especiales denominadas parches que contienen una solución para la vulnerabilidad o "parchan" el problema de seguridad.

Por este motivo, es imperativo que actualice el software siempre que sea posible, especialmente en el caso de sistemas operativos (Windows o macOS), donde las vulnerabilidades pueden ser particularmente peligrosas, como se ve en el siguiente estudio de caso.

Caso de estudio: Eternal Blue

Se cree que Eternal Blue fue descubierto por la Agencia de Seguridad Nacional de los Estados Unidos (NSA) y se filtró al público en general en abril de 2017. La vulnerabilidad afecta a una parte integral del sistema operativo Windows y le otorga a un atacante remoto control total sobre el objetivo en el nivel más alto de privilegios. Puede comprobarlo usted mismo en la sala [Blue de TryHackMe]().

Microsoft lanzó rápidamente un parche (el infame [MS17-010](https://learn.microsoft.com/en-us/security-updates/SecurityBulletins/2017/ms17-010)) que fue diseñado para eliminar el componente vulnerable del software; sin embargo, muchos administradores simplemente optaron por no descargarlo por una razón u otra.

¿Por qué es importante? Eternal Blue fue el vector de transmisión que utilizó el ransomware Wannacry (discutido en la tarea 4) para propagarse e infectar nuevos dispositivos. Eternal Blue dio acceso total a un objetivo de forma remota, lo que lo convierte en una vulnerabilidad perfecta para explotar con un virus autorreplicante. A pesar de que se había publicado un parche meses antes de la aparición de Wannacry, el ransomware aún pudo atacar millones de sistemas sin parches, con efectos devastadores.

Puede leer más sobre Eternal Blue [aquí](https://www.sentinelone.com/blog/eternalblue-nsa-developed-exploit-just-wont-die/).

Desafortunadamente, todo software eventualmente pierde el soporte de sus mantenedores, se vuelve obsoleto y ya no recibe actualizaciones (por ejemplo, Windows 7); esto se conoce como que el software llega al EOL (fin de vida útil).. En este punto , el software debe reemplazarse lo antes posible. Si no es posible reemplazar el software, entonces el dispositivo debe aislarse lo más posible para evitar la explotación de las vulnerabilidades que inevitablemente se encontrarán y dejarán sin parchear.

### Actualizaciones de antivirus
La mayoría de los paquetes de software antivirus reciben actualizaciones muy frecuentemente; esto se debe a que funcionan en gran medida utilizando una base de datos local de firmas de exploits conocidas, que deben mantenerse actualizadas.

En otras palabras: cuando se descubre un nuevo malware, se envía a los proveedores de antivirus que generan una "firma" que identifica este software malicioso en particular. Luego, estas firmas distribuyen a todos los sispositivos del planeta que usan el software antivirus, lo que garantiza que su solución antivirus instalada se mantenga actualizada con todo el malware (conocido) más reciente.

Si no se permite que el software anttivirus se actualice, podrá detectar malwware mediante otros métodos. Sin embargo, la base de datos de firmas local quedará obsoleta rápidamente, lo que puede provocar que el software malicioso se escape. En resumen: si el antivirus quiere actualizarse, ¡déjelo!

### Responda las preguntas a continuación
- (Opcional) ¡Complete la sala azul en TryHackMe para ver usted mismo los efectos brutales del exploit Eternal Blue en acción contra una máquina sin parches!

## [Información] Conclusión
Para concluir: existen muchas opciones diferentes para que un atacante malintencionado ataque tanto a individduos como a grupos de personas; sin embargo, existen soluciones para cada ataque.

Una vez que haya completado esta sala, con suerte comprenderá un poco más sobre estos staques comunes y las defensas contra ellos. No necesita ser un experto en computadoras o ciberseguridad para mantenerse seguro en línea: las soluciones son simples y vale la pena adoptarlas en sus interacciones personales y profesionales en línea.

### Responda las preguntas a continuación
- ¡Complete la sala de ataques comunes!