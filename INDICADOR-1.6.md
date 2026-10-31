# Indicador del balón — 1.6

Archivo: `ProyectoGol-1.6-ball-indicator.jar`.

En **Opciones de Proyecto Gol**, desplázate hasta **Localizar balón**, activa **Indicador del balón** y pulsa **Guardar**. La opción empieza desactivada y se guarda en `mods/mod_Sports.properties`, junto con tus preferencias actuales.

- Durante un partido, una marca señala el balón cuando está en pantalla.
- Cuando queda fuera de la vista, una flecha en el borde indica su dirección. La etiqueta muestra la distancia en metros.
- Se sigue el balón oficial del partido. El servidor envía su posición cuatro veces por segundo; el cliente interpola las actualizaciones y utiliza la posición del balón renderizado cuando está disponible. También funciona fuera del alcance de seguimiento de entidades del cliente.
- El indicador desaparece al terminar el partido, al ocultar la interfaz con F1, al abrir menús o al desactivar la opción. Las actualizaciones caducan para evitar marcas antiguas al cambiar de mundo o perder la conexión.
- Se conservan las equipaciones, los dorsales, las animaciones y la física de 1.5.2. Los mensajes de red existentes mantienen sus formatos; se añade un mensaje para la posición del balón.

**En multijugador hay que actualizar tanto el cliente como el servidor a 1.6**, porque la localización del balón la proporciona el servidor. Sustituye el JAR anterior de Proyecto Gol y mantén las mismas dependencias.

Validación: compilación y reobfuscación correctas; 76 pruebas pasan. Incluyen proyección en pantalla y detrás de la cámara, distintas escalas de interfaz, cambios de balón/dimensión, caducidad, serialización del nuevo mensaje y guardado/carga de la opción sin perder los ajustes anteriores. Se revisaron los símbolos reales del HUD en OpenGL sin errores. `Indicador-balon-1.6.png` es un esquema de esa revisión, no una captura de una partida. Falta la comprobación dentro de Minecraft.

SHA-256: `de0106f920b3b7896c6ab9c8f1e14c855a8fddc096a7c1aeecc8a4e833f5c52f`.
