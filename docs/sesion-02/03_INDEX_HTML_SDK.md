# BeatFlow — Integrar Audius SDK

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./02_ESTRUCTURA_SESION_2.md) · [Siguiente ▶](./04_CONFIG_JS.md)

---

## Archivo

```text
beatflow/index.html
```

Agregar después de Tailwind:

```html
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
<script src="https://cdn.jsdelivr.net/npm/@audius/sdk@latest/dist/sdk.min.js"></script>
```

Mantener:

```html
<link rel="stylesheet" href="./css/theme.css">
<link rel="stylesheet" href="./css/styles.css">
```

Al final:

```html
<script type="module" src="./js/app.js"></script>
```

## Validación

En Console:

```javascript
window.audiusSdk
```

No debe ser `undefined`.

---

## Navegación

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./02_ESTRUCTURA_SESION_2.md) · [Siguiente ▶](./04_CONFIG_JS.md)
