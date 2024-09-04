---
layout: single
title: Principios de Seguridad
excerpt: "Obtenga información sobre la tríada de seguridad, los modelos y principios de seguridad comunes."
date: 2024-08-27
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/Seguridad.png
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
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/Portada.png">
</p>

## Introducción
La seguridad se ha convertido en una palabra de moda; cada compañía quiere reclamar su producto o servicio es seguro. ¿Pero realmente lo es?

Antes de comenzar a discutir los diferentes principios de seguridad, es vital conocer al adversario contra quien estamos protegiendo nuestros activos.

¿Estás tratando de evitar que un niño pequeño acceda a tu computadora portátil? ¿O está tratando de proteger una computadora portátil que contiene diseños técnicos por valor de millones de dólares? El uso de mecanismos de protección exactos contra los niños pequeños y los actores de espionaje industrial sería ridículo.

En consecuencia, conocer a nuestro adversario es imprescindible para que podamos aprender sobre sus ataques y comenzar a implementar controles de seguridad apropiados.

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/Intruso.png">
</p>

Es imposible lograr una seguridad perfecta; ninguna solución es 100% segura. Por lo tanto, tratamos de mejorar nuestra postura de seguridad para que sea más difícil para nuestros adversarios obtener acceso.

El objetivo de esta habitación es:

1. Explique las funciones de seguridad: Confidencialidad, Integridad y Disponibilidad (CIA).
2. Presente lo contrario de la tríada de seguridad, CIA: Divulgación, Alteración y Destrucción / Negación.
3. Presente los conceptos fundamentales de los modelos de seguridad, como el modelo Bell-Lapadula.
4. Explique principios de seguridad como Defence-in-Depth, Zero Trust y Trust, pero verifique.
5. Presente ISO/IEC 19249.
6. Explique la diferencia entre vulnerabilidad, amenaza y riesgo.

### Responda las preguntas a continuación
- Piense en cómo describiría algo como seguro.

## CIA

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/CIA.png">
</p>

Antes de que podamos describir algo como seguro, debemos considerar mejor lo que compone la seguridad. Cuando desea juzgar la seguridad de un sistema, debe pensar en términos de la tríada de la seguridad: Confidencialidad, Integridad y Disponibilidad (CIA).

- `La confidencialidad` asegura que solo las personas o destinatarios previstas puedan acceder a los datos.
- `La integridad`tiene como objetivo garantizar que los datos no se puedan alterar; Además, podemos detectar cualquier alteración si ocurre.
- `La disponibilidad` tiene como objetivo garantizar que el sistema o servicio esté disponible cuando sea necesario.

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/Triada.png">
</p>

Consideremos la tríada de seguridad de la CIA en el caso de realizar un pedido para compras en línea.

- `Confidencialidad`: Durante las compras en línea, espera que su número de tarjeta de crédito se divulgue solo a la entidad que procesa el pago. Si duda de que la información de su tarjeta de crédito se divulgue a una parte no confiable, lo más probable es que se abstenga de continuar con la transacción. Además, si una violación de datos da como resultado la divulgación de información de identificación personal, incluidas las tarjetas de crédito, la compañía incurrirá en grandes pérdidas en múltiples niveles.

- `Integridad`: Después de completar su pedido, si un intruso puede alterar la dirección de envío que ha enviado, el paquete se enviará a otra persona. Sin la integridad de los datos, puede ser muy reacio a realizar su pedido con este vendedor.

- `Disponibilidad`: Para realizar su pedido en línea, navegará por el sitio web de la tienda o utilizará su aplicación oficial. Si el servicio no está disponible, no podrá explorar los productos o realizar un pedido. Si continúa enfrentando tales problemas técnicos, eventualmente puede rendirse y comenzar a buscar una tienda en línea diferente.

Consideremos la CIA en relación con los registros de pacientes y los sistemas relacionados:

- `Confidencialidad`: De acuerdo con varias leyes en los países modernos, los proveedores de atención médica deben garantizar y mantener la confidencialidad de los registros médicos. En consecuencia, los proveedores de atención médica pueden ser considerados legalmente responsables si revelan ilegalmente los registros médicos de sus pacientes.

- `Integridad`: Si el registro de un paciente se altera accidental o maliciosamente, puede llevar al tratamiento incorrecto que se administra, lo que, a su vez, puede conducir a una situación potencialmente mortal. Por lo tanto, el sistema sería inútil y potencialmente dañino sin garantizar la integridad de los registros médicos.

