# BeatFlow — Favorito en player.ui.js

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./05_HOME_UI_FAVORITOS.md) · [Siguiente ▶](./07_APP_JS.md)

---

## HTML requerido

En `index.html`, el botón de favorito del player debe tener:

```html
<button
  id="player-favorite-button"
  type="button"
  aria-label="Agregar a favoritos"
  aria-pressed="false"
>
  ♡
</button>
```

## En `player.ui.js`

Agregar:

```javascript
const favoriteButton =
  document.querySelector(
    '#player-favorite-button',
  )
```

Crear:

```javascript
function renderFavorite(
  favorite,
) {
  if (!favoriteButton) {
    return
  }

  favoriteButton.textContent =
    favorite
      ? '♥'
      : '♡'

  favoriteButton.setAttribute(
    'aria-label',
    favorite
      ? 'Quitar de favoritos'
      : 'Agregar a favoritos',
  )

  favoriteButton.setAttribute(
    'aria-pressed',
    String(favorite),
  )
}
```

Exportarlo:

```javascript
export const playerUI = {
  renderTrack,
  renderPlaying,
  renderProgress,
  renderVolume,
  renderFavorite,
}
```

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./05_HOME_UI_FAVORITOS.md) · [Siguiente ▶](./07_APP_JS.md)
