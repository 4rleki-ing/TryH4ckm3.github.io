---
layout: single
title: Introducción a la Seguridad Ofensiva
excerpt: "Hackea tu primer sitio web (legalmente en un entorno seguro) y experimenta el trabajo de un hacker ético."
date: 2024-08-30
classes: wide
header:
  teaser: https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Ofensiva/Seguridad.png
  teaser_home_page: true
categories:
  - Ciberseguridad
  - TryHackme
tags:
  - Pentesting
  - OSWP
  - TryHackme
---

<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Ofensiva/Portada.png" align= left>

# ¿Qué es la Seguridad Ofensiva?

<p align="left">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Ofensiva/Ofensiva.png">
</p>

En resumen, la `seguridad ofensiva` es el proceso de *entrar en los sistemas informáticos*, *explotar errores* de software y *encontrar lagunas* en las aplicaciones para obtener acceso no autorizado a ellas.

Para vencer a un hacker, se debe de comportar como un hacker, encontrar vulnerabilidades y recomendar parches antes de que lo haga un cibercriminal, como se hará en esta sala.

<p align="left">
<img src="https://4rleki-ing.github.io/TryH4ckm3.github.io/assets/images/Introduccion-Seguridad-Ofensiva/Defensiva.png">
</p>

Por otro lado, también existe la `seguridad defensiva`, que es el proceso de *proteger la red* y los sistemas informáticos de una organización mediante el análisis y la protección de cualquier amenaza digital potencial; obtén más información en la sala de [análisis forense digital]().

En un rol cibernético defensivo, podría investigar computadoras o dispositivos infectados para comprender cómo fueron atacados, rastrear cibercriminales o monitorear la infraestructura para detectar actividad maliciosa.

### Responda las preguntas a continuación
1. ¿Cuál de las siguientes opciones representa mejor el proceso en el que se simulan las acciones de un hacker para encontrar vulnerabilidades en un sistema?
    - `Seguridad Ofensiva`
    - Seguridad Defensiva

# Hackeando la primer máquina
Antes de adentrarnos en las **carreras de Seguridad Cibernética** y en lo que es la seguridad ofensiva, vamos a empezar a hackear *(simulaciones falsas)*.

Cuando abras esta tarea por primera vez en una computadora de escritorio, la pantalla iniciará automáticamente la máquina virtual de la tarea y la mostrará en una pantalla dividida.

Se usará para hackear una *aplicación bancaria* falsa llamada `FakeBank`. También se puede hacer clic en el botón **"Iniciar Máquina"** para implementarla desde un dispositivo móvil.

Usaremos una aplicación de línea de comandos llamada [GoBuster]() para forzar el sitio web de *FakeBank* y **encontrar directorios** y **páginas ocultas**. GoBuster tomará una lista de posibles nombres de páginas o directorios e intentará acceder a un sitio web con cada uno de ellos; ***si la página existe, te lo dirá***.

## Paso 1. Abre una Terminal
Una terminal, también conocida como `línea de comandos`, nos permite interactuar con una computadora sin usar una interfaz gráfica de usuario.

## Paso 2. Encuentra páginas ocultas en el sitio web
La mayoría de las empresas tienen una página de **portal de administración**, que brinda a su personal acceso a *controles administrativos básicos* para las operaciones diarias.

En el caso de un banco, un empleado puede necesitar transferir dinero hacia y desde las cuentas de los clientes. A menudo, estas páginas *no son privadas*, lo que permite a los atacantes encontrar páginas ocultas que muestran o brindan acceso a controles administrativos o datos confidenciales.

Escribe el siguiente comando en la terminal para encontrar páginas potencialmente ocultas en el sitio web de FakeBnak usando GoBuster (una aplicación de seguridad de línea de comandos).

```bash
$ gobuster -u http://fakebank.com -w wordlist.txt dir
```

En el comando anterior, se utiliza la opciónn `-u` para indicar el sitio web que estamos escaneando, y la opción `-w` toma una lista de palabras para iterar a través de ellas para encontrar páginas ocultas.

Verás que GoBuster escanea el sitio web con cada palabra de la lista y encuentra páginas que existen en el sitio. GoBuster habrá indicado las páginas que encontró en la lista de nombres de páginas/directorios (Indicadas por el Estado: 200).

## Paso 3. Hackea el Banco
Deberías haber encontrado una *página secreta de transferencia bancaria* que permite transferir dinero entre cuentas en el banco `/bank-transfer`. Escribe la página oculta en el sitio web de FakeBank en la máquina.

Esta página permite a un atacante robar dinero de cualquier cuenta bancaria, lo que es un *riesgo crítico* para un banco. Como hacker ético, deberías (con permiso) encontrar vulnerabilidades en su aplicación y reportarlas al banco para que las arregle antes de que un hacker las explote.

`Actividad`: Transfiere $2,000.00 de la cuenta bancaria (2276) a tu cuenta (Número de cuenta 8881).

### Responde las preguntas a continuación
Si tu transferencia fue exitosa, ahora deberías poder ver tu nuevo saldo reflejado en la página de tu cuenta. ¡Ve allí ahora y confirma que recibiste el dinero! (Es posible que debas actualizar para que aparezcan los cambios).

1. Sobre el saldo de tu cuenta, deberías ver un mensaje que indica la respuesta a esta pregunta. ¿Puedes encontrar la respuesta que necesitas? `BANK-HACKED`

Si fueras un evaluador de penetración o un consultor de seguridad, este es un ejercicio que realizarías para que las empresas prueben las vulnerabilidades en sus aplicaciones web; encuentra páginas ocultas para investigar en busca de vulnerabilidades.

Para cerrar la máquina se busca el botón rojo *"Cerrar"* en la parte superior de la página.

# Carreras en Seguridad Cibernética
La gente suele preguntarse cómo otros se convierten en hackers *(consultores de seguridad)* o defensores *(analistas de seguridad que luchan contra el cibercrimen)*, y la respuesta es sencilla.

**Desglóselo**, aprenda un área de seguridad cibernética que le interese y practique regularmente con ejercicios prácticos. Adquiera el hábito de aprender un poco cada día en TryHackMe y aquirirá el conocimiento para conseguir su primer trabajo en la industria.

## ¿Qué carreras existen?
La sala de carreras cibernéticas profundiza en las diferentes carreras en ciberseguridad. Sin embargo, aquí hay una breve descripción de algunos roles de seguridad ofensiva:

- `Probador de Penetración`: Responsable de probar productos tecnológicos para encontrar vulnerabilidades de seguridad explotables.
- `Red Teamer`: Desempeña el papel de un adversario, atacando a una organización y brindando retroalimentación desde la perspectiva de un enemigo.
- `Ingeniero de Seguridad`: Diseña, supervisa y mantiene controles de seguridad, redes y sistemas para ayudar a prevenir ciberataques.

### Responde las preguntas a continuación
¡Lee lo anterior y continúa con la siguiente sala!