# Indicador fuera de pantalla y movimiento del balón — 1.6.1

Archivo: `ProyectoGol-1.6.1-smooth-ball.jar`.

- El indicador aparece únicamente cuando el balón queda fuera de la pantalla. Al volver a entrar se ocultan la flecha y la distancia. El margen usado para colocar la flecha ya no hace que aparezca mientras el balón siga visible cerca de un borde.
- Corregido el avance de la posición desde el renderizado: se consumían pasos de interpolación al dibujar cada fotograma, además de las actualizaciones del juego. Esto hacía que el movimiento dependiera de los FPS y alternara entre saltos y pausas.
- La posición del cliente avanza una sola vez por tick; el renderizado dibuja la posición interpolada entre ticks. La interpolación se adapta a la frecuencia de los paquetes recibidos para evitar un retraso permanente de tres ticks con las actualizaciones habituales del servidor.
- Corregido el filtro de giro que descartaba desplazamientos legítimos de más de dos bloques por fotograma en tiros rápidos a pocos FPS. Se conserva un filtro para saltos grandes de posición.

Se conservan la opción **Localizar balón**, sus ajustes guardados, las equipaciones, los dorsales y las animaciones del jugador. La simulación física del servidor y los formatos de los mensajes de red permanecen como en 1.6.

Validación: compilación y reobfuscación correctas; 88 pruebas pasan. Se comprobó la misma trayectoria interpolada a 15, 30, 60 y 120 FPS, el avance una sola vez por tick, las distintas frecuencias de paquetes, el giro de tiros rápidos, el balón en las manos y las transiciones del indicador en los bordes reales de la pantalla. La revisión OpenGL comprueba que no se dibuja ninguna marca con el balón en pantalla y que las flechas aparecen fuera de ella. Falta la comprobación dentro de una partida.

Instalación: sustituir el JAR anterior de Proyecto Gol por este y mantener las mismas dependencias. En multijugador, actualizar cliente y servidor. El menú de mods debe mostrar 1.6.1.

SHA-256: `020764ca984efe5a50243ce690a1b7232c2f5468fd510b1d9a8c7da3e34fb970`.
