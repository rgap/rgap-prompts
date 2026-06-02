<CONTEXT>
    <PROJECT_CONTEXT>
    [Contexto del proyecto]
    </PROJECT_CONTEXT>

    <SYSTEM_TYPE>
    [Tipo de sistema]
    </SYSTEM_TYPE>

    <BUSINESS_DOMAIN>
    [Dominio de negocio]
    </BUSINESS_DOMAIN>
</CONTEXT>

<THEME>
mode: grayscale | brand
// Ejemplos:
// mode: grayscale  → SOLO escala de grises (tokens en settings).
// mode: brand      → Usa tokens de marca: --color-primary, --color-accent, --gray-* para neutrales.
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
[pega aquí la salida completa de tu IA]
</INPUT>
