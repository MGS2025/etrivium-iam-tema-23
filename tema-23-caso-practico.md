# Tema 23 — Casos Prácticos

> **Título oficial**: Aplicaciones web. Desarrollo web front-end y en servidor, multiplataforma y multidispositivo. HTML, XML y derivaciones. Navegadores y lenguajes de programación web. Lenguajes de script.
>
> **Formato**: 3 casos prácticos sobre supuestos reales del Ayuntamiento de Madrid. Cada caso suma **10 puntos**.
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

Los tres casos recorren la aplicación de referencia **sede electrónica** (ver tema-23-contenido.md, «Convenciones»): el **Caso 1** trabaja el **front-end** (formulario HTML5 responsivo y accesible); el **Caso 2**, el **back-end** (API REST, sesión y acceso a datos); y el **Caso 3**, la **capa progresiva y de seguridad** (PWA y mitigación de XSS/CSRF).

---

## Caso 1 — Formulario de cita previa: HTML5, RWD y accesibilidad

### Enunciado

El área de Atención al Ciudadano necesita un formulario de **solicitud de cita previa** en la sede electrónica, usable tanto desde un ordenador de oficina como desde el móvil de un ciudadano en la calle, y accesible para personas que navegan únicamente con teclado o con lector de pantalla.

### Cuestiones

**Cuestión 1 — Validación nativa (2 puntos).** Anote el campo de DNI/NIE del formulario usando validación **nativa de HTML5** (sin JavaScript), exigiendo 8 dígitos seguidos de una letra, y marcándolo como obligatorio.

**Cuestión 2 — Metaetiqueta viewport (2 puntos).** Indique la etiqueta imprescindible en `<head>` para que el formulario se muestre correctamente adaptado en un móvil, y explique qué ocurre si se omite.

**Cuestión 3 — Media query (3 puntos).** El formulario se maqueta con Flexbox en fila (`row`) para escritorio. Escriba la media query que lo reorganiza en columna (`column`) por debajo de 600px de ancho.

**Cuestión 4 — Accesibilidad (3 puntos).** Un campo de texto no tiene una etiqueta `<label>` visible por razones de diseño, solo un icono. ¿Cómo se etiqueta correctamente para que un lector de pantalla anuncie su propósito, cumpliendo el principio POUR «Perceptible» de WCAG?

### Solución orientativa

- **C1**: atributo `pattern` con expresión regular, `required` para obligatoriedad (§4.3.2).

```html
<label for="dni">DNI/NIE:</label>
<input type="text" id="dni" name="dni" pattern="[0-9]{8}[A-Za-z]" required>
```

- **C2**: `<meta name="viewport" content="width=device-width, initial-scale=1.0">` (§3.3.1). Sin ella, el navegador móvil renderiza a una anchura de escritorio simulada (≈980px) y luego reduce la imagen, haciendo inútiles las media queries basadas en ancho real de pantalla.

- **C3**: media query sobre el ancho de la ventana gráfica (§3.3.1).

```css
.formulario-cita { display: flex; flex-direction: row; }
@media (max-width: 600px) {
  .formulario-cita { flex-direction: column; }
}
```

- **C4**: usar el atributo `aria-label` (o un `<label>` visualmente oculto con una clase que lo saque del flujo visual sin usar `display:none`, que también lo ocultaría a tecnologías de apoyo), de forma que el lector de pantalla anuncie el propósito del campo aunque no haya texto visible (§3.3.2).

```html
<input type="search" aria-label="Buscar trámite" placeholder="Buscar...">
```

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Validación nativa `pattern`/`required` correctamente anotada | 2 |
| Metaetiqueta viewport correcta, con justificación del efecto de omitirla | 2 |
| Media query correcta, con `max-width` y cambio de `flex-direction` | 3 |
| Etiquetado accesible correcto (`aria-label` o equivalente), justificando el problema de `display:none` | 3 |

---

## Caso 2 — API REST de consulta de expedientes con sesión segura

### Enunciado

El back-end de la sede electrónica debe exponer una **API REST** para que el front-end consulte el estado de los expedientes del ciudadano **ya autenticado**, evitando que un ciudadano pueda consultar expedientes ajenos simplemente cambiando un identificador en la URL.

### Cuestiones

**Cuestión 1 — Endpoint REST (2 puntos).** Indique el método HTTP y la ruta adecuados para «obtener el expediente número 1234», siguiendo el estilo REST.

**Cuestión 2 — Consulta segura a la base de datos (3 puntos).** Escriba, en pseudocódigo de servidor, la consulta que recupera el expediente por su identificador, evitando la vulnerabilidad de inyección SQL.

**Cuestión 3 — Control de acceso (3 puntos).** Explique qué comprobación adicional, más allá de la autenticación, debe hacer el servidor antes de devolver el expediente, para no ser vulnerable a un **IDOR** (*Insecure Direct Object Reference*).

**Cuestión 4 — Cookie de sesión (2 puntos).** Indique los tres atributos de la cookie de sesión que mitigan, respectivamente, el robo por XSS y el uso indebido por CSRF.

### Solución orientativa

