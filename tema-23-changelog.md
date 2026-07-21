# Tema 23 — Changelog

> **Título oficial**: Aplicaciones web. Desarrollo web front-end y en servidor, multiplataforma y multidispositivo. HTML, XML y derivaciones. Navegadores y lenguajes de programación web. Lenguajes de script.

---

## v1.0 — 2026-07-21 — Primera versión

**Estado**: pendiente de validación por María y Ana, y de revisión técnica del IAM (Jesús Cuadrado).

**Motivo**: desarrollo del Tema 23, dentro de la serie de temas técnicos generados desde cero (tras T11-T21), replicando la estructura y el formato de los Temas 1, 11, 17-21 ya consolidados, con pestaña Índice y listas anidadas correctas desde el inicio. Generado a petición expresa de Joan, saltando el Tema 22 (arquitectura cliente/servidor multicapa y servicios web) en la cola para atender primero este tema.

### Alcance de la v1.0

| Entregable | Cantidad |
|---|---|
| Contenido teórico | ~15.500 palabras · 10 secciones (fieles al esqueleto oficial) con 40 epígrafes numerados |
| Diagramas SVG inline | 14 (accesibles con `role`/`aria-label`, clases con sufijo único anti-colisión) |
| Banco de preguntas tipo test | 60 preguntas A/B/C con explicación y referencia, balanceadas **20/20/20** |
| Casos prácticos | 3 (formulario de cita previa HTML5/RWD/accesibilidad; API REST de expedientes con sesión segura; PWA y mitigación de XSS) · 10 puntos cada uno |
| Fuentes Tier 1 | 22 referencias canónicas (WHATWG, W3C, IETF, Ecma, OWASP, Fielding) |

### Decisiones de generación

1. **Sin material de cliente**: solo el esqueleto `Test_Prompting/temas julio/23.md`. Desarrollado desde fuentes canónicas (especificaciones WHATWG/W3C/IETF/Ecma y el catálogo OWASP) y obras de arquitectura web, todas referenciadas.
2. **Estructura fiel al esqueleto oficial**, con numeración jerárquica de hasta tres niveles donde el esqueleto lo exige (H2 > H3 > H4), incluyendo la sección 10 (Seguridad en aplicaciones web) ya presente en el propio esqueleto del cliente, no añadida ex novo.
3. **Sección 10 (Seguridad) desarrollada EN PROFUNDIDAD, por decisión expresa de Joan** (confirmada tras plantear el solapamiento con T25/T32 antes de generar): se amplía más allá del único epígrafe «Buenas prácticas de desarrollo seguro» del esqueleto original, incorporando el modelo de amenazas y el catálogo OWASP Top 10 (inyección/control de acceso, XSS/CSRF, configuración incorrecta) — manteniendo referencias cruzadas explícitas a T25 y T32 para no presentar el contenido como exclusivo de este tema.
4. **Ejemplos de código reales en HTML5, CSS3, JavaScript (ES2015+), PHP y Python** (decisión de Joan, mismo criterio que T21 con Java/Jakarta): el tema trata específicamente de estas tecnologías concretas, y un pseudocódigo agnóstico perdería el sentido didáctico.
5. **Caso de referencia único para todo el tema**: la **sede electrónica** municipal (front-end responsivo y accesible, back-end con API REST y sesión, capa PWA), elegida en discovery previo a la generación (decisión de Joan) y reutilizada en contenido, diagramas y casos prácticos.
6. **Frontera con temas vecinos** cuidada: fundamentos generales de lenguajes de programación al Tema 18; POO y patrones al Tema 20; plataforma Java EE/Jakarta EE completa al Tema 21; arquitecturas cliente/servidor multicapa y protocolos de servicios web (REST/SOAP) en detalle al Tema 22 (aún no generado); desarrollo móvil nativo/híbrido al Tema 24; accesibilidad/usabilidad como disciplina completa y seguridad en el puesto de usuario al Tema 25; seguridad general de sistemas (criptografía, firma digital) al Tema 32; arquitectura de Internet y protocolos HTTP/HTTPS/TLS en detalle al Tema 35; ENS/ENI al Tema 39.
7. **Referencias cruzadas validadas contra BOAM 10.032**: T18, T20, T21, T22, T24, T25, T32, T35, T39. Todas comprobadas contra el enunciado oficial de cada tema.
8. **Anti-colisión de SVG**: las clases CSS de cada diagrama llevan **sufijo numérico único** (`.t1`…`.t14`), evitando el bug sistémico de estilos que leakean entre los SVG embebidos en la misma página (lección de T5).
9. **Orden de generación**: T23 se genera **antes** que T22 (arquitectura cliente/servidor multicapa), a petición expresa de Joan; T22 queda pendiente para una sesión posterior. Las referencias cruzadas de este tema hacia T22 se han redactado igualmente, y deberán reverificarse cuando T22 se publique.

### Pendientes para QA / próxima iteración

- Validación de profundidad por María/Ana/IAM (¿alguna sección a ampliar o recortar, dada la amplitud del temario oficial de este tema, uno de los más extensos del bloque técnico?).
- Confirmar si el nivel de detalle de la sección de Seguridad (§10) es el deseado, o si se prefiere ampliar con más vulnerabilidades OWASP (CORS, deserialización insegura, SSRF) en una v1.1.
- Verificación ortográfica con corrector es_ES (cuidado con falsos positivos por términos técnicos en inglés: *script*, *framework*, *fetch*, *cache*, *responsive*, *token*, *namespace*, *serverless*, *stateless*…).
- Reverificar las referencias cruzadas al Tema 22 en cuanto ese tema se publique.

### Origen

Generado el 2026-07-21 en el flujo de trabajo de eTrivium, replicando el patrón de los Temas 1 (v2.1), 11 (v3.2), 17-21 (v1.0). `build_t23.py` y `_build_css.txt` persistidos en el repo.
