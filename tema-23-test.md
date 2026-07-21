# Tema 23 — Test de Autoevaluación

> **Título**: Aplicaciones web. Desarrollo web front-end y en servidor, multiplataforma y multidispositivo. HTML, XML y derivaciones. Navegadores y lenguajes de programación web. Lenguajes de script.
> **Formato**: 60 preguntas tipo test A/B/C (formato oficial oposición)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid
> **Versión**: v1.0 — Pendiente validación
> **Fecha**: 2026-07-21
> **Fuentes**: ver tema-23-fuentes.md

---

## Instrucciones

- Cada pregunta tiene **3 opciones** (A, B, C). Solo una es correcta.
- Penalización en examen real: respuesta incorrecta descuenta **1/3** del valor de una correcta.
- Tiempo orientativo: 1 minuto por pregunta.
- Distribución: Introducción a las apps web (P1-P5), Fundamentos WWW (P6-P11), Desarrollo front-end (P12-P19), HTML (P20-P25), XML (P26-P31), Navegadores (P32-P36), Lenguajes de script (P37-P43), Desarrollo en servidor (P44-P50), Multiplataforma/PWA (P51-P55), Seguridad (P56-P60).

---

### Pregunta 1

**¿Qué distingue fundamentalmente a una aplicación web de una página web estática?**

A) Procesa datos, mantiene estado y reacciona a la interacción del usuario
B) Únicamente que usa HTML5 en lugar de versiones anteriores de HTML
C) Que requiere instalación de software específico en el equipo del usuario

<details><summary>Respuesta</summary>

**Correcta: A) Procesa datos, mantiene estado y reacciona a la interacción del usuario** Una página estática es de solo lectura; una aplicación web añade procesamiento, estado e interacción, con lógica ejecutada en el servidor y/o en el cliente.

*Referencia: §1.1 [WHATWG-HTML]*
</details>

---

### Pregunta 2

**¿Qué marca la transición de la Web 1.0 a la Web 2.0?**

A) La sustitución completa de HTML por XML
B) La adopción de AJAX para actualizar contenido sin recargar la página completa
C) La generalización de HTTPS frente a HTTP

<details><summary>Respuesta</summary>

**Correcta: B) La adopción de AJAX para actualizar contenido sin recargar la página completa** La Web 2.0 se caracteriza por la interactividad y el contenido generado por el usuario, posible gracias a peticiones asíncronas que evitan recargar la página entera.

*Referencia: §1.1 [WHATWG-HTML]*
</details>

---

### Pregunta 3

**¿Cuál es una ventaja de las aplicaciones web frente a las de escritorio?**

A) Mejor acceso directo al hardware del dispositivo
B) Menor dependencia de la conectividad de red
C) No requieren instalación ni actualización manual por parte del usuario

<details><summary>Respuesta</summary>

**Correcta: C) No requieren instalación ni actualización manual por parte del usuario** El servidor sirve siempre la última versión; el usuario no gestiona parches ni instaladores distintos por sistema operativo.

*Referencia: §1.2 [WHATWG-HTML]*
</details>

---

### Pregunta 4

**En el modelo cliente-servidor, ¿qué papel desempeña el cliente?**

A) Inicia la comunicación solicitando un recurso o una acción
B) Permanece a la escucha, procesando peticiones entrantes
C) Ambos roles son intercambiables en cada petición HTTP

<details><summary>Respuesta</summary>

**Correcta: A) Inicia la comunicación solicitando un recurso o una acción** El servidor es quien permanece a la escucha y responde; el cliente (típicamente el navegador) es quien inicia cada petición.

*Referencia: §1.3.1 [FIELDING2000]*
</details>

---

### Pregunta 5

**¿Qué significa que HTTP sea un protocolo «sin estado» (stateless)?**

A) No puede usarse para transmitir datos binarios
B) Cada petición se procesa de forma independiente, sin memoria de peticiones anteriores
C) Solo puede establecerse una conexión TCP por servidor

<details><summary>Respuesta</summary>

**Correcta: B) Cada petición se procesa de forma independiente, sin memoria de peticiones anteriores** Toda «sesión» percibida por el usuario se construye con mecanismos añadidos (cookies, tokens), no es una propiedad nativa de HTTP.

*Referencia: §1.3.1 [RFC9110]*
</details>

---

### Pregunta 6

**¿Cuál de las siguientes afirmaciones es correcta?**

A) La Web es uno de los servicios que se ejecutan sobre la infraestructura de Internet
B) Internet y la Web son sinónimos exactos
C) La Web es la infraestructura y HTTP uno de sus servicios

<details><summary>Respuesta</summary>

