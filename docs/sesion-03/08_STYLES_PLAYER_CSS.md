# BeatFlow — estilos del player

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./07_PLAYER_UI_JS.md) · [Siguiente ▶](./09_APP_JS.md)

---

## Archivo

```text
beatflow/css/styles.css
```

Agregar al final:

```css
.player-range {
  appearance: none;
  height: 0.375rem;
  border-radius: 999px;
  background: var(--color-bg-tertiary);
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

## Objetivo

Mantener los controles nativos accesibles, pero integrados visualmente con BeatFlow.

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./07_PLAYER_UI_JS.md) · [Siguiente ▶](./09_APP_JS.md)
