# BeatFlow — Guía docente Sesión 3

[📘 Sesión 3](./README.md) · [⬅ Documentación](../README.md) · [🏠 BeatFlow](../../README.md) · [📚 Índice general](../../../../README.md)

---

## Distribución sugerida

| Tiempo | Actividad |
|---:|---|
| 0–10 min | HTML Audio API |
| 10–20 min | Streaming de Audius |
| 20–35 min | Player Service |
| 35–45 min | Queue Service |
| 45–60 min | UI del player |
| 60–72 min | Progress + Seek |
| 72–80 min | Volume |
| 80–86 min | Previous / Next / Ended |
| 86–90 min | Git + validación |

## Conceptos

```text
Track
 ↓
Stream URL
 ↓
Audio Element
 ↓
Events
 ↓
Player State
 ↓
UI
```

## Preguntas para alumnos

1. ¿Por qué conviene crear un solo `Audio()`?
2. ¿Qué diferencia existe entre `currentTime` y `duration`?
3. ¿Qué función cumple `timeupdate`?
4. ¿Por qué `play()` devuelve una Promise?
5. ¿Qué resuelve una cola separada del player?
6. ¿Qué sucede al dispararse `ended`?
7. ¿Por qué hay que validar `isStreamable`?

## Evidencia

Solicitar:

- video corto reproduciendo audio;
- Play/Pause;
- Seek;
- Volume;
- Next;
- Previous;
- Network mostrando stream;
- Console sin errores;
- `git log --oneline`;
- tag `v0.3.0`.

---

[📘 Sesión 3](./README.md) · [🏠 BeatFlow](../../README.md)
