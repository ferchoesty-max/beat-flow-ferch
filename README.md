# BeatFlow

Aplicación web musical desarrollada como proyecto evolutivo para la materia **Aplicaciones de Internet**.

BeatFlow está inspirado en la experiencia de plataformas modernas de streaming musical, pero utiliza identidad visual propia.

---

## Índice

- [Objetivo](#objetivo)
- [Stack tecnológico](#stack-tecnológico)
- [Restricciones](#restricciones)
- [Arquitectura](#arquitectura)
- [Sesiones](#sesiones)
- [Versiones](#versiones)
- [Documentación](#documentación)
- [Flujo Git](#flujo-git)
- [Recursos](#recursos)

---

## Objetivo

Construir una aplicación web musical utilizando tecnologías fundamentales del navegador y APIs públicas gratuitas.

Al finalizar BeatFlow permitirá:

- visualizar canciones;
- consultar tendencias;
- buscar música;
- mostrar artistas;
- mostrar portadas;
- seleccionar canciones;
- reproducir audio;
- pausar y continuar;
- controlar progreso;
- controlar volumen;
- cambiar de canción;
- manejar una cola;
- guardar favoritos;
- registrar canciones reproducidas;
- persistir información mediante LocalStorage;
- funcionar en desktop, tablet y móvil.

[⬆ Regresar al índice](#índice)

---

## Stack tecnológico

| Tecnología | Uso |
|---|---|
| HTML5 | Estructura |
| TailwindCSS 4 | UI responsive |
| CSS | Design Tokens y estilos globales |
| JavaScript ES6+ | Lógica |
| ES Modules | Modularización |
| Fetch | Consumo de APIs |
| Audius API | Información musical |
| HTML Audio API | Reproducción |
| LocalStorage | Persistencia |
| Git | Control de versiones |
| GitHub | Repositorio |

[⬆ Regresar al índice](#índice)

---

## Restricciones

No se utilizarán:

- React;
- Vue;
- Angular;
- Nuxt;
- Node.js backend;
- Express;
- Firebase;
- base de datos propia.

El objetivo académico es dominar primero:

```text
HTML
+
CSS
+
JavaScript
+
DOM
+
HTTP
+
JSON
+
APIs
+
Estado
+
Persistencia
```

[⬆ Regresar al índice](#índice)

---

## Arquitectura

```text
                  USUARIO
                     │
                     ▼
               HTML / DOM
                     │
                     ▼
                  app.js
                     │
          ┌──────────┼──────────┐
          │          │          │
          ▼          ▼          ▼
         UI       Services     State
          │          │          │
          ▼          ▼          ▼
         DOM      API        LocalStorage
                     │
                     ▼
              HTML Audio API
```

[⬆ Regresar al índice](#índice)

---

## Sesiones

### Sesión 1 — UI/UX y estructura

**Versión:** `v0.1.0`

Objetivo:

Construir la primera versión visual y responsive.

Incluye:

- sidebar;
- header;
- hero;
- cards;
- player visual;
- navegación móvil;
- datos mock;
- JavaScript modular.

[📘 Abrir Sesión 1](./docs/sesion-01/README.md)

---

### Sesión 2 — API musical y búsqueda

**Versión:** `v0.2.0`

Objetivo:

Conectar BeatFlow con una API pública gratuita.

Incluye:

- REST;
- HTTP;
- JSON;
- Fetch;
- async/await;
- Audius;
- búsqueda;
- trending;
- loading;
- empty;
- error.

[📘 Abrir Sesión 2](./docs/sesion-02/README.md)

---

### Sesión 3 — Reproductor musical

**Versión:** `v0.3.0`

Objetivo:

Implementar reproducción de audio real.

Incluye:

- play;
- pause;
- duration;
- currentTime;
- progress;
- volume;
- previous;
- next;
- queue.

[📘 Abrir Sesión 3](./docs/sesion-03/README.md)

---

### Sesión 4 — Biblioteca y persistencia

**Versión:** `v1.0.0`

Objetivo:

Agregar persistencia y completar la aplicación.

Incluye:

- favoritos;
- historial;
- biblioteca;
- LocalStorage;
- preferencias;
- accesibilidad;
- validación final.

[📘 Abrir Sesión 4](./docs/sesion-04/README.md)

[⬆ Regresar al índice](#índice)

---

## Versiones

| Versión | Sesión | Resultado |
|---|---:|---|
| `v0.1.0` | 1 | UI + Responsive + Mock Data |
| `v0.2.0` | 2 | API + Search |
| `v0.3.0` | 3 | Audio Player |
| `v1.0.0` | 4 | Biblioteca + Persistencia |

[⬆ Regresar al índice](#índice)

---

## Documentación

Toda la documentación del proyecto se encuentra en:

[📚 Abrir índice de documentación](./docs/README.md)

Estructura:

```text
docs/
├── README.md
├── sesion-01/
├── sesion-02/
├── sesion-03/
└── sesion-04/
```

[⬆ Regresar al índice](#índice)

---

## Flujo Git

```text
main
 │
 ├── feature/session-01-ui
 ├── feature/session-02-api
 ├── feature/session-03-player
 └── feature/session-04-library
```

Ejemplo:

```bash
git checkout -b feature/session-01-ui
```

Al terminar:

```bash
git checkout main
git merge feature/session-01-ui
```

Tag:

```bash
git tag -a v0.1.0 -m "BeatFlow session 1"
```

[⬆ Regresar al índice](#índice)

---

## Recursos

### TailwindCSS

https://tailwindcss.com/

Play CDN:

```html
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
```

### Audius

https://audius.co/

https://docs.audius.co/

### MDN

https://developer.mozilla.org/

[⬆ Regresar al índice](#índice)

---

## Comenzar

[▶ Comenzar con la Sesión 1](./docs/sesion-01/README.md)

---

[⬅ Repositorio de la materia (Prof. Marco Ramírez)](https://github.com/MarcoARamirezS/aplicaciones-de-internet-ad-2026)
