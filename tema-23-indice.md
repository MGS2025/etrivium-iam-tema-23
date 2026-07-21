# Tema 23 — Índice

> **Título oficial**: Aplicaciones web. Desarrollo web front-end y en servidor, multiplataforma y multidispositivo. HTML, XML y derivaciones. Navegadores y lenguajes de programación web. Lenguajes de script.
>
> **Bloque**: Parte II — Técnico (Temas 11-40)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

---

## Estructura del tema

1. **Introducción a las aplicaciones web**
   1.1. Concepto y evolución de las aplicaciones web
   1.2. Características y ventajas frente a las aplicaciones de escritorio
   1.3. Arquitectura general de una aplicación web
   1.3.1. Modelo cliente-servidor

2. **Fundamentos de la World Wide Web**
   2.1. Internet, web y servicios asociados
   2.2. URL, URI y localización de recursos
   2.3. Protocolos involucrados
   2.3.1. Métodos, cabeceras y códigos de estado

3. **Desarrollo web front-end**
   3.1. Concepto y funciones del front-end
   3.2. Estructura, presentación y comportamiento
   3.2.1. HTML, CSS y JavaScript como tecnologías básicas
   3.3. Diseño adaptable y experiencia de usuario
   3.3.1. Responsive Web Design
   3.3.2. Accesibilidad y usabilidad
   3.3.3. Normativa aplicable a las administraciones públicas
   3.4. Mecanismos de almacenamiento local, sesión y caché

4. **HTML y sus evoluciones**
   4.1. Origen y características de HTML
   4.2. Estructura de un documento HTML
   4.2.1. Elementos, atributos y metadatos
   4.3. HTML5 y nuevas capacidades
   4.3.1. Etiquetas semánticas
   4.3.2. Formularios y contenidos multimedia

5. **XML y sus derivaciones**
   5.1. Concepto y objetivos de XML
   5.2. Estructura de documentos XML
   5.2.1. Elementos, atributos y espacios de nombres
   5.3. Validación de documentos XML
   5.3.1. DTD y XML Schema
   5.4. Tecnologías derivadas de XML: XHTML, XSL/XSLT y SVG

6. **Navegadores web**
   6.1. Arquitectura y funcionamiento
   6.2. Motores de renderizado y ejecución
   6.3. Modelo de objetos del documento (DOM)
   6.4. Compatibilidad e interoperabilidad

7. **Lenguajes de programación web y lenguajes de script**
   7.1. Concepto y características de los lenguajes de script
   7.2. JavaScript en el lado cliente
   7.2.1. Manipulación del DOM y gestión de eventos
   7.2.2. Comunicación asíncrona y AJAX
   7.3. Lenguajes de programación en servidor: PHP, Java y Python
   7.4. Frameworks y bibliotecas para desarrollo web

8. **Desarrollo web en servidor**
   8.1. Funciones y componentes del back-end
   8.2. Generación dinámica de contenidos
   8.3. Acceso a bases de datos
   8.4. Gestión de sesiones, autenticación y autorización
   8.5. Servicios web y APIs

9. **Aplicaciones web multiplataforma y multidispositivo**
   9.1. Principios de compatibilidad entre plataformas
   9.2. Diseño adaptativo y diseño responsivo
   9.3. Aplicaciones web progresivas (PWA)

10. **Seguridad en aplicaciones web. Principales vulnerabilidades**
    10.1. El modelo de amenazas de una aplicación web
    10.2. OWASP Top 10: vulnerabilidades más críticas
    10.2.1. Inyección y control de acceso roto
    10.2.2. Cross-Site Scripting (XSS) y Cross-Site Request Forgery (CSRF)
    10.2.3. Configuración incorrecta y componentes vulnerables
    10.3. Buenas prácticas de desarrollo seguro
    10.3.1. Validación de entrada, cabeceras de seguridad y HTTPS/TLS
    10.3.2. Gestión segura de sesiones, cookies y autenticación

---

## Conceptos clave para memorizar

| Concepto | Dato clave |
|---|---|
| Aplicación web | Software accesible mediante un navegador sobre HTTP/HTTPS, sin instalación local, ejecutado en parte en el cliente y en parte en el servidor |
| Modelo cliente-servidor | El cliente (navegador) solicita recursos; el servidor los procesa y responde; el protocolo HTTP es **sin estado** (*stateless*) |
| URI vs URL | URI identifica un recurso (puede ser solo un nombre); URL además indica **cómo localizarlo** (esquema, host, ruta) — toda URL es una URI, no al revés |
| Métodos HTTP | GET (idempotente, sin efectos secundarios), POST (crea/procesa), PUT (reemplaza, idempotente), DELETE (elimina, idempotente), PATCH (modificación parcial) |
| Códigos de estado | 1xx informativo, 2xx éxito, 3xx redirección, 4xx error del cliente, 5xx error del servidor |
| Front-end vs back-end | Front-end: lo que se ejecuta en el navegador (HTML/CSS/JS) — capa de presentación; Back-end: lo que se ejecuta en el servidor — lógica de negocio y datos |
| HTML5 | Versión de HTML con etiquetas semánticas (`<header>`, `<nav>`, `<article>`), formularios enriquecidos, audio/vídeo nativos y APIs (Storage, Service Workers) sin plugins |
| XML | Metalenguaje de marcado **extensible**: no define etiquetas fijas, permite crear vocabularios propios validables con DTD o XML Schema |
| DOM | Representación en árbol de un documento HTML/XML que JavaScript puede leer y modificar dinámicamente |
| Motor de renderizado | Convierte HTML/CSS en píxeles en pantalla mediante el pipeline parsing → estilo → layout → paint → composición (Blink, Gecko, WebKit) |
| AJAX | *Asynchronous JavaScript And XML*: petición HTTP asíncrona desde JS sin recargar la página (hoy con `fetch`, formato habitual JSON) |
| PWA | Aplicación web que, mediante *Service Worker* + *Web App Manifest*, ofrece funcionamiento offline, instalación y notificaciones push |
| Responsive Web Design | Una única base de código que se adapta a cualquier tamaño de pantalla mediante *media queries*, unidades relativas y maquetación flexible (Flexbox/Grid) |
| OWASP Top 10 | Catálogo de referencia de los riesgos de seguridad más críticos en aplicaciones web (inyección, control de acceso roto, XSS, configuración incorrecta…) |
| Cookie de sesión | Mecanismo habitual para mantener estado sobre HTTP sin estado; debe marcarse `HttpOnly`, `Secure` y `SameSite` para mitigar XSS/CSRF |

---

*Tiempo estimado de estudio: 16-18 horas*
*Extensión del contenido: ~15.500 palabras · 14 diagramas SVG embebidos*
