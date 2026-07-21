# Tema 23 — Fuentes

> **Título oficial**: Aplicaciones web. Desarrollo web front-end y en servidor, multiplataforma y multidispositivo. HTML, XML y derivaciones. Navegadores y lenguajes de programación web. Lenguajes de script.
>
> **Criterio**: todo dato del contenido cita un **ID** inline (p. ej. `[WHATWG-HTML]`). Tier 1 = especificaciones oficiales de los estándares web (W3C, WHATWG, IETF, ECMA) y obras canónicas de arquitectura web; Tier 2 = documentación de referencia de lenguajes, motores y frameworks concretos, citada para ilustrar sin atar el tema a un único producto; Tier 3 = marco normativo y del puesto, no citado como contenido técnico puro.

---

## Tier 1 — Especificaciones oficiales y obras canónicas

| ID | Referencia |
|---|---|
| `[WHATWG-HTML]` | WHATWG. *HTML Living Standard*. html.spec.whatwg.org. Especificación viva y de referencia de HTML5, mantenida por el WHATWG (Apple, Google, Mozilla, Microsoft) desde 2019 tras el fin del desarrollo paralelo con el W3C. |
| `[W3C-HTML5]` | W3C. *HTML5.2/5.3* (última recomendación formal del W3C antes de adoptar el Living Standard del WHATWG como fuente única en 2019). w3.org/TR/html5. |
| `[W3C-CSS]` | W3C CSS Working Group. *CSS Snapshot* y módulos CSS3 (Selectors, Box Model, Flexible Box, Grid Layout, Media Queries). w3.org/Style/CSS. |
| `[ECMA262]` | Ecma International. *ECMA-262: ECMAScript Language Specification* (edición vigente, ES2015+). Especificación normativa del lenguaje JavaScript. |
| `[W3C-DOM4]` | W3C / WHATWG. *DOM Living Standard* (DOM4 y sucesivas). dom.spec.whatwg.org. Define el Modelo de Objetos del Documento como API independiente del lenguaje. |
| `[RFC3986]` | Berners-Lee, T.; Fielding, R.; Masinter, L. *RFC 3986: Uniform Resource Identifier (URI): Generic Syntax* (IETF, 2005). Especificación normativa de URI/URL. |
| `[RFC9110]` | IETF HTTP Working Group. *RFC 9110: HTTP Semantics* (2022, sustituye a RFC 7230-7235). Métodos, cabeceras y códigos de estado HTTP. |
| `[RFC9112]` | IETF. *RFC 9112: HTTP/1.1*. Sintaxis de mensajes HTTP/1.1. |
| `[RFC9113]` | IETF. *RFC 9113: HTTP/2*. |
| `[RFC9114]` | IETF. *RFC 9114: HTTP/3* (sobre QUIC/RFC 9000). |
| `[RFC8446]` | IETF. *RFC 8446: The Transport Layer Security (TLS) Protocol Version 1.3*. |
| `[FIELDING2000]` | Fielding, R. T. *Architectural Styles and the Design of Network-based Software Architectures* (tesis doctoral, UC Irvine, 2000). Origen del estilo arquitectónico cliente-servidor por capas y de REST. |
| `[XML10]` | W3C. *Extensible Markup Language (XML) 1.0* (5.ª edición). w3.org/TR/xml. |
| `[XML-NAMESPACES]` | W3C. *Namespaces in XML 1.0*. w3.org/TR/xml-names. |
| `[XMLSCHEMA]` | W3C. *XML Schema Definition Language (XSD) 1.1*. w3.org/TR/xmlschema11-1. |
| `[XHTML10]` | W3C. *XHTML 1.0: The Extensible HyperText Markup Language* (2.ª edición). w3.org/TR/xhtml1. |
| `[XSLT30]` | W3C. *XSL Transformations (XSLT) Version 3.0*. w3.org/TR/xslt-30. |
| `[SVG11]` | W3C. *Scalable Vector Graphics (SVG) 1.1* (2.ª edición) y *SVG 2* (borrador de referencia). w3.org/TR/SVG11. |
| `[WCAG22]` | W3C WAI. *Web Content Accessibility Guidelines (WCAG) 2.2*. w3.org/TR/WCAG22. Estándar de accesibilidad web, base del RD 1112/2018. |
| `[SERVICE-WORKERS]` | W3C. *Service Workers* Specification. w3.org/TR/service-workers. Fundamento técnico de las PWA. |
| `[WEB-APP-MANIFEST]` | W3C. *Web Application Manifest*. w3.org/TR/appmanifest. |
| `[OWASP-TOP10]` | OWASP Foundation. *OWASP Top 10:2021 — The Ten Most Critical Web Application Security Risks*. owasp.org/Top10. Referencia canónica de vulnerabilidades web. |
| `[FOWLER-EAA]` | Fowler, M. *Patterns of Enterprise Application Architecture* (Addison-Wesley, 2002). Patrones de arquitectura multicapa (*Layers*, *Front Controller*, *MVC*) aplicables al front-end y al back-end web. |