- **C1**: `GET /api/expedientes/1234` (§8.5) — GET porque es una operación de lectura, idempotente y sin efectos secundarios (§2.3.1).

- **C2**: consulta **parametrizada**, nunca concatenando el identificador directamente en la cadena SQL (§8.3, §10.2.1).

```python
cursor.execute("SELECT * FROM expediente WHERE id = %s", (id_expediente,))
```

- **C3**: no basta con comprobar que el usuario **está autenticado** (§8.4): el servidor debe verificar además que el expediente solicitado **pertenece** al ciudadano autenticado (o que su rol tiene permiso explícito sobre él), devolviendo `403 Forbidden` si no es así. Confiar en que «si conoce el identificador es porque tiene derecho a verlo» es precisamente el fallo de control de acceso (§10.2.1) que hace posible el ataque IDOR.

```python
expediente = obtener_expediente(id_expediente)
if expediente.dni_titular != usuario_autenticado.dni:
    return jsonify(error="No autorizado"), 403
```

- **C4**: `HttpOnly` (JavaScript no puede leerla, mitiga el robo por XSS), `Secure` (solo se envía por HTTPS) y `SameSite=Strict` o `Lax` (no se envía en peticiones originadas desde otro dominio, mitiga CSRF) (§8.4, §10.2.2, §10.3.2).

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Método y ruta REST correctos (GET, recurso identificado en la ruta) | 2 |
| Consulta parametrizada, sin concatenación insegura | 3 |
| Verificación de pertenencia del expediente al usuario autenticado, con 403 correcto | 3 |
| Los tres atributos de cookie correctamente identificados y asociados a su mitigación | 2 |

---

## Caso 3 — Conversión a PWA y mitigación de XSS en un formulario de contacto

### Enunciado

La sede electrónica debe ofrecer, además, la posibilidad de **consultar el estado de un trámite sin conexión** (por ejemplo, en el metro), y su formulario de contacto —que muestra los últimos mensajes enviados por el propio ciudadano en la misma sesión— debe protegerse frente a inyección de script.

### Cuestiones

**Cuestión 1 — Registro del Service Worker (2 puntos).** Escriba el código JavaScript, ejecutado desde la página principal, que registra un Service Worker ubicado en `/sw.js`.

**Cuestión 2 — Requisito de despliegue (2 puntos).** ¿Bajo qué condición de protocolo puede registrarse un Service Worker en producción, y por qué es un requisito de seguridad, no solo una recomendación?

**Cuestión 3 — Manifest de instalación (2 puntos).** Indique dos propiedades imprescindibles del fichero `manifest.json` para que el navegador ofrezca «instalar» la sede electrónica en la pantalla de inicio.

**Cuestión 4 — Mitigación de XSS (4 puntos).** El formulario de contacto muestra el último mensaje del ciudadano insertándolo en el DOM con `innerHTML`. Explique por qué esto es vulnerable a XSS y cómo corregirlo.

### Solución orientativa

- **C1**: registro condicionado a que el navegador soporte la API (§9.3).

```javascript
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js');
}
```

- **C2**: solo puede registrarse servido por **HTTPS** (§9.3, §10.3.1). Es un requisito de seguridad, no una recomendación, porque el Service Worker obtiene un control extenso sobre el tráfico de red de la aplicación (puede interceptar y modificar cualquier petición y respuesta); permitirlo sobre HTTP sin cifrar expondría ese control a un atacante interceptando la red.

- **C3**: por ejemplo, `name` (o `short_name`) y `start_url`, junto con al menos un icono en `icons` (§9.3).

```json
{ "name": "Sede Electrónica", "start_url": "/portal/", "icons": [{"src": "/icon-192.png", "sizes": "192x192", "type": "image/png"}] }
```

- **C4**: `innerHTML` inserta la cadena recibida **interpretándola como HTML**; si el mensaje del ciudadano contiene una etiqueta `<script>` (introducida por error o, en el caso general, por un atacante mediante otro campo mal protegido), el navegador la **ejecutaría** en el contexto del propio dominio de la sede electrónica — un XSS almacenado (§10.2.2). La corrección es usar `textContent` en lugar de `innerHTML` cuando el contenido es texto plano, o, si se necesita insertar marcado, **escapar** los caracteres especiales (`<`, `>`, `&`) antes de insertarlo, reforzado con una cabecera `Content-Security-Policy` que limite qué script puede ejecutarse en la página.

```javascript
// VULNERABLE
elemento.innerHTML = ultimoMensaje;
// CORRECTO
elemento.textContent = ultimoMensaje;
```

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Registro del Service Worker correctamente condicionado a soporte del navegador | 2 |
| HTTPS identificado como requisito, con justificación de seguridad | 2 |
| Dos propiedades del manifest correctamente identificadas | 2 |
| XSS explicado correctamente (innerHTML interpreta HTML) y corregido con textContent/escapado | 4 |

---

*Los tres casos son orientativos y pensados para la autoevaluación; las soluciones muestran una vía correcta, no la única posible. Todos los ejemplos usan HTML5, CSS3, JavaScript (ES2015+), Python y JSON reales, coherentes con la decisión de Joan de no usar pseudocódigo neutro en este tema.*
