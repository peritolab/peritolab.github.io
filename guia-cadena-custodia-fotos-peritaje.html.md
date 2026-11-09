# Cadena de custodia de las fotos del peritaje: la huella SHA-256

> Qué es la huella SHA-256 de una foto, qué demuestra y qué no, cómo calcularla en Windows sin instalar nada y cómo incluirla en el informe pericial.

Publicado el 9 de noviembre de 2026 · por el equipo de PeritoLab

Un informe pericial se apoya en sus fotos, y las fotos digitales tienen un punto débil: se pueden cambiar sin que se note. Si el informe acaba en una discusión con la otra compañía, en una reclamación o en un juicio, alguien puede preguntar si las fotos que presentas son las mismas que hiciste el día de la inspección. La forma más sencilla y aceptada de responder es la huella digital de cada archivo, el llamado hash SHA-256. Esta guía explica qué es, qué demuestra y qué no, cómo calcularla en Windows sin instalar nada y cómo incluirla en el informe.

## Qué es la huella SHA-256 de una foto

SHA-256 es un cálculo matemático que se hace sobre el contenido de un archivo y da como resultado una cadena de 64 letras y números, siempre de la misma longitud. Tiene dos propiedades que la hacen útil como prueba:

- **El mismo archivo da siempre la misma huella**, en cualquier ordenador y con cualquier programa.
- **Si cambia un solo dato del archivo, la huella cambia por completo**: un píxel, la fecha guardada dentro de la foto o un recorte. No hay forma práctica de modificar una foto y conseguir que conserve su huella.

Por eso, si apuntas la huella de cada foto el día que las descargas del móvil, cualquiera puede comprobar más adelante que siguen siendo exactamente las mismas: basta con volver a calcularla y ver que coincide.

## Qué demuestra la huella y qué no

Conviene no prometer más de la cuenta:

- **Sí demuestra** que el archivo no ha cambiado desde el momento en que se calculó la huella.
- **No demuestra** cuándo se hizo la foto ni quién la hizo. La fecha y el modelo del móvil van en los datos EXIF de la propia foto, que se pueden editar antes de calcular la huella.
- **No dice nada** de lo que pasó con la foto antes de calcularla. Por eso importa el momento: cuanto antes, mejor. Lo ideal es calcularla al pasar las fotos del móvil al ordenador, antes de tocar nada.

La huella es una pieza de la cadena de custodia, no toda. La completan el resto de cosas que ya haces bien: conservar los originales sin editar, guardar una copia en un sitio seguro y anotar en el informe quién hizo las fotos, cuándo y dónde.

## Qué cambia la huella y qué no

Esto es lo que más confusiones da en el día a día:

