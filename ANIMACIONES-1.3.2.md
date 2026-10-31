# Carrera pulida y sprint específico — 1.3.2

Archivo: `ProyectoGol-1.3.2-sprint-animation.jar`.

- Trote normal con mayor flexión de brazos y recuperación de piernas.
- Sprint diferenciado al activar «Correr» (K por defecto, reasignable en controles) o el sprint normal de Minecraft. Aumenta cadencia, inclinación, zancada y empuje de brazos.
- Entrada y salida graduales del sprint manteniendo la fase de los pasos. El ciclo avanza con el desplazamiento y no se reinicia al pulsar o soltar la tecla. Las poses no se comparten entre jugadores.
- Se conserva el modo Mantener/Alternar existente. Agacharse o montar no activa el trote personalizado.
- El servidor comunica a los demás jugadores la activación de «Correr», también cuando empiezan a ver a alguien que ya corre. La sincronización visual no cambia la velocidad ni la resistencia.
- Las texturas, dorsales y correcciones de las uniones de 1.3.1 se conservan.

Compilación completa y 24 pruebas automáticas correctas: geometría/UV, articulaciones, fases/transiciones, mezcla a 30/60/120 FPS, reglas del partido, codificación y orden de paquetes. El intercambio real entre clientes y servidor y el resultado visual requieren prueba en Minecraft.

Instalación: retirar el JAR anterior de Proyecto Gol y colocar únicamente este, conservando las mismas dependencias. En multijugador, actualizar tanto servidor como clientes a esta versión para la nueva sincronización de sprint.
