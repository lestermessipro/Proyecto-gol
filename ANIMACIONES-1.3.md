# Animaciones y equipaciones — primera versión de prueba

Archivo: `ProyectoGol-1.3-animations-preview.jar`.

- Carrera y caminata con un ciclo continuo ligado al desplazamiento, rodillas flexionadas durante la recuperación, menor oscilación del torso y brazos flexionados.
- Respuesta suave calculada por tiempo transcurrido, con pruebas a 30 y 120 FPS.
- Tiros, pases y tiros con efecto con flexión de la pierna de golpeo y apoyo; barrida con pierna de arrastre doblada. Se conservan los tiempos y eventos de las acciones.
- Equipaciones articuladas en codos y rodillas que reutilizan la pose del jugador, también durante celebraciones existentes.
- Camiseta más ajustada, pantalón y medias con volúmenes distintos; mangas adaptadas a Steve y Alex. La capa exterior de la skin se oculta bajo la equipación para evitar que atraviese la ropa.
- Texturas originales, colores y sistema de nombres/dorsales sin cambios; se verifican sus hashes. Se conserva la disposición UV de las equipaciones de 64×32.

No es todavía una sustitución completa de todas las animaciones: las celebraciones, caídas y estiradas conservan sus secuencias actuales. La nueva articulación permite que las equipaciones las acompañen. Hace falta revisar visualmente esta primera versión en Minecraft y ajustar movimientos y silueta con el usuario.

Para probar: usar Minecraft 1.12.2 y las mismas dependencias de la versión anterior. Retirar el JAR anterior de la carpeta mods y colocar este; no instalar ambos simultáneamente. La versión anterior se conserva como alternativa.

No se ha ejecutado una partida ni una comprobación gráfica en este entorno. Las pruebas automatizadas verifican articulaciones, ausencia de poses arrastradas entre jugadores, continuidad de carrera y reglas del partido; no certifican el resultado visual.
