# Tema 23 — Checklist de Validación

> **Título oficial**: Aplicaciones web. Desarrollo web front-end y en servidor, multiplataforma y multidispositivo. HTML, XML y derivaciones. Navegadores y lenguajes de programación web. Lenguajes de script.
> **Versión**: v1.0 — Pendiente validación
> **Fecha**: 2026-07-21
> **Revisores**: María y Ana (eTrivium) · revisión técnica IAM (Jesús Cuadrado)
> **Instrucciones**: marcar cada ítem. Los cambios no se guardan en la web (imprimir o exportar a PDF si se desea fijarlos).

---

## 1. Cobertura del temario oficial

- [ ] **Introducción a las aplicaciones web**: concepto/evolución, ventajas frente a escritorio, arquitectura cliente-servidor — §1.1-1.3
- [ ] **Fundamentos de la WWW**: Internet/web/servicios, URL/URI, protocolos, métodos/cabeceras/códigos de estado — §2.1-2.3
- [ ] **Desarrollo web front-end**: HTML/CSS/JS, RWD, accesibilidad/usabilidad, normativa AAPP, almacenamiento — §3.1-3.4
- [ ] **HTML y sus evoluciones**: origen, estructura, HTML5 semántico, formularios/multimedia — §4.1-4.3
- [ ] **XML y sus derivaciones**: concepto, estructura, validación DTD/XSD, XHTML/XSLT/SVG — §5.1-5.4
- [ ] **Navegadores web**: arquitectura, motores de renderizado, DOM, compatibilidad — §6.1-6.4
- [ ] **Lenguajes de programación web y de script**: JS cliente, DOM/eventos, AJAX, PHP/Java/Python, frameworks — §7.1-7.4
- [ ] **Desarrollo web en servidor**: back-end, generación dinámica, acceso a BD, sesiones/auth, servicios web/APIs — §8.1-8.5
- [ ] **Apps multiplataforma y multidispositivo**: compatibilidad, diseño adaptativo/responsivo, PWA — §9.1-9.3
- [ ] **Seguridad en aplicaciones web**: modelo de amenazas, OWASP Top 10, buenas prácticas — §10.1-10.3

## 2. Contenido teórico

- [ ] El nivel de profundidad (10 secciones, con desarrollo extenso de seguridad por decisión expresa de Joan) es adecuado para C1 (¿hay que ampliar o recortar alguna sección?)
- [ ] Las definiciones de URI/URL, idempotencia HTTP, 401 vs 403, bien formado vs válido, y XSS vs CSRF son correctas y están bien diferenciadas
- [ ] La decisión de usar **snippets de código reales** (HTML/CSS/JS/PHP/Python) en lugar de pseudocódigo neutro es adecuada (¿o se prefiere un enfoque más conceptual?)
- [ ] La sección 10 (Seguridad) desarrollada en profundidad no duplica innecesariamente el contenido de los Temas 25 y 32 (frontera revisada en changelog)
- [ ] La frontera con los Temas 18 (lenguajes de programación general), 20 (POO), 21 (Java EE), 22 (arquitecturas cliente/servidor y servicios web), 24 (desarrollo móvil), 25 (accesibilidad/seguridad en el desarrollo), 32 (seguridad de sistemas), 35 (Internet/HTTP/TLS) y 39 (ENS/ENI) está clara
- [ ] Los ejemplos Ayto Madrid (sede electrónica: cita previa, expedientes) son verosímiles y coherentes entre secciones

## 3. Fuentes

- [ ] Todas las afirmaciones técnicas están respaldadas por fuente Tier 1 (especificaciones WHATWG/W3C/IETF/Ecma/OWASP)
- [ ] Las referencias inline se corresponden con `tema-23-fuentes.md`
- [ ] Atribuciones históricas correctas (HTML 1991, XHTML 1998-2009, WHATWG Living Standard único desde 2019, AJAX 2005, RD 1112/2018)

## 4. Test (60 preguntas)

- [ ] Cada pregunta tiene una sola respuesta correcta e inequívoca
- [ ] Los distractores (A/B/C) son plausibles
- [ ] La distribución de la opción correcta entre A/B/C está equilibrada (20/20/20)
- [ ] Las explicaciones y referencias de cada respuesta son correctas

## 5. Casos prácticos (3)

- [ ] Realistas y propios del Ayuntamiento (formulario de cita previa, API REST de expedientes, PWA y mitigación XSS)
- [ ] Soluciones orientativas técnicamente correctas (HTML/CSS/JS/Python funcionales en su forma simplificada)
- [ ] La puntuación de cada caso suma 10 puntos

## 6. Diagramas (14 SVG)

- [ ] Cada diagrama es correcto y legible (también impreso en B/N)
- [ ] Accesibilidad: todos tienen `role="img"` y `aria-label`
- [ ] Sin desbordes de texto ni colisiones de estilo entre SVG (clases con sufijo único, QA de caja contenedora)

## 7. Referencias cruzadas a otros temas

- [ ] Validadas contra BOAM 10.032 (T18, T20, T21, T22, T24, T25, T32, T35, T39)
- [ ] Ninguna referencia cruzada cita un enunciado de tema incorrecto

## 8. Calidad editorial

- [ ] Ortografía verificada (tildes y ñ) — sin diacríticos perdidos
- [ ] Coherencia de versión (v1.0) en title, badges, banner y footer del `index.html`
- [ ] El `index.html` abre, navega entre las 8 pestañas y el motor de test funciona
- [ ] Las listas anidadas del Contenido se muestran con sus niveles (sin aplanar)
- [ ] Los bloques de código HTML/CSS/JS/PHP/Python se muestran correctamente formateados, sin markdown crudo

---

## Observaciones abiertas

_(Espacio para anotaciones de María, Ana y la revisión IAM.)_

- Pendiente confirmar con IAM si se desea desarrollar más la sección de seguridad (§10) con casos de vulnerabilidades reales adicionales (CORS mal configurado, deserialización insegura) o si el nivel actual (OWASP Top 10 con foco en inyección/control de acceso/XSS/CSRF/configuración) es suficiente para C1.
- El Tema 22 (arquitectura cliente/servidor multicapa y servicios web) aún no está generado; las referencias cruzadas de este tema hacia T22 deberán reverificarse cuando se publique.
