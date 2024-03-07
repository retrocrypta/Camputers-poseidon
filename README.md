# Camputers Lynx
Camputers Lynx 48 / 96 core de Kyp portado a Poseidon

Solo tiene el BASIC y queda pendiente hacer la carga por audio.

Hay que tener muy claro que hay tres modelos, 48, 96 y 128 KB. Hay que matizar que El 96k es compatible con el 48k, pero cuidado que el 128k no lo es completamente y tiene sus movidas. Básicamente y si no me equivoco puedes cargar CP/M tanto en el 96K como en el 128K y es de suponer que el 128 incorpora los nuevos modos de video. En cuanto a video lleva un CRTC6845.

Hay 8 colores disponibles. Cada pixel es de color independiente del resto. Para modificar un pixel hay que escribir en 3 bytes (Rojo, Verde y Azul), lo que lo hace tedioso y monotono aparte de lento. El modo de display es planar. En realidad no hay tres sino cuatro planos : rojo, verde, azul y ''verde alternativo''. Por si fuera poco, los tres planos no pueden mapearse al mismo tiempo lo que provoca que por cada pixel se realicen dos intercambios de bancos.

Por eso mismo carece de scroll (simplemente, limpia toda la pantalla y vuelve a pintarla), a menos que el programador recurra al código máquina y a la programación en bajo nivel del Motorola 6845. Pero incluso esto es complicado porque el scroll del 6845 se hace con una granularidad de 8x4 pixels y el Lynx tiene una matriz de caracteres de 6x10.

La resolución de texto es por ello de 40x24x8. En realidad es de 42x24, pero la máquina no utiliza la primera y última columna para texto y no usa correctamente la visualización en pantalla debido a su inusual tamaño de matriz de caracteres.

De acuerdo con las especificaciones del 6845, los 127 caracteres ASCII pueden ser redefinidos. El BASIC tiene un buen soporte de gráficos.

Es un ordenador cuyo diseño se adelantó a su tiempo, y el hardware no estaba a la altura (velocidad de CPU y chip de vídeo) de la filosofía de su concepción. Creo que es el único 8bits cuya gestión del color se hace a base de planos de bits, tiene cuatro planos de memoria, uno para cada color. Con ésto se consigue que cada pixel pueda tener un color diferente del otro, pero hace que la gestión de pantalla sea lenta y un poco engorrosa, aunque he leido que accediendo mediante código máquina se puede hacer verdaderas virguerías.
