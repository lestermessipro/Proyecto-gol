# Proyecto Gol 1.6.3-test3 — pase/regate restaurado

> Sustituida por [TEST4](MARCADOR-1.6.3-test4.md): mantiene este pase/regate y actualiza el marcador y los iconos de inventario de Estudiantes.

Esta versión **revierte los cambios de conducción, recepción y animaciones introducidos en 1.6.3-test1**. El pase/regate vuelve al comportamiento de **1.6.2 oficial**.

[Descargar ProyectoGol-1.6.3-test3-estudiantes.jar](https://github.com/lestermessipro/Proyecto-gol/raw/refs/heads/test-1.6.3-estudiantes/ProyectoGol-1.6.3-test3-estudiantes.jar)

- Restaurados el impulso, la elevación, la dispersión, las ventanas de entrada y las animaciones anteriores del pase/regate.
- Eliminados la amortiguación de recepción, el ajuste del impulso según el avance, las animaciones de contacto confirmado por el servidor y el muestreo experimental del movimiento.
- Se mantienen **Estudiantes de La Plata**, su uniforme, escudo, nombre y dorsal, y **los escudos de los cinco clubes en el marcador**. Los recursos y el código de estas funciones coinciden con TEST2.
- La versión oficial continúa siendo 1.6.2; esta publicación permanece en la rama de pruebas `test-1.6.3-estudiantes`.

## Validación

Compilación desde cero y reobfuscación correctas; **120 pruebas JUnit**, sin fallos ni pruebas omitidas. Se retiraron las 15 pruebas específicas del control experimental descartado.

Se compararon los archivos compilados con el JAR oficial 1.6.2: las 17 clases de fútbol, entrada y animación comprobadas coinciden byte por byte. El método completo de actualización de controles del HUD también coincide con sus fuentes de 1.6.2. El JAR ya no contiene las clases `ManualTouch`.

Las 172 clases de equipaciones, marcador y gestión de partidos comprobadas, y los 144 recursos anteriores ajenos a los metadatos, coinciden con TEST2. El detalle está en [Revision-reversion-test3.json](Revision-reversion-test3.json); [Reversion-control-test3.patch](Reversion-control-test3.patch) recoge la reversión sobre las fuentes recuperadas de TEST2.

No se ha ejecutado una partida nueva en este entorno. Se conservan las vistas del [uniforme de Estudiantes](Estudiantes-test2.png) y del [marcador](Marcador-test2.png), que mantienen el mismo aspecto.

## Instalación

Sustituye TEST1 o TEST2 por este JAR **en cliente y servidor**. Mantén Minecraft 1.12.2, Forge, Player API y Render Player API, y carga una sola versión de Proyecto Gol. El menú de mods debe mostrar **1.6.3-test3**.

Estudiantes sigue disponible en los ajustes del partido y mediante `/match team select A estudiantes` o `/match team select B estudiantes`.

SHA-256: `7ac313f7d8d75cf3537f16c2a18347135109371439d1db9d746271b09878b444`.