**Correcta: A) La Web es uno de los servicios que se ejecutan sobre la infraestructura de Internet** Internet es la red (TCP/IP); la Web, el correo o el FTP son servicios distintos que corren sobre esa red.

*Referencia: §2.1 [WHATWG-HTML]*
</details>

---

### Pregunta 7

**¿Cuál es la relación correcta entre URI y URL?**

A) Toda URL es un URI, pero no todo URI es una URL
B) Todo URI es una URL, pero no toda URL es un URI
C) Son términos completamente independientes, sin relación de inclusión

<details><summary>Respuesta</summary>

**Correcta: A) Toda URL es un URI, pero no todo URI es una URL** URI identifica un recurso (puede ser solo un nombre, como un URN); URL además indica cómo localizarlo.

*Referencia: §2.2 [RFC3986]*
</details>

---

### Pregunta 8

**En la URL `https://sede.madrid.es/portal/cita?ano=2026`, ¿qué parte es `ano=2026`?**

A) El fragmento
B) La ruta (path)
C) La query string (cadena de consulta)

<details><summary>Respuesta</summary>

**Correcta: C) La query string (cadena de consulta)** Los parámetros clave-valor tras el símbolo `?` forman la query string; el fragmento, si existiera, iría tras `#` y no se envía al servidor.

*Referencia: §2.2 [RFC3986]*
</details>

---

### Pregunta 9

**¿Qué método HTTP es el adecuado para reemplazar por completo un recurso existente de forma idempotente?**

A) POST
B) PATCH
C) PUT

<details><summary>Respuesta</summary>

**Correcta: C) PUT** PUT reemplaza el recurso completo y es idempotente (repetirlo dos veces deja el mismo resultado); POST no es idempotente y PATCH modifica solo parcialmente.

*Referencia: §2.3.1 [RFC9110]*
</details>

---

### Pregunta 10

**Un ciudadano autenticado en la sede electrónica intenta consultar un expediente que no le pertenece. ¿Qué código de estado HTTP es el correcto?**

A) 403 Forbidden
B) 401 Unauthorized
C) 500 Internal Server Error

<details><summary>Respuesta</summary>

**Correcta: A) 403 Forbidden** El servidor sabe quién es (está autenticado), pero no tiene autorización sobre ese recurso concreto; 401 correspondería a no estar autenticado.

*Referencia: §2.3.1 [RFC9110]*
</details>

---

### Pregunta 11

**¿Qué protocolo introdujo QUIC como sustituto de TCP en el transporte?**

A) HTTP/1.1
B) HTTP/2
C) HTTP/3

<details><summary>Respuesta</summary>

**Correcta: C) HTTP/3** HTTP/3 se apoya en QUIC (sobre UDP), eliminando el bloqueo de cabeza de línea a nivel de transporte que persistía en HTTP/2 pese a su multiplexación sobre una única conexión TCP.

*Referencia: §2.3 [RFC9114]*
</details>

---

### Pregunta 12

**¿Cuál es la responsabilidad de CSS en el front-end?**

A) La estructura semántica del documento
B) La presentación: color, tipografía y disposición espacial
C) La lógica de comportamiento e interactividad

<details><summary>Respuesta</summary>

**Correcta: B) La presentación: color, tipografía y disposición espacial** HTML aporta estructura y JavaScript comportamiento; CSS es responsable exclusivamente de la presentación.

*Referencia: §3.2.1 [W3C-CSS]*
</details>

---

### Pregunta 13

**¿Qué metaetiqueta es imprescindible para que las media queries funcionen correctamente en un dispositivo móvil?**

