# Tema 23 — Catálogo de Diagramas

> **Título oficial**: Aplicaciones web. Desarrollo web front-end y en servidor, multiplataforma y multidispositivo. HTML, XML y derivaciones. Navegadores y lenguajes de programación web. Lenguajes de script.
>
> **Versión**: v1.0
> **Fecha**: 2026-07-21
> **Autor**: ETRIVIUM
> **Formato**: SVG inline (zero-dependencias, escalable, imprimible, accesible con role/aria-label)
> **Paleta**: Ayuntamiento de Madrid #0055a0 (primario) + #d13c3c (alertas) + #2d8659 (ventajas) + #e89822 (callouts)
> **Nota técnica**: las clases CSS de cada SVG llevan sufijo numérico único (`.t1`, `.h1`…) para evitar colisiones de estilos entre los 14 diagramas embebidos en la misma página.

---

## Índice de diagramas

| ID | Título | Sección | Tipo | Formato |
|---|---|---|---|---|
| D1 | Modelo cliente-servidor y ciclo petición-respuesta | §1.3.1 | Flujo | 680×300 |
| D2 | Anatomía de una URL | §2.2 | Esquema anotado | 680×260 |
| D3 | Métodos HTTP y familias de códigos de estado | §2.3.1 | Cheat sheet | 680×380 |
| D4 | HTML + CSS + JS: separación de responsabilidades | §3.2.1 | Bloques | 680×300 |
| D5 | Responsive Web Design: mobile-first y breakpoints | §3.3.1 | Comparativa | 680×320 |
| D6 | Mecanismos de almacenamiento en el cliente | §3.4 | Tabla visual | 680×340 |
| D7 | HTML5: etiquetas semánticas de layout | §4.3.1 | Layout anotado | 680×340 |
| D8 | XML: bien formado, válido y validación | §5.1, §5.3 | Flujo | 680×300 |
| D9 | Pipeline de renderizado del navegador | §6.2 | Flujo | 680×300 |
| D10 | El DOM como árbol de nodos | §6.3 | Árbol | 680×320 |
| D11 | AJAX/fetch y el bucle de eventos | §7.2.2 | Flujo | 680×340 |
| D12 | Arquitectura front-end/back-end y API REST | §8.5 | Bloques | 680×340 |
| D13 | PWA: Service Worker, Manifest y Cache | §9.3 | Bloques | 680×340 |
| D14 | XSS frente a CSRF: direcciones de la confianza explotada | §10.2.2 | Comparativa | 680×340 |

---

## D1 · Modelo cliente-servidor y ciclo petición-respuesta

**Sección**: §1.3.1 — Modelo cliente-servidor
**Propósito**: Mostrar el ciclo petición-respuesta HTTP entre cliente y servidor, y remarcar el carácter *stateless* del protocolo.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 300" role="img" aria-label="Modelo cliente-servidor: el cliente (navegador) envía una petición HTTP, el servidor la procesa consultando su lógica de negocio y datos, y devuelve una respuesta; HTTP es un protocolo sin estado">
  <style>.t1{font:700 12px system-ui,sans-serif;fill:#fff}.s1{font:10.5px system-ui,sans-serif;fill:#fff}.l1{font:11px system-ui,sans-serif;fill:#444}.h1{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="22" text-anchor="middle" class="h1">Modelo cliente-servidor: ciclo petición-respuesta</text>
  <rect x="30" y="60" width="180" height="90" rx="6" fill="#0055a0"/>
  <text x="120" y="95" text-anchor="middle" class="t1">CLIENTE</text>
  <text x="120" y="115" text-anchor="middle" class="s1">Navegador</text>
  <text x="120" y="132" text-anchor="middle" class="s1">(§6)</text>
  <rect x="470" y="60" width="180" height="90" rx="6" fill="#2d8659"/>
  <text x="560" y="90" text-anchor="middle" class="t1">SERVIDOR</text>
  <text x="560" y="108" text-anchor="middle" class="s1">Lógica + datos</text>
  <text x="560" y="125" text-anchor="middle" class="s1">(§8)</text>
  <path d="M212 90 L466 90" stroke="#0055a0" stroke-width="3" marker-end="url(#a1)"/>
  <text x="340" y="80" text-anchor="middle" style="font:700 10.5px system-ui;fill:#0055a0">GET /tramites/1234</text>
  <path d="M466 130 L212 130" stroke="#2d8659" stroke-width="3" marker-end="url(#b1)"/>
  <text x="340" y="150" text-anchor="middle" style="font:700 10.5px system-ui;fill:#2d8659">200 OK + JSON</text>
  <defs>
    <marker id="a1" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M0 0 L9 4.5 L0 9 z" fill="#0055a0"/></marker>
    <marker id="b1" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M9 0 L0 4.5 L9 9 z" fill="#2d8659"/></marker>
  </defs>
  <rect x="140" y="196" width="400" height="66" rx="6" fill="#d13c3c"/>
  <text x="340" y="220" text-anchor="middle" class="t1">HTTP es SIN ESTADO (stateless)</text>
  <text x="340" y="240" text-anchor="middle" class="s1">Cada petición se procesa de forma independiente:</text>
  <text x="340" y="256" text-anchor="middle" class="s1">el servidor no recuerda peticiones anteriores por sí solo</text>
  <text x="670" y="292" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: RFC9110; FIELDING2000]</text>
