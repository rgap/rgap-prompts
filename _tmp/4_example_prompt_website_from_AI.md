<CONTEXT>
    <PROJECT_CONTEXT>
    Las pequeñas y medianas empresas (PYMES) enfrentan barreras al acceder a crédito rápido por procesos burocráticos. 
    "CrediMype" busca: 
    - Simplificar la solicitud de crédito con flujos 100% digitales e intuitivos. 
    - Acelerar la revisión con validaciones automáticas. 
    - Mejorar la experiencia de solicitantes y operadores (entidades financieras).
    </PROJECT_CONTEXT>

    <SYSTEM_TYPE>
    Onboarding Digital de Crédito
    </SYSTEM_TYPE>

    <BUSINESS_DOMAIN>
    Servicios financieros (Fintech)
    </BUSINESS_DOMAIN>
</CONTEXT>

<THEME>
mode: grayscale
</THEME>

<ROLE>
Desarrollador Frontend con conocimientos sólidos de UX/UI.
</ROLE>

<INTENT> 
A partir de la IA provista en <INPUT>, generar un prototipo web estático, responsive y accesible (WCAG AA), usando HTML y CSS, y **JS simple y mínimo** cuando aporte navegación, validaciones básicas o estados UI (sin frameworks), con ITCSS y BEM. Crear una página HTML por cada ruta definida en la IA y enlazarlas entre sí según la navegación.
</INTENT>

<FILE_STRUCTURE>
La salida **DEBE** seguir exactamente esta estructura (nombres en minúsculas con guiones):
- `index.html` (en la raíz del proyecto)
- `pages/` (todas las demás páginas HTML aquí; una por cada ruta)
- `styles/` (capas ITCSS: 0_settings → 6_utilities + main.css)
- `scripts/` (JS simple, p. ej. main.js y módulos mínimos si aplica)

Reglas de rutas/enlaces (usar SIEMPRE rutas relativas):
- Desde `index.html` hacia páginas internas: `pages/<nombre>.html`
- Desde cualquier archivo en `pages/` hacia el home: `../index.html`
- Hojas de estilo desde root: `styles/main.css`
- Hojas de estilo desde `pages/`: `../styles/main.css`
</FILE_STRUCTURE>

<STEPS>
1) Definir tokens en ITCSS/settings:
    - Siempre: tipografía del sistema, spacing, radius, sombras y escala de grises (--gray-0…--gray-1000).
    - Si <THEME>.mode == "grayscale": usar exclusivamente --gray-*.
    - Si <THEME>.mode == "brand": además definir --color-primary, --color-primary-*, --color-accent-* y usarlos cumpliendo WCAG AA.
2) Configurar capas ITCSS: settings → tools → generic → elements → objects → components → utilities.
3) **Archivos**:
    - Crear **`index.html` en la raíz** (home/landing).
    - Crear **una página por cada ruta** en `pages/` (ej.: `pages/solicitud.html`, `pages/signup.html`, etc.).
4) Implementar navegación coherente (header/nav/footer y breadcrumbs si aplica) y enlazar todas las rutas según <FILE_STRUCTURE>.
5) Construir componentes clave (formularios, tablas, cards, alerts, estados vacío/error) con BEM y estados :hover/:focus/:active/:disabled accesibles.
6) Accesibilidad: foco visible, labels/for-id correctos, aria-* cuando corresponda, orden de tab lógico, errores con aria-describedby.
7) (Opcional) JS mínimo y aislado si la interacción lo exige, sin comprometer accesibilidad.
8) Verificar que **TODOS** los enlaces internos existan y usen las rutas relativas definidas en <FILE_STRUCTURE>. No generar reportes.
8) Verificar que **TODOS** los enlaces internos existan y usen las rutas relativas definidas en <FILE_STRUCTURE> y dirijan donde deban dirigir, y lo mismo en las funciones JS. No generar reportes.
9) **Demo completa (autorrelleno de campos)**: añadir un módulo JS mínimo (p. ej., `scripts/demo-data.js`) que, al activar un flag (`?demo=1` en la URL o un botón “Rellenar demo”), **precargue valores plausibles** en todos los campos de formularios (inputs, selects, radios, checkboxes), respetando accesibilidad y validaciones. Usar atributos `data-demo`/`data-demo-value` para mapear campos. Debe poder desactivarse (`?demo=0`) y no enviar datos reales por defecto.
</STEPS>

<CONSTRAINTS>
    - Sin frameworks ni librerías externas.
    - Sin estilos inline (salvo width/height en imágenes si es necesario).
    - Paleta según <THEME>.mode:
      • grayscale → SOLO grises (--gray-*) con contraste WCAG AA.
      • brand     → usar tokens de marca (--color-primary/--color-accent) + neutrales (--gray-*) con contraste WCAG AA.
    - HTML semántico, mobile-first; comentarios solo cuando aporten claridad.
</CONSTRAINTS>

<DELIVERABLES>
    1) Código separado por archivos en bloques (usar separadores tipo: ===== index.html ===== y ===== pages/<archivo>.html =====).
    2) Tokens definidos en settings y uso consistente en las demás capas.
    3) **`index.html` en la raíz** y **todas las páginas adicionales en `pages/`**, enlazadas según la navegación.
    4) Componentes con BEM y estados de interacción accesibles.
    5) README breve con estructura ITCSS, ubicación de los tokens, pautas de accesibilidad **y cómo activar la demo (`?demo=1`)**.
</DELIVERABLES>

<OUTPUT_FORMAT>
    - Entregar el código en bloques por archivo.
    - Incluir README (texto). Sin reporte de enlaces.
</OUTPUT_FORMAT>

<INPUT>
1. Inicio público
   Ruta: /
   Tipo: Página nueva
   Área: Público
   Prioridad: Secundaria

Layout y Grid:

