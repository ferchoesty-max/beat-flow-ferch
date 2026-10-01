# BeatFlow — app.js Sesión 4

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./06_PLAYER_UI_FAVORITO.md) · [Siguiente ▶](./08_STYLES_ACCESIBILIDAD_CSS.md)

---

## Imports nuevos

Agregar:

```javascript
import {
  addToHistory,
  getFavorites,
  getHistory,
  getLastTrack,
  getVolume,
  isFavorite,
  saveLastTrack,
  saveVolume,
  toggleFavorite,
} from './services/storage.service.js'

import {
  renderLibrary,
} from './ui/library.ui.js'
```

## Estado

```javascript
const state = {
  currentView: 'home',
  currentTrack: null,
  trendingTracks: [],
  searchResults: [],
  favorites: [],
  history: [],
  isPlaying: false,
}
```

## Inicialización

```javascript
async function initializeApp() {
  state.favorites =
    getFavorites()

  state.history =
    getHistory()

  const savedVolume =
    getVolume()

  setVolume(savedVolume)

  registerNavigationEvents()
  registerGlobalEvents()
  registerPlayerEvents()

  await loadHome()

  restoreLastTrack()
}
```

## Restaurar último track

```javascript
function restoreLastTrack() {
  const track =
    getLastTrack()

  if (!track) {
    return
  }

  state.currentTrack =
    track

  playerUI.renderTrack(
    track,
  )

  playerUI.renderFavorite(
    isFavorite(track.id),
  )
}
```

## Al reproducir

Después de cargar correctamente un track:

```javascript
state.currentTrack =
  track

state.history =
  addToHistory(track)

saveLastTrack(track)

playerUI.renderTrack(
  track,
)

playerUI.renderFavorite(
  isFavorite(track.id),
)
```

## Favorito

```javascript
function handleFavorite(
  trackId,
) {
  const track =
    getAllKnownTracks()
      .find(
        (item) =>
          item.id === trackId,
      )

  if (!track) {
    return
  }

  state.favorites =
    toggleFavorite(track)

  if (
    state.currentTrack?.id
    === track.id
  ) {
    playerUI.renderFavorite(
      isFavorite(track.id),
    )
  }

  if (
    state.currentView
    === 'library'
  ) {
    renderLibraryView()
  }
}
```

## Todos los tracks conocidos

```javascript
function getAllKnownTracks() {
  return [
    ...state.trendingTracks,
    ...state.searchResults,
    ...state.favorites,
    ...state.history,
  ]
}
```

## Library

```javascript
function renderLibraryView() {
  state.currentView =
    'library'

  state.favorites =
    getFavorites()

  state.history =
    getHistory()

  renderLibrary({
    target: app,
    favorites:
      state.favorites,
    history:
      state.history,
  })

  updateNavigationStyles()
}
```

## Delegación de favoritos

Dentro de:

```javascript
document.addEventListener(
  'click',
  (event) => {
```

agregar:

```javascript
const favoriteButton =
  event.target.closest(
    '.favorite-track',
  )

if (favoriteButton) {
  handleFavorite(
    favoriteButton.dataset.trackId,
  )

  return
}
```

## Botón favorito del player

```javascript
const playerFavoriteButton =
  document.querySelector(
    '#player-favorite-button',
  )

playerFavoriteButton
  ?.addEventListener(
    'click',
    () => {
      if (!state.currentTrack) {
        return
      }

      handleFavorite(
        state.currentTrack.id,
      )
    },
  )
```

## Persistir volumen

```javascript
volumeRange.addEventListener(
  'input',
  () => {
    const volume =
      Number(
        volumeRange.value,
      )

    setVolume(volume)
    saveVolume(volume)
  },
)
```

## Navegación Library

Cuando:

```javascript
view === 'library'
```

usar:

```javascript
renderLibraryView()
```

## Regla importante

La Sesión 4 debe extender el `app.js` funcional de Sesión 3.

No debes eliminar:

```text
playTrack()
loadAndPlayTrack()
playNextTrack()
playPreviousTrack()
registerPlayerEvents()
```

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./06_PLAYER_UI_FAVORITO.md) · [Siguiente ▶](./08_STYLES_ACCESIBILIDAD_CSS.md)
