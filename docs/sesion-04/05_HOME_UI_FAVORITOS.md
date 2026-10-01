# BeatFlow — Favoritos en Home

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./04_LIBRARY_UI_JS.md) · [Siguiente ▶](./06_PLAYER_UI_FAVORITO.md)

---

## Archivo

```text
beatflow/js/ui/home.ui.js
```

## Objetivo

Agregar un botón de favorito a cada card.

Dentro de `createTrackCard(track)` agregar:

```html
<button
  type="button"
  class="favorite-track absolute right-3 top-3
         grid h-9 w-9 place-items-center
         rounded-full bg-black/60 text-white"
  data-track-id="${track.id}"
  aria-label="Agregar ${track.title} a favoritos"
  aria-pressed="false"
>
  ♡
</button>
```

## Importante

Debe incluir:

```text
favorite-track
data-track-id
aria-pressed
```

porque `app.js` utilizará delegación de eventos:

```javascript
event.target.closest(
  '.favorite-track',
)
```

## Versión

Cambiar:

```text
BeatFlow · v0.3.0
```

por:

```text
BeatFlow · v1.0.0
```

## Principio

La UI:

```text
NO escribe LocalStorage
```

La persistencia corresponde a:

```text
storage.service.js
```

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./04_LIBRARY_UI_JS.md) · [Siguiente ▶](./06_PLAYER_UI_FAVORITO.md)