* Contenedor: ancho máx: 1280, márgenes 24px, padding 24px
* Grid: 12 cols desktop | 6 tablet | 4 móvil; gutters 24px
* Breakpoints: móvil ≤640, tablet 641–1024, desktop ≥1025
* Patrón de escaneo: Z; Orden de bloques: [Hero → Beneficios → Cómo funciona → Preguntas frecuentes → Footer]

Navegación y Routing:

* Ubicación en menú: primaria
* Breadcrumb: No
* Variantes de ruta (si aplica): —
* Redirecciones/guardas (auth/rol): si autenticado → /app/mis-solicitudes

Secciones (2–7):

* Hero

- CTA primario: "Crear mi cuenta"
- Microcopy: "Solicita tu crédito 100% digital. Sin filas, con seguimiento en tiempo real."
- Secundarios: "Ingresar" (/login), "Saber requisitos" (/faq)
- Elementos (3–6): [headline H1], [subhead], [botones], [ilustración]
- Datos mostrados (si aplica): —
- Interacciones: hover|focus en botones; teclado: Enter activa CTA

* Cómo funciona

- CTA primario: "Empezar solicitud"
- Microcopy: "Regístrate, completa pasos, sube documentos y firma digitalmente."
- Secundarios: "Ver demo" (/demo), "Preguntas" (/faq)
- Elementos: [pasos 1–4], [iconos], [cards]
- Interacciones: foco visible, lectura por lector de pantalla

Componentes clave (inventario por página):

* Button | {variant, size} | {primary, secondary, link, disabled} | usar aria-pressed false/true si toggle
* NavBar | {items} | {auth, guest} | colapsa en móvil; role="navigation"
* StepList | {steps} | {4pasos} | orden semántico

Formularios y Validaciones (si aplica):

* —

Contenido mínimo:

* Hero: H1, párrafo, 2 CTAs, ilustración; Cómo funciona: 4 pasos con iconos; FAQ breve; Footer con enlaces legales
* Fuente: Marketing/Legal
* i18n: ES-PE por defecto; claves sugeridas: home.hero.title, home.how.steps

Estados UI (por página y/o sección):

* vacío: —
* carga: —
* error: banner de alerta si falla cargar FAQ

Accesibilidad (A11y) y SEO:

* A11y: H1 único; nav con landmarks; contraste AA
* SEO (público): title (≤60) "Crédito para PYMES en línea", meta description (≤160), canonical, OG básicos
* Roles/aria para componentes críticos (nav, main, footer, alert)

Performance y Caching:

* SLI/objetivo: TTFB ≤300ms, LCP ≤2.5s, INP ≤200ms
* Carga: diferir scripts; imágenes responsive
* Cache: HTTP/Etag para estáticos; stale-while-revalidate para FAQ
* Critical CSS: sí, fuentes: sistema

Analítica y Eventos (por página):

* "click_crear_cuenta" | click CTA | {ubicacion:"hero"} | / | CTR | ≥5%
* "scroll_how_it_works" | 50% scroll | {seccion:"how"} | / | tasa scroll | ≥60%

Dependencias:

* Servicios/terceros: —
* Datos: FAQ CMS
* Seguridad: CSP estricta; XSS en contenidos CMS

Notas para handoff:

* Slugs: /faq, /demo
* Convenciones: BEM utilitario; z-index overlays: modal 1000
* Estados de overlays: modal demo video
* Tokens sugeridos (THEME=grayscale): usar grises 50–900; énfasis por tipografía/espaciado

---

2. Crear cuenta (Registro)
   Ruta: /signup
   Tipo: Página nueva
   Área: Público
   Prioridad: CORE

Layout y Grid:

* Contenedor: ancho máx: 640, márgenes 24px, padding 24px
* Grid: 4 cols desktop | 4 tablet | 4 móvil; gutters 16px
* Breakpoints: móvil ≤640, tablet 641–1024, desktop ≥1025
* Patrón de escaneo: F; Orden de bloques: [Título → Formulario → Ayudas → Legal]

Navegación y Routing:

* Ubicación en menú: oculta
* Breadcrumb: No
* Variantes de ruta (si aplica): /signup?ref=campaña
* Redirecciones/guardas (auth/rol): si autenticado → /app/mis-solicitudes

Secciones (2–7):

* Formulario de registro

- CTA primario: "Enviar verificación"
- Microcopy: "Te enviaremos un enlace o código a tu correo."
- Secundarios: "Ingresar" (/login), "Ayuda" (/faq)
- Elementos: [input email], [botón], [checkbox términos]
- Datos mostrados: email; origen local
- Interacciones: validación onBlur/onInput; teclado Enter; feedback inline

* Avisos y soporte

- CTA primario: "Ver requisitos"
- Microcopy: "Formatos y tiempos estimados del proceso."
- Secundarios: "Contacto" (/soporte)
- Elementos: [links], [icono info]

Componentes clave (inventario por página):

* EmailField | {id, value} | {valid, invalid, disabled} | type="email", autocomplete="email"
* Checkbox | {id, checked, label} | {required} | foco con outline; label clickable
* SubmitButton | {loading} | {enabled, loading, disabled} | bloquea múltiples envíos

Formularios y Validaciones (si aplica):

* Campos: [email, "Correo electrónico", "Usa tu correo de trabajo", "Correo inválido", 120, required], [terms, "Acepto Términos", "Requerido para continuar", "Debes aceptar los Términos", —, required]
* Reglas: regex RFC 5322; bloquear dominios desechables opcional; dependencias: habilitar CTA si email válido y terms
* Mensajes de error: claros y accionables (≤120 chars)
* Estados: pristine, dirty, valid, invalid, submitLoading

Contenido mínimo:

* Título H1, párrafo de ayuda, formulario, enlaces a Términos/Política
* Fuente: UX/Legal
* i18n: signup.title, signup.form.email.label

