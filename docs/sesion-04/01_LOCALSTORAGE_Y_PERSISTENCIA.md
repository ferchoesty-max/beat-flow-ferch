# BeatFlow — LocalStorage y persistencia

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./00_SESION_4_COMPLETA.md) · [Siguiente ▶](./02_ESTRUCTURA_SESION_4.md)

---

## Concepto

`localStorage` guarda texto en el navegador y persiste después de recargar o cerrar.

### Guardar

```javascript
localStorage.setItem('key', 'value')
```

### Leer

```javascript
const value = localStorage.getItem('key')
```

### Objetos

```javascript
localStorage.setItem(
  'beatflow:favorites',
  JSON.stringify(favorites),
)
```

```javascript
const favorites =
  JSON.parse(
    localStorage.getItem('beatflow:favorites')
    || '[]',
  )
```

## Datos de BeatFlow

```text
beatflow:favorites
beatflow:history
beatflow:volume
beatflow:last-track
```

## No guardar

```text
contraseñas
Bearer Token
tokens privados
credenciales sensibles
```

---

## Navegación

[📘 Sesión 4](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md) · [◀ Anterior](./00_SESION_4_COMPLETA.md) · [Siguiente ▶](./02_ESTRUCTURA_SESION_4.md)
