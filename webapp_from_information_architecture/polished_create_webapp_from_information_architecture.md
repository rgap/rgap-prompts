A partir del contexto definido dentro de [contexto], crea un prototipo UI siguiendo EXACTAMENTE la arquitectura de información definida dentro de [arquitectura].

## CONTEXTO:

[contexto]

Aquí pega el contexto de la webapp, negocio, usuario, problema o caso de estudio.

Ejemplo: Catálogo de productos sin compra con registro, login y guardar a favoritos; Ecommerce de cotizaciones por whatsapp; precios en soles

[/contexto]

## REGLAS OBLIGATORIAS:

1. El prototipo debe representar visualmente el contexto definido en [contexto].

2. Respeta EXACTAMENTE:
   - la jerarquía
   - el orden
   - los niveles
     definidos en [arquitectura].

3. REGLA DE INTERPRETACIÓN:

La arquitectura es un contrato estructural estricto.
La creatividad debe aplicarse como “capa visual” sobre esa estructura.

Antes de generar el prototipo, valida mentalmente que:

- cada página existe solo si está definida
- cada sección existe solo si está definida

## REGLAS DE CREATIVIDAD PERMITIDA:

Usa una estética de fondo claro (light mode).

Haz el diseño visualmente atractivo, moderno y creativo.

Puedes usar:

- animaciones
- microinteracciones
- transiciones
- gradientes suaves
- sombras
- tarjetas modernas
- efectos hover
- composición visual creativa
- tipografía moderna
- detalles visuales premium

Revisa y ajusta el contraste entre texto y fondo de cada elemento.

PERO sin romper la estructura definida en [arquitectura].

## ARQUITECTURA:

[arquitectura]

Aquí pega la arquitectura de la información.

Ejemplo:

```text
Página: Inicio
	Sección:Header
		Logo
		Menú principal
			Link: Catálogo -> Página: Catálogo
			Link: Cosas guardadas -> Página: Cosas guardadas
			Link: Ayuda
		Link icon: Iniciar sesión -> Página: Login
		Link icon: Registrarse -> Página: Registro

	Sección: Categorías
	Sección: Slider animado de productos
	Sección: Consulta por WhatsApp
		Botón: Preguntar por WhatsApp
	Sección: Footer

Página: Catálogo
	Sección:Header
		Logo
		Menú principal
			Link: Catálogo -> Página: Catálogo
			Link: Cosas guardadas -> Página: Cosas guardadas
			Link: Ayuda
		Link icon: Iniciar sesión -> Página: Login
		Link icon: Registrarse -> Página: Registro

	Sección: Filtros
		Input sin label con placeholder: Buscar en catálogo

	Sección: Catálogo
		Tarjeta de producto
			Imagen de producto
			Nombre de producto
			Precio
			Enlace: Ver detalle -> Modal: Detalle de produto

	Sección: Footer

Modal: Detalle de producto
    Link icon: Cerrar modal
	Imagen de producto
	Nombre de producto
	Precio
	Descripción
	Características
	Botón: Guardar en cosas guardadas
	Botón: Cotizar por WhatsApp

Página: Cosas guardadas
	Sección: Header
		Logo
		Menú principal
			Link: Catálogo -> Página: Catálogo
			Link: Cosas guardadas -> Página: Cosas guardadas
			Link: Ayuda
		Link icon: Iniciar sesión -> Página: Login
		Link icon: Registrarse -> Página: Registro

	Sección: Lista de cosas guardadas
		Tarjeta de producto favorito
			Imagen de producto
			Nombre de producto
			Precio referencial
			Botón: Ver detalle
			Botón: Quitar de cosas guardadas
			Botón: Cotizar por WhatsApp

	Sección: Footer

Página: Login
	Sección: Header
		Logo
		Menú principal
			Link: Catálogo -> Página: Catálogo
			Link: Cosas guardadas -> Página: Cosas guardadas
			Link: Ayuda
        Link icon: Iniciar sesión -> Página: Login
		Link icon: Registrarse -> Página: Registro

	Sección: Formulario de login
		Input: Correo electrónico
		Input: Contraseña
		Botón: Iniciar sesión

	Sección: Footer

Página: Registro
	Sección: Header
		Logo
		Menú principal
			Link: Catálogo -> Página: Catálogo
			Link: Cosas guardadas -> Página: Cosas guardadas
			Link: Ayuda
		Link icon: Iniciar sesión -> Página: Login
		Link icon: Registrarse -> Página: Registro

	Sección: Formulario de registro
		Input: Nombre
		Input: Correo electrónico
		Input: Contraseña
		Button: Crear cuenta

	Sección: Footer
```

[/arquitectura]