</svg>
```

---

## D2 · Anatomía de una URL

**Sección**: §2.2 — URL, URI y localización de recursos
**Propósito**: Descomponer una URL real de la sede electrónica en sus partes constitutivas.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 260" role="img" aria-label="Anatomía de una URL: esquema https, host sede.madrid.es, ruta portal/tramites/cita-previa, y query string ano=2026, con la relación URI contiene URL contiene URN">
  <style>.t2{font:700 11px system-ui,sans-serif;fill:#fff}.s2{font:10px system-ui,sans-serif;fill:#fff}.l2{font:12px ui-monospace,monospace;fill:#222}.h2{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="22" text-anchor="middle" class="h2">Anatomía de una URL</text>
  <text x="340" y="50" text-anchor="middle" class="l2">https://sede.madrid.es/portal/tramites/cita-previa?ano=2026</text>
  <rect x="30" y="66" width="90" height="30" rx="4" fill="#0055a0"/><text x="75" y="86" text-anchor="middle" class="t2">esquema</text>
  <rect x="130" y="66" width="150" height="30" rx="4" fill="#2d8659"/><text x="205" y="86" text-anchor="middle" class="t2">host</text>
  <rect x="290" y="66" width="210" height="30" rx="4" fill="#e89822"/><text x="395" y="86" text-anchor="middle" class="t2">ruta</text>
  <rect x="510" y="66" width="140" height="30" rx="4" fill="#d13c3c"/><text x="580" y="86" text-anchor="middle" class="t2">query string</text>
  <line x1="75" y1="96" x2="60" y2="116" stroke="#0055a0" stroke-width="2"/>
  <line x1="205" y1="96" x2="205" y2="116" stroke="#2d8659" stroke-width="2"/>
  <line x1="395" y1="96" x2="395" y2="116" stroke="#e89822" stroke-width="2"/>
  <line x1="580" y1="96" x2="600" y2="116" stroke="#d13c3c" stroke-width="2"/>
  <text x="60" y="132" text-anchor="middle" class="l2" style="fill:#0055a0;font-weight:700">https</text>
  <text x="205" y="132" text-anchor="middle" class="l2" style="fill:#2d8659;font-weight:700">sede.madrid.es</text>
  <text x="395" y="132" text-anchor="middle" class="l2" style="fill:#e89822;font-weight:700">/portal/.../cita-previa</text>
  <text x="600" y="132" text-anchor="middle" class="l2" style="fill:#d13c3c;font-weight:700">ano=2026</text>
  <rect x="60" y="160" width="560" height="76" rx="6" fill="none" stroke="#0055a0" stroke-width="2"/>
  <text x="80" y="180" class="l2" style="fill:#0055a0;font-weight:700">URI (identifica)</text>
  <rect x="90" y="192" width="510" height="34" rx="5" fill="#0055a0"/>
  <text x="345" y="214" text-anchor="middle" class="t2">URL — identifica Y localiza (esta URL es un URI)</text>
  <text x="670" y="252" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: RFC3986]</text>
</svg>
```

---

## D3 · Métodos HTTP y familias de códigos de estado

**Sección**: §2.3.1 — Métodos, cabeceras y códigos de estado
**Propósito**: Cheat sheet de los métodos HTTP con su idempotencia y de las cinco familias de códigos de estado.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 380" role="img" aria-label="Cheat sheet de métodos HTTP GET POST PUT PATCH DELETE con su idempotencia, y de las cinco familias de códigos de estado 1xx a 5xx">
  <style>.t3{font:700 11px system-ui,sans-serif;fill:#fff}.s3{font:9.5px system-ui,sans-serif;fill:#fff}.l3{font:11px system-ui,sans-serif;fill:#444}.h3{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h3">Métodos HTTP y códigos de estado</text>
  <rect x="20" y="34" width="120" height="40" rx="5" fill="#0055a0"/><text x="80" y="50" text-anchor="middle" class="t3">GET</text><text x="80" y="66" text-anchor="middle" class="s3">idempotente · seguro</text>
  <rect x="150" y="34" width="120" height="40" rx="5" fill="#d13c3c"/><text x="210" y="50" text-anchor="middle" class="t3">POST</text><text x="210" y="66" text-anchor="middle" class="s3">no idempotente</text>
  <rect x="280" y="34" width="120" height="40" rx="5" fill="#2d8659"/><text x="340" y="50" text-anchor="middle" class="t3">PUT</text><text x="340" y="66" text-anchor="middle" class="s3">idempotente</text>
  <rect x="410" y="34" width="120" height="40" rx="5" fill="#e89822"/><text x="470" y="50" text-anchor="middle" class="t3">PATCH</text><text x="470" y="66" text-anchor="middle" class="s3">no idempotente</text>
  <rect x="540" y="34" width="120" height="40" rx="5" fill="#2d8659"/><text x="600" y="50" text-anchor="middle" class="t3">DELETE</text><text x="600" y="66" text-anchor="middle" class="s3">idempotente</text>
  <line x1="20" y1="92" x2="660" y2="92" stroke="#ccc" stroke-width="1"/>
  <text x="340" y="112" text-anchor="middle" style="font:700 11px system-ui;fill:#0055a0">Familias de códigos de estado</text>
  <rect x="20" y="126" width="120" height="56" rx="5" fill="#888"/><text x="80" y="148" text-anchor="middle" class="t3">1xx</text><text x="80" y="166" text-anchor="middle" class="s3">Informativo</text>
  <rect x="150" y="126" width="120" height="56" rx="5" fill="#2d8659"/><text x="210" y="148" text-anchor="middle" class="t3">2xx</text><text x="210" y="166" text-anchor="middle" class="s3">Éxito (200, 201, 204)</text>
  <rect x="280" y="126" width="120" height="56" rx="5" fill="#0055a0"/><text x="340" y="148" text-anchor="middle" class="t3">3xx</text><text x="340" y="166" text-anchor="middle" class="s3">Redirección (301, 304)</text>
  <rect x="410" y="126" width="120" height="56" rx="5" fill="#e89822"/><text x="470" y="148" text-anchor="middle" class="t3">4xx</text><text x="470" y="166" text-anchor="middle" class="s3">Error cliente (401, 403, 404)</text>
  <rect x="540" y="126" width="120" height="56" rx="5" fill="#d13c3c"/><text x="600" y="148" text-anchor="middle" class="t3">5xx</text><text x="600" y="166" text-anchor="middle" class="s3">Error servidor (500, 503)</text>
  <rect x="60" y="200" width="560" height="130" rx="6" fill="none" stroke="#d13c3c" stroke-width="2"/>
  <text x="340" y="222" text-anchor="middle" style="font:700 12px system-ui;fill:#d13c3c">401 vs 403 — el par de examen más confundido</text>
  <text x="90" y="248" class="l3"><tspan style="font-weight:700;fill:#d13c3c">401 Unauthorized</tspan> → fallo de AUTENTICACIÓN</text>
  <text x="90" y="266" class="l3">El servidor no sabe quién eres, o tus credenciales no son válidas</text>
  <text x="90" y="292" class="l3"><tspan style="font-weight:700;fill:#d13c3c">403 Forbidden</tspan> → fallo de AUTORIZACIÓN</text>
  <text x="90" y="310" class="l3">Sabe quién eres, pero no tienes permiso sobre ese recurso</text>
  <text x="670" y="360" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: RFC9110]</text>