- `Disponibilidad`: Cuando un paciente visita una clínica para hacer un seguimiento de su condición médica, el sistema debe estar disponible. Un sistema no disponible significcaría que el médico no puede acceder a los registros del paciente y, en consecuencia, no sabrá si algún síntoma actual está reelacionado con el historial médico del paciente. Esta situación puede hacer que el diagnóstico médico sea más desafiante y propenso a errores.

El énfasis no necesita ser el mismo en las tres funciones de seguridad. Un ejemplo sería un anuncio universitario; Aunque generalmente no es confidencial, la integridad del documento es crítica.

### Más allá de la CIA

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/Mas-Alla.png">
</p>

Yendo un paso más allá de la tríada de seguridad de la CIA, podemos pensar en:

- `Autenticidad`: Auténtico significa que no es fraudulento ni falsificado. La autenticidad consiste en garantizar que el documento/archivo/datos proceden de la fuente declarada.

- `No repudio`: Repudiar significa negarse a reconocer la validez de algo. El no repudio garantiza que la fuente original no pueda negar que es la fuente de un documento/archivo/datos en  particular. Esta característica es indispensable para varios ámbitos, como las compras, el diagnóstico de pacientes y la banca.

Estos 2 requisitos están estrechamente relacionados. La necesidad de distinguir los archivos o pedidos auténticos de los falsos es indispensable. Además, garantizar que la otra parte no pueda negar ser la fuente es vital para que muchos sistemas sean utilizables.

En las compras en línea, dependiendo de su negocio, puede tolerar intentar entregar una camiseta con pago contra reembolso y descubrir más tarde que el destinatario nunca realizó ese pedido. Sin embargo, ninguna empresa puede tolerar enviar 1,000 coches para descubrir que el pedido era falso. En el ejemplo de un pedido de compra, desea confirmar que el cliente en cuestión efectivamente realizó el pedido; eso es autenticidad. Además, desea asegurarse de que no pueda negar haber realizado el pedido; eso es no repudio.

Como empresa, si recibe un pedido de envío de 1,000 automóviles, debe garantizar la autenticidad de este pedido; además, la fuente no debe poder negar haber realizado dicho pedido. Sin autenticidad y no repudio, la empresa no puede llevar adelante el negocio.

### Hexada Parkeriana
En 1998, Donn Parker propuso la Hexada Parkeriana, un conjunto de 6 elementos de seguridad. Son:

1. Disponibilidad.
2. Utilidad.
3. Integridad.
4. Autenticidad.
5. Confidencialidad.
6. Posesión.

Ya hemos cubierto 4 de los 6 elementos anteriores. Analicemos los 2 elementos restantes:

- `Utilidad`: La utilidad se centra en la utilidad de la información. Por ejemplo, un usuario podría haber perdido la clave de descifrado para acceder a una computadora portátil con lamacenamiento cifrado. Aunque el usuario todavía tiene el portátil con su(s) disco(s) intacto(s), no puede acceder a ellos. En otras palabras, aunque todavía es útil, es decir, no tiene ninguna utilidad.

- `Posesión`: Este elemento de seguridad requiere que protejamos la información de la toma, copia o control no autorizados. Por ejemplo, un adversario podría tomar una unidad de copia de seguridad, lo que significa que perderemos la posesión de la información mientras tenga la unidad. Alternativamente, el adversario podría lograr cifrar nuestros datos mediante ransomware; esto también conduce a la pérdida de la posesión de los datos.

### Responda las preguntas a continuación
1. Haga clic en "Ver Sitio" y responda las 5 preguntas. ¿Cuál es la bandera que obtuvo al final?
    - `THM{CIA_TRIAD}`

### Preguntas
En principio de seguridad, elija opciones para salvaguardar la información. Asegure la *confidencialidad*, *integridad* y *disponibilidad* del sistema.

1. Cuando las tropas se desplegaron, el líder enfatizó que no debían comunicar su ubicación a nadie mientras la misión estuviera en curso. ¿Qué función de seguridad quería tener el líder? `Confidencialidad`

2. Dos empresas están negociando un determinado acuerdo; sin embargo, quieren mantener en secreto los detalles del acuerdo. ¿Qué pilar de seguridad están enfatizando? `Confidencialidad`

