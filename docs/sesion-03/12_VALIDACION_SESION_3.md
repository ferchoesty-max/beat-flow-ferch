# BeatFlow — Validación Sesión 3

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./10_PRUEBAS_MANUALES.md)

---

## Streaming

- [ ] `getTrackStreamUrl()` existe.
- [ ] Usa el `id` normalizado del track.
- [ ] Se verifica `isStreamable`.
- [ ] El navegador obtiene audio desde Audius.

## Player Service

- [ ] `Audio()` creado una sola vez.
- [ ] `play()` funciona.
- [ ] `pause()` funciona.
- [ ] `seekAudio()` funciona.
- [ ] `setVolume()` funciona.
- [ ] Eventos nativos registrados.

## Queue

- [ ] Cola configurada.
- [ ] Índice actual correcto.
- [ ] Previous funciona.
- [ ] Next funciona.
- [ ] `ended` avanza automáticamente.

## UI

- [ ] Título actualizado.
- [ ] Artista actualizado.
- [ ] Portada actualizada.
- [ ] Play/Pause sincronizado.
- [ ] Current time actualizado.
- [ ] Duration actualizada.
- [ ] Progress actualizado.
- [ ] Volume sincronizado.

## Arquitectura

- [ ] `player.service.js`
- [ ] `queue.service.js`
- [ ] `player.ui.js`
- [ ] `audius.api.js` actualizado.
- [ ] `app.js` actualizado.
- [ ] `index.html` actualizado.
- [ ] `styles.css` actualizado.

## Responsive

```text
375px
768px
1024px
1440px
```

## Console

```text
0 errores no controlados
```

## Git

```bash
git status
git log --oneline --graph --decorate --all
```

## Integración

```bash
git checkout main
git merge feature/session-03-player
```

## Tag

```bash
git tag -a v0.3.0 -m "BeatFlow session 3"
```

## Resultado

```text
BeatFlow v0.3.0

Audius Stream
+
HTML Audio
+
Queue
+
Player Controls
+
Progress
+
Volume
```

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./10_PRUEBAS_MANUALES.md)
