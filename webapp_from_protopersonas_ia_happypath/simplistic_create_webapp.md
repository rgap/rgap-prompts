A partir del contexto definido dentro de [contexto], crea un prototipo UI siguiendo EXACTAMENTE la arquitectura de información definida dentro de [arquitectura], y alineado con la protopersona descrita dentro de en [protopersona] para completar el taskflow dentro de en [taskflow].

## CONTEXTO, PROTOPERSONA Y TASKFLOW:

[contexto]

Aquí pega el contexto de la webapp, negocio, usuario, problema o caso de estudio.

Ejemplo: Catálogo de productos sin compra con registro, login y guardar a favoritos; Ecommerce de cotizaciones por whatsapp; precios en soles

[/contexto]

[protopersona]

Aquí pega la descripción de la protopersona.

Ejemplo:

```text
Nombre y apellido: Miguel O'hara
Rol / tipo de usuario: Compradora online
Descripción del rol: Persona que busca, compara y compra accesorios de viaje desde la tienda virtual.
Puntos de dolor: No sabe si el producto es resistente, tiene dudas sobre tamaños, tiempos de entrega y calidad real del accesorio.
Necesidades: Ver productos claros, fotos, precios, características, reseñas, stock disponible y opciones de pago confiables.
```

[/protopersona]

[taskflow]

Aquí pega la descripción del taskflow.

Ejemplo:

```text
Taskflow 1: Consulta de producto específico vía WhatsApp

Rol / tipo de usuario: Cliente potencial

Objetivo del usuario dentro del sistema: Encontrar un producto desde la página principal, guardarlo en cosas guardadas y cotizarlo por WhatsApp

Entra a página de inicio
Hace clic en el link Catálogo
Mira la página de catálogo
Mira la tarjeta del primer producto
Hace clic en ver detalle
Mira el modal de detalle de producto
Hace clic en el botón guardar en cosas guardadas
Mira una animación de "Fué guardado en cosas guardadas"
Mira como se cierra el modal automáticamente
Mira la página de catálogo
Hace clic en la página de cosas guardadas
Mira la tarjeta del primer producto guardado
Hace clic en el botón cotizar por WhatsApp
Finaliza la cotización por WhatsApp
```

[/taskflow]

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

4. ALINEACIÓN CON EL USUARIO Y FLUJO:

El diseño debe priorizar la facilidad de uso y la eficiencia para la protopersona definida en [protopersona], facilitando la compleción del [taskflow]. Los elementos visuales y de interacción deben guiar al usuario a través del flujo sin fricción.

## REGLAS DE CREATIVIDAD PERMITIDA:

Usa una estética de fondo claro (light mode).

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
