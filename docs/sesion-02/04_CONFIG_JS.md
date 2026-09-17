# BeatFlow — config.js

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./03_INDEX_HTML_SDK.md) · [Siguiente ▶](./05_AUDIUS_API_JS.md)

---

## Archivo

```text
beatflow/js/config.js
```

## Código

```javascript
export const APP_CONFIG = {
  audius: {
    apiKey: 'REEMPLAZA_CON_TU_API_KEY',
  },

  search: {
    minLength: 2,
    limit: 20,
  },

  trending: {
    limit: 12,
    time: 'week',
  },
}
```

No agregar Bearer Token, passwords ni private keys.

---

## Navegación

[📘 Sesión 2](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./03_INDEX_HTML_SDK.md) · [Siguiente ▶](./05_AUDIUS_API_JS.md)