Estados UI (por página y/o sección):

* vacío: campos vacíos con placeholders
* carga: botón en loading, spinner dentro
* error: banner si falla envío correo; link a soporte

Accesibilidad (A11y) y SEO:

* A11y: labels asociadas; descripciones aria-describedby; foco visible
* SEO (público): title "Crear cuenta", meta noindex
* Roles/aria: role="form", aria-live="polite" para errores

Performance y Caching:

* SLI/objetivo: LCP ≤1.8s
* Carga: input sin JS pesado; máscara ligera
* Cache: no-cache en respuesta de envío
* Critical CSS: sí; fuentes: sistema

Analítica y Eventos (por página):

* "signup_submit" | submit | {dominio,email_hash} | /signup | tasa éxito | ≥70%
* "email_validation_error" | blur | {motivo} | /signup | error rate | ≤5%

Dependencias:

* Servicios/terceros: auth (OTP/magic link), SMTP
* Datos: —
* Seguridad: CSRF, rate limiting por IP, reCAPTCHA invisible opcional

Notas para handoff:

* Slug recomendado: /signup
* Nombrado: form__email, btn__submit
* Overlays: dialog términos (focus trap)

Para páginas CORE, añadir:

* Resumen rápido (≤120 chars): Registro por email con verificación y aceptación de términos.
* Acciones principales (3 bullets, verbo+objeto): Enviar verificación; Aceptar términos; Abrir soporte.
* KPI/estado visible (si aplica): Progreso "Paso 1/4".

---

3. Ingresar / Verificar código
   Ruta: /login
   Tipo: Página existente
   Área: Público
   Prioridad: CORE

Layout y Grid:

* Contenedor: ancho máx: 640, márgenes 24px, padding 24px
* Grid: 4 cols; gutters 16px
* Breakpoints: móvil ≤640, tablet 641–1024, desktop ≥1025
* Patrón de escaneo: F; Orden: [Título → Email → Código → Reenviar]

Navegación y Routing:

* Ubicación en menú: oculta
* Breadcrumb: No
* Variantes de ruta (si aplica): /login?mode=link|otp
* Redirecciones/guardas (auth/rol): si autenticado → /app/mis-solicitudes

Secciones (2–7):

* Verificación

- CTA primario: "Ingresar"
- Microcopy: "Ingresa el código recibido o usa el enlace del correo."
- Secundarios: "Reenviar código" (/login/resend), "Problemas" (/soporte)
- Elementos: [email], [código 6 dígitos], [temporizador]
- Interacciones: autoadvance inputs; teclado; feedback inline

* Seguridad

- CTA primario: "Más opciones"
- Microcopy: "Protege tu cuenta con 2FA."
- Secundarios: "Configurar 2FA" (/app/seguridad)
- Elementos: [link informativo]

Componentes clave (inventario por página):

* OtpInput | {length=6} | {filled, partial, error} | auto-focus secuencial
* ResendLink | {cooldown} | {enabled, disabled} | reintento cada 30s

Formularios y Validaciones (si aplica):

* Campos: [email, "Correo", "Te enviaremos el código", "Correo inválido", 120, required], [otp, "Código", "Revisa bandeja y spam", "Código incorrecto o vencido", 6, required]
* Reglas: expiración 10 min; 5 intentos
* Mensajes de error: específicos y cortos
* Estados: pristine, dirty, valid, invalid, submitLoading

Contenido mínimo:

* Título, ayuda, inputs, enlaces de soporte
* Fuente: UX/Seguridad
* i18n: auth.login.title, auth.otp.error

Estados UI (por página y/o sección):

* vacío: placeholders
* carga: al validar código
* error: banner con reintento

Accesibilidad (A11y) y SEO:

* A11y: aria-live para errores; tabindex ordenado
* SEO (público): noindex
* Roles/aria: role="alert" para errores

Performance y Caching:

* SLI/objetivo: INP ≤150ms
* Carga: JS minimalista; sin libs pesadas
* Cache: no-store en respuestas OTP
* Critical CSS: sí

Analítica y Eventos (por página):

* "login_success" | submit ok | {mfa:false|true} | /login | tasa éxito | ≥80%
* "otp_resend" | click | {reintentos} | /login | ratio reenvío | ≤20%

Dependencias:

* Servicios/terceros: auth OTP/magic link, SMTP
* Datos: —
* Seguridad: rate limiting; bloqueo tras N intentos

Notas para handoff:

* Slug: /login, /login/resend
* Nombrado: otp__digit-1..6

Para páginas CORE, añadir:

* Resumen rápido: Acceso por correo con OTP/enlace.
* Acciones principales: Ingresar código; Reenviar código; Ir a soporte.
* KPI/estado visible: Contador de validez de código.

---

4. Recuperar acceso
   Ruta: /recuperar
   Tipo: Página nueva
   Área: Público
   Prioridad: Secundaria

Layout y Grid:

* Contenedor: 640; márgenes 24px; padding 24px
* Grid: 4 cols; gutters 16px
* Breakpoints: móvil ≤640, tablet 641–1024, desktop ≥1025
* Patrón: F; Orden: [Título → Form → Confirmación]

Navegación y Routing:

* Ubicación: oculta
* Breadcrumb: No
* Variantes: /recuperar?via=email
* Guardas: —

Secciones (2–7):

* Solicitar enlace/código

- CTA primario: "Enviar enlace"
- Microcopy: "Te enviaremos un enlace para restablecer acceso."
- Secundarios: "Ingresar" (/login)
- Elementos: [input email], [botón], [alerta éxito]

* Confirmación

- CTA primario: "Abrir correo"
- Microcopy: "Revisa tu bandeja y sigue las instrucciones."
- Secundarios: "Reenviar" (/recuperar?resend)

Componentes clave (inventario por página):

