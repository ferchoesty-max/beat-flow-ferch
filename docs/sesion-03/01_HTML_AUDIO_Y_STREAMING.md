# BeatFlow — HTML Audio API y streaming

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./00_SESION_3_COMPLETA.md) · [Siguiente ▶](./02_ESTRUCTURA_SESION_3.md)

---

## HTMLAudioElement

JavaScript permite crear un reproductor sin mostrar directamente una etiqueta `<audio>`:

```javascript
const audio = new Audio()
```

## Propiedades importantes

```javascript
audio.src
audio.currentTime
audio.duration
audio.volume
audio.paused
audio.ended
```

## Métodos

```javascript
audio.play()
audio.pause()
audio.load()
```

## Eventos

```text
loadedmetadata
timeupdate
play
pause
ended
error
volumechange
```

## Flujo de reproducción

```text
track.id
   ↓
Audius stream endpoint
   ↓
audio.src
   ↓
audio.load()
   ↓
audio.play()
```

## Endpoint de Audius

```text
GET /v1/tracks/{track_id}/stream
```

BeatFlow construirá una URL como:

```text
https://api.audius.co/v1/tracks/TRACK_ID/stream
```

La API Key puede agregarse como parámetro de aplicación:

```text
?api_key=TU_API_KEY
```

## Track reproducible

Antes de reproducir se debe revisar:

```text
isStreamable
```

## Range Requests

El endpoint de streaming admite solicitudes parciales del audio. Esto permite:

```text
play
pause
seek
buffer
resume
```

## Autoplay

Los navegadores pueden bloquear audio iniciado automáticamente. Por ello la reproducción debe comenzar después de una acción explícita del usuario.

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./00_SESION_3_COMPLETA.md) · [Siguiente ▶](./02_ESTRUCTURA_SESION_3.md)
