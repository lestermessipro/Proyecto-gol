# Tiros durante la carrera — 1.5.1

Archivo: `ProyectoGol-1.5.1-running-shots.jar`.

En 1.5, cargar o ejecutar un tiro sustituía la zancada por una pose completa y reiniciaba el ciclo de carrera. El jugador seguía desplazándose por el mundo con las piernas casi quietas, dando la impresión de deslizarse.

- El ciclo de pasos continúa durante la carga, el golpe y la recuperación, tanto en carrera normal como en sprint.
- La pierna que golpea utiliza una animación breve sobre la zancada; la pierna de apoyo sigue su recorrido y planta la bota durante el contacto.
- Los brazos mantienen parte de su balanceo. El torso acompaña el golpe y vuelve progresivamente a la carrera.
- La corrección se aplica al tiro normal, al tiro con comba y al pase. El toque corto también conserva el movimiento de carrera.
- Al tirar quieto se mantienen las poses de 1.5. La mezcla depende del desplazamiento real del jugador, con transición al arrancar o detenerse.

Se conservan las texturas, los dorsales, los controles, la física y las duraciones de las acciones. No se frena al jugador para ocultar el deslizamiento.

Validación: compilación y reobfuscación correctas; 60 pruebas pasan, incluidas las de apoyo del pie, continuidad de los pasos, contacto con ambas piernas y conservación de los tiros quietos. Se verificaron los recursos originales y los archivos protegidos de física/red. `Tiros-en-carrera-1.5.1.mp4` compara el comportamiento anterior con el corregido utilizando el modelo y las equipaciones en OpenGL; no es una captura de una partida. La comprobación dentro de Minecraft queda pendiente.

Instalación: sustituir el JAR anterior de Proyecto Gol por este, manteniendo las mismas dependencias. En multijugador, actualizar cliente y servidor. El menú de mods debe indicar 1.5.1.

SHA-256: `77eaf77bd33e2668b235053e7d942439795378aae85b8436b78b21b2c1562558`.
