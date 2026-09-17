# BeatFlow — Audius, recursos y API Key

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./00_SESION_2_COMPLETA.md) · [Siguiente ▶](./02_ESTRUCTURA_SESION_2.md)

---

## Recursos

Audius:

```text
https://audius.co/
```

SDK:

```text
https://docs.audius.co/sdk/
```

Tracks:

```text
https://docs.audius.co/sdk/tracks/
```

## SDK HTML + JS

```html
<script src="https://cdn.jsdelivr.net/npm/@audius/sdk@latest/dist/sdk.min.js"></script>
```

El SDK queda disponible como:

```javascript
window.audiusSdk
```

## Credenciales

Para BeatFlow en navegador se utiliza:

```text
API Key
```

No utilizar en frontend:

```text
Bearer Token
```

El Bearer Token es una credencial de backend y nunca debe exponerse en navegador.

## Operaciones de la sesión

```text
getTrendingTracks()
searchTracks()
```

No utilizaremos todavía:

```text
stream
favoriteTrack
OAuth
uploads
```

---

## Navegación

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./00_SESION_2_COMPLETA.md) · [Siguiente ▶](./02_ESTRUCTURA_SESION_2.md)
