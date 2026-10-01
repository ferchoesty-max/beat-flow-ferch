# BeatFlow — Audius streaming

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./02_ESTRUCTURA_SESION_3.md) · [Siguiente ▶](./04_INDEX_HTML_PLAYER.md)

---

## Archivo a modificar

```text
beatflow/js/api/audius.api.js
```

## 1. Agregar `isStreamable`

Dentro de `normalizeTrack()` agregar:

```javascript
isStreamable:
  track.isStreamable
  ?? track.is_streamable
  ?? true,
```

## 2. Agregar `getTrackStreamUrl()`

```javascript
export function getTrackStreamUrl(
  trackId,
) {
  if (!trackId) {
    throw new Error(
      'Track id is required.',
    )
  }

  const apiKey =
    APP_CONFIG.audius.apiKey

  const params =
    new URLSearchParams()

  if (
    apiKey
    && apiKey !==
      'REEMPLAZA_CON_TU_API_KEY'
  ) {
    params.set(
      'api_key',
      apiKey,
    )
  }

  const baseUrl =
    `https://api.audius.co/v1/tracks/${encodeURIComponent(trackId)}/stream`

  const query =
    params.toString()

  return query
    ? `${baseUrl}?${query}`
    : baseUrl
}
```

## Flujo

```text
Track ID
   ↓
getTrackStreamUrl()
   ↓
Audius stream endpoint
   ↓
HTMLAudioElement.src
```

## Track no reproducible

Antes de intentar reproducir:

```javascript
if (
  track.isStreamable === false
) {
  throw new Error(
    'Track is not streamable.',
  )
}
```

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./02_ESTRUCTURA_SESION_3.md) · [Siguiente ▶](./04_INDEX_HTML_PLAYER.md)
