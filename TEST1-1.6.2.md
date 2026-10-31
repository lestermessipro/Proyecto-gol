# Proyecto Gol 1.6.2-test1

Versión experimental basada en **1.6.1** (`d1402b6`). Se distribuye en la rama `test-1.6.2-test1`; la rama principal y el JAR 1.6.1 se conservan.

[Descargar ProyectoGol-1.6.2-test1.jar](https://github.com/lestermessipro/Proyecto-gol/raw/refs/heads/test-1.6.2-test1/ProyectoGol-1.6.2-test1.jar)

## Correcciones

- Los eventos de renderizado y de cliente se procesan una sola vez, al terminar cada fotograma o tick. Antes se atendían tanto al principio como al final.
- El consumo y la recuperación de resistencia, la ventana de carga perfecta y los avisos del HUD usan el tiempo transcurrido del temporizador existente de 100 Hz. Antes contaban llamadas al HUD y dependían de los FPS. La resistencia y la duración de los avisos pueden sentirse diferentes respecto a 1.6.1, especialmente con pocos FPS.
- La barra de potencia conserva la carga mientras se mantiene pulsado el botón y se oculta después de soltarlo. Antes podía borrarse durante la carga.
- Las opciones rechazan índices fuera de rango y normalizan valores negativos, excesivos, NaN o infinitos. Se corrige también el cambio hacia atrás entre modos del HUD y la creación del directorio de ajustes cuando falta.
- Al conectar o desconectar se limpian el marcador, los datos temporales del campo y las referencias a jugadores remotos. El HUD deja de conservar cargas y acciones de una sesión anterior; la referencia al jugador local se actualiza cada tick.
- La recepción de mensajes usa el lado del canal de red. Se ignoran mensajes vacíos, desconocidos o truncados, identificadores de animación/deporte inválidos y valores no finitos en los controles. Los mensajes pendientes del canal GCA se descartan si pertenecen a otro mundo.
- Un cliente ya no puede reenviar estados inventados de recoger o soltar el balón: esos avisos proceden del servidor. Los identificadores y formatos de los paquetes existentes se mantienen.

## Optimización

- El balón **Lowpoly (hexágonos)** agrupa su geometría en un único lote de triángulos y lo reutiliza. Mantiene los colores, las normales y la forma originales.
- Se elimina una copia del búfer al enviar mensajes GCA y se libera el búfer si falla su codificación.
- Se elimina la construcción repetida de un texto de depuración que no se mostraba.

La comparación aislada del balón usa OpenGL por software (`llvmpipe`), 1000 dibujos por ronda y la mediana de cinco rondas. El tiempo pasó de **143,745 a 129,088 microsegundos por dibujo**, aproximadamente un **10 % menos**. Las llamadas Java a OpenGL por malla pasan de 308 a una tras crear la caché. Esta medición corresponde únicamente a esa malla: no mide los FPS de Minecraft ni garantiza una mejora equivalente en una tarjeta gráfica. Los resultados completos están en [Rendimiento-TEST1.json](Rendimiento-TEST1.json).

## Validación

- Compilación, reobfuscación y comprobación de integridad del JAR correctas.
- **106 pruebas JUnit**, sin fallos ni pruebas omitidas, incluidas las regresiones existentes de animaciones, equipaciones, interpolación del balón e indicador.
- **20 comparaciones de imagen exactamente iguales** entre el balón lowpoly de 1.6.1 y TEST1: cuatro paletas y cinco orientaciones. Sin errores OpenGL.
- Comprobación de una llamada de renderizado por fotograma y una actualización de cliente por tick, reinicio del HUD y conservación/expiración de la barra de carga.
- Se conservaron los 132 recursos empaquetados ajenos a los metadatos y al manifiesto, incluida la textura de River suministrada. El manifiesto mantiene la configuración Mixin. El código de animaciones, la simulación física del servidor, las reglas y el registro de dorsales permanecen como en 1.6.1.

**Pendiente:** probar una partida real y una sesión multijugador con servidor dedicado. Las comprobaciones automatizadas y de OpenGL no sustituyen esa prueba.

El archivo [Cambios-TEST1.patch](Cambios-TEST1.patch) permite revisar las modificaciones de código y las nuevas pruebas respecto a las fuentes recuperadas de 1.6.1. Es un parche incremental de esas fuentes; la rama principal del repositorio distribuye los JAR y no contiene ese árbol completo de fuentes.

## Instalación y prueba

1. Usa Minecraft 1.12.2 con Forge y las mismas dependencias que en 1.6.1: Player API y Render Player API.
2. Sustituye el JAR anterior de Proyecto Gol en `mods` por `ProyectoGol-1.6.2-test1.jar`. Carga una sola versión del mod. El menú de mods debe mostrar **1.6.2-test1**.
3. En multijugador, actualiza cliente y servidor a TEST1.
4. Comprueba correr y recuperar resistencia, cargar/soltar pases y tiros, la carga perfecta, barridas, saltos y atajadas. Revisa las opciones del HUD, el indicador fuera de pantalla y el modo lowpoly; después desconecta y vuelve a entrar para comprobar marcador y dorsales.

Para volver a 1.6.1, sustituye únicamente el JAR de TEST1 por el anterior, también en el servidor si lo utilizas. Se conservan los formatos de configuración y de guardado existentes.

SHA-256 del JAR: `f0347bcb179bbae6418e7b7534e0c8be4b091dbd4aa838baaa0bc295f7dfd2e7`.
