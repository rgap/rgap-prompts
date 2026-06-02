# Objetivo

Revisa automáticamente los commits no pusheados del repositorio y genera un nombre de rama en español basado en esos commits.

# Comandos a usar

Usa estos comandos para analizar los commits que existen en la rama local pero todavía no están en el upstream remoto:

- git status -sb
- git log --oneline @{u}..HEAD
- git log --stat @{u}..HEAD
- git diff --stat @{u}..HEAD
- git diff @{u}..HEAD

# Reglas

- Analiza todos los commits no pusheados, no solo el último commit.
- Usa `@{u}..HEAD` para detectar los commits locales que todavía no fueron pusheados.
- Si hay varios commits no pusheados, genera un nombre de rama que resuma el cambio principal en conjunto.
- No inventes cambios.
- No uses cambios staged o no staged para decidir el nombre de la rama, excepto si no existen commits no pusheados.
- Si no existen commits no pusheados, entonces analiza los cambios actuales con:
  - git status
  - git diff --cached
  - git diff
  - git diff --stat
- No ejecutes `git switch`.
- Usa formato kebab-case.
- Usa un tipo compatible con Conventional Commits.
- El nombre de la rama en español

# Tipos permitidos

- feat
- fix
- docs
- style
- refactor
- test
- chore
- ci

# Formato obligatorio

Devuelve solo este comando:

git switch -c tipo/name-of-change

# Ejemplo

git switch -c docs/add-github-pr-guide