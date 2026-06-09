Según el issue descrito en [ISSUE.md](ISSUE.md), crea proyectos progresivos a partir del proyecto en estado inicial [00_initial_state](00_initial_state/) hasta cumplir con el issue.

## Requisitos de los proyectos progresivos

- Los proyectos progresivos deben empezar desde `01_`.
- Cada proyecto progresivo debe tener un archivo `COMMIT.md`.
- Cada archivo `COMMIT.md` debe usar la estructura indicada en `[estructura_commit]`.
- Siempre deja espacio entre título, subtítulo o sección y el contenido.
- No uses referencias a archivos con formato `[...](...)`.

## Verificación del issue

Luego verifica que el último proyecto progresivo resuelve completamente el issue descrito en [ISSUE.md](ISSUE.md).

## Proyecto final

Luego crea un proyecto llamado `_issue_project`.

Este proyecto debe tener commiteado en la rama `main` todo el avance desde `00_initial_state` hasta el último proyecto progresivo.

Los commit messages deben obtenerse a partir de cada archivo `COMMIT.md`.

## Estructura de COMMIT.md

[estructura_commit]

feat: ...

# ...

## Descripción

...

## Archivos modificados

| Archivo | Cambio |
| ------- | ------ |
...

## Archivos agregados

...

## Por qué se hace

...

## Dónde se usa lo que se cambió

...

## Validación

...

[/estructura_commit]

## Archivo final

Finalmente, crea un archivo llamado `SOLVED.md`.

Este archivo debe contener una explicación de por qué el último proyecto progresivo resuelve completamente el issue.
