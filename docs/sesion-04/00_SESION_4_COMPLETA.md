# BeatFlow — Sesión 4 completa

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_LOCALSTORAGE_Y_PERSISTENCIA.md)

---

## Biblioteca, favoritos y persistencia

**Duración:** 1 hora 30 minutos  
**Versión objetivo:** `v1.0.0`

## Objetivo

Completar BeatFlow agregando persistencia local y una biblioteca personal del usuario.

En esta sesión se implementará:

- LocalStorage
- favoritos
- historial de reproducción
- biblioteca
- preferencias
- restauración al recargar
- persistencia de volumen
- persistencia de último track
- accesibilidad final
- responsive final

## Resultado esperado

```text
Usuario → reproduce → History → LocalStorage
Usuario → favorito → Favorites → LocalStorage
Reload → restore() → preferencias y biblioteca
```

## Arquitectura final

```text
Audius API
    ↓
audius.api.js
    ↓
app.js
 ┌──┴───────────┐
 ↓              ↓
Player       Storage
 ↓              ↓
Audio       LocalStorage
 └──────┬───────┘
        ↓
       UI
 ┌──────┼──────┐
 ↓      ↓      ↓
Home  Search Library
```

## Orden práctico

```text
01  00_SESION_4_COMPLETA.md
02  01_LOCALSTORAGE_Y_PERSISTENCIA.md
03  02_ESTRUCTURA_SESION_4.md
04  03_STORAGE_SERVICE_JS.md
05  04_LIBRARY_UI_JS.md
06  05_HOME_UI_FAVORITOS.md
07  06_PLAYER_UI_FAVORITO.md
08  07_APP_JS.md
09  08_STYLES_ACCESIBILIDAD_CSS.md
10  09_PERSISTENCIA_Y_RESTAURACION.md
11  10_PRUEBAS_MANUALES.md
12  12_VALIDACION_SESION_4.md
```

`11_PASOS_CLASE.md` se utiliza en paralelo como guía docente.

## Rama

```bash
git checkout main
git pull
git checkout -b feature/session-04-library
```

## Commits sugeridos

```bash
git add .
git commit -m "feat: add local storage service"
git commit -m "feat: add favorite tracks"
git commit -m "feat: add playback history"
git commit -m "feat: add library view"
git commit -m "feat: persist player preferences"
git commit -m "fix: improve accessibility and responsive behavior"
```

## Tag final

```bash
git checkout main
git merge feature/session-04-library
git tag -a v1.0.0 -m "BeatFlow version 1.0"
```

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_LOCALSTORAGE_Y_PERSISTENCIA.md)
