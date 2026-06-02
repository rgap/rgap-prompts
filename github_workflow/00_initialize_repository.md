# Comandos para configurar el repositorio del equipo

Guia rapida con los comandos usados para crear, publicar y dejar configurado un repositorio colaborativo en GitHub.

## 1. Variables, repositorio local y publicacion inicial

Define el propietario, el nombre del repositorio y las ramas principales. Luego inicializa Git, crea el primer commit, publica el repositorio en GitHub y abre la vista web.

```sh
export OWNER="kravizt"
export REPO="my-team-webapp"
export MAIN_BRANCH="main"
export DEV_BRANCH="development"

git init -b "$MAIN_BRANCH"

git add -A
git commit -m "chore: commit inicial"

gh repo create "$OWNER/$REPO" \
  --public \
  --description "Team repository" \
  --source=. \
  --remote=origin \
  --push

git push -u origin "$MAIN_BRANCH"

git switch -c "$DEV_BRANCH"
git push -u origin "$DEV_BRANCH"

git switch "$MAIN_BRANCH"

gh repo view --web
```

## 2. Configuracion general del repositorio

Aplica las opciones recomendadas: issues y projects activos, wiki desactivada, squash merge como estrategia principal y limpieza automatica de ramas al cerrar Pull Requests.

```sh
gh repo edit "$OWNER/$REPO" \
  --enable-issues=true \
  --enable-projects=true \
  --enable-wiki=false \
  --enable-squash-merge=true \
  --squash-merge-commit-message pr-title-description \
  --enable-merge-commit=false \
  --enable-rebase-merge=false \
  --delete-branch-on-merge=true \
  --allow-update-branch=true \
  --enable-auto-merge=false
```

## 3. Etiquetas del proyecto

Elimina etiquetas por defecto que no se van a usar y crea etiquetas basicas para clasificar trabajo de frontend, backend y errores.

```sh
gh label delete "duplicate" --yes
gh label delete "good first issue" --yes
gh label delete "help wanted" --yes
gh label delete "invalid" --yes
gh label delete "question" --yes
gh label delete "wontfix" --yes
gh label delete "enhancement" --yes
gh label delete "documentation" --yes

gh label create "frontend" \
  --color "1d76db" \
  --description "UI, pages, components, styles" \
  --force

gh label create "backend" \
  --color "0e8a16" \
  --description "API, server, database logic" \
  --force

gh label create "bug" \
  --color "d73a4a" \
  --description "Something is broken" \
  --force
```

## 4. Plantilla para Pull Requests

Crea una plantilla para que cada Pull Request explique el cambio, indique el tipo de trabajo realizado y deje claro como fue probado.

```sh
mkdir -p .github

cat > .github/PULL_REQUEST_TEMPLATE.md <<'EOF'
## ¿Qué se cambió?

Explica brevemente el cambio realizado.

## Tipo de trabajo

- [ ] Corrección de error
- [ ] Nueva funcionalidad
- [ ] Documentación
- [ ] Frontend
- [ ] Backend

## ¿Cómo se probó?

Explica cómo verificaste que funciona.

## Checklist

- [ ] Probé mis cambios localmente.
- [ ] El código es fácil de entender.
- [ ] Actualicé la documentación si era necesario.
- [ ] El Pull Request es pequeño y fácil de revisar.
EOF
```

## 5. Proteccion de ramas principales

Configura reglas de proteccion para `main` y `development`, exigiendo al menos una aprobacion antes de integrar cambios.

```sh
for BRANCH in "$MAIN_BRANCH" "$DEV_BRANCH"; do
  gh api \
    -X PUT "repos/$OWNER/$REPO/branches/$BRANCH/protection" \
    --input - <<EOF
{
  "required_status_checks": null,
  "enforce_admins": false,
  "required_pull_request_reviews": {
    "required_approving_review_count": 1
  },
  "restrictions": null,
  "allow_deletions": false
}
EOF
done
```