</svg>
```

---

## D4 · HTML + CSS + JS: separación de responsabilidades

**Sección**: §3.2.1 — HTML, CSS y JavaScript como tecnologías básicas
**Propósito**: Visualizar el principio de separación estructura/presentación/comportamiento.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 300" role="img" aria-label="Separación de responsabilidades del front-end: HTML aporta estructura, CSS aporta presentación, JavaScript aporta comportamiento, las tres capas se combinan en la página final que ve el usuario">
  <style>.t4{font:700 12px system-ui,sans-serif;fill:#fff}.s4{font:10px system-ui,sans-serif;fill:#fff}.l4{font:11px system-ui,sans-serif;fill:#444}.h4{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h4">HTML · CSS · JavaScript — responsabilidades separadas</text>
  <rect x="40" y="40" width="170" height="90" rx="6" fill="#0055a0"/>
  <text x="125" y="70" text-anchor="middle" class="t4">HTML</text>
  <text x="125" y="90" text-anchor="middle" class="s4">Estructura</text>
  <text x="125" y="106" text-anchor="middle" class="s4">«El esqueleto»</text>
  <rect x="255" y="40" width="170" height="90" rx="6" fill="#2d8659"/>
  <text x="340" y="70" text-anchor="middle" class="t4">CSS</text>
  <text x="340" y="90" text-anchor="middle" class="s4">Presentación</text>
  <text x="340" y="106" text-anchor="middle" class="s4">«El estilo»</text>
  <rect x="470" y="40" width="170" height="90" rx="6" fill="#e89822"/>
  <text x="555" y="70" text-anchor="middle" class="t4">JavaScript</text>
  <text x="555" y="90" text-anchor="middle" class="s4">Comportamiento</text>
  <text x="555" y="106" text-anchor="middle" class="s4">«Los reflejos»</text>
  <path d="M125 130 L300 168" stroke="#888" stroke-width="2" marker-end="url(#c4)"/>
  <path d="M340 130 L340 168" stroke="#888" stroke-width="2" marker-end="url(#c4)"/>
  <path d="M555 130 L380 168" stroke="#888" stroke-width="2" marker-end="url(#c4)"/>
  <defs><marker id="c4" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M0 0 L9 4.5 L0 9 z" fill="#888"/></marker></defs>
  <rect x="150" y="176" width="380" height="60" rx="6" fill="#0055a0"/>
  <text x="340" y="200" text-anchor="middle" class="t4">Página final en el navegador</text>
  <text x="340" y="220" text-anchor="middle" class="s4">Estructura + presentación + comportamiento combinados</text>
  <text x="340" y="264" text-anchor="middle" style="font:700 11px system-ui;fill:#d13c3c">Mezclar las tres capas degrada el mantenimiento — no es obligación técnica, es buena práctica</text>
  <text x="670" y="292" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: WHATWG-HTML; W3C-CSS]</text>
</svg>
```

---

## D5 · Responsive Web Design: mobile-first y breakpoints

