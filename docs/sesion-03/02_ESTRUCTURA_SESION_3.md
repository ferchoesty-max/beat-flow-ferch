# BeatFlow — Estructura Sesión 3

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./01_HTML_AUDIO_Y_STREAMING.md) · [Siguiente ▶](./03_AUDIUS_API_STREAMING.md)

---

## Evolución del proyecto

Partimos de `v0.2.0`.

```text
beatflow/
├── index.html
├── css/
│   ├── theme.css
│   └── styles.css
├── js/
│   ├── app.js
│   ├── config.js
│   ├── api/
│   │   └── audius.api.js
│   ├── services/
│   │   ├── player.service.js
│   │   └── queue.service.js
│   └── ui/
│       ├── home.ui.js
│       ├── search.ui.js
│       ├── states.ui.js
│       └── player.ui.js
└── docs/
    ├── sesion-01/
    ├── sesion-02/
    └── sesion-03/
```

## Archivos nuevos

```text
js/services/player.service.js
js/services/queue.service.js
js/ui/player.ui.js
```

## Archivos modificados

```text
index.html
css/styles.css
js/api/audius.api.js
js/app.js
```

## Crear directorios

macOS/Linux:

```bash
mkdir -p js/services
touch js/services/player.service.js
touch js/services/queue.service.js
touch js/ui/player.ui.js
```

PowerShell:

```powershell
mkdir js\services
New-Item js\services\player.service.js
New-Item js\services\queue.service.js
New-Item js\ui\player.ui.js
```

## Responsabilidades

```text
audius.api.js = stream URL
player.service.js = HTMLAudioElement
queue.service.js = cola e índice
player.ui.js = sincronización visual
app.js = coordinación
```

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./01_HTML_AUDIO_Y_STREAMING.md) · [Siguiente ▶](./03_AUDIUS_API_STREAMING.md)
