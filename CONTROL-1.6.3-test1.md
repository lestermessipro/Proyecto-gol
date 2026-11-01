# Proyecto Gol 1.6.3-test1 — conducción y recepción

> Esta prueba fue descartada. [TEST3](ESTUDIANTES-1.6.3-test3.md) restaura el pase/regate de 1.6.2 y conserva Estudiantes y los escudos del marcador.

Versión de prueba basada en **1.6.2 oficial** (`8436aa4`). Se publica en la rama `test-1.6.3-control`. La versión oficial y la rama principal siguen en 1.6.2.

[Descargar ProyectoGol-1.6.3-test1-control.jar](https://github.com/lestermessipro/Proyecto-gol/raw/refs/heads/test-1.6.3-control/ProyectoGol-1.6.3-test1-control.jar)

## Cómo se usa

Se usa el mismo botón de **pase/regate**, con su sensibilidad habitual. Una pulsación de carga suave da un toque de control; una carga mayor conserva el pase anterior. No hay botones adicionales ni conducción automática.

- **Conducción:** el toque suave sobre el césped sale en la dirección horizontal de la mirada, con un pequeño impulso adicional al avanzar. El ajuste aumenta con la velocidad de avance; caminar hacia atrás o moverse perpendicularmente a la mirada no lo aumenta.
- **Recepción:** cuando el balón llega hacia el jugador, un toque suave amortigua su salida y permite orientarlo con la mirada. El balón debe llegar a la zona de contacto habitual; no se atrae desde lejos.
- **Trayectoria:** los controles bajos eliminan la elevación añadida de la función de tiro y su dispersión aleatoria. Una pelota que baja cerca de los pies conserva una pequeña velocidad vertical amortiguada.
- **Animación:** hay gestos cortos de toque y recepción, con ambos pies y combinados con la carrera. Comienzan al recibir la confirmación del contacto del servidor, incluidas las recepciones preparadas con antelación. Una confirmación tardía no sustituye un tiro, barrida o atajada que el jugador haya empezado después.

El balón queda libre después de cada toque. Se mantiene la pausa existente de **10 ticks (medio segundo a 20 TPS)** entre contactos de pase/regate y la ventana anterior de espera del balón. La carga fuerte, los tiros normales y con comba, las atajadas y las reglas del partido conservan su comportamiento anterior. Las equipaciones, escudos, dorsales e indicador de balón se mantienen.

## Alcance de esta prueba

El nuevo cálculo de impulso se aplica a cargas de hasta **18**, con el jugador apoyado y el balón en la zona baja, hasta 0,9 bloques por encima de sus pies. Las cargas mayores, los balones altos y los saques desde las manos utilizan el impulso anterior. El ajuste de avance se reduce progresivamente hasta cero al llegar a ese límite, conservando la continuidad con el pase cargado.

La velocidad de avance se obtiene de posiciones sucesivas del jugador en el servidor, con suavizado y descarte de teletransportes o cambios de dimensión. No se confía en que los campos de velocidad del jugador contengan su desplazamiento al caminar.

No cambia el formato de los paquetes existentes ni sus identificadores. Se añaden dos animaciones al final de la lista, sin desplazar las anteriores; **cliente y servidor deben usar esta versión test**.

## Validación y límites

- Compilación y reobfuscación correctas; **125 pruebas JUnit**, sin fallos ni pruebas omitidas.
- Pruebas de dirección, amortiguación, continuidad de la carga, avance, rechazo de entradas inválidas, muestreo de movimiento y recuperación de las animaciones sin cortar la zancada.
- Comparación con la física real de `EntitySoccer` sobre un suelo de césped de pruebas: toque en parado, carrera, sprint y recepción frontal. También se verificó que las animaciones terminan aunque no se dibuje el modelo del jugador. Datos en [Revision-control-1.6.3-test1.json](Revision-control-1.6.3-test1.json).
- Los recursos de las equipaciones y las clases de su renderizado coinciden con 1.6.2. El código de tiros, reglas, dorsales e interpolación del balón conserva su base anterior.

**Falta una partida real y una sesión multijugador con latencia.** La confirmación de contacto depende de la conexión; esta prueba no incluye predicción ni compensación nueva de latencia. Conviene comprobar especialmente la fuerza de los toques al sprintar y la respuesta al preparar una recepción.

## Instalación

Sustituye el JAR de Proyecto Gol por este en `mods`, **en cliente y servidor**, manteniendo Minecraft 1.12.2, Forge, Player API y Render Player API. Carga una sola versión del mod. El menú de mods debe mostrar **1.6.3-test1**. Para volver a la oficial, sustituye este archivo por `ProyectoGol-1.6.2.jar` en ambos lados.

[Cambios-control-1.6.3-test1.patch](Cambios-control-1.6.3-test1.patch) contiene las modificaciones respecto a las fuentes recuperadas de 1.6.2.

SHA-256: `69bc546a52ab8e7b4ad0c055917d4a616cdfd8c3f3d475ef85bcc163c008a4bf`.
