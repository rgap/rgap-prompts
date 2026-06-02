# Objetivo

Revisa automáticamente los cambios actuales del repositorio y genera un mensaje de commit largo usando Conventional Commits.

# Comandos a usar

Usa estos comandos para analizar los cambios:

- git status
- git diff --cached
- git diff
- git diff --stat

# Reglas

- Si hay cambios staged, prioriza esos cambios.
- Si no hay cambios staged, analiza los cambios no staged.
- No inventes cambios.
- No repitas solo nombres de archivos.
- Explica qué cambió de forma clara.
- Incluye los archivos principales modificados o creados.
- No ejecutes git commit.

# Formato obligatorio del mensaje

Genera el mensaje usando este formato:

type: short summary in Spanish

**Resumen**

Explica brevemente en español el propósito general del cambio.

**Archivos cambiados**

- `archivo1`: qué se agregó, modificó o eliminó.
- `archivo2`: qué se agregó, modificó o eliminó.

# Salida

- La salida debe estar en formato Markdown.
- Muestra el mensaje final dentro de un bloque de código text.
- Devuelve solo el mensaje de commit final.
- No incluyas explicaciones adicionales.
- No uses títulos Markdown con # dentro del mensaje final.

# Portapapeles

Después de generar el mensaje, cópialo automáticamente al portapapeles.

Copia solo el contenido del mensaje de commit, sin los backticks de Markdown.

Usa el comando adecuado según el sistema operativo:

- macOS: pbcopy
- Windows PowerShell: Set-Clipboard
- Linux: xclip, xsel o wl-copy si está disponible