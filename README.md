# MK Grand Circuit — Frontend

Frontend del torneo "MK Grand Circuit", organizado por la comunidad **Code Genius eSports**. Permite a los jugadores registrarse, crear equipos, inscribirse en el torneo y seguir el bracket, los partidos y la clasificación en tiempo real. Incluye un panel de administración independiente para gestionar equipos e inscripciones.

## Funcionalidades

- Registro e inicio de sesión de usuarios.
- Creación y gestión de equipos (alta de miembros por User ID, un equipo por jugador).
- Inscripción de equipos al torneo, sujeta a aprobación del administrador.
- Bracket, partidos y clasificación en vivo.
- Panel de administración (`admin.html`) con su propio login, para aprobar equipos y gestionar el torneo.
- Interfaz bilingüe (inglés / español) con cambio de idioma persistente.
- Fondo animado con partículas conectadas en `<canvas>`.
- Página de "coming soon" (`coming-soon.html`) para el lanzamiento.

## Tecnologías

HTML, CSS y JavaScript vanilla (sin frameworks ni build). Toda la interfaz es una única página (`index.html`) que gestiona estado, vistas y llamadas a la API a mano.

## Cómo usarlo

Al ser HTML/CSS/JS estático, basta con abrir `index.html` en el navegador. La aplicación consume una API REST externa (backend en Node/Express, repositorio aparte) para autenticación, equipos, partidos y clasificación.

## Estructura

| Archivo | Contenido |
|---|---|
| `index.html` | Aplicación principal (torneo, equipos, bracket) |
| `admin.html` | Panel de administración |
| `coming-soon.html` | Página de espera previa al lanzamiento |
| `gclogo.png` | Logo del torneo |

## Notas técnicas

- La autenticación usa JWT: el token se guarda en `localStorage` y se envía como cabecera `Authorization: Bearer` en cada petición a la API.
- El idioma seleccionado también se persiste en `localStorage`.
- No hay dependencias externas más allá de las fuentes de Google Fonts.
