# BeatFlow — Actualizar player en index.html

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./03_AUDIUS_API_STREAMING.md) · [Siguiente ▶](./05_PLAYER_SERVICE_JS.md)

---

## Archivo

```text
beatflow/index.html
```

Reemplazar únicamente el bloque del player por el siguiente.

```html
<footer
  class="fixed inset-x-0 bottom-[68px] z-40 border-t
         border-white/10 bg-zinc-950/95 backdrop-blur
         lg:bottom-0 lg:left-[250px]"
>
  <div
    class="grid min-h-[96px] grid-cols-[1fr_auto]
           items-center gap-4 px-4 py-3
           md:grid-cols-[1fr_1.4fr_1fr] md:px-6"
  >

    <div class="flex min-w-0 items-center gap-3">
      <img
        id="player-cover"
        src="https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&w=160&q=80"
        alt="Portada actual"
        class="h-14 w-14 rounded-xl object-cover"
      >

      <div class="min-w-0">
        <p id="player-title" class="truncate text-sm font-semibold">
          Selecciona una canción
        </p>

        <p id="player-artist" class="truncate text-xs text-zinc-500">
          BeatFlow
        </p>
      </div>
    </div>

    <div class="flex flex-col items-center gap-2">
      <div class="flex items-center gap-4">
        <button
          id="previous-button"
          type="button"
          class="text-zinc-400 transition hover:text-white"
          aria-label="Canción anterior"
        >
          ◀
        </button>

        <button
          id="play-button"
          type="button"
          class="grid h-11 w-11 place-items-center rounded-full
                 bg-white text-black transition hover:scale-105"
          aria-label="Reproducir"
        >
          ▶
        </button>

        <button
          id="next-button"
          type="button"
          class="text-zinc-400 transition hover:text-white"
          aria-label="Siguiente canción"
        >
          ▶
        </button>
      </div>

      <div class="hidden w-full items-center gap-3 md:flex">
        <span id="current-time" class="w-10 text-right text-xs text-zinc-500">
          0:00
        </span>

        <input
          id="progress-range"
          class="player-range flex-1"
          type="range"
          min="0"
          max="100"
          value="0"
          step="0.1"
          aria-label="Progreso de reproducción"
        >

        <span id="duration-time" class="w-10 text-xs text-zinc-500">
          0:00
        </span>
      </div>
    </div>

    <div class="hidden items-center justify-end gap-3 md:flex">
      <span aria-hidden="true">🔊</span>

      <input
        id="volume-range"
        class="player-range w-28"
        type="range"
        min="0"
        max="1"
        value="0.7"
        step="0.05"
        aria-label="Volumen"
      >
    </div>

  </div>
</footer>
```

## IDs agregados

```text
previous-button
next-button
current-time
duration-time
progress-range
volume-range
```

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./03_AUDIUS_API_STREAMING.md) · [Siguiente ▶](./05_PLAYER_SERVICE_JS.md)
