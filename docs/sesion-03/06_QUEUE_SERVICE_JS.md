# BeatFlow — queue.service.js

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./05_PLAYER_SERVICE_JS.md) · [Siguiente ▶](./07_PLAYER_UI_JS.md)

---

## Archivo

```text
beatflow/js/services/queue.service.js
```

## Código completo

```javascript
let queue = []
let currentIndex = -1

export function setQueue(
  tracks,
  selectedTrackId = null,
) {
  queue = [...tracks]

  if (queue.length === 0) {
    currentIndex = -1
    return
  }

  if (!selectedTrackId) {
    currentIndex = 0
    return
  }

  const index =
    queue.findIndex(
      (track) =>
        track.id ===
        selectedTrackId,
    )

  currentIndex =
    index >= 0
      ? index
      : 0
}

export function getCurrentTrack() {
  return queue[currentIndex]
    || null
}

export function getNextTrack() {
  if (queue.length === 0) {
    return null
  }

  currentIndex =
    (currentIndex + 1)
    % queue.length

  return getCurrentTrack()
}

export function getPreviousTrack() {
  if (queue.length === 0) {
    return null
  }

  currentIndex =
    currentIndex - 1

  if (currentIndex < 0) {
    currentIndex =
      queue.length - 1
  }

  return getCurrentTrack()
}

export function getQueueSnapshot() {
  return {
    tracks: [...queue],
    currentIndex,
    currentTrack:
      getCurrentTrack(),
  }
}
```

## Comportamiento

La cola es circular:

```text
A → B → C → A
```

Y hacia atrás:

```text
A ← B ← C ← A
```

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./05_PLAYER_SERVICE_JS.md) · [Siguiente ▶](./07_PLAYER_UI_JS.md)