- **No la cambia** renombrar el archivo, moverlo de carpeta o copiarlo a otro disco: el contenido es el mismo.
- **Sí la cambia** cualquier cosa que vuelva a guardar la foto: comprimirla, girarla y guardarla, pasarla de HEIC a JPG, recortarla o [quitarle la ubicación GPS](https://peritolab.es/guia-quitar-gps-fotos.html).

La consecuencia práctica es importante: la huella hay que calcularla de las fotos que vas a conservar como prueba, y esas fotos no se tocan. Las copias que comprimes para la plataforma de la aseguradora tendrán otra huella, y es normal. Lo que puedas defender son los originales.

## Cómo calcularla en Windows, sin instalar nada

Windows trae dos formas de hacerlo.

**Con el símbolo del sistema**, foto a foto:

1. Abre la carpeta de las fotos en el Explorador, escribe `cmd` en la barra de direcciones y pulsa Intro. 2. Escribe `certutil -hashfile "IMG_2214.jpg" SHA256` con el nombre de tu foto. 3. La línea de 64 caracteres que aparece es su huella.

**Con PowerShell**, para toda la carpeta de una vez:

1. En la misma carpeta, escribe `powershell` en la barra de direcciones y pulsa Intro. 2. Escribe `Get-FileHash *.jpg` y pulsa Intro. 3. Sale una lista con la huella de cada foto. Para guardarla en un archivo de texto: `Get-FileHash *.jpg | Format-List > huellas.txt`.

Funciona igual con cualquier tipo de archivo (HEIC, PNG, vídeos). Lo que obtienes es una lista que tendrías que copiar después al informe, foto por foto, con el riesgo de equivocarte al pegar una huella en la fila que no es.

PeritoLab Matrículas puede añadir al reportaje en PDF una hoja con la huella SHA-256 de cada foto. [Ver cómo funciona →](https://peritolab.es/matriculas.html)

## Cómo incluirla en el informe

La huella sirve de poco si nadie sabe a qué foto corresponde. Una hoja de cadena de custodia útil tiene, para cada foto del reportaje:

1. **El número de la foto** en el informe, el mismo que citas en el texto («ver foto 7»). 2. **El nombre del archivo**, tal como está en tu archivo. 3. **La fecha y la hora** en que se hizo, si la foto la guarda. 4. **La huella SHA-256** completa, sin cortar.

Añade una línea que explique cómo se comprueba, para que quien lea el informe no tenga que preguntarte: por ejemplo, «la huella se puede comprobar en cualquier Windows con la orden certutil -hashfile "archivo" SHA256». Y guarda los archivos originales con el mismo nombre que aparece en la hoja: si mañana te piden las fotos, tienen que dar exactamente esas huellas.

Un último detalle: las huellas se copian a mano mal con mucha facilidad. Un solo carácter cambiado basta para que la comprobación falle y para que se ponga en duda todo lo demás. Si puedes, que la hoja la genere un programa y no la escribas tú.

## Que lo haga el programa al crear el reportaje

Si ya montas el reportaje fotográfico de cada vehículo con [PeritoLab Matrículas](https://peritolab.es/matriculas.html), la hoja de custodia sale con él. Al crear el informe en PDF puedes añadir, si quieres, una hoja con la huella SHA-256 de cada foto, junto a las páginas de fotos con su número, su pie, su fecha y hora y el nombre del archivo. Matrículas siempre trabaja sobre una copia: los originales se quedan como estaban, que es lo que una cadena de custodia necesita. Y todo se hace en tu ordenador, sin subir ninguna foto a internet.

Si aún montas el reportaje a mano, en la guía sobre el [reportaje fotográfico del informe pericial](https://peritolab.es/guia-reportaje-fotografico-pericial.html) tienes cómo elegir, ordenar y numerar las fotos antes de añadir la hoja.

## En resumen

- La huella SHA-256 demuestra que una foto no ha cambiado desde que se calculó; no demuestra cuándo se hizo.
- Calcúlala lo antes posible, sobre los originales, y no los toques después.
- En Windows: `certutil -hashfile "foto.jpg" SHA256` o `Get-FileHash *.jpg` para toda la carpeta.
- En el informe, una hoja con el número de cada foto, su nombre, su fecha y su huella, y cómo se comprueba.

**PeritoLab Matrículas**

Lee la matrícula de cada foto y deja la jornada separada en una carpeta por vehículo.

- Una carpeta por matrícula, con las fotos renombradas «2821MPF (1)», «(2)»…
- Lo que no está claro se marca para revisar: la última palabra es tuya.
- El reportaje fotográfico en PDF de cada vehículo, listo para el expediente.
- Todo en tu ordenador: las fotos no salen de él.

[Descargar · 30 días gratis](https://peritolab.es/descarga.html?app=matriculas) [Ver cómo funciona](https://peritolab.es/matriculas.html)

Para Windows 10 y 11 · 30 días gratis, sin tarjeta

## Sigue leyendo

- [**Caso real: cómo GPFIAL organiza miles de fotos de peritaje al año** Cómo un gabinete pericial de Canarias organiza miles de fotos al año: 56.963 fotos reales de 1.866 vehículos, más del 99 % en su carpeta.](https://peritolab.es/guia-caso-gpfial.html)
- [**Programa para las fotos del peritaje: qué mirar antes de elegirlo** Cuánto tiempo te cuesta separar las fotos a mano y qué comprobar en un programa para el peritaje: fotos en local, revisión de dudas, originales y PDF.](https://peritolab.es/guia-elegir-programa-fotos-peritaje.html)
- [**Cómo ordenar las fotos por fecha de captura en Windows** Por qué las fotos del peritaje salen desordenadas por nombre y cómo ordenarlas en Windows por la fecha en que se hicieron, sin instalar nada.](https://peritolab.es/guia-ordenar-fotos-fecha-captura.html)

[← Todas las guías](https://peritolab.es/guias.html)

---

- Página original: [https://peritolab.es/guia-cadena-custodia-fotos-peritaje.html](https://peritolab.es/guia-cadena-custodia-fotos-peritaje.html)
- Índice de la web para asistentes: [https://peritolab.es/llms.txt](https://peritolab.es/llms.txt)
- Mapa del sitio: [https://peritolab.es/sitemap.xml](https://peritolab.es/sitemap.xml)
- Contacto: [contacto.peritolab@gmail.com](mailto:contacto.peritolab@gmail.com)