## Tier 2 — Documentación de lenguajes, motores y herramientas

| ID | Referencia |
|---|---|
| `[MDN-JS]` | Mozilla Developer Network. *JavaScript Guide y Reference*. developer.mozilla.org/en-US/docs/Web/JavaScript. |
| `[MDN-HTTP]` | Mozilla Developer Network. *HTTP*. developer.mozilla.org/en-US/docs/Web/HTTP. |
| `[MDN-CSS]` | Mozilla Developer Network. *CSS*. developer.mozilla.org/en-US/docs/Web/CSS. |
| `[MDN-PWA]` | Mozilla Developer Network. *Progressive web apps*. developer.mozilla.org/en-US/docs/Web/Progressive_web_apps. |
| `[V8-DOC]` | Google. *V8 JavaScript Engine — Documentación de arquitectura* (parser, Ignition, TurboFan, recolector de basura generacional). v8.dev/docs. |
| `[CHROMIUM-BLINK]` | The Chromium Project. *Blink Rendering Engine* — documentación de arquitectura (pipeline de renderizado: parsing, estilo, layout, paint, composición). www.chromium.org/blink. |
| `[GECKO-DOC]` | Mozilla. *Gecko / Servo — arquitectura del motor de renderizado de Firefox*. firefox-source-docs.mozilla.org. |
| `[WEBKIT-DOC]` | Apple/The WebKit Project. *WebKit — arquitectura* (WebCore + JavaScriptCore). webkit.org. |
| `[NODE-DOC]` | OpenJS Foundation. *Node.js Documentation* — bucle de eventos, E/S no bloqueante sobre V8. nodejs.org/docs. |
| `[PHP-DOC]` | The PHP Group. *PHP Manual*. php.net/manual. |
| `[PYTHON-DOC]` | Python Software Foundation. *The Python Standard Library* y documentación de WSGI (PEP 3333). docs.python.org. |
| `[DJANGO-DOC]` | Django Software Foundation. *Django Documentation*. docs.djangoproject.com. |
| `[EXPRESS-DOC]` | OpenJS Foundation. *Express.js — Guía*. expressjs.com. |
| `[REACT-DOC]` | Meta. *React Documentation*. react.dev. |
| `[MDN-SERVICEWORKER]` | Mozilla Developer Network. *Service Worker API — Guía práctica*. developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API. |
| `[LIGHTHOUSE-DOC]` | Google. *Lighthouse — PWA y rendimiento web*. developer.chrome.com/docs/lighthouse. |

## Tier 3 — Marco normativo y del puesto (contexto, no contenido técnico)

| ID | Referencia |
|---|---|
| `[RD1112-2018]` | Real Decreto 1112/2018, de 7 de septiembre, sobre accesibilidad de los sitios web y aplicaciones para dispositivos móviles del sector público. Transpone la Directiva (UE) 2016/2102. Base normativa de §3.4.3. |
| `[ENS]` | Real Decreto 311/2022, Esquema Nacional de Seguridad — requisitos de autenticación, cifrado en tránsito y trazabilidad aplicables al desarrollo seguro de aplicaciones web municipales. |
| `[RGPD]` | Reglamento (UE) 2016/679 (RGPD) y LO 3/2018 (LOPDGDD) — base legal de la gestión de cookies, sesiones y datos personales en aplicaciones web (§3.5, §8.4). |
| `[BOAM10032]` | BOAM 10.032 (23-dic-2025). Bases específicas TIC C1 Ayto. Madrid — temario oficial. |

---

*Las referencias Tier 1 fijan el fundamento normativo de los estándares abiertos de la web (WHATWG, W3C, IETF, Ecma, OWASP) y son la base de todo el contenido; Tier 2 documenta lenguajes, motores de navegador y frameworks concretos citados como ejemplo (V8/Blink, Node, PHP, Python/Django, React) sin que el tema dependa de ninguno en particular; Tier 3 enmarca la normativa de accesibilidad, seguridad y protección de datos aplicable a una aplicación web del Ayuntamiento de Madrid.*
