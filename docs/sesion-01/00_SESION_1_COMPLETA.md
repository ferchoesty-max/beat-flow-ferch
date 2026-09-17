# BeatFlow — Sesión 1 completa

[📘 Sesión 1](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_RECURSOS_Y_LINKS.md)

---

---

## UI/UX, estructura y layout responsive

**Duración:** 1 hora 30 minutos  
**Versión objetivo:** `v0.1.0`

## Objetivo

Construir la primera versión visual de BeatFlow utilizando:

- HTML5
- TailwindCSS mediante CDN
- CSS separado
- JavaScript ES Modules
- Datos mock
- Git

En esta sesión **no se conecta ninguna API**, **no se reproduce audio real** y **no se utiliza LocalStorage**.

## Resultado esperado

- Sidebar desktop
- Header
- Buscador visual
- Hero
- Tendencias
- Cards musicales
- Recently Played
- Player visual fijo
- Navegación móvil
- Layout responsive

## Estructura final

```text
beatflow/
├── README.md
├── index.html
├── .gitignore
├── css/
│   ├── theme.css
│   └── styles.css
├── js/
│   ├── app.js
│   ├── data/
│   │   └── mock.data.js
│   └── ui/
│       └── home.ui.js
└── docs/
    └── sesion-01/
```

## Orden práctico

```text
01  00_SESION_1_COMPLETA.md
02  01_RECURSOS_Y_LINKS.md
03  02_ESTRUCTURA_PROYECTO.md
04  09_GITIGNORE.md
05  03_INDEX_HTML.md
06  04_THEME_CSS.md
07  05_STYLES_CSS.md
08  06_MOCK_DATA_JS.md
09  07_HOME_UI_JS.md
10  08_APP_JS.md
11  10_README.md
12  12_VALIDACION_SESION_1.md
```

`11_PASOS_CLASE.md` se utiliza en paralelo como guía docente.

## Flujo de trabajo

```text
mock.data.js
      ↓
    app.js
      ↓
 home.ui.js
      ↓
renderHome()
      ↓
     DOM
```

## Rama sugerida

```bash
git checkout -b feature/session-01-ui
```

## Commits sugeridos

```bash
git add .
git commit -m "chore: create BeatFlow project structure"
```

```bash
git add .
git commit -m "feat: create BeatFlow base layout"
```

```bash
git add .
git commit -m "style: add BeatFlow theme and global styles"
```

```bash
git add .
git commit -m "feat: add mock music data"
```

```bash
git add .
git commit -m "feat: render trending tracks"
```

```bash
git add .
git commit -m "feat: add mobile navigation"
```

## Tag de versión

```bash
git checkout main
git merge feature/session-01-ui
git tag -a v0.1.0 -m "BeatFlow session 1"
```

## Checklist

- [ ] UI responsive
- [ ] Tailwind funcionando
- [ ] CSS separado
- [ ] Datos mock
- [ ] ES Modules
- [ ] Sin errores de consola
- [ ] Git limpio
- [ ] Tag `v0.1.0`

---

---

## Navegación

[📘 Sesión 1](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_RECURSOS_Y_LINKS.md)