**Sección**: §3.3.1 — Responsive Web Design
**Propósito**: Mostrar la misma base de código reorganizándose en tres anchos de pantalla mediante media queries.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 320" role="img" aria-label="Responsive Web Design: la misma página se reorganiza en móvil con columna única, tablet con dos columnas y escritorio con tres columnas, mediante media queries sobre el mismo código">
  <style>.t5{font:700 11px system-ui,sans-serif;fill:#fff}.s5{font:9.5px system-ui,sans-serif;fill:#fff}.l5{font:11px system-ui,sans-serif;fill:#444}.h5{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h5">Una base de código · tres disposiciones</text>
  <rect x="40" y="40" width="120" height="200" rx="8" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <rect x="52" y="52" width="96" height="30" rx="3" fill="#0055a0"/><text x="100" y="72" text-anchor="middle" class="s5">Cabecera</text>
  <rect x="52" y="90" width="96" height="60" rx="3" fill="#2d8659"/><text x="100" y="124" text-anchor="middle" class="s5">Contenido</text>
  <rect x="52" y="158" width="96" height="60" rx="3" fill="#e89822"/><text x="100" y="192" text-anchor="middle" class="s5">Barra lateral</text>
  <text x="100" y="256" text-anchor="middle" class="l5" style="font-weight:700">Móvil (&lt; 600px)</text>
  <rect x="200" y="40" width="220" height="200" rx="8" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <rect x="212" y="52" width="196" height="30" rx="3" fill="#0055a0"/><text x="310" y="72" text-anchor="middle" class="s5">Cabecera</text>
  <rect x="212" y="90" width="120" height="128" rx="3" fill="#2d8659"/><text x="272" y="158" text-anchor="middle" class="s5">Contenido</text>
  <rect x="338" y="90" width="70" height="128" rx="3" fill="#e89822"/><text x="373" y="158" text-anchor="middle" class="s5">Lateral</text>
  <text x="310" y="256" text-anchor="middle" class="l5" style="font-weight:700">Tablet (600-960px)</text>
  <rect x="460" y="40" width="180" height="200" rx="8" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <rect x="472" y="52" width="156" height="30" rx="3" fill="#0055a0"/><text x="550" y="72" text-anchor="middle" class="s5">Cabecera</text>
  <rect x="472" y="90" width="60" height="128" rx="3" fill="#e89822"/><text x="502" y="158" text-anchor="middle" class="s5" style="font-size:8px">Nav</text>
  <rect x="536" y="90" width="60" height="128" rx="3" fill="#2d8659"/><text x="566" y="158" text-anchor="middle" class="s5" style="font-size:8px">Contenido</text>
  <rect x="600" y="90" width="28" height="128" rx="3" fill="#d13c3c"/>
  <text x="550" y="256" text-anchor="middle" class="l5" style="font-weight:700">Escritorio (&gt; 960px)</text>
  <text x="340" y="288" text-anchor="middle" style="font:700 11px system-ui;fill:#0055a0">@media (max-width: 600px) { .layout { flex-direction: column } }</text>
  <text x="670" y="312" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: MDN-CSS]</text>
</svg>
```

---

## D6 · Mecanismos de almacenamiento en el cliente

**Sección**: §3.4 — Mecanismos de almacenamiento local, sesión y caché
**Propósito**: Comparar cookies, localStorage, sessionStorage e IndexedDB por persistencia y envío automático.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Comparativa de almacenamiento en el cliente: cookies con envío automático al servidor y persistencia configurable, localStorage persistente sin envío automático, sessionStorage limitado a la pestaña, IndexedDB para grandes volúmenes">
  <style>.t6{font:700 11px system-ui,sans-serif;fill:#fff}.s6{font:9.5px system-ui,sans-serif;fill:#fff}.l6{font:10.5px system-ui,sans-serif;fill:#444}.h6{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h6">Almacenamiento en el cliente</text>
  <rect x="30" y="40" width="150" height="110" rx="6" fill="#0055a0"/>
  <text x="105" y="66" text-anchor="middle" class="t6">Cookies</text>
  <text x="105" y="86" text-anchor="middle" class="s6">~4 KB</text>
  <text x="105" y="102" text-anchor="middle" class="s6">Envío AUTOMÁTICO</text>
  <text x="105" y="118" text-anchor="middle" class="s6">en cada petición</text>
  <text x="105" y="134" text-anchor="middle" class="s6">HttpOnly/Secure/SameSite</text>
  <rect x="190" y="40" width="150" height="110" rx="6" fill="#2d8659"/>
  <text x="265" y="66" text-anchor="middle" class="t6">localStorage</text>
  <text x="265" y="86" text-anchor="middle" class="s6">~5-10 MB</text>
  <text x="265" y="102" text-anchor="middle" class="s6">Sin envío automático</text>
  <text x="265" y="118" text-anchor="middle" class="s6">Persiste indefinido</text>
  <text x="265" y="134" text-anchor="middle" class="s6">hasta borrado explícito</text>
  <rect x="350" y="40" width="150" height="110" rx="6" fill="#e89822"/>
  <text x="425" y="66" text-anchor="middle" class="t6">sessionStorage</text>
  <text x="425" y="86" text-anchor="middle" class="s6">~5-10 MB</text>
  <text x="425" y="102" text-anchor="middle" class="s6">Sin envío automático</text>
  <text x="425" y="118" text-anchor="middle" class="s6">Dura lo que</text>
  <text x="425" y="134" text-anchor="middle" class="s6">la pestaña abierta</text>
  <rect x="510" y="40" width="150" height="110" rx="6" fill="#d13c3c"/>
  <text x="585" y="66" text-anchor="middle" class="t6">IndexedDB</text>
  <text x="585" y="86" text-anchor="middle" class="s6">Cientos de MB</text>
  <text x="585" y="102" text-anchor="middle" class="s6">Sin envío automático</text>
  <text x="585" y="118" text-anchor="middle" class="s6">Base de datos</text>
  <text x="585" y="134" text-anchor="middle" class="s6">estructurada local</text>
  <rect x="90" y="176" width="500" height="120" rx="6" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <text x="340" y="200" text-anchor="middle" style="font:700 12px system-ui;fill:#0055a0">Caché HTTP y Cache API (Service Worker, §9.3)</text>
  <text x="340" y="224" text-anchor="middle" class="l6">Cache-Control / ETag evitan repetir peticiones de recursos sin cambios</text>
  <text x="340" y="244" text-anchor="middle" class="l6">La Cache API, gestionada por el Service Worker, es la base técnica</text>
  <text x="340" y="264" text-anchor="middle" class="l6">del funcionamiento OFFLINE de una PWA</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: MDN-JS; SERVICE-WORKERS]</text>
</svg>
```

---

## D7 · HTML5: etiquetas semánticas de layout

