# Transiciones y acciones de fútbol — 1.5

Archivo: `ProyectoGol-1.5-actions.jar`. Minecraft 1.12.2 con Forge y las mismas dependencias de la versión anterior.

- Transición progresiva al retroceder desde el movimiento frontal o lateral: se mezclan las piernas y la orientación del cuerpo, manteniendo la fase de los pasos. También se suaviza la vuelta al movimiento frontal.
- Barrida con descenso, pierna de ataque extendida, pierna de apoyo recogida y recuperación. El ajuste de altura evita que las botas atraviesen el suelo durante el gesto.
- Tiro con preparación, extensión de la rodilla, acompañamiento y recuperación; tiro con comba con giro de cadera y recorrido lateral del pie.
- Pase con el interior del pie y una variante de toque corto al soltar el pase estando agachado. Se utiliza la acción de pase existente; no se añade una mecánica de conducción del balón.
- Salto con poses de subida, punto alto, descenso y absorción del aterrizaje, a partir del movimiento real del jugador.
- Atajada en estirada y recepción con los brazos, con transición a la postura de sostener el balón. Se respeta el pie elegido y la dirección de la estirada.
- Mezcla por jugador para entrar y salir de las acciones sin reutilizar la pose de otro jugador.

Se conservan las texturas, los dorsales y las uniones de las equipaciones. No cambian los controles, la física del balón ni los identificadores de las acciones de red. Se mantienen las duraciones originales de tiro, comba, pase, barrida y estirada.

Validación: compilación y reobfuscación correctas; 53 pruebas pasan. Se verificaron los hashes de los recursos originales, del sistema de dorsales y de los archivos de física/red protegidos. Se revisaron 540 fotogramas OpenGL con el modelo y la equipación reales. `Animaciones-1.5.mp4` muestra esa revisión fuera de una partida; falta comprobar el resultado dentro de Minecraft.

Instalación: retirar el JAR anterior de Proyecto Gol de `mods` y colocar este archivo. Mantener las mismas dependencias. En multijugador, actualizar cliente y servidor. El menú de mods debe mostrar la versión 1.5.

SHA-256 del JAR: `45f1579d14e9cfeec32b194edd522f7dd3d7545f5f3d205754db7671d2704688`.