* EmailField | {value} | {valid, invalid} | idem /signup
* Alert | {type} | {success, error} | role="status"

Formularios y Validaciones (si aplica):

* Campos: [email, "Correo", "Usa tu correo registrado", "Correo no encontrado", 120, required]
* Reglas: mismas de /signup
* Mensajes de error: claros
* Estados: pristine→submitLoading→success

Contenido mínimo:

* Título, input, mensajes, enlaces
* Fuente: UX/Soporte
* i18n: recover.title, recover.success

Estados UI:

* vacío: —
* carga: spinner en botón
* error: banner con pasos alternos

Accesibilidad y SEO:

* A11y: aria-live
* SEO: noindex
* Roles: form, status

Performance y Caching:

* Objetivo: INP ≤150ms
* Cache: no-store en respuesta
* Critical CSS: sí

Analítica:

* "recover_submit" | submit | {email_hash} | /recuperar | éxito | ≥70%

Dependencias:

* Servicios: auth/SMTP
* Seguridad: rate limit

Notas para handoff:

* —

---

5. Mis solicitudes (Panel del solicitante)
   Ruta: /app/mis-solicitudes
   Tipo: Página nueva
   Área: Solicitante
   Prioridad: CORE

Layout y Grid:

* Contenedor: 1280; márgenes 24px; padding 24px
* Grid: 12/6/4; gutters 24px
* Breakpoints: estándar
* Patrón: F; Orden: [Header → KPIs → Lista → Empty/Help]

Navegación y Routing:

* Ubicación: primaria
* Breadcrumb: Sí → Home > Mis solicitudes
* Variantes: /app/mis-solicitudes?estado=, /app/solicitudes/:id
* Guardas: requiere auth rol=solicitante

Secciones (2–7):

* Header y acciones

- CTA primario: "Nueva solicitud"
- Microcopy: "Crea una solicitud y guárdala en borrador."
- Secundarios: "Ver requisitos" (/faq), "Soporte" (/soporte)
- Elementos: [search], [filtros], [CTA]

* Lista de solicitudes

- CTA primario: "Abrir detalle"
- Microcopy: "Revisa estado, monto y fecha."
- Secundarios: "Exportar CSV" (/app/mis-solicitudes/export)
- Elementos: [tabla], [chips estado], [paginación]
- Datos mostrados: {id, fecha, monto, estado}; origen API
- Interacciones: sort, filter, teclado, row clickable

Componentes clave (inventario por página):

* CardSolicitud/List | {estado, fecha, monto, id} | {borrador, evaluacion, observada, aprobada, rechazada, firmada, desembolsada} | clickable, no overflow
* FiltersBar | {estado, fecha} | — | persistir en querystring
* EmptyState | {cta} | — | mostrar si 0 items

Formularios y Validaciones (si aplica):

* Filtros: [estado, "Estado", "Filtra por estado", "Estado inválido", —, —]
* Reglas: validar estados permitidos
* Mensajes: simples

Contenido mínimo:

* KPIs (conteo por estado), tabla con columnas mínimas, ayuda y enlaces
* Fuente: UX/Backoffice
* i18n: app.requests.list.title, app.requests.status.*

Estados UI:

* vacío: "Aún no tienes solicitudes. Crea una ahora."
* carga: skeleton rows
* error: banner con reintentar

Accesibilidad y SEO:

* A11y: H1 único; tabla con thead/th; aria-sort; foco visible
* SEO: noindex
* Roles/aria: role="table", aria-live para cargas

Performance y Caching:

* Objetivo: LCP ≤2.0s
* Carga: paginación server-side
* Cache: SWR con stale-while-revalidate
* Critical CSS: sí

Analítica:

* "nueva_solicitud_click" | click | {} | /app/mis-solicitudes | tasa click | ≥30%
* "filtro_estado" | change | {estado} | /app/mis-solicitudes | uso filtros | ≥40%

Dependencias:

* Servicios: API solicitudes, auth
* Datos: catálogos sector/montos
* Seguridad: control de acceso por ownerId

Notas para handoff:

* Slugs: /app/solicitudes/:id
* Convenciones: card--state-{estado}

Para páginas CORE, añadir:

* Resumen rápido: Bandeja del solicitante con creación y seguimiento.
* Acciones principales: Crear solicitud; Filtrar bandeja; Abrir detalle.
* KPI/estado visible: conteo por estado y total.

---

6. Nueva solicitud (Wizard con autosave)
   Ruta: /app/solicitudes/nueva
   Tipo: Página nueva
   Área: Solicitante
   Prioridad: CORE

Layout y Grid:

* Contenedor: 1280; márgenes 24px; padding 24px
* Grid: 12 cols; gutters 24px; sidebar 3/9
* Breakpoints: estándar
* Patrón: F; Orden: [Stepper → Form → Sidebar ayuda]

Navegación y Routing:

* Ubicación: oculta
* Breadcrumb: Sí → Home > Mis solicitudes > Nueva
* Variantes: /app/solicitudes/:id/editar?step=1..n
* Guardas: auth solicitante; bloquear si estado ≠ borrador

Secciones (2–7):

* Paso 1: Datos del solicitante

- CTA primario: "Guardar y continuar"
- Microcopy: "Completa datos básicos de tu empresa y representante."
- Secundarios: "Guardar borrador" (/app/mis-solicitudes), "Cancelar" (/app/mis-solicitudes)
- Elementos: [inputs], [selects], [helper]
- Datos mostrados: {razón social, RUC, rubro, ingresos}; API/local
- Interacciones: autosave onChange; teclado; validación paso

* Paso 2: Datos del crédito

- CTA primario: "Continuar"
- Microcopy: "Indica monto, plazo y destino del crédito."
- Secundarios: "Volver" (/app/solicitudes/nueva?step=1)
- Elementos: [currency input], [slider plazo], [select destino]