**Sección**: §4.3.1 — Etiquetas semánticas
**Propósito**: Mapear visualmente `<header>`, `<nav>`, `<main>`, `<article>`, `<aside>` y `<footer>` sobre una página típica.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Layout de página con etiquetas semánticas HTML5: header en la parte superior, nav debajo, main con article a la izquierda y aside a la derecha, footer en la parte inferior">
  <style>.t7{font:700 11px system-ui,sans-serif;fill:#fff}.s7{font:9.5px system-ui,sans-serif;fill:#fff}.h7{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h7">Etiquetas semánticas HTML5</text>
  <rect x="60" y="36" width="560" height="44" rx="4" fill="#0055a0"/><text x="340" y="63" text-anchor="middle" class="t7">&lt;header&gt;</text>
  <rect x="60" y="86" width="560" height="34" rx="4" fill="#3778b5"/><text x="340" y="108" text-anchor="middle" class="t7">&lt;nav&gt;</text>
  <rect x="60" y="126" width="560" height="150" rx="4" fill="none" stroke="#2d8659" stroke-width="2" stroke-dasharray="4 3"/>
  <text x="80" y="142" class="s7" style="fill:#2d8659;font-weight:700">&lt;main&gt;</text>
  <rect x="72" y="150" width="350" height="116" rx="4" fill="#2d8659"/><text x="247" y="212" text-anchor="middle" class="t7">&lt;article&gt;</text>
  <rect x="432" y="150" width="176" height="116" rx="4" fill="#e89822"/><text x="520" y="212" text-anchor="middle" class="t7">&lt;aside&gt;</text>
  <rect x="60" y="284" width="560" height="40" rx="4" fill="#d13c3c"/><text x="340" y="308" text-anchor="middle" class="t7">&lt;footer&gt;</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: WHATWG-HTML]</text>
</svg>
```

---

## D8 · XML: bien formado, válido y validación

**Sección**: §5.1, §5.3 — Concepto de XML y validación de documentos
**Propósito**: Distinguir sintaxis bien formada de validación contra DTD/XSD.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 300" role="img" aria-label="Un documento XML puede estar bien formado sin ser válido; la validación contra una gramática DTD o XML Schema comprueba si respeta una estructura de datos esperada">
  <style>.t8{font:700 11px system-ui,sans-serif;fill:#fff}.s8{font:9.5px system-ui,sans-serif;fill:#fff}.l8{font:11px system-ui,sans-serif;fill:#444}.h8{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h8">XML: bien formado ≠ válido</text>
  <rect x="40" y="40" width="230" height="70" rx="6" fill="#0055a0"/>
  <text x="155" y="66" text-anchor="middle" class="t8">Documento XML</text>
  <text x="155" y="86" text-anchor="middle" class="s8">Etiquetas cerradas, anidamiento correcto</text>
  <text x="155" y="102" text-anchor="middle" class="s8">→ BIEN FORMADO</text>
  <path d="M270 75 L330 75" stroke="#888" stroke-width="3" marker-end="url(#d8)"/>
  <defs><marker id="d8" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M0 0 L9 4.5 L0 9 z" fill="#888"/></marker></defs>
  <rect x="340" y="40" width="150" height="70" rx="6" fill="#e89822"/>
  <text x="415" y="68" text-anchor="middle" class="t8">DTD</text>
  <text x="415" y="86" text-anchor="middle" class="s8">o XML Schema</text>
  <text x="415" y="102" text-anchor="middle" class="s8">(gramática)</text>
  <path d="M415 110 L415 140" stroke="#888" stroke-width="3" marker-end="url(#d8)"/>
  <rect x="500" y="40" width="150" height="70" rx="6" fill="#2d8659"/>
  <text x="575" y="68" text-anchor="middle" class="t8">Validador</text>
  <text x="575" y="86" text-anchor="middle" class="s8">Compara estructura</text>
  <path d="M340 75 L340 140" stroke="#888" stroke-width="0"/>
  <rect x="150" y="160" width="380" height="70" rx="6" fill="#2d8659"/>
  <text x="340" y="188" text-anchor="middle" class="t8">DOCUMENTO VÁLIDO</text>
  <text x="340" y="208" text-anchor="middle" class="s8">Cumple la gramática esperada (tipos, cardinalidad, orden)</text>
  <text x="340" y="256" text-anchor="middle" style="font:700 11px system-ui;fill:#d13c3c">XSD: escrito en el propio XML, tipos ricos y espacios de nombres</text>
  <text x="670" y="292" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: XML10; XMLSCHEMA]</text>
</svg>
```

---

## D9 · Pipeline de renderizado del navegador

