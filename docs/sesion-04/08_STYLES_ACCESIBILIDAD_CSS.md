# BeatFlow — Accesibilidad y CSS final

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./07_APP_JS.md) · [Siguiente ▶](./09_PERSISTENCIA_Y_RESTAURACION.md)

---

## Archivo

```text
beatflow/css/styles.css
```

Agregar:

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

.player-range {
  accent-color:
    var(--color-brand-primary);
}
```

## Focus visible

Mantener:

```css
:focus-visible {
  outline:
    2px solid
    var(--color-brand-primary);

  outline-offset: 3px;
}
```

## Reduced motion

Mantener:

```css
@media (
  prefers-reduced-motion: reduce
) {
  *,
  *::before,
  *::after {
    scroll-behavior:
      auto !important;

    transition-duration:
      0.01ms !important;

    animation-duration:
      0.01ms !important;

    animation-iteration-count:
      1 !important;
  }
}
```

## Checklist de accesibilidad

- imágenes con `alt`;
- botones con nombre accesible;
- favoritos con `aria-pressed`;
- player con `aria-label`;
- focus visible;
- navegación por teclado;
- contraste suficiente;
- reduced motion.

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./07_APP_JS.md) · [Siguiente ▶](./09_PERSISTENCIA_Y_RESTAURACION.md)