3. Un hotel está enfatizando que Internet a través de su red WiFi debe ser accesible las 24 horas del día, los siete días de la semana. ¿Qué pilar de seguridad exige el hotel? `Disponibilidad`

4. Fuiste a cobrar un cheque y el cajero del banco te hizo esperar cinco minutos mientras confirmaba la firma del emisor del cheque. ¿Qué función de seguridad está verificando el cajero del banco? `Integridad`

## DAD

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/DAD.png">
</p>

La seguridad de un sistema se ataca a través de varios medios. Puede ser mediante la divulgación de datos secretos, la alteración de datos o la destrucción de datos.

- La `divulgación` es lo opuesto a la confidencialidad. En otras palabras, la divulgación de datos confidenciales sería un ataque a la confidencialidad.

- La `alteración` es lo opuesto a la integridad.. Por ejemplo, la integridad de un cheque es indispensable.

- La `destrucción/negación` es lo opuesto a la disponibilidad.

Lo opuesto de la tríada CIA sería la tríada DAD: Divulgación, Alteración, Destrucción.

Consideremos el ejemplo anterior de los registros de pacientes y los sistemas relacionados:

- `Divulgación`: Como en la mayoría de los países modernos, los proveedores de atención médica deben mantener la confidenccialidad de los registros médicos. Como resultado, si un atacante logra robar algunos de estos registros médicos y publicarlos en línea para que sean vistos públicamente, el proveedor de atención médica sufrirá una pérdida debido a este ataque de divulgación de datos.

- `Alteración`: Considere la gravedad de la situación si el atacante logra modificar los registros médicos de los pacientes. Este ataque de alteración podría llevar a que se administre el tratamiento incorrecto y, en consecuencia, podría poner en peligro la vida.

- `Destrucción/Denegación`: Considere el caso en el que un centro médico se ha vuelto completamente sin papel. Si un atacante logra que los sistemas de bases de datos no estén disponibles, el centro no podrá funcionar correctamente. Pueden volver al papel temporalmente; sin embargo, los registros de los pacientes no estarán disponibles. Este ataque de denegación paralizaría todo el centro.

La protección contra la divulgación, alteración y destrucción/denegación es de suma importancia. Esta protección es equivalente a trabajar para mantener la confidencialidad, la integridad y la disponibilidad.

Proteger la confidencialiddad y la integridad al extremo puede restringir la disponibilidad, y aumentar la disponibilidad al exxtremo puede resultar en la pérdida de confidencialidad e integridad. La implementación de buenos principios de seguridad requiere un equilibrio entre los 3.

### Responda las preguntas a continuación
1. El atacante logró obtener acceso a los registros de los clientes y los volcó en línea. ¿En qué consiste este ataque?
    - `Disclosure` -> Divulgación

2. Un grupo de atacantes logró localizar los sistemas de suministro de energía principal y de respaldo y apagarlos. Como resultado, se apagó toda la red. ¿En qué consiste este ataque?
    - `Destruction/Denial` -> Destrucción/Denegación

## Conceptos Fundamentales de los Modelos de Seguridad

Hemos aprendido que la tríada de seguridad está representada por *Confidencialidad*, *Integridad* y *Disponibilidad* (CIA). Uno podría preguntarse, ¿cómo podemos crear un sistema que garantice una o más funciones de seguridad? La respuesta estaría en el uso de `modelos de seguridad`. En esta tarea, presentaremos 3 modelos de seguridad fundamentales:

1. Modelo Bell-LaPadula
2. Modelo de Integridad Biba
3. Modelo Clark-Wilson

### Modelo Bell-LaPadula
El modelo `Bell-LaPadula` tiene como objetivo lograr la confidencialidad mediante la especificación de 3 reglas:

- `Propiedad de Seguridad Simple`: Esta propiedad se denomina "no leer hacia arriba"; establece que un sujeto con un nivel de seguridad más bajo no puede leer un objeto con un nivel de seguridad más alto. Esta regla impide el acceso a información confidencial por encima del nivel autorizado.

- `Propiedad de Seguridad Estrella`: Esta propiedad se denomina "no escribir hacia abajo"; establece que un sujeto con un nivel de seguridad más alto no puede escribir en un objeto con un nivel de seguridad más bajo. Esta regla impide la divulgación de información confidencial a un sujeto con un nivel de seguridad más bajo.

