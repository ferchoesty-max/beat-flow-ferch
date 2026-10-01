# BeatFlow — Pruebas manuales Sesión 3

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./09_APP_JS.md) · [Siguiente ▶](./12_VALIDACION_SESION_3.md)

---

## Prueba 1 — Selección

Seleccionar una canción desde Trending.

Esperado:

```text
portada cambia
artista cambia
título cambia
audio inicia
```

## Prueba 2 — Play/Pause

Presionar el botón central varias veces.

Esperado:

```text
▶ ↔ ❚❚
```

El audio debe detenerse y continuar desde el mismo segundo.

## Prueba 3 — Progress

Mientras se reproduce una canción:

```text
currentTime aumenta
slider avanza
```

## Prueba 4 — Seek

Mover manualmente el slider.

Esperado: la reproducción salta al segundo seleccionado.

## Prueba 5 — Volumen

Mover:

```text
volume-range
```

Esperado: volumen real cambia entre 0 y 1.

## Prueba 6 — Next

Seleccionar una colección con varias canciones y presionar siguiente.

Esperado: reproduce el siguiente track de la cola.

## Prueba 7 — Previous

Si la canción lleva más de 3 segundos:

```text
Previous → currentTime = 0
```

Si está al inicio:

```text
Previous → track anterior
```

## Prueba 8 — ended

Dejar terminar una canción o simularlo desde DevTools.

Esperado: inicia automáticamente la siguiente.

## Prueba 9 — Search + Player

Buscar una canción y reproducir desde Search.

Esperado: la cola se genera con los resultados actuales.

## Prueba 10 — Console

```text
0 errores no controlados
```

## Prueba 11 — Network

Confirmar solicitudes hacia:

```text
/tracks/{track_id}/stream
```

## Prueba 12 — Responsive

Probar:

```text
375px
768px
1024px
1440px
```

---

## Navegación

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./09_APP_JS.md) · [Siguiente ▶](./12_VALIDACION_SESION_3.md)
