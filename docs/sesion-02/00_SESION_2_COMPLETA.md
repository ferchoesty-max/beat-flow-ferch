# BeatFlow — Sesión 2 completa

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_AUDIUS_RECURSOS_Y_API_KEY.md)

---

## API musical, datos reales y búsqueda

**Duración:** 1 hora 30 minutos  
**Versión objetivo:** `v0.2.0`

## Objetivo

Conectar BeatFlow con Audius y reemplazar progresivamente los datos mock por información musical real.

Temas:

- Audius JavaScript SDK
- API Key
- Promises
- `async` / `await`
- `try` / `catch`
- Trending tracks
- Search
- Normalización de datos
- Loading / Empty / Error / Success

En esta sesión todavía **no se implementa reproducción de audio real**.

## Resultado esperado

- Home obtiene tendencias reales.
- Search consulta canciones reales.
- Portadas y artistas provienen de Audius.
- La UI contempla Loading / Empty / Error / Success.
- Los datos externos se normalizan antes de llegar a UI.

## Arquitectura

```text
Usuario
   ↓
app.js
   ↓
audius.api.js
   ↓
Audius SDK
   ↓
Audius API
   ↓
TrackResponse[]
   ↓
normalizeTrack()
   ↓
UI Models[]
   ↓
Home / Search
   ↓
DOM
```

## Orden práctico

```text
01  00_SESION_2_COMPLETA.md
02  01_AUDIUS_RECURSOS_Y_API_KEY.md
03  02_ESTRUCTURA_SESION_2.md
04  03_INDEX_HTML_SDK.md
05  04_CONFIG_JS.md
06  05_AUDIUS_API_JS.md
07  06_STATES_UI_JS.md
08  07_SEARCH_UI_JS.md
09  08_HOME_UI_JS.md
10  09_APP_JS.md
11  10_PRUEBAS_MANUALES.md
12  12_VALIDACION_SESION_2.md
```

`11_PASOS_CLASE.md` se usa en paralelo como guía docente.

## Rama

```bash
git checkout main
git pull
git checkout -b feature/session-02-api
```

## Commits

```bash
git add .
git commit -m "feat: add Audius SDK configuration"
```

```bash
git add .
git commit -m "feat: add Audius API service"
```

```bash
git add .
git commit -m "feat: load trending tracks from Audius"
```

```bash
git add .
git commit -m "feat: implement music search"
```

```bash
git add .
git commit -m "feat: add loading empty and error states"
```

## Tag

```bash
git checkout main
git merge feature/session-02-api
git tag -a v0.2.0 -m "BeatFlow session 2"
```

---

## Navegación

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_AUDIUS_RECURSOS_Y_API_KEY.md)
