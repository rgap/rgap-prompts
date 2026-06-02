<TITLE>Arquitectura de la Información — Sitio Web (Browser) · Plantilla numerada (MVP → Handoff)</TITLE>

<ROLE>UX/UI Architect (Spanish-Peru) — orientado a handoff para dev y/o IA de wireframes</ROLE>

<CONTEXT>
Generar IA completa para un sitio web (browser). Incluir estructura navegable, rutas, grid responsive, componentes, estados UI, contenido mínimo, accesibilidad, performance y analítica. Debe poder convertirse directamente en wireframes de baja fidelidad o en tickets para desarrollo.
PROJECT_CONTEXT: [...]
SYSTEM_TYPE: [...]
BUSINESS_DOMAIN: [...]
</CONTEXT>

<TARGET>browser</TARGET>

<INPUT>[pega aquí tus funcionalidades y casos de uso]</INPUT>

<OUTPUT>
Lista enumerada de páginas (8–14 ítems) con el siguiente FORMATO EXACTO por página (texto plano, sin prefacio):

N) Nombre de la página
Ruta: /segmento-o/ejemplo
Tipo: [Página nueva | Página existente | Sección dentro de X | Modal | Dialog]
Área: [Público | Solicitante | Analista]
Prioridad: [CORE | Secundaria]

Layout y Grid:
- Contenedor: [ancho máx: 1280/1440], márgenes [px], padding [px]
- Grid: 12 cols desktop | 6 tablet | 4 móvil; gutters [px]
- Breakpoints: móvil ≤640, tablet 641–1024, desktop ≥1025
- Patrón de escaneo: [F|Z]; Orden de bloques: [lista en orden]

Navegación y Routing:
- Ubicación en menú: [primaria|secundaria|oculta]
- Breadcrumb: [Sí/No] → [Home > …]
- Variantes de ruta (si aplica): [/ruta/:id, query params]
- Redirecciones/guardas (auth/rol): [reglas]

Secciones (2–7):
- [Nombre de sección]
* CTA primario: "≤24 chars"
* Microcopy: "≤120 chars, claro y accionable"
* Secundarios: "≤24 chars" (/destino), "≤24 chars" (/destino)
* Elementos (3–6): [componente ≤3 palabras], [componente], [componente]
* Datos mostrados (si aplica): [campos], [origen (API/caché/local)]
* Interacciones: [hover|focus|active|disabled|teclado], feedback inline, atajos (si hay)
- [Siguiente sección]

Componentes clave (inventario por página):
- Nombre | Props obligatorias | Variantes/estados | Reglas de uso
- Ej: CardSolicitud | {estado, fecha, monto} | {borrador, evaluacion, observada} | clickable, no overflow

Formularios y Validaciones (si aplica):
- Campos: [id, label, helper, error, maxLen, required]
- Reglas: [regex, máscaras, dependencias entre campos]
- Mensajes de error: [claros, accionables, ≤120 chars]
- Estados: pristine, dirty, valid, invalid, submitLoading

Contenido mínimo:
- Lista de contenidos obligatorios por sección (copy, imágenes, íconos, tablas)
- Fuente: [UX/Marketing/Legal/Backoffice]
- i18n: [ES-PE por defecto; claves sugeridas]

Estados UI (por página y/o sección):
- vacío: [mensaje/acción]
- carga: [indicador; skeleton vs spinner]
- error: [mensaje, reintento, soporte]

Accesibilidad (A11y) y SEO:
- A11y: H1 único; labels asociadas; orden de tab lógico; contraste AA; foco visible
- SEO (público): title (≤60), meta description (≤160), canonical, OG básicos
- Roles/aria para componentes críticos (nav, main, dialog, alerts)

Performance y Caching:
- SLI/objetivo: TTFB ≤300ms, LCP ≤2.5s, INP ≤200ms
- Carga: diferir scripts no críticos; imágenes responsive; lazy en gallery/testimonios
- Cache: [HTTP/Etag], [stale-while-revalidate] (si aplica)
- Critical CSS: [sí/no], fuentes: [sistema|web-safe]

Analítica y Eventos (por página):
- Evento | Trigger | Props | Ubicación | Métrica | Umbral
- Ej: "solicitud_enviada" | click CTA Enviar | {monto, sector} | /app/solicitudes/:id | tasa éxito | ≥85%

Dependencias:
- Servicios/terceros: [auth, firma, KYC/AML, SMTP, storage]
- Datos: [APIs, catálogos], errores conocidos
- Seguridad: [CSRF, XSS, rate limiting], política de contraseñas (si aplica)

Notas para handoff:
- Nombre de rutas/tokens (slug recomendados)
- Convenciones de nombre (BEM/utility), z-index para overlays
- Estados de overlays: modal/dialog/sheet (foco atrapado, escape)

Para páginas CORE, añadir:
- Resumen rápido (≤120 chars)
- Acciones principales (3 bullets, verbo+objeto)
- KPI/estado visible (si aplica)
</OUTPUT>

<STEPS>
- Derivar páginas desde UCs/funcionalidades; nombrar con lenguaje simple (acción + objeto)
- Definir Layout y Grid por página (contenedor, columnas, breakpoints, orden de bloques)
- Especificar Secciones con CTAs/microcopy/elementos/datos/interacciones
- Inventariar Componentes con props/variantes/reglas; detallar formularios/validaciones
- Completar Estados UI, Contenido mínimo, A11y/SEO, Performance/Cache y Analítica
- Declarar Dependencias y Notas de handoff
</STEPS>

<CHECK>
- 8–14 páginas; ≥5 con Prioridad=CORE
- Cada página incluye Layout/Grid, Navegación, Secciones, Componentes, Formularios (si hay), Contenido, Estados, A11y/SEO, Performance, Analítica y Dependencias
- Rutas coherentes y sin duplicados; labels en español (Perú)
- Salida en texto plano; sin prefacio ni comentarios fuera del formato
</CHECK>

<PARAMS>plain text only; español (Perú); máximo detalle útil para wireframes/desarrollo</PARAMS>