- `Propiedad de Seguridad Discrecional`: Esta propiedad utiliza una matriz de acceso para permitir operaciones de lectura y escritura. En la tabla siguiente se muestra un ejemplo de matriz de acceso que se utiliza junto con las 2 primeras propiedades.

<table align="center">
    <tr>
        <th>Sujetos</th>
        <th>Objeto A</th>
        <th>Objeto B</th>
    </tr>
    <tr>
        <td>Sujeto 1</td>
        <td>Escritura</td>
        <td>Sin Acceso</td>
    </tr>
    <tr>
        <td>Sujeto 2</td>
        <td>Lectura/Escritura</td>
        <td>Lectura</td>
    </tr>
</table>

Las 2 primeras propiedades se pueden resumir como "escribir hacia arriba, leer hacia aabajo". Puede compartir información confidencial con personas con mayor nivel de seguridad (escritura) y puede recibir información confidencial de personas con menor nivel de seguridad (lectura).

El modelo Bell-LaPadula tiene ciertas limitaciones. Por ejemplo, no fue ddiseñado para gestionar el intercambio de archivos.

### Modelo Biba
El modelo `Biba` tiene como objetivo lograr la integridad mediante la especificación de 2 reglas principales:

- `Propiedad de Integridad Simple`: Esta propiedad se conoce como "no lectura hacia abajo"; un sujeto de mayor integridad no debe leer de un objeto de menor integridad.

- `Propiedad de Integridad de Estrella`: Esta propiedad se conoce como "no escritura hacia arriba"; un sujeto de menor integridad no debe escribir en un objeto de mayor integridad.

Estas 2 propiedades se pueden resumir como "lectura hacia arriba, escritura hacia abajo". Esta regla contrasta con el modelo Bell-LaPadula, y esto no debería sorprender, ya que uno se ocupa de la confidencialidad mientras que el otro se ocupa de la integridad.

El modelo Biba sufre varias limitaciones. Un ejemplo es que no maneja amenazas internas.

### Modelo de Clark-Wilson
El modelo de `Clark-Wilson` también tiene como objetivo lograr la integridad mediante el uso de los siguientes conceptos:

- `Elemento de datos restringidos (CDI)`: Se refiere al tipo de datos cuya integridad queremos preservar.

- `Elemento de datos no restringidos (UDI)`: Se refiere a todos los tipos de datos más allá de CDI, como la entrada del usuario y del sistema.

- `Procedimientos de Transformación (TP)`: Estos procedimientos son operaciones programadas, como lectura y escritura, y deben mantener la integridad de los CDI.

- `Procedimientos de Verificación de Integridad (IVP)`: Estos procedimientos verifican y garantizan la validez de los CDI.

Cubrimos solo 3 modelos de seguridad. El lector pueede explorar muchos modelos de seguridadd adicionales. Algunos ejemplos inluyen:

- Modelo de Brewer y Nash
- Modelo de Goguen-Meseguer
- Modelo de Sutherland
- Modelo de Graham-Denning
- Modelo de Harrison-Ruzzo-Ullman

### Responda las preguntas a continuación
1. Haga clic en "Ver Sitio" y responda las cuatro preguntas. ¿Cuál es la bandera que obtuvo al final?
    - `THM{SECURITY_MODELS}`

### Preguntas
En principio de seguridad, elija opciones para salvaguardar la información. Asegure la confidencialidad, la integridad y la disponibilidad del sistema.

1. ¿Qué modelo dicta “no leer hacia abajo”? `Biba`
2. ¿Qué modelo establece “no leer hacia arriba”? `Bell-LaPadula`
3. ¿Qué modelo enseña “no escribir hacia abajo”? `Bell-LaPadula`
4. ¿Qué modelo obliga a “no escribir hacia arriba”? `Biba`

## Defensa en Profundidad

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/Defensa-Profundidad.png">
</p>

La defensa en profundidad se refiere a la creación de un sistema de seguridad de múltiples niveles; por eso también se le llama seguridad multinivel.

Considere la siguiente analogía: tiene un cajón cerrado con llave donde guarda sus documentos importantes y objetos de valor. El cajón está cerrado con llave; sin embargo, ¿quiere que la cerradura de este cajón sea lo único que se interponga entre un ladrón y sus objetos de valor? Si pensamos en la seguridad multinivel, preferiríamos que el cajón estuviera cerrado con llave, la habitación correspondiente, la puerta principal del apartamento, la puerta del edificio e incluso podría querer incluir algunas cámaras de seguridad en el camino.

