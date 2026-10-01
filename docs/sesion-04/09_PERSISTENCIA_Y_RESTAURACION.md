# BeatFlow — Persistencia y restauración

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./08_STYLES_ACCESIBILIDAD_CSS.md) · [Siguiente ▶](./10_PRUEBAS_MANUALES.md)

---

## Favoritos

```text
Click ♥
↓
toggleFavorite()
↓
storage.service.js
↓
LocalStorage
↓
renderFavorite()
```

## Historial

```text
playTrack()
↓
audio.play()
↓
addToHistory()
↓
LocalStorage
```

## Volumen

```text
range input
↓
setVolume()
↓
saveVolume()
↓
LocalStorage
```

Al iniciar:

```text
getVolume()
↓
setVolume()
```

## Última canción

```text
Track seleccionado
↓
saveLastTrack()
↓
LocalStorage
```

Al recargar:

```text
getLastTrack()
↓
playerUI.renderTrack()
```

No debe ejecutarse `play()` automáticamente.

## Inspeccionar datos

DevTools:

```text
Application
↓
Local Storage
↓
http://localhost...
```

Deben existir:

```text
beatflow:favorites
beatflow:history
beatflow:volume
beatflow:last-track
```

## Limpiar

```javascript
localStorage.clear()
location.reload()
```

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./08_STYLES_ACCESIBILIDAD_CSS.md) · [Siguiente ▶](./10_PRUEBAS_MANUALES.md)
