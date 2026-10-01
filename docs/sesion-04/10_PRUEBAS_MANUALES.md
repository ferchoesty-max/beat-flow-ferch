# BeatFlow — Pruebas manuales Sesión 4

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./09_PERSISTENCIA_Y_RESTAURACION.md) · [Siguiente ▶](./12_VALIDACION_SESION_4.md)

---

## Favoritos

1. Marcar canción.
2. Abrir Biblioteca.

Esperado:

```text
canción en Favoritos
```

## Persistencia

1. Marcar favorito.
2. Recargar.
3. Abrir Biblioteca.

Esperado:

```text
favorito permanece
```

## Historial

Reproducir tres canciones.

Esperado:

```text
última reproducción primero
```

## Sin duplicados

Reproducir varias veces la misma canción.

Esperado:

```text
una sola entrada
```

## Volumen

Cambiar volumen y recargar.

Esperado:

```text
volumen restaurado
```

## Último track

Seleccionar una canción y recargar.

Esperado:

```text
portada
título
artista
```

No debe reproducirse automáticamente.

## Quitar favorito

Desde Biblioteca:

```text
♥
↓
click
↓
se elimina
```

## Search → Favorite

Buscar, marcar favorito y abrir Library.

Esperado:

```text
track en Favoritos
```

## Teclado

Probar:

```text
Tab
Shift + Tab
Enter
Space
```

## Responsive

```text
375px
768px
1024px
1440px
```

## LocalStorage

Validar:

```text
beatflow:favorites
beatflow:history
beatflow:volume
beatflow:last-track
```

## Console

```text
0 errores no controlados
```

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./09_PERSISTENCIA_Y_RESTAURACION.md) · [Siguiente ▶](./12_VALIDACION_SESION_4.md)