Aunque estos múltiples niveles de seguridad no pueden detener a todos los ladrones, bloquearían a la amayoría de ellos y ralentizarían a los demás.

### Responda las preguntas a continuación
1. Asegúrese de haber leído lo anterior.

## ISO/IEC 19249
La organización Internacional de Normalización (ISO) y la comisión Electrotécnica Internacional (IEC) han creado la norma `ISO/IEC 19249`. En esta tarea, repasaremos brevemente la norma ***ISO/IEC 19249:2017*** Tecnología de la Información - Técnicas de Seguridad - Catálogo de principios arquitectónicos y de diseño para productos, sistemas y aplicaciones seguros. El objetivo es tenerr una mejor idea de lo que las organizaciones internacionales enseñarían sobre los principios de seguridad.

La norma **ISO/IEC 19249** enumera 5 principios arquitectónicos:

1. `Separación de Dominios`: Cada conjunto de componentes relacionados se agrupa como una sola entidad; los componentes pueeden ser aplicaciones, datos u otros recursos. Cada entidad tendrá su propio dominio y se le asignará un conjunto común de atributos de seguridad. Porr ejemplo, considere los niveles de privilegio del procesador x86: el núcleo del sistema operativo puede ejecutarse en el anillo 0 (el nivel más privilegiado). En contraste, las aplicaciones en modo usuario pueden ejecutarse en el anillo 3 (el nivel menos privilegiado). La separación de dominios está incluida en el modelo de Goguen-Meseguer.

2. `Capas`: Cuando un sistema está estructurado en muchos niveles abstractos o capas, es posible imponer políticas de seguridad en diferentes niveles; además, sería factible validar el funcionamiento. Consideremos el modelo OSI (Open Systems Interconnection) con sus 7 capas en redes. Cada capa en el modelo OSI proporciona servicios específicos a la capa superior. Esta superposición permite imponer políticas de seguridad y validar fácilmente que el sistema está funcionando como se espera. Otro ejemplo del mundo de la programación son las operaciones de disco; un programador generalmente utiliza las funciones de lectura y escritura de disco proporcionadas por el lenguaje de programación de alto nivel elegido. El lenguaje de programación oculta las llamadas al sistema de bajo nivel y las presenta como métodos más fáciles de usar. La superposición se relaciona con la defensa en profundidad.

3. `Encapsulación`: En la programación orientada a objetos (OOP), ocultamos las implementaciones de bajo nivel y evitamos la manipulación directa de los datos en un objeto proporrcionando métodos específicos para ese propósito. Por ejemplo, si tiene un objeto de reloj, proporcionaría un método increment() en lugar de darle al usuario acceso directo a la variable de segundos. El objetivo es evitar valores no válidos para sus variables. De manera similar, en sistemas más grandes, utilizaría para acceder a la base de datos.

4. `Redundancia`: Este principio garantiza la disponibilidad y la integridad. Hay muchos ejemplos relacionados con la redundancia. Considere el caso de un servidor de hardware con dos fuentes de alimentación integradas: si una fuente de alimentación falla, el sistema continúa funcionando. Considere una configuración RAID 5 con 3 unidades: si una unidad falla, los datos permanecen disponibles utilizando las 2 unidades restantes. Además, si los ddatos se modifican incorrecctamente en uno de los discos, se detectaría a través de la paridad, lo que garantiza la integridad de los datos.

5. `Virtualización`: Con la llegada de los servicios en la nube, la virtualización se ha vuelto más común y popular. El concepto de virtualización es compartir un único conjunto de hardware entre varios sistemas operativos. La virtualización proporciona capacidades de sandbox que mejoran los límites de seguridad, la detonación segura y la observación de programas maliciosos.

La norma ISO/IEC 19249 enseña 5 principios de diseño:

1. `Privilegio Mínimo`: También puede expresarlo de manera informal como "según la necesidad" o "según la necesidad de saber" al responder a la pregunta "¿quién puede acceder a qué?. El principio del privilegio mínimo enseña que debe proporcionar la menor cantidad de permisos para que alguien realice su tarea y nada más. Por ejemplo, si un usuario necesita poder ver un documento, debe otorgarle derechos de lectura sin derechos de escritura.

