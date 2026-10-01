# Evidencia 28 Sep — Reproductor de Audio y Player UI (BeatFlow)

**Nombre:** Fernando Daniel Tolentino Uribe  
**NUA:** 395108  
**Materia:** Aplicaciones de Internet  
**Fecha:** 28 de Septiembre de 2026  

---

## 📁 `css/styles.css`

```css
.player-range {
  appearance: none;
  height: 0.375rem;
  border-radius: 999px;
  background:
    linear-gradient(
      90deg,
      var(--color-brand-primary) 0%,
      var(--color-brand-secondary) var(--range-progress, 0%),
      var(--color-bg-tertiary) var(--range-progress, 0%)
    );
  accent-color: var(--color-brand-primary);
}

.player-range::-webkit-slider-thumb {
  appearance: none;
  width: 0.875rem;
  height: 0.875rem;
  border-radius: 999px;
  background: white;
  cursor: pointer;
}

.player-range::-moz-range-thumb {
  width: 0.875rem;
  height: 0.875rem;
  border: 0;
  border-radius: 999px;
  background: white;
  cursor: pointer;
}

.player-range:focus-visible {
  outline: 2px solid var(--color-brand-primary);
  outline-offset: 4px;
}
```

---

## 📁 `js/app.js`

```javascript
// Import sesion 3
import { getTrackStreamUrl, getTrendingTracks, searchTracks } from './api/audius.api.js'
import { getNexttrack, getPreviousTrack, setQueue } from './services/queue.service.js'
import { getPlayerSnapshot, loadAudio, onPlayerEvent, pauseAudio, playAudio, seekAudio, setVolume, toggleAudio } from './services/player.service.js'
import { createPlayerUI } from './ui/player.ui.js'

const previousButton = document.querySelector('#previous-button')
const nextButton = document.querySelector('#next-button')
const progressRange = document.querySelector('#progress-range')
const volumeRange = document.querySelector('#volume-range')
const playerUI = createPlayerUI()

function getActiveCollection() {
  if (state.currentView === 'search' && state.searchResults.length > 0) {
    return state.searchResults
  }
  return state.trendingTracks
}

async function playTrack(trackId) {
  const tracks = getActiveCollection()
  const track = tracks.find((item) => item.id === trackId)
  if (!track) {
    return
  }
  if (track.isStreamable === false) {
    alert('La cancion no esta disponible')
    return
  }
  setQueue(tracks, track.id)
  await loadAndPlayTrack(track)
}

async function loadAndPlayTrack(track) {
  try {
    state.currentTrack = track
    playerUI.renderTrack(track)
    const streamUrl = getTrackStreamUrl(track.id)
    loadAudio(streamUrl)
    await playAudio()
  } catch (error) {
    alert(`No es posible reproducir la cancion ${error}`)
  }
}

async function playNextTrack() {
  const track = getNexttrack()
  if (!track) {
    return
  }
  await loadAndPlayTrack(track)
}

async function playPreviousTrack() {
  const snapshot = getPlayerSnapshot()
  if (snapshot.currentTime > 3) {
    seekAudio(0)
    return
  }
  const track = getPreviousTrack()
  if (!track) {
    return
  }
  await loadAndPlayTrack(track)
}

function registerPlayerEvents() {
  onPlayerEvent('play', () => {
    state.isPlaying = true
    playerUI.renderPlaying(true)
  })
  onPlayerEvent('pause', () => {
    state.isPlaying = false
    playerUI.renderPlaying(false)
  })
  onPlayerEvent('timeupdate', (payload) => {
    playerUI.renderProgress(payload)
  })
  onPlayerEvent('metadata', ({ duration }) => {
    playerUI.renderProgress({
      currentTime: 0,
      duration
    })
  })
  onPlayerEvent('volumechange', ({ volume }) => {
    playerUI.renderVolume(volume)
  })
  onPlayerEvent('ended', playNextTrack)
  onPlayerEvent('error', (error) => {
    console.error('Audio error:', error)
  })
}

// Eventos de controles de reproducción y barras de rango
previousButton.addEventListener('click', playPreviousTrack)
nextButton.addEventListener('click', playNextTrack)
progressRange.addEventListener('input', () => {
  seekAudio(Number(progressRange.value))
})
volumeRange.addEventListener('input', () => {
  setVolume(Number(volumeRange.value))
})
```

---

## 📁 `js/ui/player.ui.js`

