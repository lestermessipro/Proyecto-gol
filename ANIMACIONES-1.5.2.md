# Camiseta de River y dorsales integrados — 1.5.2

Archivo: `ProyectoGol-1.5.2-river-dorsales.jar`.

- Camiseta de River sustituida por `river_plate.png`, el PNG de 64×32 que subiste. El archivo se incorpora al mod sin modificar sus píxeles ni su transparencia. Se conserva el pantalón de River.
- Nombres y dorsales situados junto a la superficie real de la camiseta, para reducir la separación visible al mirarlos de lado.
- El estampado recibe la misma iluminación que el uniforme y se oscurece con él en la sombra. Se evita el parpadeo entre la tela y las letras.
- Se conserva la asignación de nombres y números del sistema de dorsales. Las animaciones y la física permanecen como en 1.5.1.

Validación: compilación y reobfuscación correctas; 60 pruebas pasan. El PNG incluido en el JAR coincide byte por byte con el original subido a GitHub. Se verificaron los demás recursos, el registro de dorsales y los archivos de animación/física protegidos. Se revisó el modelo en OpenGL por delante y por detrás, con brazos normales y finos, y con distintas iluminaciones. `Vista-River-1.5.2.png` muestra el modelo fuera de una partida; falta comprobarlo dentro de Minecraft.

Instalación: sustituir el JAR anterior de Proyecto Gol por este y mantener las mismas dependencias. En multijugador, actualizar cliente y servidor. El menú de mods debe indicar 1.5.2.

SHA-256 del JAR: `2cb0b0db522bc44f0fd1d9b9277ef76c1ffd90f5762a111687b7cf695542225b`.
