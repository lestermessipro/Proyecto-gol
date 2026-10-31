# Ajustes de brazos y retroceso — 1.4.1

Archivo: `ProyectoGol-1.4.1-arms-backpedal.jar`.

- Brazos con balanceo continuo más corto, menor apertura y codos más relajados. Las manos permanecen por debajo del pecho en el trote y el sprint, conservando la diferencia de intensidad.
- Retroceso propio, detectado por la dirección real del desplazamiento respecto al cuerpo, incluidas diagonales: pasos bajos y cortos, apoyos solapados sin fase de vuelo y brazos de equilibrio. No reutiliza el ciclo de carrera hacia delante.
- El torso sigue orientado hacia delante al retroceder y se restaura su orientación después de dibujar al jugador. La transición de dirección se mezcla sin reiniciar la zancada.
- Se conservan texturas, dorsales, articulaciones, tobillos, física y sincronización de la versión anterior.

Compilación y reobfuscación correctas. Pasan 35 pruebas, incluidas dirección del retroceso, altura del pie, transición y altura de las manos. La comprobación de controles y acabado visual dentro de una partida queda pendiente.

Instalación: sustituir el JAR anterior de Proyecto Gol por este; mismas dependencias. En multijugador, actualizar cliente y servidor. En el menú de mods debe aparecer versión 1.4.1.