A) `<meta name="description">`
B) `<meta charset="UTF-8">`
C) `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

<details><summary>Respuesta</summary>

**Correcta: C) `<meta name="viewport" content="width=device-width, initial-scale=1.0">`** Sin ella, el navegador móvil simula una anchura de escritorio y luego reduce la página, invalidando las media queries basadas en el ancho real de pantalla.

*Referencia: §3.3.1 [MDN-CSS]*
</details>

---

### Pregunta 14

**¿Cuál de los siguientes es uno de los cuatro principios WCAG (POUR)?**

A) Operable
B) Portable
C) Optimizado

<details><summary>Respuesta</summary>

**Correcta: A) Operable** Los cuatro principios son Perceptible, Operable, Comprensible y Robusto; «Operable» exige que la interfaz pueda manejarse, por ejemplo, íntegramente por teclado.

*Referencia: §3.3.2 [WCAG22]*
</details>

---

### Pregunta 15

**Según el RD 1112/2018, ¿qué nivel de las WCAG deben cumplir los sitios web del sector público en España?**

A) Nivel A
B) Nivel AAA
C) Nivel AA

<details><summary>Respuesta</summary>

**Correcta: C) Nivel AA** El Real Decreto exige el nivel AA (o superior) de las WCAG, más el requisito adicional de publicar una declaración de accesibilidad revisable.

*Referencia: §3.3.3 [RD1112-2018]*
</details>

---

### Pregunta 16

**¿Qué diferencia principal existe entre `localStorage` y `sessionStorage`?**

A) `localStorage` se envía automáticamente en cada petición HTTP y `sessionStorage` no
B) `sessionStorage` desaparece al cerrar la pestaña; `localStorage` persiste indefinidamente hasta borrado explícito
C) `sessionStorage` tiene mayor capacidad de almacenamiento que `localStorage`

<details><summary>Respuesta</summary>

**Correcta: B) `sessionStorage` desaparece al cerrar la pestaña; `localStorage` persiste indefinidamente hasta borrado explícito** Ambos comparten la misma API (`setItem`/`getItem`), pero difieren en el ciclo de vida de los datos; ninguno de los dos se envía automáticamente al servidor, a diferencia de las cookies.

*Referencia: §3.4 [MDN-JS]*
</details>

---

### Pregunta 17

**¿Cuál es el objetivo del Responsive Web Design (RWD)?**

A) Servir versiones de código HTML completamente distintas según el dispositivo detectado
B) Sustituir HTML por una aplicación nativa instalada en el dispositivo
C) Que una única base de código HTML/CSS se reorganice según el tamaño de pantalla mediante media queries

<details><summary>Respuesta</summary>

**Correcta: C) Que una única base de código HTML/CSS se reorganice según el tamaño de pantalla mediante media queries** Frente al diseño adaptativo (varias maquetaciones fijas predefinidas), el RWD usa una única maquetación fluida.

*Referencia: §3.3.1 [MDN-CSS]*
</details>

---

### Pregunta 18

**¿Qué separa el patrón `addEventListener` frente a asignar un manejador con el atributo `onclick`?**

A) `addEventListener` permite registrar varios manejadores para el mismo evento sin sobrescribirse
B) `onclick` es más moderno y sustituye completamente a `addEventListener`
C) `addEventListener` solo funciona con eventos de teclado, no de ratón

<details><summary>Respuesta</summary>

**Correcta: A) `addEventListener` permite registrar varios manejadores para el mismo evento sin sobrescribirse** Además, separa mejor el comportamiento (JS) de la estructura (HTML), reforzando el principio de separación de responsabilidades.

*Referencia: §3.2.1 [MDN-JS]*
</details>

---

### Pregunta 19

**¿Qué mecanismo de caché evita repetir peticiones HTTP de recursos que no han cambiado?**

A) `sessionStorage`
B) IndexedDB
C) Cabeceras `Cache-Control` y validadores como `ETag`

<details><summary>Respuesta</summary>

**Correcta: C) Cabeceras `Cache-Control` y validadores como `ETag`** La caché HTTP gobernada por estas cabeceras mejora el rendimiento percibido y es la base sobre la que se construye el funcionamiento offline de una PWA mediante la Cache API.

*Referencia: §3.4 [MDN-HTTP]*
</details>

---

### Pregunta 20

**¿De qué lenguaje deriva HTML originalmente?**

A) De XML
B) De SGML
C) De ECMAScript

<details><summary>Respuesta</summary>

**Correcta: B) De SGML** HTML fue creado por Tim Berners-Lee en 1991 como un lenguaje de marcado derivado de SGML (Standard Generalized Markup Language).

*Referencia: §4.1 [WHATWG-HTML]*
</details>

---

### Pregunta 21

**Desde 2019, ¿cuál es la única fuente normativa de referencia de HTML?**

A) El WHATWG Living Standard
B) La recomendación HTML5.2 del W3C
C) La especificación XHTML 1.1

<details><summary>Respuesta</summary>

**Correcta: A) El WHATWG Living Standard** El W3C y el WHATWG acordaron en 2019 que el Living Standard, en evolución continua, sustituye al antiguo modelo de recomendaciones numeradas fijas.

*Referencia: §4.1 [WHATWG-HTML]*
</details>

---

### Pregunta 22

**¿Dónde deben declararse los metadatos de un documento HTML, como el `<title>` o el `<meta charset>`?**

A) Dentro de `<head>`
B) Dentro de `<body>`, al principio del documento
C) En un fichero externo enlazado con `<link rel="metadata">`

<details><summary>Respuesta</summary>

**Correcta: A) Dentro de `<head>`** Los metadatos no se muestran en el cuerpo visible de la página y residen exclusivamente en `<head>`.

*Referencia: §4.2.1 [WHATWG-HTML]*
</details>

---

### Pregunta 23

**¿Cuál de las siguientes es una etiqueta semántica introducida por HTML5 para el contenido principal, único por página?**

A) `<div id="main">`
B) `<content>`
C) `<main>`

<details><summary>Respuesta</summary>

**Correcta: C) `<main>`** Frente al uso indiscriminado de `<div>` genéricos, HTML5 introduce `<main>` para describir explícitamente el contenido principal, único por página.

*Referencia: §4.3.1 [WHATWG-HTML]*
</details>

---

### Pregunta 24

**¿Qué ventaja aportan principalmente las etiquetas semánticas de HTML5?**

A) Cambian automáticamente la apariencia visual por defecto de la página
B) Mejoran la accesibilidad y el SEO al describir la estructura a máquinas, no solo a humanos
C) Sustituyen por completo la necesidad de escribir CSS

<details><summary>Respuesta</summary>

**Correcta: B) Mejoran la accesibilidad y el SEO al describir la estructura a máquinas, no solo a humanos** No cambian la apariencia por defecto (siguen pudiendo estilizarse como cualquier `<div>`), pero sí el significado que transmiten a lectores de pantalla y buscadores.

*Referencia: §4.3.1 [WHATWG-HTML]*
</details>

---

### Pregunta 25

**¿Qué atributo HTML5 permite validar en el navegador, sin JavaScript, que un campo cumple una expresión regular?**

A) `required`
B) `validate`
C) `pattern`

<details><summary>Respuesta</summary>

**Correcta: C) `pattern`** El atributo `pattern` acepta una expresión regular que el navegador valida de forma nativa; `required` solo exige que el campo no esté vacío, sin comprobar su formato.

*Referencia: §4.3.2 [WHATWG-HTML]*
</details>

---

### Pregunta 26

**¿Cuál es la diferencia esencial entre HTML y XML?**

A) XML no puede representar texto, solo datos binarios
B) HTML tiene un vocabulario fijo de etiquetas; XML permite definir vocabularios propios
C) HTML es más estricto sintácticamente que XML

<details><summary>Respuesta</summary>

**Correcta: B) HTML tiene un vocabulario fijo de etiquetas; XML permite definir vocabularios propios** XML es un metalenguaje: no define ninguna etiqueta propia, a diferencia del conjunto predeterminado de HTML.

*Referencia: §5.1 [XML10]*
</details>

---

### Pregunta 27

**¿Qué diferencia «bien formado» de «válido» en un documento XML?**

A) Son sinónimos exactos, no hay diferencia
B) Bien formado cumple la sintaxis general de XML; válido además cumple una gramática concreta (DTD/XSD)
C) Válido se refiere solo a la codificación de caracteres del documento

<details><summary>Respuesta</summary>

**Correcta: B) Bien formado cumple la sintaxis general de XML; válido además cumple una gramática concreta (DTD/XSD)** Un documento puede estar sintácticamente bien formado y aun así no respetar la estructura de datos esperada por una aplicación concreta.

*Referencia: §5.3 [XML10; XMLSCHEMA]*
</details>

---

### Pregunta 28

**¿Qué mecanismo de validación XML está escrito en el propio XML y admite tipos de datos ricos (fecha, entero, patrones)?**

A) XML Schema (XSD)
B) DTD
C) XHTML

<details><summary>Respuesta</summary>

**Correcta: A) XML Schema (XSD)** DTD, heredado de SGML, tiene sintaxis propia distinta de XML y tipos muy básicos; XSD es XML válido en sí mismo y admite restricciones de tipo, rango y cardinalidad.

*Referencia: §5.3.1 [XMLSCHEMA]*
</details>

---

### Pregunta 29

**¿Qué elemento evita colisiones cuando dos vocabularios XML definen una etiqueta con el mismo nombre pero significado distinto?**

A) El atributo `xmlns` (espacio de nombres)
B) La declaración `<!DOCTYPE>`
C) El atributo `encoding` de la cabecera XML

<details><summary>Respuesta</summary>

**Correcta: A) El atributo `xmlns` (espacio de nombres)** El espacio de nombres, junto a su prefijo, asocia cada elemento a su vocabulario declarado, evitando ambigüedad entre etiquetas homónimas de significado distinto.

*Referencia: §5.2.1 [XML-NAMESPACES]*
</details>

---

### Pregunta 30

**¿Qué tecnología derivada de XML se usa para transformar un documento XML en otro formato mediante plantillas declarativas?**

A) XHTML
B) SVG
C) XSLT

<details><summary>Respuesta</summary>

**Correcta: C) XSLT** XSL/XSLT es un lenguaje declarativo escrito en XML que transforma un documento XML en otro (otro XML, HTML o texto) mediante coincidencia de patrones.

*Referencia: §5.4 [XSLT30]*
</details>

---

### Pregunta 31

**¿Qué caracteriza al formato SVG frente a un mapa de bits como PNG o JPEG?**

A) Es un formato binario propietario
B) Describe las formas de manera vectorial en XML, por lo que escala sin perder calidad
C) Solo puede mostrarse mediante un plugin del navegador

<details><summary>Respuesta</summary>

**Correcta: B) Describe las formas de manera vectorial en XML, por lo que escala sin perder calidad** SVG es un formato de gráficos vectoriales descrito íntegramente en XML, manipulable con CSS y JavaScript como cualquier otro nodo del DOM.

*Referencia: §5.4 [SVG11]*
</details>

---

### Pregunta 32

**¿Cuál de los siguientes pares motor de renderizado/navegador es correcto?**

A) Gecko / Safari
B) WebKit / Firefox
C) Blink / Chrome

<details><summary>Respuesta</summary>

**Correcta: C) Blink / Chrome** Chrome, Edge, Opera y Brave se basan en Chromium/Blink; Firefox usa Gecko; Safari usa WebKit.

*Referencia: §6.2 [CHROMIUM-BLINK]*
</details>

---

### Pregunta 33

**¿Cuál es el orden correcto del pipeline de renderizado de un navegador?**

A) Layout → parsing → paint → estilo → composición
B) Parsing → estilo → layout → paint → composición
C) Paint → parsing → composición → estilo → layout

<details><summary>Respuesta</summary>

**Correcta: B) Parsing → estilo → layout → paint → composición** El motor primero construye DOM y CSSOM (parsing), los combina (estilo), calcula posiciones (layout), pinta píxeles (paint) y finalmente ensambla capas con la GPU (composición).

*Referencia: §6.2 [CHROMIUM-BLINK]*
</details>

---

### Pregunta 34

**¿Qué es el DOM?**

A) Un lenguaje de programación equivalente a JavaScript
B) Una representación en árbol del documento, accesible mediante una API independiente del lenguaje
C) El motor de renderizado del navegador

<details><summary>Respuesta</summary>

**Correcta: B) Una representación en árbol del documento, accesible mediante una API independiente del lenguaje** El DOM es una interfaz (API), no un lenguaje: JavaScript la usa habitualmente, pero no es exclusiva de él.

*Referencia: §6.3 [W3C-DOM4]*
</details>

---

### Pregunta 35

**¿Por qué JavaScript se describe como un lenguaje «de un solo hilo» en el navegador?**

A) Porque solo puede ejecutar una pieza de código a la vez, gestionando la asincronía mediante el bucle de eventos
B) Porque solo puede ejecutarse en servidores de un único núcleo
C) Porque no admite funciones recursivas

<details><summary>Respuesta</summary>

**Correcta: A) Porque solo puede ejecutar una pieza de código a la vez, gestionando la asincronía mediante el bucle de eventos** La sensación de paralelismo en operaciones de red se logra mediante el bucle de eventos y una cola de tareas, no mediante hilos reales concurrentes.

*Referencia: §6.2 [V8-DOC]*
</details>

---

### Pregunta 36

**¿Qué práctica consiste en construir primero una experiencia funcional básica y añadir capacidades avanzadas solo donde el navegador las soporte?**

A) Compilación *just-in-time*
B) Mejora progresiva (*progressive enhancement*)
C) Renderizado del lado del servidor

<details><summary>Respuesta</summary>

**Correcta: B) Mejora progresiva (*progressive enhancement*)** Esta práctica, junto a la comprobación previa de compatibilidad de cada API, mitiga las diferencias de implementación entre motores de navegador.

*Referencia: §6.4*
</details>

---

### Pregunta 37

**¿Qué caracteriza a un lenguaje de script frente a un lenguaje compilado por adelantado?**

A) Está diseñado para automatizar tareas dentro de un entorno anfitrión, habitualmente interpretado o compilado JIT
B) No puede ejecutar bucles ni condicionales
C) Solo puede ejecutarse en el servidor, nunca en el navegador

<details><summary>Respuesta</summary>

**Correcta: A) Está diseñado para automatizar tareas dentro de un entorno anfitrión, habitualmente interpretado o compilado JIT** JavaScript es el lenguaje de script más relevante del contexto web, tanto en cliente como, con Node.js, en servidor.

*Referencia: §7.1 [ECMA262]*
</details>

---

### Pregunta 38

**¿Qué nombre real recibe hoy, en la práctica, el formato de intercambio de datos usado en la técnica AJAX, pese a lo que sugiere su nombre histórico?**

A) XML, tal como indica el propio nombre AJAX
B) JSON
C) YAML

<details><summary>Respuesta</summary>

**Correcta: B) JSON** El nombre AJAX es histórico (2005, usaba XML); hoy la práctica casi universal es JSON, más ligero y nativo del propio lenguaje JavaScript.

*Referencia: §7.2.2 [MDN-JS]*
</details>

---

### Pregunta 39

**¿Qué objeto devuelve la API `fetch` para representar un valor que estará disponible en el futuro?**

A) Un `Callback`
B) Un `Thread`
C) Una `Promise`

<details><summary>Respuesta</summary>

**Correcta: C) Una `Promise`** La promesa permite encadenar el manejo del resultado de una petición de red sin bloquear el hilo único de ejecución de JavaScript.

*Referencia: §7.2.2 [MDN-JS]*
</details>

---

### Pregunta 40

**¿Cuál de los siguientes lenguajes se embebe directamente dentro del flujo HTML, ejecutándose típicamente por petición en el servidor?**

A) Java
B) Python
C) PHP

<details><summary>Respuesta</summary>

**Correcta: C) PHP** PHP fue diseñado específicamente para la web desde 1994 y se embebe directamente en el HTML, con una ejecución típica sin estado persistente entre peticiones salvo mecanismos explícitos.

*Referencia: §7.3 [PHP-DOC]*
</details>

---

### Pregunta 41

**¿Qué entorno de ejecución permite usar JavaScript también en el lado servidor, empleando el motor V8 fuera del navegador?**

A) Django
B) Node.js
C) Jakarta EE

<details><summary>Respuesta</summary>

**Correcta: B) Node.js** Node.js emplea V8 con un modelo de E/S no bloqueante, adecuado para aplicaciones con muchas conexiones concurrentes de corta duración.

*Referencia: §7.3 [NODE-DOC]*
</details>

---

### Pregunta 42

**¿Qué distingue a un framework de una biblioteca?**

A) Un framework impone la estructura y el flujo de control (inversión de control); una biblioteca es invocada por el propio código del desarrollador
B) Una biblioteca siempre es de pago y un framework siempre es gratuito
C) No existe diferencia real entre ambos términos

<details><summary>Respuesta</summary>

**Correcta: A) Un framework impone la estructura y el flujo de control (inversión de control); una biblioteca es invocada por el propio código del desarrollador** Es el mismo principio de inversión de control estudiado en el Tema 21 para los contenedores Java EE.

*Referencia: §7.4 [REACT-DOC]*
</details>

---

### Pregunta 43

**Java, como lenguaje de servidor en el ámbito web, se apoya principalmente en qué especificación de plataforma, desarrollada en profundidad en otro tema del temario?**

A) Jakarta EE (Tema 21)
B) ECMAScript
C) WSGI

<details><summary>Respuesta</summary>

**Correcta: A) Jakarta EE (Tema 21)** El Tema 21 desarrolla en profundidad Servlets, JSF, EJB, CDI y JPA como plataforma Java de servidor; este tema sitúa Java como una de las opciones de lenguaje de servidor junto a PHP y Python.

*Referencia: §7.3 [JAKARTA-PLAT]*
</details>

---

### Pregunta 44

**¿Cuál es la responsabilidad principal del back-end de una aplicación web?**

A) Aplicar estilos CSS al contenido
B) Ejecutar la lógica que no debe o no puede correr en el navegador del cliente: datos persistentes, reglas de negocio y autenticación
C) Interpretar el HTML recibido del servidor

<details><summary>Respuesta</summary>

**Correcta: B) Ejecutar la lógica que no debe o no puede correr en el navegador del cliente: datos persistentes, reglas de negocio y autenticación** El back-end concentra todo aquello que requiere confianza o recursos que el cliente no puede garantizar.

*Referencia: §8.1*
</details>

---

### Pregunta 45

**¿Qué enfoque de generación de contenidos construye el HTML completo en el servidor antes de enviarlo al navegador?**

A) *Client-Side Rendering* (CSR)
B) *Server-Side Rendering* (SSR)
C) *Progressive Web App* (PWA)

<details><summary>Respuesta</summary>

**Correcta: B) *Server-Side Rendering* (SSR)** Es el modelo clásico (PHP, JSP/JSF de Java EE); en CSR, en cambio, es el JavaScript del cliente el que construye el contenido visible.

*Referencia: §8.2*
</details>

---

### Pregunta 46

**¿Cuál es la forma recomendada de evitar la inyección SQL al acceder a la base de datos desde el back-end?**

A) Validar el formato del campo únicamente en JavaScript, en el front-end
B) Concatenar directamente la entrada del usuario en la cadena SQL
C) Usar consultas parametrizadas (o un ORM), donde el dato del usuario se trata siempre como un valor

<details><summary>Respuesta</summary>

**Correcta: C) Usar consultas parametrizadas (o un ORM), donde el dato del usuario se trata siempre como un valor** El motor de base de datos recibe el dato siempre como valor, nunca como parte de la sintaxis del comando, sea cual sea su contenido.

*Referencia: §8.3 [OWASP-TOP10]*
</details>

---

### Pregunta 47

**¿Cuál es la diferencia entre autenticación y autorización?**

A) Son sinónimos y se usan indistintamente
B) Autorización verifica quién es el usuario; autenticación determina qué puede hacer
C) Autenticación verifica quién es el usuario; autorización determina qué puede hacer ese usuario ya identificado

<details><summary>Respuesta</summary>

**Correcta: C) Autenticación verifica quién es el usuario; autorización determina qué puede hacer ese usuario ya identificado** Confundir ambos conceptos explica por qué el código 401 (fallo de autenticación) se confunde a menudo con un fallo de permisos, que en realidad corresponde a 403.

*Referencia: §8.4*
</details>

---

### Pregunta 48

**¿Qué atributo de una cookie impide que JavaScript pueda leerla desde el DOM, mitigando su robo mediante XSS?**

A) `Secure`
B) `SameSite`
C) `HttpOnly`

<details><summary>Respuesta</summary>

**Correcta: C) `HttpOnly`** `Secure` restringe el envío a HTTPS y `SameSite` restringe el envío entre dominios distintos (mitigando CSRF); `HttpOnly` es el que impide la lectura por script.

*Referencia: §8.4*
</details>

---

### Pregunta 49

**¿Qué estilo arquitectónico trata cada entidad de negocio como un recurso identificado por una URL, manipulado con los métodos HTTP estándar?**

A) SOAP
B) REST
C) RPC clásico

<details><summary>Respuesta</summary>

**Correcta: B) REST** Formulado por Fielding en el año 2000, REST domina el desarrollo de APIs nuevas por su simplicidad y su alineamiento natural con HTTP, frente al sobre XML y el contrato WSDL de SOAP.

*Referencia: §8.5 [FIELDING2000]*
</details>

---

### Pregunta 50

**¿Qué alternativa a la cookie de sesión con estado en el servidor incluye la identidad y los permisos firmados digitalmente, sin necesitar un almacén de sesiones?**

A) Un token autocontenido como JWT
B) Un `localStorage` sin cifrar
C) Un identificador incremental en la URL

<details><summary>Respuesta</summary>

**Correcta: A) Un token autocontenido como JWT** A cambio, revocar un token individual antes de su expiración resulta más difícil que invalidar una entrada en un almacén de sesiones del servidor.

*Referencia: §8.4*
</details>

---

### Pregunta 51

**¿Por qué una aplicación web es multiplataforma por construcción?**

A) Porque el mismo HTML/CSS/JS se ejecuta en cualquier sistema operativo con un navegador compatible, sin recompilar
B) Porque siempre requiere una API nativa distinta por sistema operativo
C) Porque XML sustituye a HTML en los dispositivos móviles

<details><summary>Respuesta</summary>

**Correcta: A) Porque el mismo HTML/CSS/JS se ejecuta en cualquier sistema operativo con un navegador compatible, sin recompilar** Es la misma ventaja frente a las aplicaciones de escritorio descrita al inicio del tema, aplicada ahora a la variedad de plataformas y dispositivos.

*Referencia: §9.1*
</details>

---

### Pregunta 52

**¿Qué diferencia al diseño adaptativo del diseño responsivo?**

A) El adaptativo usa varias maquetaciones fijas predefinidas; el responsivo usa una única maquetación fluida y continua
B) Son exactamente la misma técnica con nombres distintos
C) El responsivo solo funciona en dispositivos móviles, nunca en escritorio

<details><summary>Respuesta</summary>

**Correcta: A) El adaptativo usa varias maquetaciones fijas predefinidas; el responsivo usa una única maquetación fluida y continua** En la práctica, muchas aplicaciones combinan ambas ideas en distintos puntos de ruptura.

*Referencia: §9.2*
</details>

---

### Pregunta 53

**¿Cuáles son los tres pilares técnicos de una Progressive Web App (PWA)?**

A) HTML, CSS y JavaScript
B) Service Worker, Web App Manifest y servicio obligatorio por HTTPS
C) DTD, XML Schema y XSLT

<details><summary>Respuesta</summary>

**Correcta: B) Service Worker, Web App Manifest y servicio obligatorio por HTTPS** El Service Worker gestiona la caché y el funcionamiento offline; el Manifest permite instalar la aplicación; HTTPS es requisito de seguridad para registrar el Service Worker.

*Referencia: §9.3 [MDN-PWA]*
</details>

---

### Pregunta 54

**¿Por qué el Service Worker puede seguir funcionando aunque la pestaña de la aplicación esté cerrada?**

A) Porque se ejecuta en un hilo separado de la página y no tiene acceso directo al DOM
B) Porque forma parte del propio DOM y se mantiene en memoria indefinidamente
C) Porque sustituye por completo al navegador como proceso del sistema operativo

<details><summary>Respuesta</summary>

**Correcta: A) Porque se ejecuta en un hilo separado de la página y no tiene acceso directo al DOM** Esta separación, y la comunicación por paso de mensajes con la página, es lo que permite servir contenido cacheado o recibir notificaciones push sin que la pestaña esté abierta.

*Referencia: §9.3 [SERVICE-WORKERS]*
</details>

---

### Pregunta 55

**¿Qué fichero describe metadatos como el nombre, los iconos y el color de tema de una PWA, para que el navegador ofrezca instalarla?**

A) `robots.txt`
B) `sw.js`
C) `manifest.json` (Web App Manifest)

<details><summary>Respuesta</summary>

**Correcta: C) `manifest.json` (Web App Manifest)** El `sw.js` es el propio script del Service Worker, responsable de interceptar peticiones de red, no de describir metadatos de instalación.

*Referencia: §9.3 [WEB-APP-MANIFEST]*
</details>

---

### Pregunta 56

**Según el OWASP Top 10:2021, ¿qué riesgo ocupa el primer puesto por su frecuencia e impacto directo sobre la confidencialidad de datos de terceros?**

A) Configuración de seguridad incorrecta
B) Uso de componentes con vulnerabilidades conocidas
C) Control de acceso roto

<details><summary>Respuesta</summary>

**Correcta: C) Control de acceso roto** Ocurre cuando la aplicación no verifica en el servidor que el usuario autenticado tiene permiso sobre el recurso concreto que solicita, dando lugar a ataques como el IDOR.

*Referencia: §10.2.1 [OWASP-TOP10]*
</details>

---

### Pregunta 57

**¿Cómo se mitiga la inyección SQL de forma efectiva?**

A) Confiando en la validación del formulario en el front-end
B) Escapando solo los caracteres `<` y `>` de la entrada del usuario
C) Con consultas parametrizadas en el back-end, donde el dato del usuario nunca forma parte de la sintaxis del comando

<details><summary>Respuesta</summary>

**Correcta: C) Con consultas parametrizadas en el back-end, donde el dato del usuario nunca forma parte de la sintaxis del comando** La validación de front-end puede eludirse enviando la petición directamente al servidor, sin pasar por el formulario ni por el JavaScript de la página.

*Referencia: §10.2.1 [OWASP-TOP10]*
</details>

---

### Pregunta 58

**¿Qué diferencia esencial existe entre XSS y CSRF?**

A) XSS explota la confianza del usuario en el sitio; CSRF explota la confianza del sitio en el navegador ya autenticado del usuario
B) Son exactamente el mismo ataque con nombres distintos
C) XSS solo afecta a aplicaciones móviles, nunca a aplicaciones web de escritorio

<details><summary>Respuesta</summary>

**Correcta: A) XSS explota la confianza del usuario en el sitio; CSRF explota la confianza del sitio en el navegador ya autenticado del usuario** XSS ejecuta script inyectado como si fuera del propio dominio; CSRF envía una petición no deseada aprovechando que el navegador adjunta automáticamente la cookie de sesión válida.

*Referencia: §10.2.2 [OWASP-TOP10]*
</details>

---

### Pregunta 59

**¿Qué atributo de cookie impide que el navegador la adjunte en peticiones originadas desde un dominio distinto, mitigando CSRF?**

A) `HttpOnly`
B) `SameSite`
C) `Max-Age`

<details><summary>Respuesta</summary>

**Correcta: B) `SameSite`** Junto con un token CSRF único por sesión o formulario, `SameSite=Strict` o `Lax` es la mitigación estándar frente a peticiones falsificadas entre sitios.

*Referencia: §10.3.2 [OWASP-TOP10]*
</details>

---

### Pregunta 60

**Un formulario valida el DNI con una expresión regular únicamente en JavaScript, en el navegador. ¿Es esto seguridad suficiente?**

A) Sí, porque el navegador garantiza que ningún dato inválido llegará nunca al servidor
B) No, porque un atacante puede enviar la petición HTTP directamente al servidor, sin pasar por el formulario ni por el JavaScript de la página
C) Sí, siempre que el campo tenga también el atributo `required`

<details><summary>Respuesta</summary>

**Correcta: B) No, porque un atacante puede enviar la petición HTTP directamente al servidor, sin pasar por el formulario ni por el JavaScript de la página** La validación de cliente mejora la experiencia de uso, pero la validación de seguridad real debe repetirse siempre en el servidor, el único punto de confianza.

*Referencia: §10.3.1 [OWASP-TOP10]*
</details>
