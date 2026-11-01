# Proyecto Gol 1.6.3-test5 — marcador más pequeño

[Descargar ProyectoGol-1.6.3-test5-marcador.jar](https://github.com/lestermessipro/Proyecto-gol/raw/refs/heads/test-1.6.3-estudiantes/ProyectoGol-1.6.3-test5-marcador.jar)

El marcador se reduce un **30 % en ancho y alto** respecto a su tamaño habitual en TEST4: la escala máxima pasa de 1,00 a 0,70. Se conservan el diseño, los colores, las proporciones y el ajuste adicional a pantallas pequeñas.

Los iconos de Estudiantes, los uniformes y el pase/regate de 1.6.2 se mantienen. La comparación de JAR confirma que solo cambian la escala del marcador y los datos de versión.

Compilación y reobfuscación correctas; **125 pruebas**, sin fallos ni pruebas omitidas. El cambio de código está en [Reducir-marcador-test5.patch](Reducir-marcador-test5.patch).

Sustituye el JAR anterior **en cliente y servidor**, manteniendo las mismas dependencias y una sola versión de Proyecto Gol. El menú de mods debe mostrar **1.6.3-test5**. La oficial sigue siendo 1.6.2.

SHA-256: `043d8013347d3acfce5f1ec5d837cbf64218b63865419ec9ccdd90ef7f74363b`.