2. `Minimización de la Superficie de Ataque`: Todos los sistemas tienen vulnerabilidades que un atacante podría usar para comprometer un sistema. Algunas vulnerabilidades son conocidas, mientras que otras aún no se han descubierto. Estas vulnerabilidades representan riesgos que debemos intentar minimizar. Por ejemplo, en uno de los pasos para fortalecer un sistema Linux, deshabilitaríamos cualquier servicio que no necesitemos.

3. `Validación Centralizada de Parámetros`: Muchas amenazas se deben a que el sistema recibe información, especialmente de los usuarios. Las entradas no válidas se pueden utilizar para explotar vulnerabilidades en el sistema, como la denegación de servicio y la ejecución remota de código. Por lo tanto, la validación de parámetros es un paso necesario para garantizar el estado correcto del sistema. Teniendo en cuenta la cantidad de parámetros que maneja un sistema, la validación de los parámetros debe estar centralizada dentro de una biblioteca o sistema.

4. `Servicios de Seguridad General Centralizados`: Como principio de seguridad, deberíamos intentar centralizar todos los servicios de seguridad. Por ejemplo, crearíamos un servidor centralizado para la autenticación. Por supuesto, es posible que tome las medidas adecuadas para garantizar la disponibilidad y evitar la creacación de un único punto de falla.

5. `Preparación para el manejo de errores y excepciones`: Siempre que construyamos un sistema, debemos tener en cuenta que los errores y las excepcionees ocurren y ocurrirán. Por ejemplo, en una aplicación de compras, un cliente podría intentar realizar un pedido de un artículo fuera de stock. Una base de datos podría sobrecargarse y dejar de responder a una aplicación web. Este principio enseña que los sistemas deben diseñarse para que sean a prueba de fallas;, por ejemplo, si un firewall falla, debería bloquearr todo el tráfico en lugar de permitirlo. Además, debemos tener cuidado de que los mensajes de error no filtren información que consideramos confidencial, como volcar contenido de la memoria que contiene información relacionada con otros clientes.

En las siguientes preguntas, haga referencia a los cinco principios de diseño de la norma ISO/IEC 19249 anteriores. Responda con un número entre 1 y 5, según el número del principio de diseño.

### Responda las preguntas a continuación
1. ¿Qué principio está aplicando cuando apaga un servidor inseguro que no es crítico para el negocio? `2`

2. Su empresa contrató a un nuevo representante de ventas. ¿Qué principio está aplicando cuando le dice que le dé acceso solo a los productos y precios de la empresa? `1`

3. Mientras leía el código de un cajero automático, notó una gran cantidad de código para manejar situaciones inesperadas, como la desconexión de la red y el corte de energía. ¿Qué principio está aplicando? `5`

## Confianza Cero vs Confianza pero Verificación

La confianza es un tema muy complejo; en realidad, no podemos funcionar sin confianza. Si uno pensara que el fabricante de la computadora portátil ha instalado softwware eespía en la computadora portátil, lo más probable es que terminara reconstruyendo el sistema.

Si uno desconfiara del fabricante del hardware, dejaría de usarlo por completo. Si pensamos en la confianza a nivel empresarial, las cosas solo se vuelven más sofisticadas; sin embargo, necesitamos algunos principios de seguridad que nos sirvan de guía. 2 principios de seguridad que nos interesan en relación con la confianza:

- Confianza pero Verificación
- Confianza Cero

- `Confianza pero Verificación`: Este principio enseña que siempre debemos verificar, incluso cuando confiamos en una entidad y su comportamiento. Una entidad puede ser un usuario o un sistema. La verificación generalmente requiere establecer mecanismos de registro adecuados; verificar significa revisar los registros para asegurarse de que todo esté normal. En realidad, no es posible verificar todo; solo pieense en el trabajo que requiere revisar todas las acciones realizadas por una sola entidad, como las páginas de Internet visitadaspor un solo usuario. Esto requiere mecanismos de seguridad automatizados, como servidores proxy, detección de intrusionees y sistemas de prevención de intrusiones.

- `Confianza Cero`: Este principio trata la confianza como una vulnerabilidad y, en consecuencia, atiende las amenazas internas. Despues de considerar la confianza como una vulnerabilidad, la confianza cero intenta eliminarla. Enseña indirectamente "nunca confíes, siempre verifica"". En otras palabras, cada entidad se considera adversaria hasta que se demuestre lo contrario. La confianza cero no otorga confianza a un dispositivo en función de su ubicación o propiedad. Este enfoque contrasta con los modelos más antiguos que confiarían en las redes internas o en los dispositivos propiedad de la empresa. Se requiere autenticación y autorización antes de acceder a cualquier recurso. Como resultado, si ocurre alguna infracción, el daño estaría más contenido si se hubiera implementado una arquitectura de confianza cero.

