# BeatFlow — Sesión 3 completa

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_HTML_AUDIO_Y_STREAMING.md)

---

## Reproductor musical real

**Duración:** 1 hora 30 minutos  
**Versión objetivo:** `v0.3.0`

## Objetivo

Convertir el player visual desarrollado en las sesiones anteriores en un reproductor musical funcional.

En esta sesión se implementará:

- `HTMLAudioElement`
- streaming de Audius
- Play
- Pause
- Seek
- Progress
- Duration
- Volume
- Previous
- Next
- Queue
- evento `ended`
- sincronización Player ↔ UI

Todavía **no se implementan favoritos persistentes ni LocalStorage**. Eso corresponde a la Sesión 4.

## Resultado esperado

```text
Seleccionar track
      ↓
obtener stream URL
      ↓
HTMLAudioElement
      ↓
play()
      ↓
actualizar UI
      ↓
progress
      ↓
ended
      ↓
next()
```

## Arquitectura

```text
Audius Track
     │
     ▼
audius.api.js
     │
     ▼
stream URL
     │
     ▼
player.service.js
     │
     ├──────────────┐
     ▼              ▼
Audio Element    Queue Service
     │              │
     └──────┬───────┘
            ▼
       player.ui.js
            │
            ▼
           DOM
```

## Orden práctico

```text
01  00_SESION_3_COMPLETA.md
02  01_HTML_AUDIO_Y_STREAMING.md
03  02_ESTRUCTURA_SESION_3.md
04  03_AUDIUS_API_STREAMING.md
05  04_INDEX_HTML_PLAYER.md
06  05_PLAYER_SERVICE_JS.md
07  06_QUEUE_SERVICE_JS.md
08  07_PLAYER_UI_JS.md
09  08_STYLES_PLAYER_CSS.md
10  09_APP_JS.md
11  10_PRUEBAS_MANUALES.md
12  12_VALIDACION_SESION_3.md
```

`11_PASOS_CLASE.md` se utiliza en paralelo como guía docente.

## Rama sugerida

```bash
git checkout main
git pull
git checkout -b feature/session-03-player
```

## Commits sugeridos

```bash
git add .
git commit -m "feat: add Audius stream URL support"
```

```bash
git add .
git commit -m "feat: add audio player service"
```

```bash
git add .
git commit -m "feat: implement playback queue"
```

```bash
git add .
git commit -m "feat: connect player controls"
```

```bash
git add .
git commit -m "feat: add progress and volume controls"
```

```bash
git add .
git commit -m "feat: implement previous and next playback"
```

## Tag

```bash
git checkout main
git merge feature/session-03-player
git tag -a v0.3.0 -m "BeatFlow session 3"
```

## Criterio de salida

```text
Audius Stream
+
HTML Audio API
+
Play / Pause
+
Progress
+
Seek
+
Volume
+
Queue
+
Previous / Next
=
BeatFlow v0.3.0
```

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [Siguiente ▶](./01_HTML_AUDIO_Y_STREAMING.md)