**Sección**: §6.2 — Motores de renderizado y ejecución
**Propósito**: Mostrar las fases de parsing → estilo → layout → paint → composición.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 300" role="img" aria-label="Pipeline de renderizado del navegador: parsing construye DOM y CSSOM, estilo los combina, layout calcula posiciones, paint pinta píxeles, composición ensambla capas con la GPU">
  <style>.t9{font:700 10.5px system-ui,sans-serif;fill:#fff}.s9{font:9px system-ui,sans-serif;fill:#fff}.h9{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h9">Pipeline de renderizado (Blink/Gecko/WebKit)</text>
  <rect x="20" y="60" width="120" height="70" rx="5" fill="#0055a0"/><text x="80" y="88" text-anchor="middle" class="t9">Parsing</text><text x="80" y="106" text-anchor="middle" class="s9">DOM + CSSOM</text>
  <rect x="150" y="60" width="120" height="70" rx="5" fill="#3778b5"/><text x="210" y="88" text-anchor="middle" class="t9">Estilo</text><text x="210" y="106" text-anchor="middle" class="s9">Combina árboles</text>
  <rect x="280" y="60" width="120" height="70" rx="5" fill="#2d8659"/><text x="340" y="88" text-anchor="middle" class="t9">Layout</text><text x="340" y="106" text-anchor="middle" class="s9">Posición/tamaño</text>
  <rect x="410" y="60" width="120" height="70" rx="5" fill="#e89822"/><text x="470" y="88" text-anchor="middle" class="t9">Paint</text><text x="470" y="106" text-anchor="middle" class="s9">Pinta píxeles</text>
  <rect x="540" y="60" width="120" height="70" rx="5" fill="#d13c3c"/><text x="600" y="88" text-anchor="middle" class="t9">Composición</text><text x="600" y="106" text-anchor="middle" class="s9">Capas + GPU</text>
  <path d="M140 95 L148 95" stroke="#888" stroke-width="2" marker-end="url(#e9)"/>
  <path d="M270 95 L278 95" stroke="#888" stroke-width="2" marker-end="url(#e9)"/>
  <path d="M400 95 L408 95" stroke="#888" stroke-width="2" marker-end="url(#e9)"/>
  <path d="M530 95 L538 95" stroke="#888" stroke-width="2" marker-end="url(#e9)"/>
  <defs><marker id="e9" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto"><path d="M0 0 L8 4 L0 8 z" fill="#888"/></marker></defs>
  <rect x="60" y="160" width="560" height="90" rx="6" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <text x="340" y="184" text-anchor="middle" style="font:700 12px system-ui;fill:#0055a0">Motor JS — independiente, un solo hilo</text>
  <text x="340" y="206" text-anchor="middle" style="font:10.5px system-ui;fill:#444">V8 (Chrome/Edge) · SpiderMonkey (Firefox) · JavaScriptCore (Safari)</text>
  <text x="340" y="226" text-anchor="middle" style="font:10.5px system-ui;fill:#444">Ejecuta con bucle de eventos (event loop), no con hilos paralelos reales</text>
  <text x="670" y="292" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: CHROMIUM-BLINK; V8-DOC]</text>
</svg>
```

---

## D10 · El DOM como árbol de nodos

**Sección**: §6.3 — Modelo de objetos del documento (DOM)
**Propósito**: Representar el árbol DOM correspondiente a un documento HTML simple.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 320" role="img" aria-label="El DOM representa un documento HTML como un árbol de nodos: el nodo raíz html tiene hijos head y body, head contiene title, body contiene h1 y p">
  <style>.t10{font:700 11px system-ui,sans-serif;fill:#fff}.l10{font:11px system-ui,sans-serif;fill:#444}.h10{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h10">El DOM: documento como árbol de nodos</text>
  <rect x="290" y="40" width="100" height="36" rx="5" fill="#0055a0"/><text x="340" y="63" text-anchor="middle" class="t10">&lt;html&gt;</text>
  <path d="M340 76 L200 116" stroke="#888" stroke-width="2"/>
  <path d="M340 76 L480 116" stroke="#888" stroke-width="2"/>
  <rect x="150" y="118" width="100" height="36" rx="5" fill="#2d8659"/><text x="200" y="141" text-anchor="middle" class="t10">&lt;head&gt;</text>
  <rect x="430" y="118" width="100" height="36" rx="5" fill="#2d8659"/><text x="480" y="141" text-anchor="middle" class="t10">&lt;body&gt;</text>
  <path d="M200 154 L200 194" stroke="#888" stroke-width="2"/>
  <path d="M480 154 L400 194" stroke="#888" stroke-width="2"/>
  <path d="M480 154 L560 194" stroke="#888" stroke-width="2"/>
  <rect x="150" y="196" width="100" height="36" rx="5" fill="#e89822"/><text x="200" y="219" text-anchor="middle" class="t10">&lt;title&gt;</text>
  <rect x="350" y="196" width="100" height="36" rx="5" fill="#e89822"/><text x="400" y="219" text-anchor="middle" class="t10">&lt;h1&gt;</text>
  <rect x="510" y="196" width="100" height="36" rx="5" fill="#e89822"/><text x="560" y="219" text-anchor="middle" class="t10">&lt;p&gt;</text>
  <rect x="60" y="252" width="560" height="52" rx="6" fill="#d13c3c"/>
  <text x="340" y="272" text-anchor="middle" class="t10">document.querySelector('h1').textContent = '...'</text>
  <text x="340" y="290" text-anchor="middle" style="font:9.5px system-ui;fill:#fff">JavaScript lee y modifica este árbol después de la carga</text>
  <text x="670" y="316" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: W3C-DOM4]</text>
</svg>
```

---

## D11 · AJAX/fetch y el bucle de eventos

