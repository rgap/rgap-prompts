Revisa automáticamente los commits no pusheados de la rama actual.

Usa estos comandos:

git branch --show-current
git status
git log --oneline @{u}..HEAD
git log --format=fuller @{u}..HEAD
git log --stat @{u}..HEAD
git show --stat --oneline --summary HEAD

Genera un comando para crear un Pull Request con GitHub CLI.

Reglas:
- Usa solo los commits no pusheados.
- Considera el mensaje completo de cada commit no pusheado.
- Analiza tanto el título como el cuerpo del commit, si existe.
- No inventes cambios.
- El title debe estar en español.
- El title debe seguir Conventional Commits.
- El title debe ser breve y claro.
- El body debe estar en español.
- El body debe usar formato Markdown.
- El body debe usar emojis de forma moderada.
- El body debe usar títulos en negrita con **.
- El body debe explicar el propósito general del cambio.
- El body debe listar los archivos principales cambiados.
- El body debe explicar qué se agregó, modificó o eliminó en cada archivo.
- No incluyas una sección de pruebas.
- No ejecutes el Pull Request.
- No uses --body.
- Usa --body-file - con heredoc.
- El body debe mostrarse con saltos de línea reales, no con \n escapados.
- No uses backticks dentro del comando final.
- Retorna únicamente el comando final.

El body debe seguir este formato:

**🧾 Resumen**

Explica brevemente en español el propósito general del cambio.

**📁 Archivos cambiados**

- archivo1: qué se agregó, modificó o eliminó.
- archivo2: qué se agregó, modificó o eliminó.

Formato obligatorio de salida:

gh pr create \
  --base development \
  --head "$(git branch --show-current)" \
  --title "feat: short description of the change" \
  --body-file - <<'EOF'
**🧾 Resumen**

Describe el propósito general del cambio.

**📁 Archivos cambiados**

- archivo1: describe qué cambió.
- archivo2: describe qué cambió.
EOF