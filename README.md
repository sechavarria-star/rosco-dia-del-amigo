# El Rosco de la Amistad · HP Argentina

Juego estilo **Pasapalabra** para el **Día del Amigo** de HP, con temática de amistad y
alusiones al **9 de Julio** (Día de la Independencia argentina).

## Cómo se juega (modo evento)

1. Abrir `index.html` en cualquier navegador (doble clic alcanza, no necesita internet)
   y poner pantalla completa con **F11**.
2. Escribir el nombre del jugador o equipo, elegir un rosco y tocar **EMPEZAR EL ROSCO**.
3. El conductor lee la definición en voz alta; el jugador responde de viva voz.
4. El conductor marca con los botones o el teclado:

   | Acción | Botón | Teclas |
   |---|---|---|
   | Acierto | ✔ verde | `A` o `↑` |
   | Error | ✘ rojo | `E` o `↓` |
   | Pasapalabra | amarillo | `Espacio` o `→` |
   | Ver/ocultar respuesta | 👁 | `V` |
   | Pausa | ⏸ | `P` |

5. Hay **2:30** en el reloj. La respuesta se revela sola al marcar acierto o error.
6. Al terminar se muestra el resumen y el puntaje queda en la **Tabla del día**
   (guardada en `localStorage` de esa computadora).

## Contenido

- Dos roscos completos de 27 letras (A–Z con Ñ) definidos en `const ROSCOS` dentro de
  `index.html`: **Rosco Celeste** y **Rosco Blanco**. Cada segundo jugador puede usar el
  otro rosco para que no se sepan las respuestas.
- Para editar definiciones basta modificar ese array (campos: `l` letra, `t`
  `empieza`/`contiene`, `d` definición, `r` respuesta).

## Notas

- Un solo archivo, sin backend ni dependencias (mismo patrón que el amigo invisible y la
  cartelera Work & Fun). Marca HP: Electric Blue `#024AD8`, Orange Bloom `#FF5050`.
- Sonidos generados con WebAudio (sin archivos); se silencian con el botón 🔊.
- Para borrar la tabla del día: consola del navegador →
  `localStorage.removeItem("rosco-hp-ranking-v1")`.