**Sección**: §7.2.2 — Comunicación asíncrona y AJAX
**Propósito**: Ilustrar cómo una petición `fetch` no bloquea el hilo único de JavaScript.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="fetch envía una petición de red que se procesa fuera del hilo principal de JavaScript; cuando la respuesta llega, se encola en la cola de tareas y el bucle de eventos la ejecuta cuando el hilo principal queda libre">
  <style>.t11{font:700 11px system-ui,sans-serif;fill:#fff}.s11{font:9.5px system-ui,sans-serif;fill:#fff}.l11{font:11px system-ui,sans-serif;fill:#444}.h11{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h11">fetch() y el bucle de eventos</text>
  <rect x="30" y="44" width="220" height="60" rx="6" fill="#0055a0"/>
  <text x="140" y="68" text-anchor="middle" class="t11">Hilo único de JS</text>
  <text x="140" y="86" text-anchor="middle" class="s11">Ejecuta await fetch(...)</text>
  <path d="M250 74 L340 74" stroke="#888" stroke-width="2" marker-end="url(#f11)"/>
  <rect x="350" y="44" width="220" height="60" rx="6" fill="#e89822"/>
  <text x="460" y="68" text-anchor="middle" class="t11">Red (fuera del hilo)</text>
  <text x="460" y="86" text-anchor="middle" class="s11">Petición HTTP en curso</text>
  <path d="M140 104 L140 150" stroke="#888" stroke-width="2" marker-end="url(#f11)"/>
  <defs><marker id="f11" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M0 0 L9 4.5 L0 9 z" fill="#888"/></marker></defs>
  <rect x="30" y="152" width="220" height="60" rx="6" fill="#2d8659"/>
  <text x="140" y="176" text-anchor="middle" class="t11">Sigue ejecutando</text>
  <text x="140" y="194" text-anchor="middle" class="s11">otro código sin bloquear</text>
  <path d="M460 104 L460 150" stroke="#888" stroke-width="2" stroke-dasharray="4 3" marker-end="url(#f11)"/>
  <rect x="350" y="152" width="220" height="60" rx="6" fill="#d13c3c"/>
  <text x="460" y="176" text-anchor="middle" class="t11">Cola de tareas</text>
  <text x="460" y="194" text-anchor="middle" class="s11">Respuesta lista, en espera</text>
  <path d="M140 212 L300 250" stroke="#888" stroke-width="2"/>
  <path d="M460 212 L380 250" stroke="#888" stroke-width="2"/>
  <rect x="230" y="252" width="220" height="60" rx="6" fill="#0055a0"/>
  <text x="340" y="278" text-anchor="middle" class="t11">Bucle de eventos</text>
  <text x="340" y="296" text-anchor="middle" class="s11">Ejecuta la continuación cuando el hilo está libre</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: V8-DOC; MDN-JS]</text>
</svg>
```

---

## D12 · Arquitectura front-end/back-end y API REST

**Sección**: §8.5 — Servicios web y APIs
**Propósito**: Situar la API REST como punto de contacto entre front-end y back-end.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="El front-end consume una API REST expuesta por el back-end; la API traduce peticiones HTTP en operaciones sobre la lógica de negocio y la base de datos, devolviendo JSON">
  <style>.t12{font:700 11px system-ui,sans-serif;fill:#fff}.s12{font:9.5px system-ui,sans-serif;fill:#fff}.h12{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h12">Front-end · API REST · Back-end</text>
  <rect x="30" y="50" width="160" height="80" rx="6" fill="#0055a0"/>
  <text x="110" y="80" text-anchor="middle" class="t12">FRONT-END</text>
  <text x="110" y="98" text-anchor="middle" class="s12">HTML/CSS/JS</text>
  <text x="110" y="114" text-anchor="middle" class="s12">(§3, §7.2)</text>
  <path d="M190 90 L260 90" stroke="#888" stroke-width="3" marker-end="url(#g12)"/>
  <text x="225" y="80" text-anchor="middle" style="font:700 9.5px system-ui;fill:#0055a0">fetch()</text>
  <rect x="270" y="50" width="160" height="80" rx="6" fill="#e89822"/>
  <text x="350" y="76" text-anchor="middle" class="t12">API REST</text>
  <text x="350" y="94" text-anchor="middle" class="s12">GET/POST/PUT/DELETE</text>
  <text x="350" y="110" text-anchor="middle" class="s12">/api/tramites/{id}</text>
  <path d="M430 90 L500 90" stroke="#888" stroke-width="3" marker-end="url(#g12)"/>
  <defs><marker id="g12" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M0 0 L9 4.5 L0 9 z" fill="#888"/></marker></defs>
  <rect x="510" y="50" width="150" height="80" rx="6" fill="#2d8659"/>
  <text x="585" y="76" text-anchor="middle" class="t12">BACK-END</text>
  <text x="585" y="94" text-anchor="middle" class="s12">Lógica + BD</text>
  <text x="585" y="110" text-anchor="middle" class="s12">(§8.1-8.4)</text>
  <rect x="80" y="160" width="520" height="70" rx="6" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <text x="340" y="184" text-anchor="middle" style="font:700 11px system-ui;fill:#0055a0">REST trata cada entidad como un RECURSO identificado por URL</text>
  <text x="340" y="204" text-anchor="middle" style="font:10px system-ui;fill:#444">manipulado con los métodos HTTP estándar (§2.3.1) — sin envoltura de protocolo propia</text>
  <rect x="150" y="248" width="380" height="60" rx="6" fill="#d13c3c"/>
  <text x="340" y="272" text-anchor="middle" class="t12">SOAP: alternativa con sobre XML + WSDL</text>
  <text x="340" y="292" text-anchor="middle" class="s12">Contrato formal; vigente en integraciones heredadas (Tema 22)</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: FIELDING2000]</text>
</svg>
```

---

## D13 · PWA: Service Worker, Manifest y Cache