* Paso 3: Documentos

- CTA primario: "Cargar documentos"
- Microcopy: "PDF/JPG/PNG, máx. 10 MB por archivo."
- Secundarios: "Ver guía" (/faq#docs)
- Elementos: [uploader], [lista], [validador]

* Paso 4: Revisión y envío

- CTA primario: "Enviar a evaluación"
- Microcopy: "Revisa y confirma. Al enviar, no podrás editar."
- Secundarios: "Editar" (/app/solicitudes/:id/editar), "Descargar resumen" (/app/solicitudes/:id/pdf)
- Elementos: [resumen], [checkbox declaraciones]

Componentes clave (inventario por página):

* Stepper | {current,total} | {1..4} | accesible con aria-current
* FormField | {id,label,required} | {valid, invalid, disabled} | helper + error
* Uploader | {accept,maxSize} | {idle, uploading, success, error} | validaciones en cliente/servidor
* SummaryCard | {campos} | — | lectura, no editable

Formularios y Validaciones (si aplica):

* Campos clave: [ruc, "RUC", "11 dígitos", "RUC inválido", 11, required], [dni_front, "DNI frente", "PDF/JPG/PNG, máx. 10MB", "Formato o tamaño no válido", —, required], [monto, "Monto", "Ingresa en S/", "Monto fuera de rango", 15, required], [plazo, "Plazo (meses)", "1–60", "Plazo inválido", 2, required]
* Reglas: regex RUC; rango monto y plazo; dependencias: destino según sector
* Mensajes de error: específicos; ≤120 chars
* Estados: pristine, dirty, valid, invalid, submitLoading

Contenido mínimo:

* Títulos por paso, descripciones, tooltips, lista de documentos requeridos
* Fuente: UX/Legal/Backoffice
* i18n: app.request.new.*

Estados UI:

* vacío: placeholders
* carga: skeleton al abrir paso
* error: toasts + inline

Accesibilidad y SEO:

* A11y: Stepper con aria; labels; foco manejado al cambiar de paso
* SEO: noindex
* Roles: main, form, progressbar

Performance y Caching:

* Objetivo: INP ≤200ms
* Carga: dividir por pasos (code-splitting)
* Cache: autosave local + API; SWR para catálogos
* Critical CSS: sí

Analítica:

* "autosave_ok" | change | {step} | /app/solicitudes/nueva | tasa autosave | ≥95%
* "enviar_evaluacion_click" | click | {id} | /app/solicitudes/:id | éxito envío | ≥85%

Dependencias:

* Servicios: API solicitudes, storage (S3/Blob)
* Datos: catálogos
* Seguridad: CSRF; validación server-side; límites de tamaño; antivirus opcional

Notas para handoff:

* Slugs: /app/solicitudes/:id/editar?step=n
* Nombres: form__ruc, upload__dni_front

Para páginas CORE, añadir:

* Resumen rápido: Wizard con autosave y validaciones por paso.
* Acciones principales: Completar datos; Subir documentos; Enviar a evaluación.
* KPI/estado visible: Progreso 4/4 con porcentaje.

---

7. Carga de documentos
   Ruta: /app/solicitudes/:id/documentos
   Tipo: Sección dentro de Detalle de solicitud
   Área: Solicitante
   Prioridad: CORE

Layout y Grid:

* Contenedor: 1280; márgenes 24px; padding 24px
* Grid: 12 cols; gutters 24px
* Breakpoints: estándar
* Patrón: F; Orden: [Lista requeridos → Uploader → Validaciones]

Navegación y Routing:

* Ubicación: secundaria
* Breadcrumb: Sí → Home > Mis solicitudes > Detalle > Documentos
* Variantes: ?tab=documentos
* Guardas: auth; estado permite edición (borrador/observada)

Secciones (2–7):

* Requeridos

- CTA primario: "Subir archivos"
- Microcopy: "PDF/JPG/PNG, máx. 10MB por archivo. Nombra tus archivos claramente."
- Secundarios: "Ver guía" (/faq#docs), "Eliminar todo" (#)
- Elementos: [lista], [estado], [validaciones]
- Datos mostrados: {tipo, estado, fecha}; API
- Interacciones: drag&drop, teclado, reintento

* Cumplimiento

- CTA primario: "Validar ahora"
- Microcopy: "Ejecuta validaciones automáticas."
- Secundarios: "Actualizar" (#)
- Elementos: [checks], [log]

Componentes clave (inventario por página):

* DocItem | {tipo,estado} | {pendiente, cargado, validado, error} | acciones: reemplazar, borrar
* Uploader | {accept,maxSize} | {uploading, success, error} | múltiple

Formularios y Validaciones (si aplica):

* Campos: [file, "Documento", "Arrastra o selecciona", "Archivo no permitido o muy grande", —, required]
* Reglas: lista blanca de extensiones; tamaño
* Mensajes: accionables

Contenido mínimo:

* Lista de tipos (DNI, RUC, EEFF), estados, timestamps
* Fuente: Backoffice/Legal
* i18n: app.request.docs.*

Estados UI:

* vacío: "Aún no has cargado documentos."
* carga: barra de progreso
* error: inline por archivo y banner general

Accesibilidad y SEO:

* A11y: input file accesible; zona drop con role
* SEO: noindex
* Roles: list, status

Performance y Caching:

* Objetivo: subidas chunked
* Carga: parallel uploads con límite
* Cache: firma URL temporal
* Critical CSS: sí

Analítica:

* "doc_upload" | success | {tipo, size} | /app/solicitudes/:id/documentos | tasa éxito | ≥95%
* "doc_validate" | click | {resultado} | idem | pass rate | ≥90%

Dependencias:

* Servicios: storage, antivirus, validaciones de archivos
* Seguridad: escaneo malware; URL firmadas

Notas para handoff:

* Nombrado: doc-item--estado-{x}

Para páginas CORE, añadir:

* Resumen rápido: Subida y validación de documentos requeridos.
* Acciones principales: Subir archivo; Reemplazar archivo; Validar cumplimiento.
* KPI/estado visible: % documentos completos.

---

8. Detalle y tracking de solicitud
   Ruta: /app/solicitudes/:id
   Tipo: Página nueva
   Área: Solicitante
   Prioridad: CORE

Layout y Grid:

* Contenedor: 1280; márgenes 24px; padding 24px
* Grid: 12 cols; gutters 24px; layout 8/4
* Breakpoints: estándar
* Patrón: F; Orden: [Resumen → Timeline → Observaciones → Documentos]

Navegación y Routing:

* Ubicación: primaria
* Breadcrumb: Sí → Home > Mis solicitudes > Detalle
* Variantes: ?tab=tracking|docs|observaciones
* Guardas: auth solicitante

Secciones (2–7):

* Resumen

- CTA primario: "Reanudar edición"
- Microcopy: "Modifica si está en Borrador u Observada."
- Secundarios: "Descargar PDF" (/app/solicitudes/:id/pdf), "Eliminar" (#)
- Elementos: [datos clave], [estado], [monto], [plazo]

* Timeline de estado

- CTA primario: "Ver detalles"
- Microcopy: "Seguimiento: Recibida → Evaluación → Observada → Aprobada/Rechazada → Firmada → Desembolsada."
- Secundarios: "Ver mensajes" (#)
- Elementos: [timeline], [chips]

* Observaciones

- CTA primario: "Responder"
- Microcopy: "Atiende pedidos del analista con datos o documentos."
- Secundarios: "Ver historial" (#)
- Elementos: [lista], [form respuesta]

Componentes clave (inventario por página):

* StatusBadge | {estado} | {todos} | mapea a color neutro/grayscale
* Timeline | {events[]} | {completo} | orden cronológico
* ObservationItem | {texto, fecha} | {abierta, resuelta} | adjuntos opcionales

Formularios y Validaciones (si aplica):

* Campos: [respuesta, "Respuesta", "Sé claro y adjunta evidencia", "Respuesta muy corta", 1000, required], [archivo, "Adjunto", "PDF/JPG/PNG", "Archivo no permitido", —, optional]
* Reglas: longitud mínima; extensiones
* Mensajes: concretos

Contenido mínimo:

* Cabecera con estado y resumen; timeline; listado de observaciones; CTA
* Fuente: UX/Backoffice
* i18n: app.request.detail.*

Estados UI:

* vacío: sin observaciones: "No tienes observaciones."
* carga: skeleton para timeline
* error: banner con reintento

Accesibilidad y SEO:

* A11y: landmarks; aria-labels en timeline; foco gestionado
* SEO: noindex
* Roles: main, list, status

Performance y Caching:

* Objetivo: LCP ≤2.2s
* Carga: lazy de tabs
* Cache: SWR por secciones
* Critical CSS: sí

Analítica:

* "abrir_detalle" | view | {id, estado} | /app/solicitudes/:id | tasa view→acción | ≥60%
* "responder_observacion" | submit | {id_obs} | idem | resolución | ≥80%

Dependencias:

* Servicios: API solicitudes, storage
* Seguridad: control de acceso por ownerId

Notas para handoff:

* Slugs tabs: ?tab=tracking|docs|observaciones

Para páginas CORE, añadir:

* Resumen rápido: Vista integral con estado, timeline y observaciones.
* Acciones principales: Reanudar edición; Responder observación; Descargar PDF.
* KPI/estado visible: Estado actual y fecha de última actualización.

---

9. Firma digital
   Ruta: /app/solicitudes/:id/firma
   Tipo: Página nueva
   Área: Solicitante
   Prioridad: Secundaria

Layout y Grid:

* Contenedor: 960; márgenes 24px; padding 24px
* Grid: 8 cols; gutters 24px
* Breakpoints: estándar
* Patrón: F; Orden: [Instrucciones → Botón firmar → Estado]

Navegación y Routing:

* Ubicación: secundaria
* Breadcrumb: Sí → Home > Mis solicitudes > Firma
* Variantes: callback /app/solicitudes/:id/firma/callback?status=ok|fail
* Guardas: auth; estado=lista_para_firma

Secciones (2–7):

* Instrucciones

- CTA primario: "Ir a firmar"
- Microcopy: "Serás redirigido al proveedor de firma. Regresa para ver el resultado."
- Secundarios: "Ver contrato" (/app/solicitudes/:id/contrato)
- Elementos: [texto], [link], [estado]

* Resultado

- CTA primario: "Ver comprobante"
- Microcopy: "Comprobante y sello de tiempo disponibles."
- Secundarios: "Intentar de nuevo" (#)
- Elementos: [alerta], [detalle]

Componentes clave (inventario por página):

* ExternalLinkButton | {href} | {enabled, disabled} | abre en nueva pestaña
* Alert | {type} | {success, error, info} | aria-live

Formularios y Validaciones (si aplica):

* —

Contenido mínimo:

* Texto de proceso, botones, resultado y comprobante
* Fuente: Legal/Backoffice
* i18n: app.request.sign.*

Estados UI:

* vacío: sin resultado
* carga: esperando callback
* error: proveedor rechaza; mostrar mensaje y soporte

Accesibilidad y SEO:

* A11y: foco retorna al contenido; role="status"
* SEO: noindex
* Roles: main, status

Performance y Caching:

* Objetivo: INP ≤150ms
* Carga: mínima
* Cache: no-store en callback
* Critical CSS: sí

Analítica:

* "firma_iniciada" | click | {id} | /app/solicitudes/:id/firma | tasa inicio | ≥90%
* "firma_resultado" | callback | {status} | /app/solicitudes/:id/firma/callback | éxito | ≥85%

Dependencias:

* Servicios: Proveedor de firma; storage de comprobantes
* Seguridad: validación de webhook/callback; verificación de integridad

Notas para handoff:

* Callback path documentado

---

10. Subsanación (Responder observaciones)
    Ruta: /app/solicitudes/:id/subsanacion
    Tipo: Sección dentro de Detalle de solicitud
    Área: Solicitante
    Prioridad: CORE

Layout y Grid:

* Contenedor: 960; márgenes 24px; padding 24px
* Grid: 8 cols; gutters 24px
* Breakpoints: estándar
* Patrón: F; Orden: [Observación → Respuesta → Adjuntos → Enviar]

Navegación y Routing:

* Ubicación: secundaria
* Breadcrumb: Sí → Home > Mis solicitudes > Detalle > Subsanación
* Variantes: ?obs=:obsId
* Guardas: auth; estado=observada

Secciones (2–7):

* Detalle de observación

- CTA primario: "Responder"
- Microcopy: "Aclara o corrige según lo solicitado por el analista."
- Secundarios: "Ver documento" (#)
- Elementos: [texto], [historial], [adjuntos]

* Envío de respuesta

- CTA primario: "Reenviar a evaluación"
- Microcopy: "Tu solicitud volverá a ‘En evaluación’."
- Secundarios: "Guardar borrador" (#)
- Elementos: [botón], [confirmación]

Componentes clave (inventario por página):

* ObservationView | {obs} | {pendiente, enviada} | muestra metadatos
* ReplyForm | {texto, archivos} | {valid, invalid} | límite de tamaño

Formularios y Validaciones (si aplica):

* Campos: [texto, "Respuesta", "Describe tu corrección", "Escribe al menos 20 caracteres", 1000, required], [archivos, "Adjuntos", "Opcional", "Archivo no permitido", —, optional]
* Reglas: minLength 20; tipos de archivo whitelist
* Mensajes: accionables

Contenido mínimo:

* Texto de observación, campos de respuesta, botones
* Fuente: Backoffice/Legal
* i18n: app.request.observations.*

Estados UI:

* vacío: sin observaciones
* carga: cargando obs
* error: envío fallido

Accesibilidad y SEO:

* A11y: role="form"; aria-live en confirmación
* SEO: noindex
* Roles: form, alert

Performance y Caching:

* Objetivo: INP ≤150ms
* Carga: ligera
* Cache: autosave local de respuesta
* Critical CSS: sí

Analítica:

* "subsanacion_enviada" | submit | {obsId} | /app/solicitudes/:id/subsanacion | aceptación | ≥85%

Dependencias:

* Servicios: API observaciones
* Seguridad: control de acceso; auditoría de cambios

Notas para handoff:

* —

Para páginas CORE, añadir:

* Resumen rápido: Flujo para atender observaciones y reenviar.
* Acciones principales: Escribir respuesta; Adjuntar evidencia; Reenviar a evaluación.
* KPI/estado visible: contador de observaciones pendientes.

---

11. Panel del analista (Bandeja)
    Ruta: /ops/solicitudes
    Tipo: Página nueva
    Área: Analista
    Prioridad: CORE

Layout y Grid:

* Contenedor: 1440; márgenes 24px; padding 24px
* Grid: 12 cols; gutters 24px; tabla full-width
* Breakpoints: estándar
* Patrón: F; Orden: [Filtros → Tabla → Acciones masivas]

Navegación y Routing:

* Ubicación: primaria
* Breadcrumb: Sí → Ops > Solicitudes
* Variantes: ?estado=&fecha=&monto=&sector=&riesgo=&q=
* Guardas: auth rol=analista

Secciones (2–7):

* Filtros y búsqueda

- CTA primario: "Aplicar filtros"
- Microcopy: "Filtra por estado, fecha, monto, sector o riesgo."
- Secundarios: "Limpiar" (#)
- Elementos: [selects], [date range], [search], [chips]
- Interacciones: teclado; atajos "/" para buscar

* Tabla de solicitudes

- CTA primario: "Abrir expediente"
- Microcopy: "Revisa detalles y gestiona el caso."
- Secundarios: "Exportar CSV" (/ops/solicitudes/export)
- Elementos: [tabla], [paginación], [acciones masivas]
- Datos: API; SLA listado <1s

Componentes clave (inventario por página):

* DataTable | {columns, rows} | {loading, empty} | columnas reordenables; aria-sort
* FilterBar | {filtros} | — | persistencia en URL
* MassActions | {selección} | {habilitado, deshabilitado} | confirmar antes de ejecutar

Formularios y Validaciones (si aplica):

* Filtros: validar rangos; estados permitidos
* Mensajes: inline

Contenido mínimo:

* Filtros, tabla con columnas: id, fecha, solicitante, RUC, monto, sector, riesgo, estado, acciones
* Fuente: Backoffice
* i18n: ops.inbox.*

Estados UI:

* vacío: "Sin resultados con estos filtros."
* carga: skeleton rows
* error: banner y reintento

Accesibilidad y SEO:

* A11y: tabla accesible; atajos documentados; foco visible
* SEO: noindex
* Roles: table, search, toolbar

Performance y Caching:

* Objetivo: TTFB ≤300ms, INP ≤150ms
* Carga: server-side pagination/sorting
* Cache: SWR lista; ETag
* Critical CSS: sí

Analítica:

* "ops_filter_apply" | click | {filtros} | /ops/solicitudes | latencia | <1s
* "ops_open_case" | row click | {id} | /ops/solicitudes | tasa apertura | ≥60%

Dependencias:

* Servicios: API solicitudes, export CSV
* Seguridad: RBAC; auditoría

Notas para handoff:

* Slug: /ops/solicitudes/export
* Nombres: table__col--riesgo

Para páginas CORE, añadir:

* Resumen rápido: Bandeja con filtros y acciones para analistas.
* Acciones principales: Filtrar bandeja; Abrir expediente; Exportar CSV.
* KPI/estado visible: Conteo por estado y SLA de atención.

---

12. Expediente del analista
    Ruta: /ops/solicitudes/:id
    Tipo: Página nueva
    Área: Analista
    Prioridad: CORE

Layout y Grid:

* Contenedor: 1440; márgenes 24px; padding 24px
* Grid: 12 cols; gutters 24px; layout 8/4
* Breakpoints: estándar
* Patrón: F; Orden: [Resumen → Datos → Documentos → Bitácora → Acciones]

Navegación y Routing:

* Ubicación: primaria
* Breadcrumb: Sí → Ops > Solicitudes > Expediente
* Variantes: ?tab=datos|docs|bitacora|kyc
* Guardas: auth rol=analista

Secciones (2–7):

* Resumen del caso

- CTA primario: "Cambiar estado"
- Microcopy: "Aprueba o rechaza con comentario."
- Secundarios: "Solicitar subsanación" (#), "Ver KYC/AML" (?tab=kyc)
- Elementos: [estado], [monto], [riesgo], [timeline]

* Datos y validaciones

- CTA primario: "Guardar comentario"
- Microcopy: "Registra hallazgos en la bitácora."
- Secundarios: "Ver documentos" (?tab=docs)
- Elementos: [tabs], [form notas]

* Acciones

- CTA primario: "Aprobar"
- Microcopy: "Confirma la decisión. Se notificará al solicitante."
- Secundarios: "Rechazar" (#)
- Elementos: [confirm dialog]

Componentes clave (inventario por página):

* CaseHeader | {estado, monto, solicitante} | {todas} | persistir cambios
* DecisionBar | {estadoActual} | {aprobar, rechazar, observar} | requiere comentario
* ActivityLog | {items} | {info, warn, error} | orden descendente

Formularios y Validaciones (si aplica):

* Campos: [comentario, "Comentario", "Motivo de la decisión", "Comentario requerido", 1000, required]
* Reglas: comentario obligatorio para aprobar/rechazar/observar
* Mensajes: claros

Contenido mínimo:

* Resumen, tabs, bitácora, acciones
* Fuente: Backoffice/Legal
* i18n: ops.case.*

Estados UI:

* vacío: sin bitácora: "Aún no hay notas."
* carga: skeleton en tabs
* error: toasts

Accesibilidad y SEO:

* A11y: roles en tabs (tablist, tab, tabpanel); dialog con focus trap
* SEO: noindex
* Roles: main, tablist, dialog

Performance y Caching:

* Objetivo: INP ≤150ms
* Carga: lazy por tab
* Cache: SWR por secciones
* Critical CSS: sí

Analítica:

* "ops_decision" | click | {accion, id} | /ops/solicitudes/:id | tasa decisión | ≥80%
* "ops_request_fix" | click | {id} | idem | % casos observados

Dependencias:

* Servicios: API decisiones, bitácora
* Seguridad: RBAC, auditoría de acciones

Notas para handoff:

* Nombres: dialog__decision, log__item

Para páginas CORE, añadir:

* Resumen rápido: Vista completa del expediente con decisiones y bitácora.
* Acciones principales: Aprobar; Rechazar; Solicitar subsanación.
* KPI/estado visible: Riesgo preliminar y estado actual.

---

13. KYC/AML y validaciones automáticas
    Ruta: /ops/solicitudes/:id/kyc
    Tipo: Sección dentro de Expediente
    Área: Analista
    Prioridad: Secundaria

Layout y Grid:

* Contenedor: 1440; márgenes 24px; padding 24px
* Grid: 12 cols; gutters 24px; cards 4/4/4
* Breakpoints: estándar
* Patrón: F; Orden: [Resultados → Detalles → Acciones]

Navegación y Routing:

* Ubicación: secundaria
* Breadcrumb: Sí → Ops > Solicitudes > KYC/AML
* Variantes: —
* Guardas: auth rol=analista

Secciones (2–7):

* Resultados

- CTA primario: "Actualizar resultados"
- Microcopy: "Consulta listas y vigencias en tiempo real."
- Secundarios: "Ver historial" (#)
- Elementos: [cards], [semáforo], [timestamp]
- Datos: API KYC/AML; caché

* Detalles de coincidencias

- CTA primario: "Escalar caso"
- Microcopy: "Si hay match positivo, bloquea envío o escala."
- Secundarios: "Descargar reporte" (#)
- Elementos: [tabla], [links]

Componentes clave (inventario por página):

* RiskCard | {tipo, resultado} | {ok, warning, match} | tooltips
* MatchesTable | {items} | {expandible} | accesible

Formularios y Validaciones (si aplica):

* —

Contenido mínimo:

* Cards (DNI, listas, domicilio, actividad), tabla de matches
* Fuente: Backoffice
* i18n: ops.kyc.*

Estados UI:

* vacío: "Aún no hay resultados."
* carga: spinners en cards
* error: banner

Accesibilidad y SEO:

* A11y: aria-live para actualizaciones
* SEO: noindex
* Roles: main, status

Performance y Caching:

* Objetivo: INP ≤150ms
* Carga: cargar por bloques
* Cache: ETag, SWR
* Critical CSS: sí

Analítica:

* "kyc_refresh" | click | {seccion} | /ops/solicitudes/:id/kyc | latencia | ≤2s
* "kyc_escalate" | click | {motivo} | idem | ratio escalamiento | ≤10%

Dependencias:

* Servicios: Proveedores KYC/AML, validación RENIEC/SUNAT
* Seguridad: enmascarar datos sensibles; auditoría

Notas para handoff:

* —

---
</INPUT>
