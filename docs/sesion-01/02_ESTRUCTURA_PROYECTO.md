# BeatFlow — Estructura del proyecto

[📘 Sesión 1](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./01_RECURSOS_Y_LINKS.md) · [Siguiente ▶](./09_GITIGNORE.md)

---

---

## Estructura

```text
beatflow/
├── index.html
├── css/
│   ├── theme.css
│   └── styles.css
├── js/
│   ├── app.js
│   ├── data/
│   │   └── mock.data.js
│   └── ui/
│       └── home.ui.js
├── README.md
└── .gitignore
```

## macOS / Linux

```bash
mkdir -p beatflow/css beatflow/js/data beatflow/js/ui
cd beatflow

touch index.html
touch css/theme.css
touch css/styles.css
touch js/app.js
touch js/data/mock.data.js
touch js/ui/home.ui.js
touch README.md
touch .gitignore
```

## Windows PowerShell

```powershell
mkdir beatflow
cd beatflow
mkdir css
mkdir js
mkdir js\data
mkdir js\ui

New-Item index.html
New-Item css\theme.css
New-Item css\styles.css
New-Item js\app.js
New-Item js\data\mock.data.js
New-Item js\ui\home.ui.js
New-Item README.md
New-Item .gitignore
```

## Git

```bash
git init
git checkout -b main
git checkout -b feature/session-01-ui
```

```bash
git add .
git commit -m "chore: create BeatFlow project structure"
```

---

---

## Navegación

[📘 Sesión 1](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./01_RECURSOS_Y_LINKS.md) · [Siguiente ▶](./09_GITIGNORE.md)
