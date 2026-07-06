# Rosco HP · Día del Amigo

Juego estilo **Pasapalabra** para el **Día del Amigo** de HP Argentina, con temática
100% de amistad.

## Cómo se juega (modo evento, dos ventanas)

Hay dos vistas sincronizadas en vivo (sin backend, via BroadcastChannel/postMessage):

- **Ventana del conductor** (`index.html`): definiciones, la **respuesta correcta siempre
  visible**, la próxima letra con su respuesta en chico, y los botones de marcado.
  ⚠️ Esta ventana NO se proyecta.
- **Pantalla del público** (`index.html?display`): el rosco gigante con los KPIs
  (reloj, aciertos, errores) y la definición actual debajo (nunca la respuesta).
  Es la que va al proyector/TV.

Pasos:

1. Abrir `index.html` en el navegador (doble clic alcanza, no necesita internet).
2. Tocar **🖥 Abrir pantalla del público** → se abre la segunda ventana: arrastrarla al
   proyector y poner pantalla completa con **F11**.
3. Escribir el nombre del jugador o equipo, elegir un rosco y tocar **EMPEZAR EL ROSCO**.
4. El conductor lee la definición en voz alta (la ve junto con la respuesta); el jugador
   responde de viva voz. Se marca con botones o teclado:

   | Acción | Botón | Teclas |
   |---|---|---|
   | Acierto | ✔ verde | `A` o `↑` |
   | Error | ✘ rojo | `E` o `↓` |
   | Pasapalabra | amarillo | `Espacio` o `→` |
   | Pausa | ⏸ | `P` |

   La pantalla del público muestra la definición actual debajo del rosco (sin la
   respuesta); la tecla `D` la oculta/muestra.
5. Hay **2:30** en el reloj. Al marcar, la respuesta del conductor se pinta verde/roja y
   se pasa a la siguiente letra pendiente.
6. Al terminar, ambas ventanas muestran el resumen y el puntaje queda en la
   **Tabla del día** (guardada en `localStorage` de la compu del conductor).

## Contenido

- **Cinco roscos completos** de 27 letras (A–Z con Ñ) definidos en `const ROSCOS` dentro
  de `index.html` (**Rosco 1** a **Rosco 5**): uno distinto para cada equipo, así ningún
  equipo escucha las respuestas del suyo antes de jugar. En la pantalla de inicio, los
  roscos ya jugados quedan marcados con "ya jugado".
- Para editar definiciones basta modificar ese array (campos: `l` letra, `t`
  `empieza`/`contiene`, `d` definición, `r` respuesta).

## Notas

- Un solo archivo, sin backend ni dependencias (mismo patrón que el amigo invisible y la
  cartelera Work & Fun). Marca HP: Electric Blue `#024AD8`, Orange Bloom `#FF5050`.
- Sonidos generados con WebAudio (sin archivos); se silencian con el botón 🔊.
- Para borrar la tabla del día: consola del navegador →
  `localStorage.removeItem("rosco-hp-ranking-v1")`.
