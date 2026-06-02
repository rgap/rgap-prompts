A partir del contexto de la webapp definido dentro de [contexto], genera taskflows en texto.

## Usa EXACTAMENTE este formato:

```text
Taskflow [número]: [Nombre del flujo]

Rol / tipo de usuario: [Rol o tipo de usuario que realiza el flujo]

Objetivo del usuario dentro del sistema: [Objetivo concreto del usuario]

[Paso 1]
[Paso 2]
[Paso 3]
[Paso 4]
...
```

## REGLAS OBLIGATORIAS:

1. Cada taskflow debe indicar claramente el Rol / tipo de usuario que realiza el flujo.

2. El rol / tipo de usuario debe representar a una persona que interactúa directamente con la webapp.

3. Cada paso debe empezar con un verbo de acción en tercera persona singular del presente indicativo.
   El sujeto implícito es “el usuario”.

   Ejemplos:
   - Entra
   - Hace clic
   - Mira
   - Selecciona
   - Escribe
   - Revisa
   - Confirma
   - Completa
   - Regresa
   - Finaliza

4. No escribas los pasos en infinitivo.
   Incorrecto:
   - Entrar al Home
   - Hacer clic en “Comprar”
   - Seleccionar producto

   Correcto:
   - Entra al Home
   - Hace clic en “Comprar”
   - Selecciona producto

5. No uses viñetas, números ni tablas dentro del taskflow.

6. No expliques el taskflow. Solo genera los taskflows.

7. Mantén los pasos simples, claros y secuenciales.

8. Cada taskflow debe representar un camino completo del usuario dentro de la webapp.

9. Usa nombres de pantallas, botones, secciones y acciones que existan en el contexto.

10. No inventes funcionalidades que no estén mencionadas en el contexto.

11. Si hay varios usuarios principales, genera taskflows para cada rol / tipo de usuario relevante.

12. Si hay varios objetivos importantes, genera varios taskflows:

- Happy path principal
- Búsqueda o exploración
- Registro o inicio de sesión, si aplica
- Compra, reserva, envío o acción principal, si aplica
- Flujo alternativo relevante, si aplica

## CONTEXTO:

[contexto]
Pega aquí el contexto de la webapp:

- tipo de webapp
- usuarios principales
- páginas o pantallas
- funcionalidades principales
- objetivo del sistema
- acciones que puede realizar el usuario

Ejemplo: Catálogo de productos sin compra (Estático) (Static Product Catalog / Showcase) - Ecommerce de cotizaciones por whatsapp
[/contexto]
