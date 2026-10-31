# Locomoción 1.4: trote y sprint con ciclos distintos

- Mod: [ProyectoGol-1.4-grounded-motion.jar](ProyectoGol-1.4-grounded-motion.jar).
- [Comparación renderizada de las dos animaciones](Comparacion-animaciones-1.4.mp4).

La carrera normal usa una postura erguida, brazos más relajados y un apoyo más largo. El sprint de «Correr» (K por defecto, reasignable) y el sprint de Minecraft usan otra secuencia: impulso de brazos, torso inclinado, recuperación alta de la rodilla y mayor fase de vuelo. La cadencia cambia progresivamente sin reiniciar los pasos.

Los ciclos se dividen en contacto, impulso y recuperación, en lugar de aplicar el mismo balanceo con amplitudes diferentes. Una pierna permanece en apoyo aproximadamente el 44 % de su ciclo en el trote y el 30 % en el sprint. La cinemática inversa mantiene la altura de la suela durante el apoyo sobre el plano base del jugador. Se articulan también los tobillos, con apoyo de talón/punta, y se estabiliza la orientación de la cabeza sin separarla del torso. La intensidad responde al desplazamiento real; la entrada en movimiento y el retorno a reposo se mezclan suavemente.

Piel y equipación comparten codos, rodillas, tobillos y desplazamiento vertical. Las articulaciones incorporan superficies que conectan los segmentos al doblarse, utilizando su propia textura; las tapas interiores dejan de quedar expuestas. Los guantes acompañan el antebrazo articulado. Se conservan las correcciones de las uniones de 1.3.1 y la sincronización de sprint de 1.3.2.

Las imágenes de todas las equipaciones, las texturas de dorsales y su sistema de asignación/nombres se conservan. Los metadatos de Sports se actualizan a versión 1.4; los autores, créditos y demás metadatos se mantienen.

## Validación

Compilación, empaquetado y reobfuscación correctos. Pasan 30 pruebas: apoyos y límites articulares, separación entre los dos ciclos, continuidad y transiciones, mezcla a distintas tasas de fotogramas, cabeza/hombros, articulaciones de la equipación, geometría/UV, reglas y paquetes de sprint. Se verifican los hashes de los recursos y el código de dorsales; el único cambio de contenido de recursos es la versión en `mcmod.info`.

Se renderizaron las geometrías y las equipaciones reales del proyecto en OpenGL, usando el mismo cálculo de pose y transformación de la locomoción que el renderizador del mod. Se revisaron secuencias de ambos ciclos y las cinco equipaciones, incluidas variantes de brazos estrechos. El vídeo de nueve segundos es una revisión del modelo fuera del juego: no es una grabación de Minecraft ni sustituye la prueba de una partida, de los controles o del multijugador.

La altura de apoyo se calcula respecto a un plano liso; no es un sistema de detección de desniveles ni un bloqueo horizontal del pie sobre el terreno. Se mantiene la física existente del desplazamiento. Los tiros y celebraciones mantienen sus secuencias actuales.

## Instalar

Retirar de `mods` el JAR anterior de Proyecto Gol y colocar únicamente el nuevo, con las mismas dependencias. En multijugador, actualizar clientes y servidor. En el menú de mods, Sports/Proyecto Gol debe figurar como versión **1.4**. No instalar varios JAR de Proyecto Gol simultáneamente.
