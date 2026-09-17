# BeatFlow — Sesión 1

## UI/UX, estructura y layout responsive

**Duración:** 1 hora 30 minutos  
**Versión objetivo:** `v0.1.0`

[⬅ Regresar a documentación](../README.md) · [🏠 BeatFlow](../../README.md)

---

## Índice

- [Objetivo](#objetivo)
- [Resultado esperado](#resultado-esperado)
- [Orden de trabajo](#orden-de-trabajo)
- [Documentos de la sesión](#documentos-de-la-sesión)
- [Arquitectura de la sesión](#arquitectura-de-la-sesión)
- [Flujo de trabajo](#flujo-de-trabajo)
- [Rama Git](#rama-git)
- [Commits](#commits)
- [Validación](#validación)
- [Cierre](#cierre)

---

## Objetivo

Construir la primera versión visual de BeatFlow utilizando:

- HTML5;
- TailwindCSS mediante CDN;
- CSS;
- JavaScript ES Modules;
- datos mock;
- Git.

Durante esta sesión:

```text
NO API
NO AUDIO REAL
NO LOCALSTORAGE
```

El objetivo es construir una base sólida que posteriormente pueda evolucionar sin rehacer la aplicación.

[⬆ Regresar al índice](#índice)

---

## Resultado esperado

Al terminar debe existir:

- Sidebar responsive;
- Header;
- buscador visual;
- Hero principal;
- tendencias;
- cards musicales;
- Recently Played;
- player visual;
- navegación móvil;
- layout responsive;
- JavaScript modular;
- datos mock.

Resultado:

```text
BeatFlow v0.1.0
```

[⬆ Regresar al índice](#índice)

---

## Orden de trabajo

Aunque los documentos están numerados, el orden práctico recomendado es:

```text
01  00_SESION_1_COMPLETA.md
        ↓
02  01_RECURSOS_Y_LINKS.md
        ↓
03  02_ESTRUCTURA_PROYECTO.md
        ↓
04  09_GITIGNORE.md
        ↓
05  03_INDEX_HTML.md
        ↓
06  04_THEME_CSS.md
        ↓
07  05_STYLES_CSS.md
        ↓
08  06_MOCK_DATA_JS.md
        ↓
09  07_HOME_UI_JS.md
        ↓
10  08_APP_JS.md
        ↓
11  10_README.md
        ↓
12  12_VALIDACION_SESION_1.md
```

El documento:

```text
11_PASOS_CLASE.md
```

puede utilizarse en paralelo como guía docente.

[⬆ Regresar al índice](#índice)

---

## Documentos de la sesión

### 1. Planeación completa

[📄 00_SESION_1_COMPLETA.md](./00_SESION_1_COMPLETA.md)

Contiene:

- objetivo;
- duración;
- alcance;
- arquitectura;
- distribución de tiempo;
- Git;
- checklist.

---

### 2. Recursos

[📄 01_RECURSOS_Y_LINKS.md](./01_RECURSOS_Y_LINKS.md)

Contiene:

- TailwindCSS;
- Play CDN;
- Live Server;
- DevTools;
- recursos externos.

---

### 3. Estructura

[📄 02_ESTRUCTURA_PROYECTO.md](./02_ESTRUCTURA_PROYECTO.md)

Contiene:

- estructura de directorios;
- creación de archivos;
- comandos macOS;
- comandos Windows.

---

### 4. `.gitignore`

[📄 09_GITIGNORE.md](./09_GITIGNORE.md)

Debe configurarse antes de comenzar a generar archivos adicionales.

---

### 5. HTML

[📄 03_INDEX_HTML.md](./03_INDEX_HTML.md)

Contiene el código completo de:

```text
index.html
```

Incluye:

- Sidebar;
- Header;
- Main;
- Player;
- Mobile Navigation.

---

### 6. Design Tokens

[📄 04_THEME_CSS.md](./04_THEME_CSS.md)

Contiene el código de:

```text
css/theme.css
```

Responsabilidad:

```text
colores
radios
espaciados
variables
tokens visuales
```

---

### 7. CSS

[📄 05_STYLES_CSS.md](./05_STYLES_CSS.md)

Contiene:

```text
css/styles.css
```

Responsabilidad:

```text
estilos globales
scrollbar
focus
navegación
player
accesibilidad
```

---

### 8. Datos Mock

[📄 06_MOCK_DATA_JS.md](./06_MOCK_DATA_JS.md)

Contiene:

```text
js/data/mock.data.js
```

Responsabilidad:

```text
datos musicales simulados
```

---

### 9. UI

[📄 07_HOME_UI_JS.md](./07_HOME_UI_JS.md)

Contiene:

```text
js/ui/home.ui.js
```

Responsabilidad:

```text
datos
  ↓
HTML
  ↓
componentes
  ↓
DOM
```

---

### 10. Controlador

[📄 08_APP_JS.md](./08_APP_JS.md)

Contiene:

```text
js/app.js
```

Responsabilidad:

```text
estado
+
eventos
+
navegación
+
coordinación
```

---

### 11. README generado por la sesión

[📄 10_README.md](./10_README.md)

Contiene la documentación correspondiente a la versión desarrollada.

---

### 12. Guía docente

[📄 11_PASOS_CLASE.md](./11_PASOS_CLASE.md)

Puede mantenerse abierto durante la sesión como guía de desarrollo.

---

### 13. Validación

[📄 12_VALIDACION_SESION_1.md](./12_VALIDACION_SESION_1.md)

Debe ejecutarse antes de considerar terminada la sesión.

[⬆ Regresar al índice](#índice)

---

## Arquitectura de la sesión

```text
index.html
     │
     ├──────────────┐
     │              │
     ▼              ▼
theme.css       styles.css
                    │
                    ▼
                   UI
                    ▲
                    │
                app.js
                 ▲   ▲
                 │   │
                 │   └───────────────┐
                 │                   │
                 ▼                   ▼
         mock.data.js          home.ui.js
```

Responsabilidades:

```text
index.html
= estructura

theme.css
= identidad

styles.css
= estilos

mock.data.js
= datos

home.ui.js
= render

app.js
= lógica
```

[⬆ Regresar al índice](#índice)

---

## Flujo de trabajo

```text
DATOS MOCK
    │
    ▼
mock.data.js
    │
    ▼
app.js
    │
    ▼
home.ui.js
    │
    ▼
renderHome()
    │
    ▼
DOM
    │
    ▼
USUARIO
```

Conceptualmente:

```text
DATA
  ↓
STATE
  ↓
RENDER
  ↓
DOM
```

[⬆ Regresar al índice](#índice)

---

## Rama Git

Crear:

```bash
git checkout -b feature/session-01-ui
```

Confirmar:

```bash
git branch
```

Debe aparecer:

```text
* feature/session-01-ui
  main
```

[⬆ Regresar al índice](#índice)

---

## Commits

### Estructura

```bash
git add .
git commit -m "chore: create BeatFlow project structure"
```

### Layout

```bash
git add .
git commit -m "feat: create BeatFlow base layout"
```

### Sidebar

```bash
git add .
git commit -m "feat: add responsive sidebar navigation"
```

### Theme

```bash
git add .
git commit -m "style: add BeatFlow theme and global styles"
```

### Datos

```bash
git add .
git commit -m "feat: add mock music data"
```

### Cards

```bash
git add .
git commit -m "feat: add track card component"
```

### Player

```bash
git add .
git commit -m "feat: add desktop music player"
```

### Mobile

```bash
git add .
git commit -m "feat: add mobile navigation"
```

[⬆ Regresar al índice](#índice)

---

## Validación

Antes de terminar:

```text
HTML       ✓
Tailwind   ✓
CSS        ✓
JavaScript ✓
Responsive ✓
Console    ✓
Git        ✓
```

Abrir:

[✅ Validación completa](./12_VALIDACION_SESION_1.md)

La consola debe mostrar:

```text
0 errores
```

Probar:

```text
375px
768px
1024px
1440px
```

[⬆ Regresar al índice](#índice)

---

## Cierre

Integrar la rama:

```bash
git checkout main
```

```bash
git merge feature/session-01-ui
```

Crear tag:

```bash
git tag -a v0.1.0 -m "BeatFlow session 1"
```

Verificar:

```bash
git tag
```

Resultado:

```text
v0.1.0
```

La Sesión 1 queda terminada cuando tenemos:

```text
HTML
+
TailwindCSS
+
CSS
+
Responsive
+
Mock Data
+
JavaScript Modules
+
Git
=
BeatFlow v0.1.0
```

---

## Siguiente sesión

```text
Sesión 2
   ↓
Audius API
   ↓
Fetch
   ↓
Search
   ↓
Loading / Empty / Error
   ↓
v0.2.0
```

[➡ Continuar con Sesión 2](../sesion-02/README.md)

---

[⬅ Regresar a documentación](../README.md)

[🏠 Regresar a BeatFlow](../../README.md)