La microsegmentación es una de las implementaciones utilizadas para la confianza cero. Se refiere al diseño donde un segmento de red puede ser tan pequeño como un solo host. Además, la comunicación entre segmentos requiere autenticación, verificaciones de listas de control de acceso y otros requisitos de seguridad.

Hay un límite en cuanto a cuánto podemos aplicar la confianza cero sin afectar negativamente a una empresa; Sin embargo, esto no significa que no debamos aplicarlo siempre que sea factible.

### Responde las preguntas a continuación
1. Asegúrate de haber leído lo anterior.
    - `No se necesita respuesta`

## Amenaza vs Riesgo

<p align="center">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Principios-Seguridad/Amenaza-Riesgo.png">
</p>

Hay tres términos que debemos tener en cuenta para evitar confusiones.

- `Vulnerabilidad`: Significa susceptible a ataques o daños. En seguridad de la información, una vulnerabilidad es una debilidad.

- `Amenaza`: Es un peligro potencial asociado con esta debilidad o vulnerabilidad.

- `Riesgo`: Se relaciona con la probabilidad de que un actor de amenazas explote una vulnerabilidad y el consiguiente impacto en el negocio.

Fuera de los sistemas de información, una sala de exposición con puertas y ventanas hechas de vidrio estándar sufre una debilidad o vulnerabilidad debido a la naturaleza del vidrio. En consecuencia, existe la amenaza de que las puertas y ventanas de vidrio se rompan. Los propietarios de la sala de exposición deben contemplar el riesgo, es decir, la probabiliddad de que una puerta o ventana de vidirio se rompa y el impacto resultante en el negocio.

Considere otro ejemplo directamente relacionado con los sistemas de información. Usted trabaja para un hospital que utiliza un sistema de base de datos particular para almacenar todos los registros médicos. Un día, está siguiendo las últimas noticias de seguridad y se entera de que eñ sistema de base de datos utilizado bo solo es vulnerable, sino que también se ha publicado un código de explotación funcional de prueba de concepto; El código de explotación publicado indica que la amenaza es real. Con este conocimiento, debe considerar el riesgo resultante y decidir los pasos a seguir.

Abordaremos las amenazas y los riesgos en detalle en una sala aparte.

### Responda las preguntas a continuación
1. Asegúrese de haber leído lo anterior

## Conclusión

En esta sala se trataron varios principios y conceptos relacionados con la seguridad A estas alturas, ya debería estar muy familiarizado con CIA y DAD y otros términos como autenticidad, repudio, vulnerabilidad, amenaza y riesgo.

Visitamos tres modelos de seguridad y la norma ISO/IEC 19249. Hemos tratado diferentes principios de seguridad como defensa en profundidad, confianza pero verificación y confianza cero.

Por último, vale la pena mencionar el modelo de responsabilidad compartida, especialmente con la mayor dependencia de los servicios en la nube. Se requieren varios aspectos para garantizar una seguridad adecuada. Entre ellos se incluyen el hardware, la infraestructura de red, los sistemas operativos, las aplicaciones, etc.

Sin embargo, los clientes que utilizan servicios en la nube tienen diferentes niveles de acceso según los servicios en la nube que utilicen. Por ejemplo, un usuario de Infraestructura como Servicio (IaaS) tiene control (y responsabilidad) completo sobre el sistema operativo.

Por otro lado, un usuario de Software como Servicio (SaaS) no tiene acceso directo al sistema operativo subyacentee. En consecuencia, lograr seguridad en un entorno de nube requiere que tanto el proveedor de servicios en la nube como el usuario hagan su parte. El modelo de responsabilidad compartida es un marco de seguridad en la nube que garantiza que cada parte sea conssciente de su responsabilidad.

Una vez que haya terminado la sala de *Principios de Seguridad*, puede pasar a la sala de [Introducción a la Criptografía]().

### Responda las preguntas a continuación
1. Asegúrese de tomar nota de todos los términos y acrónimos clave que cubrimos en esta sala.
