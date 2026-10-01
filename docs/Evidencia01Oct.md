# Evidencia 01 Oct — Biblioteca, Favoritos, Persistencia y Accesibilidad (BeatFlow)

**Nombre:** Fernando Daniel Tolentino Uribe  
**NUA:** 395108  
**Materia:** Aplicaciones de Internet  
**Fecha:** 1 de Octubre de 2026  

---

## 📁 `js/services/storage.service.js`

```javascript
const STORAGE_KEYS = {
  favorites: 'beatflow:favorites',
  history: 'beatflow:history',
  volume: 'beatflow:volume',
  lastTrack: 'beatflow:last-track',
}

function readJson(key, fallback) {
  try {
    const value = localStorage.getItem(key)
    return value ? JSON.parse(value) : fallback
  } catch (error) {
    console.error(`Error reading ${key}:`, error)
    return fallback
  }
}

function writeJson(key, value) {
  try {
    localStorage.setItem(
      key,
      JSON.stringify(value),
    )
  } catch (error) {
    console.error(`Error writing ${key}:`, error)
  }
}

export function getFavorites() {
  return readJson(STORAGE_KEYS.favorites, [])
}

export function isFavorite(trackId) {
  return getFavorites()
    .some((track) => track.id === trackId)
}

export function toggleFavorite(track) {
  const favorites = getFavorites()

  const exists =
    favorites.some(
      (item) => item.id === track.id,
    )

  const nextFavorites =
    exists
      ? favorites.filter(
          (item) => item.id !== track.id,
        )
      : [track, ...favorites]

  writeJson(
    STORAGE_KEYS.favorites,
    nextFavorites,
  )

  return nextFavorites
}

export function getHistory() {
  return readJson(STORAGE_KEYS.history, [])
}

export function addToHistory(track) {
  const history = getHistory()

  const withoutDuplicate =
    history.filter(
      (item) => item.id !== track.id,
    )

  const nextHistory = [
    {
      ...track,
      playedAt: new Date().toISOString(),
    },
    ...withoutDuplicate,
  ].slice(0, 20)

  writeJson(
    STORAGE_KEYS.history,
    nextHistory,
  )

  return nextHistory
}

export function saveVolume(volume) {
  localStorage.setItem(
    STORAGE_KEYS.volume,
    String(volume),
  )
}

export function getVolume() {
  const value =
    localStorage.getItem(
      STORAGE_KEYS.volume,
    )

  if (value === null) {
    return 0.7
  }

  const parsed = Number(value)

  if (Number.isNaN(parsed)) {
    return 0.7
  }

  return Math.min(
    1,
    Math.max(0, parsed),
  )
}

export function saveLastTrack(track) {
  writeJson(
    STORAGE_KEYS.lastTrack,
    track,
  )
}

export function getLastTrack() {
  return readJson(
    STORAGE_KEYS.lastTrack,
    null,
  )
}

export function clearLibrary() {
  localStorage.removeItem(STORAGE_KEYS.favorites)
  localStorage.removeItem(STORAGE_KEYS.history)
  localStorage.removeItem(STORAGE_KEYS.lastTrack)
}
```

---

## 📁 `js/ui/library.ui.js`

```javascript
function createTrackRow(
  track,
  {
    showFavorite = false,
  } = {},
) {
  return `
    <article
      class="grid grid-cols-[auto_1fr_auto]
             items-center gap-4 rounded-2xl
             p-3 transition hover:bg-zinc-900"
    >
      <img
        src="${track.cover}"
        alt="Portada de ${track.title}"
        class="h-14 w-14 rounded-xl object-cover"
        loading="lazy"
      >

      <div class="min-w-0">
        <h3 class="truncate font-semibold">
          ${track.title}
        </h3>

        <p class="mt-1 truncate text-sm text-zinc-500">
          ${track.artist}
        </p>
      </div>

      <div class="flex items-center gap-2">
        ${
          showFavorite
            ? `
              <button
                type="button"
                class="favorite-track grid h-10 w-10
                       place-items-center rounded-full
                       bg-zinc-800 text-rose-500"
                data-track-id="${track.id}"
                aria-label="Quitar ${track.title} de favoritos"
                aria-pressed="true"
              >
                ♥
              </button>
            `
            : ''
        }

        <button
          type="button"
          class="play-track grid h-10 w-10
                 place-items-center rounded-full
                 bg-white text-black"
          data-track-id="${track.id}"
          aria-label="Reproducir ${track.title}"
        >
          ▶
        </button>
      </div>
    </article>
  `
}

export function renderLibrary({
  target,
  favorites,
  history,
}) {
  target.innerHTML = `
    <section>
      <p
        class="text-xs font-semibold uppercase
               tracking-[0.2em] text-violet-400"
      >
        Tu música
      </p>

      <h1 class="mt-2 text-3xl font-bold">
        Biblioteca
      </h1>

      <p class="mt-2 text-zinc-500">
        Tu música guardada en este navegador.
      </p>

      <section class="mt-8">
        <div class="flex items-center justify-between">
          <h2 class="text-xl font-bold">Favoritos</h2>
          <span class="text-sm text-zinc-500">
            ${favorites.length}
          </span>
        </div>

        <div
          class="mt-4 divide-y divide-white/5
                 rounded-3xl border border-white/10
                 bg-zinc-900/40 p-2"
        >
          ${
            favorites.length
              ? favorites
                  .map((track) =>
                    createTrackRow(
                      track,
                      { showFavorite: true },
                    ),
                  )
                  .join('')
              : `
                <p class="p-8 text-center text-zinc-500">
                  Todavía no tienes canciones favoritas.
                </p>
              `
          }
        </div>
      </section>

      <section class="mt-10">
        <div class="flex items-center justify-between">
          <h2 class="text-xl font-bold">
            Escuchados recientemente
          </h2>

          <span class="text-sm text-zinc-500">
            ${history.length}
          </span>
        </div>

        <div
          class="mt-4 divide-y divide-white/5
                 rounded-3xl border border-white/10
                 bg-zinc-900/40 p-2"
        >
          ${
            history.length
              ? history
                  .map((track) =>
                    createTrackRow(track),
                  )
                  .join('')
              : `
                <p class="p-8 text-center text-zinc-500">
                  Reproduce canciones para construir tu historial.
                </p>
              `
          }
        </div>
      </section>
    </section>
  `
}
```

---

## 📁 `css/styles.css` (Nuevas reglas de Accesibilidad y Favoritos)

```css
.favorite-track {
  transition:
    transform var(--transition-fast),
    color var(--transition-fast),
    background-color var(--transition-fast);
}

.favorite-track:hover {
  transform: scale(1.05);
}

.favorite-track[aria-pressed="true"] {
  color: #f43f5e;
}
```

---

## 📋 Validación de Sesión 4

- [x] Agregar canciones a favoritos desde Home, Search y Player
- [x] Quitar canciones de favoritos desde Biblioteca, Home, Search y Player
- [x] Persistencia de favoritos en LocalStorage (`beatflow:favorites`)
- [x] Registro automático de historial de reproducción sin duplicados (máximo 20)
- [x] Persistencia de nivel de volumen (`beatflow:volume`)
- [x] Persistencia de última canción reproducida (`beatflow:last-track`) sin auto-play
- [x] Vistas y Empty States en la Biblioteca
- [x] Accesibilidad (atributos `aria-pressed`, `aria-label`, foco visual, contraste)
