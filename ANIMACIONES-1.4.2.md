# Brazos dinámicos y postura erguida — 1.4.2

Archivo: `ProyectoGol-1.4.2-dynamic-arms.jar`.

- Mayor recorrido de hombros y brazos tanto en el trote como en el sprint.
- Los codos se abren en el movimiento hacia atrás y se flexionan al avanzar, con un pequeño desfase para dar continuidad e inercia al gesto. La apertura y orientación de los hombros también varían durante el ciclo.
- Torso más erguido: inclinación base del sprint reducida de aproximadamente 19° a 7°; la carrera normal queda casi vertical. Se reduce ligeramente el descenso de la pelvis en apoyo, conservando la altura de la suela mediante el cálculo de las piernas.
- Se conserva el retroceso de 1.4.1, las texturas, los dorsales y las uniones de las articulaciones.

Compilación y reobfuscación correctas. Pasan 36 pruebas, incluidas amplitud de hombros/codos, postura y apoyos del pie. Se revisaron muestras de ambos ciclos renderizados con el modelo y las equipaciones reales en OpenGL. La prueba de una partida queda pendiente.

Instalación: sustituir el JAR anterior de Proyecto Gol; mismas dependencias. En multijugador, actualizar cliente y servidor. El menú de mods debe indicar 1.4.2.