```javascript
function formatTime(seconds = 0) {
  if (!Number.isFinite(seconds)) {
    return '0:00'
  }

  const minutes = Math.floor(seconds / 60)
  const remaining = Math.floor(seconds % 60)

  return `${minutes}:${String(remaining).padStart(2, '0')}`
}

export function createPlayerUI() {
  const cover = document.querySelector('#player-cover')
  const title = document.querySelector('#player-title')
  const artist = document.querySelector('#player-artist')
  const playButton = document.querySelector('#play-button')
  const currentTime = document.querySelector('#current-time')
  const durationTime = document.querySelector('#duration-time')
  const progress = document.querySelector('#progress-range')
  const volume = document.querySelector('#volume-range')

  function updateRangeProgress(input, current, max) {
    if (!input) return
    const safeMax = Number(max) > 0 ? Number(max) : 100
    const percent = Math.min(100, Math.max(0, (Number(current) / safeMax) * 100))
    input.style.setProperty('--range-progress', `${percent}%`)
  }

  progress?.addEventListener('input', (event) => {
    updateRangeProgress(progress, event.target.value, progress.max)
  })

  volume?.addEventListener('input', (event) => {
    updateRangeProgress(volume, event.target.value, volume.max || 1)
  })

  if (volume) {
    updateRangeProgress(volume, volume.value, volume.max || 1)
  }

  function renderTrack(track) {
    if (!track) {
      return
    }

    cover.src = track.cover
    cover.alt = `Portada de ${track.title}`
    title.textContent = track.title
    artist.textContent = track.artist
  }

  function renderPlaying(isPlaying) {
    playButton.textContent = isPlaying ? '❚❚' : '▶'
    playButton.setAttribute('aria-label', isPlaying ? 'Pausar' : 'Reproducir')
  }

  function renderProgress({ currentTime: current, duration }) {
    const safeDuration = duration > 0 ? duration : 0

    currentTime.textContent = formatTime(current)
    durationTime.textContent = formatTime(safeDuration)
    progress.max = String(safeDuration || 100)
    progress.value = String(current || 0)

    updateRangeProgress(progress, current, safeDuration)
  }

  function renderVolume(value) {
    volume.value = String(value)
    updateRangeProgress(volume, value, 1)
  }

  return {
    renderTrack,
    renderPlaying,
    renderProgress,
    renderVolume,
  }
}
```

---

## 📁 `js/services/player.service.js`

```javascript
const audio = new Audio()

audio.preload = 'metadata'
audio.volume = 0.7

const listeners = new Map()

function emit(eventName, payload) {
  const handlers = listeners.get(eventName) || []
  handlers.forEach((handler) => handler(payload))
}

function bindNativeEvents() {
  audio.addEventListener('loadedmetadata', () => {
    emit('metadata', {
      duration: Number.isFinite(audio.duration) ? audio.duration : 0,
    })
  })

  audio.addEventListener('timeupdate', () => {
    emit('timeupdate', {
      currentTime: audio.currentTime,
      duration: Number.isFinite(audio.duration) ? audio.duration : 0,
    })
  })

  audio.addEventListener('play', () => emit('play'))
  audio.addEventListener('pause', () => emit('pause'))
  audio.addEventListener('ended', () => emit('ended'))
  audio.addEventListener('error', () => emit('error', audio.error))

  audio.addEventListener('volumechange', () => {
    emit('volumechange', {
      volume: audio.volume,
    })
  })
}

bindNativeEvents()

export function onPlayerEvent(eventName, handler) {
  const handlers = listeners.get(eventName) || []
  handlers.push(handler)
  listeners.set(eventName, handlers)
}

export function loadAudio(streamUrl) {
  audio.pause()
  audio.src = streamUrl
  audio.load()
}

export async function playAudio() {
  await audio.play()
}

export function pauseAudio() {
  audio.pause()
}

export function toggleAudio() {
  if (audio.paused) {
    return playAudio()
  }
  pauseAudio()
  return Promise.resolve()
}

export function seekAudio(seconds) {
  if (!Number.isFinite(seconds)) {
    return
  }
  audio.currentTime = Math.max(0, Math.min(seconds, audio.duration || seconds))
}

export function setVolume(volume) {
  const safeVolume = Math.max(0, Math.min(1, volume))
  audio.volume = safeVolume
}

export function getPlayerSnapshot() {
  return {
    paused: audio.paused,
    currentTime: audio.currentTime,
    duration: Number.isFinite(audio.duration) ? audio.duration : 0,
    volume: audio.volume,
  }
}
```

---

## 📁 `js/services/queue.service.js`

```javascript
let queue = []
let currentIndex = -1

export function setQueue(tracks, selectedTrackId = null) {
  queue = [...tracks]
  if (queue.length === 0) {
    currentIndex = -1
    return
  }
  if (!selectedTrackId) {
    currentIndex = 0
    return
  }
  const index = queue.findIndex((track) => track.id === selectedTrackId)
  currentIndex = index >= 0 ? index : 0
}

export function getCurrentTrack() {
  return queue[currentIndex] || null
}

export function getNexttrack() {
  if (queue.length === 0) {
    return null
  }
  currentIndex = (currentIndex + 1) % queue.length
  return getCurrentTrack()
}

export function getPreviousTrack() {
  if (queue.length === 0) {
    return null
  }
  currentIndex = currentIndex - 1
  if (currentIndex < 0) {
    currentIndex = queue.length - 1
  }
  return getCurrentTrack()
}

export function getQueueSnapshot() {
  return {
    tracks: [...queue],
    currentIndex,
    currentTrack: getCurrentTrack()
  }
}
```

---

## 📁 `js/api/audius.api.js`

```javascript
export function getTrackStreamUrl(trackId) {
  if (!trackId) {
    throw new Error('Track id es requerido')
  }
  const apiKey = APP_CONFIG.audius.apikey
  const params = new URLSearchParams()
  if (!apiKey && apiKey !== 'REEMPLAZA_CON_TU_API_KEY') {
    params.set('api_key', apiKey)
  }
  const baseUrl = `https://api.audius.co/v1/tracks/${encodeURIComponent(trackId)}/stream`
  const query = params.toString()
  return query ? `${baseUrl}?${query}` : baseUrl
}
```
