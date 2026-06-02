A partir del contexto definido dentro de [contexto], genera una arquitectura de la información para una webapp.

## Usa EXACTAMENTE este formato:

```text
Páginas:
	Página: [Nombre de página]
		[Sección o componente principal]
			[Subcomponente]
				[Elemento]
		[Sección o componente principal]
		Footer

	Página: [Nombre de página]
		[Sección o componente principal]
			[Subcomponente]
				[Elemento]
		Footer
```

## REGLAS OBLIGATORIAS:

1. La arquitectura debe salir en forma de árbol indentado usando tabs.

2. El primer nivel siempre debe ser:
   Páginas:

3. El segundo nivel siempre debe ser:
   Página: [Nombre de página]

4. Dentro de cada página, organiza los elementos por jerarquía:

- Página
- Secciones principales
- Componentes
- Subcomponentes
- Elementos finales

5. Si existe navegación entre páginas, escribe los enlaces así:
   Enlace: [Nombre visible] -> Página: [Nombre de página destino]

6. No escribas explicaciones antes ni después.

7. No uses viñetas, números, emojis ni párrafos descriptivos dentro de la arquitectura.

8. No inventes páginas innecesarias. Solo crea las páginas que tengan sentido según el contexto.

9. No inventes demasiados componentes. La arquitectura debe ser clara, ordenada y útil para luego crear un prototipo UI.

10. Mantén nombres simples y consistentes.

11. Si una página tiene Header, incluye dentro de Header los elementos principales de navegación si corresponden.

12. Si hay productos, servicios, usuarios, formularios, reportes o configuraciones, represéntalos como secciones o componentes según su importancia.

13. Usa esta arquitectura como una estructura funcional, no como un diseño visual.

## CONTEXTO:

[contexto]
Escribe aquí el contexto de la webapp, el negocio, los usuarios, objetivos y funcionalidades principales.

Ejemplo: Catálogo de productos sin compra (Estático) (Static Product Catalog / Showcase) - Ecommerce de cotizaciones por whatsapp
[/contexto]
