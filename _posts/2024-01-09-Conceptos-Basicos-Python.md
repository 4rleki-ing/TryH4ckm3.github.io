---
layout: single
title: Conceptos básicos de Python
excerpt: "Con un editor de código basado en la web, aprenda los conceptos básicos de Python y ponga en práctica sus conocimientos codificando un breve proyecto de inversión en Bitcoin."
date: 2024-08-23
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Conceptos-Python/Python.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Conceptos-Python/Portada.png">

## Introducción
En esta sala, aprenderá y practicará sobre el lenguaje de programación Python, Aunque no es necesario saber programar para tener éxito en seguridad, es una gran habilidad. Como demuestra el módulo "Programación para Pentesters", saber programar le permite crear herramientas de seguridad y crear scripts rápidos que lo ayudarán a piratear (así como defenderse y analizar).

En esta sala aprenderá:
- Variables
- Bucles
- Funciones
- Estructura de datos
- Declaraciones if
- Archivos

Usará el editor de código (en el lado derecho) para completar ejercicios y resolver desafíos. En esta sala, aprenderá los conceptos básicos, lo suficiente para brindarle el conocimiento necesario para crear sus scripts básicos. Si desea utilizar su entorno de desarrollo para codificar, descargue Python en el [sitio web oficial](https://www.python.org/downloads/); que le brinda un IDE (entorno de desarrollo integrado) para ccodificar.

En programación, la sintaxis es importante ya que describe la estructura de un lenguaje de programación válido. En términos simples, la sintaxis le dice a la computadora cómo leer el código usando reglas que controlan la estructura de los símbolos, la puntuación y las palabras de un lenguaje de programación.

### Responde las preguntas a continuación
- Ejecuta lo que se encuentra actualmente en el editor de ccódigo haciendo clic en el botón verde "Ejecutar código" (en el lado derecho de tu pantalla) y pasa a la siguiente tarea.

## Hola Mundo
Para comenzar, vamos a crear un programa simple que genere algún texto.

```py
# This is an example comment
print("Hello World")
```

Como puede ver en el bloque de código de ejemplo anterior, es solo una línea (que se muestra en la línea 2) y, cuando ejecutamos este código, mostrará un texto `Hola Mundo`. Vamos a desglosarlo. En el ejemplo, la línea 1 es un comentario, una línea que comienza con un símbolo de `hashtag (#)` y no la ejecuta la computadora. El pogramador (usted) escribe un comentario para ayudar a otras personas que leen el código a comprender lo que está sucediendo.

Podemos controlar lo que se muestra en la pantalla mediante la declaración `print()`. Se mostrará todo lo que esté dentro de los paréntesis (). Sin embargo, debido a que estamos imprimiendo una cadena (más sobre los tipos de datos más adelante en esta sala), tenemos que ponerlos entre comillas `""`.

Tenga en cuenta que los ejemplos de esta sala son pára Python3.

### Responda las preguntas a continuación
1. En el editor de código, imprima "Hello world". ¿Cuál es la bandera? `THM{PRINT_STATEMENTS}`

## Operadores Matemáticos
Abordemos ahora los operadores matemáticos y cómo se pueden aplicar a Python. Al igual que una calculadora, existen operaciones como sumar, restar, multiplicar y dividir; utilizando Python, podemos codificar nuestra calculadora; después de todo, la programación es simplemente escribir reglas para que la computadora las siga dadas las entradas y condiciones específicas. La siguiente tabla muestra las diferentes operaciones.

<table align="center">
    <tr>
        <th>Operador</th>
        <th>Sintaxis</th>
        <th>Ejemplo</th>
    </tr>
    <tr>
        <td>Suma</td>
        <td>+</td>
        <td>1 + 1 = 2</td>
    </tr>
    <tr>
        <td>Resta</td>
        <td>-</td>
        <td>5 - 1 = 4</td>
    </tr>
    <tr>
        <td>Multiplicación</td>
        <td>*</td>
        <td>10 * 10 = 100</td>
    </tr>
    <tr>
        <td>División</td>
        <td>/</td>
        <td>10 / 2 = 5</td>
    </tr>
    <tr>
        <td>Módulo</td>
        <td>%</td>
        <td>10 % 2 = 0</td>
    </tr>
    <tr>
        <td>Exponente</td>
        <td>**</td>
        <td>5**2 = 25</td>
    </tr>
</table>

Ahora que conocemos los operadores matemáticos básicos, pasemos a los operadores de comparación; estos desempeñan un papel importante en Python y se utilizarán cuando analicemos los bucles y las instrucciones if. Estos operadores se utilizan para evaluar la condición de un programa en un estado particular.

<table align="center">
    <tr>
        <th>Símbolo</th>
        <th>Sintaxis</th>
    </tr>
    <tr>
        <td>Mayor que</td>
        <td>></td>
    </tr>
    <tr>
        <td>Menor que</td>
        <td><</td>
    </tr>
    <tr>
        <td>Igual a</td>
        <td>==</td>
    </tr>
    <tr>
        <td>No igual a</td>
        <td>!=</td>
    </tr>
    <tr>
        <td>Mayor o igual que</td>
        <td>>=</td>
    </tr>
    <tr>
        <td>Menor o igual que</td>
        <td><=</td>
    </tr>
</table>

### Responde las preguntas a continuación
1. En el editor de código, imprime el resultado de 21 + 43. ¿Cuál es la bandera? `THM{ADDITI0N}`
2. Imprime el resultado de 142 - 52. ¿Cuál es la bandera? `THM{SUBTRCT}`
3. Imprime el resultado de 10 * 342. ¿Cuál es la bandera? `THM{MULTIPLICATION_PYTHON}`
4. Imprime el resultado de 5 al cuadrado. ¿Cuál es la bandera? `THM{EXP0N3NT_POWER}`

## Variables y Tipos de Datos
Las variables permiten almacenar y actualizar datos en un programa informático. La `variable` tiene un nombre y almacena datos con ese nombre.

```py
food = "ice cream"
money = 2000
```

En el ejemplo anterior, tenemos dos variables. La variable llamada "food" almacenada en la cadena (palabras o words) helado, mientras que otra vriable llamada "money" almacena un número (2000).

Las variables son muy útiles, ya que puedes cambiarlas a lo largo de tu programa. El siguiente ejemplo establece la variable de edad en 30, luego aumentamos esta variable de edad en 1, lo que hace que la variable final sea 31. Puedes copiar y pegar esto en el editor, ejecutar el código y ver el resultado.

```py
age = 30
age = age + 1
print(age)
```

Observe que, en la línea 2, la forma en que actualizamos una variable, a la izquierda, ya tenemos el nombre de variable `edad` seguido del operador `=`. A la derecha, tenemos lo que estamos configurando para la variable; en nuestro caso, la variable edad (que actualmente está configurada en 30) se está incrementando en 1.

Hablemos de los tipos de datos, que es el tipo de datos que se almacenan en una variable. Puede almacenar texto, números y muchos otros tipos. Los tipos de datos que ddebe conocer son:

- `Cadena`: Se utiliza para combinaciones de caracteres, como letras o símbolos.
- `Entero`:  Números enteros.
- `Flotante`: Números que contienen puntos decimales o para fracciones.
- `Booleano`: Se utiliza para datos que están restringidos a las opciones Verdadero o Falso.
- `Lista`: Serie de diferentes tipos de datos almacenados en una colección.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Conceptos-Python/datos.png">

### Responde las preguntas a continuación
1. En el editor de código, crea una variable llamada altura y establece su valor inicial en 200.
2. En una nueva línea, agrega 50 a la variable altura.
3. En otra nueva línea, imprime el valor de la altura. ¿Cuál es la bandera que aparece? `THM{VARIABL3S}`

## Operadores Lógicos y Booleanos
Los operadores lógicos permiten realizar asignaciones y comparaciones u se utilizan en pruebas condicionales (como las declaraciones if).

<table align="center">
    <tr>
        <th>Operación Lógica</th>
        <th>Operador</th>
        <th>Ejemplo</th>
    </tr>
    <tr>
        <td>Equivalencia</td>
        <td>==</td>
        <td>if x == 5</td>
    </tr>
    <tr>
        <td>Menor que</td>
        <td><</td>
        <td>if x < 5</td>
    </tr>
    <tr>
        <td>Menor o igual que</td>
        <td><=</td>
        <td></td>
    </tr>
    <tr>
        <td>Mayor que</td>
        <td>></td>
        <td>if x > 5</td>
    </tr>
    <tr>
        <td>Mayor o igual que</td>
        <td>>=</td>
        <td>if x >= 5</td>
    </tr>
</table>

Los operadores booleanos se utilizan para conectar y comparar relaciones entre declaraciones. Al igual que en una declaración if, las condiciones pueden ser verdaderas o falsas.

<table align="center">
    <tr>
        <th>Operación Booleana</th>
        <th>Operador</th>
        <th>Ejemplo</th>
    </tr>
    <tr>
        <td>Ambas condiciones deben ser verdaderas para que la declaración sea verdadera.</td>
        <td>AND</td>
        <td>if x >= 5 AND X <= 100 (Devuelve TRUE si x es un número entre 5 y 100)</td>
    </tr>
    <tr>
        <td>Sólo una condición de la declaración debe ser verdadera.</td>
        <td>OR</td>
        <td>if x == 1 OR x == 10 (Devuelve TRUE si x es 1 o 10)</td>
    </tr>
    <tr>
        <td>Si una condición es lo opuesto de un argumento</td>
        <td>NOT</td>
        <td>if NOT y (Devuelve TRUE si el valor y es Falso)</td>
    </tr>
</table>

Veamos algunos ejemplos de código Python:

```py
a = 1
if a == 1 or a > 10:
     print("a is either 1 or above 10")
```
```py
name = "bob" 
hungry = True
if name == "bob" and hungry == True:
     print("bob is hungry")
elif name == "bob" and not hungry:
     print("Bob is not hungry")
else: # If all other if conditions are not met
     print("Not sure who this is or if they are hungry")
```

### Responda las preguntas a continuación
1. Lea la sección anterior

## [Proyecto de Envío] Introducción a las Instrucciones if
El uso de instrucciones `if` permite a los programas tomar decisiones. Permiten que un programa elija una desición en función de una condición. A continuación, se muestra un ejemplo de cómo se pueden utilizar una instrucción if para determinar la sección de código (qué instrucción de impresión) utilizar.

```py
if age < 17:
    print('You are NOT old enough to drive')
else:
    print('You are old enough to drive')
```

En el ejemplo, si eres menor de 17 años, el programa mostrará el texto "NO tienes la edad suficiente para conducir"; sin embargo, si eres mayor de 17 años, el programa mostrará "Tienes la edad suficiente para conducir". Según una condición (en este ejemplo, es la variable edad), el programa ejecutará diferentes secciones de código.

Hay algunos componentes clave que notamos en nuestro ejemplo de código anterior:

- La palabra clave `if` indica el comienza de la declaración if, seguida de un conjunto de condiciones.
- La declaración if sólo se ejecuta si la condición (o conjunto de condiciones) es verdadera. En nuestro ejemplo, es `age < 17`; si esta conddición ees verdadera (edad es menor de 17), se ejecuta el código dentro de la declaración if. Según el ejemplo, si no se cumplen ciertas condiciones, el programa puede ejecutar de manera predeterminada el código que se muestra en la parte `else` de la declaración if.
- `Dos puntos (:)` Marca el final de la declaración if.
- Tenga en cuenta `la sangría`. Cualquier cosa después de los dos puntos que esté sangrada se considera parte de la declaración if, que el programa ejecutará.

<img align="center" src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Conceptos-Python/Prueba-Manejo.png">

Las instrucciones if son esenciales en la programación y serán algo que usará mucho.

### Responda las preguntas a continuación
En este ejercicio, codificaremos una pequeña aplicación que calcula y genera el costo de envío para un cliente en función de cuánto gastó.

1. En el editor de código, haga clic en la pestaña `shipping.py` y siga las instrucciones para completar esta tarea.

```py
"""
En este proyecto, creará un programa que calcule el costo total
de la cesta de la compra de un cliente, incluido el envío.

- Si un cliente gasta más de $100, obtiene envío gratis
- Si un cliente gasta menos de $100, el costo de envío es de $1,20 por kg de peso de la cesta

Imprima el costo total de la cesta del cliente (incluido el envío) para completar este ejercicio.

"""

shipping_cost_per_kg = 1.20
customer_basket_cost = 101
customer_basket_weight = 44

if(customer_basket_cost >= 100):
  print('Free shipping!')
else:
  shipping_cost = customer_basket_weight * shipping_cost_per_kg
  customer_basket_cost = customer_basket_cost + shipping_cost

print("Total basket cost including shipping is " + str(customer_basket_cost))
```

2. Una vez que haya escrito la aplicación en la pestaña "sshipping.py" del editor de código, aparecerá una bandera, que es la respuesta a esta pregunta. `THM{IF_STATEMENT_SHOPPING}`
3. En "Shipping.py", en la línea 12 (Cuando use la sugerencia del editor de código), cambie la variable `customer_basket_cost` a 101 y vuelva a ejecutar su código. Obtendrá una bandera (si el costo total es correcto según su código); la bandera es la respuesta a esta pregunta. `THM{MY_FIRST_APP}`

## Bucles (Loops)

En programación, los bucles permiten que los programas se repita y realicen acciones varias veces. Hay dos tipos de bucles: `bucles for` y `bucles while`.

### Bucles While
Comencemos por ver cómo estructuramos un bucle While. Podemos hacer que el bucle se ejecute indefinidamente o (de manera similar a una declaración if) determinar cuántas veces debe ejecutarse el bucle en función de una condición.

```py
i = 1
while i <= 10:
     print(i)
     i = i + 1
```

Este bucle while se ejecutará 10 veces y mostrará el valor de la variable `i` cada vez qye se repita. Analicemos esto:

- La variable `i` se establece en 1
- La instrucción `while` especifica dónde debe comenzar el inicio del bucle.
- Cada vez que se repita, comenzará en la parte superior (mostrando el valor de i)
- Luego (como no hay más código para que el programa ejecute), pasa al princcipio del bucle y comienza el proceso nuevamente
- El programa seguirá repitiéndose hasta que el valor de la variable i sea mayor que 10.

### Bucles for
Un bucle for se usa para iterar sobre una secuencia, como una lista. Las listas se usan para almacenar varios elementos en una sola variable y se crean usando corchetes (ver a continuación). Aprendamos a través del siguiente ejemplo:

```py
websites = ["facebook.com", "google.com", "amazon.com"]
for site in websites:
     print(site)
```

Este bucle for que se muestra en el bloque de código anterior se ejecutará 3 veces y mostrará cada sitio web de la lista. Analicemos esto:

- La variable de lista denominada sitios web almacena 3 elementos
- El bucle itera a través de cada elemento y lo imprime
- El programa deja de repetirse cuando ha pasado por cada elemento del buble

Para dar un escenario del mundo real, podría crear un programa que verifique si un sitio web está en línea o si un artículo está en stock. Recorrería la lista de sitios web, agregaría una funcionalidad dentro y mostraría los resultados. La sala [Python para Pentesters]() le muestra cómo usar Python para enumerar un objetivo, crear un keylogger, escanear una red y más.

En Python, también podemos iterar a través de un rango de números usando la función `range`. A continuación se muestra un código de ejemplo de Python que imprimirá los números del 0 al 4. En programación, 0 suele ser el número inicial, por lo que contar hasta 5 es del 0 al 4 (pero tiene 5 números: 0, 1, 2, 3 y 4).

```py
for i in range(5):
     print(i)
```

### Reesponda las preguntas a continuación
1. En el editor de código, vuelva a hacer en la pestaña ""script.py" y codifique un bucle que genere todos los números del 0 al 50. `THM{L00PS_WHILE_FOR}`

```py
i = 0
while i <= 50:
  print(i)
  i = i + 1
```

## [Proyecto Bitcoin] Introducción a las Funciones
A medida que los programas se vuelven más grandes y complejos, parte del código será repetitivo, y se escribirá el mismo ccódigo para hacer los mismos cálculos. Aquí es donde entran en juego las funcciones. Una función es un bloque de código que se puede llamar en diferentes lugares de un programa.

Se pueden tener una función paraa realizar un cálculo, como la distancia entre 2 puntos en un mapa, o generar texto formateado en función de ciertas condiciones. Tener funciones elimina el código repetitivo, ya que el propósito de la función se puede utilizar varias veces a lo largo de un programa.

```py
def sayHello(name):
     print("Hello " + name + "! Nice to meet you.")

sayHello("ben") # Output is: Hello Ben! Nice to meet you
```

hay algunos componentes clave que podemos notar en esta función:

- La palabra clave `def` indica el comienzo de una función. La función va seguida de un nombre que define el programador (y es un parámetro de la función). En nuestro ejemplo, es **sayHello**.
- Después del nombre de la función hay un par de `paréntesis ()` que contienen valores de entrada, datos que podemos pasar a la función. En nuestro ejemplo, es **name**.
- `Dos puntos (:)` marca el final del encabezado de la función.

En la función, observe la sangría. De manera similar a las declaraciones if, todo lo que esté sangrado después de los dos puntos se considera parte de la función.

Una función también puede devolver un resultado, vea el bloque de código a continuación:

```py
def calcCost(item):
     if(item == "sweets"):
          return 3.99
     elif (item == "oranges"):
          return 1.99
     else:
          return 0.99

spent = 10
spent = spent + calcCost("sweets")
print("You have spent:" + str(spent))
```

Si llamamos a la función `calcCost` y pasamos "sweets" como parámetro del artículo, la función devolverá un número decimal (float). En el código anterior, tomamos una variable llamada "spent" y sumamos el costo de "sweets" a través de la función "calcCost"; cuando llamamos a calcCost, devolverá el número 3.99

### Responde las preguntas a continuación
Has invertido en Bitcoin y quieres escribir un programa que te diga cuándo el valor de Bitcoin cae por debajo de un valor particular en dólares.

En el editor de código, haz clic en la peestaña `bitcoin.py`. Escribe una función llamada `bitcoinToUSD` con dos paarámetros: bitcoin_amount, la cantidad de Bitcoin que posees, y bitcoin_value_usd, el valor de Bitcoin en USD. La función debe devolver usd_value, que es el valor de tu Bitcoin en USD (paara calcularlo, en la función, multiplicas la variable bitccoin_amount por la variable bitcoin_value_usd y devuelves el valor). El inicio de la función debe verse así:

```py
def bitcoinToUSD(bitcoin_amount, bitcoin_value_usd):
```

1. Una vez que haya escrito la función bitcoinToUSD, úsela para calcular el valor de su Bitcoin en USD y luego cree una declaración if para determinar si el valor cae por debajo de $30,000; si lo hace, genere un mensaje para alertarlo (a través de una declaración de impresión).
    - `THM{BITC0IN_INVESTOR}`

2. 1 bitcoin ahora vale $24,000. En el editor de código, en la línea 14, actualice el valor de la variable bitcoin_to_usd a 24000 y vea si su programa Python reconoce que su inversión está por debajo del umbral de $30,000.

```py
"""
    In this project, you'll create a program that that tells
    you when the value of your Bitcoin falls below $30,000.

    You will need to:
    - Create a function to convert Bitcoin to USD
    - If your Bitcoin falls below $30,000 print a message.

    You can assume that 1 Bitcoin is worth $40,000

    ===> You've redeemed a hint. Replace the _'s with code to complete this exercise.

"""

investment_in_bitcoin = 1.2
bitcoin_to_usd = 40000

# 1) write a function to calculate bitcoin to usd
def bitcoinToUSD(bitcoin_amount, bitcoin_value_usd):
  usd_value = investment_in_bitcoin * bitcoin_to_usd
  return usd_value

investment_in_usd = bitcoinToUSD(investment_in_bitcoin, bitcoin_to_usd)
if investment_in_usd <= 30000:
  print("Investment below $30,000! SELL!")
else:
  print("Investment above $30,000")
```

## Archivos
En Python, puedes leer y escribir desde archivos. Hemos visto que, en el ámbito de la seguridad informática, es habitual escribir un script e importarlo o exportarlo desde un archivo, ya sea como una forma de almacenar el resultado del script o para importar una lista de cientos de sitios web desde un archivo paara enumerarlos. Veamos un ejemplo:

```py
f = open("file_name", "r")
print(f.read())
```

Para abrir el archivo, utilizamos la función `open()` incorporada, y el parámetro `r` significa "leer" y se utiliza mientras leemos el contenido del archivo. La variable tiene un método `read()` para leer el contenido del archivo. También puede utilizar el método `readlines()` y recorrer cada línea del archivo; es útil si tiene una lista en la que cada elemento está en una nueva lista. En el ejemplo anterior, el archivo está en la misma carpeta que el script de Python; si estuviera en otro lugar, necesitaría especificar la ruta completa del archivo.

También puede crear y escribir archivos. Si está escribiendo en un archivo existente, primero abre el archivo y utiliza la `a` en la función `open` después de la llamada al nombre del archivo (que significa "add"). Si está escribiendo en un archivo nuevo, utiliza `w` (escribir) en lugar de `a`. Vea los ejemplos a continuación para mayor claridad:

```py
f = open("demofile1.txt", "a") # Append to an existing file
f.write("The file will include more text..")
f.close()

f = open("demofile2.txt", "w") # Creating and writing to a new file
f.write("demofile2 file created, with this content in!")
f.close()
```

Observe que usamos el método `close()` después de escribir en un archivo; esto cierra el archivo, por lo que ya ano se puede escribir más en él (dentro del programa).

### Responda las preguntas a continuación
1. En el editor de código, escriba el código Python ppara leer el archivo (flag.txt). ¿Cuál es la bandera en este archivo? `THM{F1LE_R3AD}`

```py
f = open("flag.txt", "r")
print(f.read())
```

## Importaaciones
En Python, podemos importar bbibliotecas, que son una colección de archivos que contienen funciones. Piense en la importación de una biblioteca como en la importación de funcionees que pueden utilizar y que ya se han escrito paara usted. Por ejemplo, existe una biblioteca "date" que le brinda acceso a cientos de funciones diferentes para cualquier cosa relacionada con la fecha y la hora.

```py
import datetime
current_time = datetime.datetime.now()
print(current_time)
```

Importamos otras bibliotecas usando la palabra clave `import`. Luego, en Python, usamos el nombre de la biblioteca de esa importación para hacer referencia a sus funciones. En el ejemplo anterior, importamos `datetime` y luego accedemos al método `.now()` llamando a `library_name.method_name()`. Copia y pega el ejemplo anterior en el editor de código.

A continuación, se muestran algunas biblioetcas populares que pueden resultarte útiles al crear scripts como pentester:

- Request: Biblioteca HTTP simple
- [Scapy](https://scapy.readthedocs.io/en/latest/introduction.html): Envía, rastrea, disecciona y falsifica paquetes de red.
- [Pwntools](https://docs.pwntools.com/en/stable/): Una biblioteca de desarrollo de CTF y exploits.

Muchas de estas bibliotecas ya están integradas en el lenguaje de programación; sin embargo, las bibliotecas escritas por otros programadores que aún no están instaladas en tu máquina se pueden instalar usando una aplicación llamada `pip`, que es el administrador de paquetes de Python. Digamos que quieres instalar la biblioteca `scapy` (que te permite crear tus propios paquetes en código y enviarlos a otras máquinas); Primero lo instalas ejecutando el comando `pip install sscapy`, luego en tu programa puedes importar la biblioteca scapy.

### Responde las preguntas a continuación
1. Lee la tarea y ejecuta el código de ejemplo de Python anterior en el editor de código a la derecha.