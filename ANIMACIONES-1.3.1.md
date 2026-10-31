# Corrección de articulaciones y sprint — 1.3.1

Archivo: `ProyectoGol-1.3.1-sprint-fix.jar`.

- Las caras internas de codos y rodillas continúan la fila de textura contigua a la unión, en lugar de reutilizar la zona del hombro o pie del atlas. Se aplica a la piel y a la equipación.
- Los extremos internos de cada mitad dejan de inflarse en altura: ambas piezas se encuentran en el mismo plano al estar rectas, evitando collares superpuestos. Se conserva el grosor de las caras exteriores.
- Sprint con zancada más amplia, mayor recuperación de rodilla, impulso de brazos e inclinación del torso. Respuesta más rápida de las extremidades para conservar la amplitud de movimiento; el cuerpo mantiene una transición suave. El impulso vertical coincide con la fase de vuelo.
- Texturas originales, asignación de dorsales, nombres y dependencias conservados.

Compilación completa y 17 pruebas automáticas correctas, incluidas comprobaciones de geometría/UV, amplitud del sprint a 30/60/120 FPS y aislamiento de poses entre jugadores. No se ha realizado comprobación gráfica ni una partida: falta confirmar visualmente esta corrección con el usuario.

Para instalar: retirar el JAR anterior de Proyecto Gol de `mods` y poner únicamente el nuevo. Usar las mismas dependencias. Las versiones anteriores permanecen disponibles en el repositorio.