**Sección**: §9.3 — Aplicaciones web progresivas (PWA)
**Propósito**: Mostrar los tres pilares técnicos de una PWA y el papel del Service Worker como intermediario de red.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Una PWA se compone de Service Worker que intercepta peticiones de red y sirve contenido desde caché sin conexión, Web App Manifest que permite instalar la aplicación, y servicio obligatorio por HTTPS">
  <style>.t13{font:700 11px system-ui,sans-serif;fill:#fff}.s13{font:9.5px system-ui,sans-serif;fill:#fff}.h13{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h13">PWA: tres pilares técnicos</text>
  <rect x="30" y="44" width="190" height="80" rx="6" fill="#0055a0"/>
  <text x="125" y="70" text-anchor="middle" class="t13">Service Worker</text>
  <text x="125" y="88" text-anchor="middle" class="s13">Intercepta peticiones</text>
  <text x="125" y="104" text-anchor="middle" class="s13">Sin acceso al DOM</text>
  <rect x="245" y="44" width="190" height="80" rx="6" fill="#2d8659"/>
  <text x="340" y="70" text-anchor="middle" class="t13">Web App Manifest</text>
  <text x="340" y="88" text-anchor="middle" class="s13">JSON: nombre, iconos</text>
  <text x="340" y="104" text-anchor="middle" class="s13">Permite «instalar»</text>
  <rect x="460" y="44" width="190" height="80" rx="6" fill="#e89822"/>
  <text x="555" y="70" text-anchor="middle" class="t13">HTTPS obligatorio</text>
  <text x="555" y="88" text-anchor="middle" class="s13">Requisito para registrar</text>
  <text x="555" y="104" text-anchor="middle" class="s13">el Service Worker</text>
  <path d="M125 124 L125 160" stroke="#888" stroke-width="2" marker-end="url(#h13a)"/>
  <defs><marker id="h13a" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M0 0 L9 4.5 L0 9 z" fill="#888"/></marker></defs>
  <rect x="30" y="164" width="300" height="70" rx="6" fill="#d13c3c"/>
  <text x="180" y="188" text-anchor="middle" class="t13">Con conexión → red</text>
  <text x="180" y="206" text-anchor="middle" class="s13">Sin conexión → Cache API (§3.4)</text>
  <text x="180" y="222" text-anchor="middle" class="s13">sirve contenido cacheado</text>
  <rect x="350" y="164" width="300" height="70" rx="6" fill="#2d8659"/>
  <text x="500" y="188" text-anchor="middle" class="t13">Notificaciones push</text>
  <text x="500" y="206" text-anchor="middle" class="s13">Reactiva incluso con</text>
  <text x="500" y="222" text-anchor="middle" class="s13">la pestaña cerrada</text>
  <rect x="80" y="252" width="520" height="60" rx="6" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <text x="340" y="278" text-anchor="middle" style="font:700 11px system-ui;fill:#0055a0">El Service Worker vive en un hilo separado de la página</text>
  <text x="340" y="298" text-anchor="middle" style="font:10px system-ui;fill:#444">se comunica con ella por paso de mensajes, nunca accede al DOM directamente</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: SERVICE-WORKERS; MDN-PWA]</text>
</svg>
```

---

## D14 · XSS frente a CSRF: direcciones de la confianza explotada

**Sección**: §10.2.2 — Cross-Site Scripting (XSS) y Cross-Site Request Forgery (CSRF)
**Propósito**: Contrastar las dos direcciones de confianza que explota cada ataque.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="XSS explota la confianza del usuario en el sitio ejecutando script inyectado como si fuera propio del dominio; CSRF explota la confianza del sitio en el navegador ya autenticado del usuario enviando una petición no deseada">
  <style>.t14{font:700 11px system-ui,sans-serif;fill:#fff}.s14{font:9.5px system-ui,sans-serif;fill:#fff}.h14{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h14">XSS frente a CSRF: dos direcciones de confianza</text>
  <rect x="30" y="44" width="300" height="120" rx="6" fill="#d13c3c"/>
  <text x="180" y="68" text-anchor="middle" class="t14">XSS</text>
  <text x="180" y="88" text-anchor="middle" class="s14">Script inyectado se ejecuta</text>
  <text x="180" y="104" text-anchor="middle" class="s14">como si fuera del propio dominio</text>
  <text x="180" y="124" text-anchor="middle" class="s14">Explota: confianza del USUARIO</text>
  <text x="180" y="140" text-anchor="middle" class="s14">en el SITIO</text>
  <rect x="350" y="44" width="300" height="120" rx="6" fill="#0055a0"/>
  <text x="500" y="68" text-anchor="middle" class="t14">CSRF</text>
  <text x="500" y="88" text-anchor="middle" class="s14">Petición no deseada, enviada</text>
  <text x="500" y="104" text-anchor="middle" class="s14">con la cookie de sesión válida</text>
  <text x="500" y="124" text-anchor="middle" class="s14">Explota: confianza del SITIO</text>
  <text x="500" y="140" text-anchor="middle" class="s14">en el NAVEGADOR autenticado</text>
  <rect x="30" y="184" width="300" height="80" rx="6" fill="#f0f0f0" stroke="#d13c3c" stroke-width="2"/>
  <text x="180" y="206" text-anchor="middle" style="font:700 10.5px system-ui;fill:#d13c3c">Mitigación</text>
  <text x="180" y="226" text-anchor="middle" style="font:9.5px system-ui;fill:#444">Escapar toda salida no confiable</text>
  <text x="180" y="242" text-anchor="middle" style="font:9.5px system-ui;fill:#444">Cabecera Content-Security-Policy</text>
  <rect x="350" y="184" width="300" height="80" rx="6" fill="#f0f0f0" stroke="#0055a0" stroke-width="2"/>
  <text x="500" y="206" text-anchor="middle" style="font:700 10.5px system-ui;fill:#0055a0">Mitigación</text>
  <text x="500" y="226" text-anchor="middle" style="font:9.5px system-ui;fill:#444">Token CSRF único por sesión</text>
  <text x="500" y="242" text-anchor="middle" style="font:9.5px system-ui;fill:#444">Cookie con SameSite=Strict/Lax</text>
  <text x="340" y="292" text-anchor="middle" style="font:700 11px system-ui;fill:#2d8659">HttpOnly limita el impacto de XSS (no lo evita) al impedir leer la cookie por JS</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: OWASP-TOP10]</text>
</svg>
```
