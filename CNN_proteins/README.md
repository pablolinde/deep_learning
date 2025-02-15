En este notebook se clasifican proteínas con una CNN.

Los datos a procesar son un conjunto de imágenes sintéticas de cryo-EM. Cada imagen contiene una proyección 2D de una instancia de un determinado complejo molecular a una orientación aleatoria, específicamente los hay de cinco clases que según su código en la base de datos Protein Data Bank ([PDB](https://www.rcsb.org/)):

1. [3j9i](https://www.rcsb.org/structure/3J9I)
2. [4cr2](https://www.rcsb.org/structure/4CR2)
3. [4v4r](https://www.rcsb.org/structure/4V4R)
4. [4v94](https://www.rcsb.org/structure/4V94)
5. [6utj](https://www.rcsb.org/structure/6UTJ)

Las imágenes tienen un tamaño de 50x50 píxeles y están guardadas en ficheros en formato PNG. El nombre de estos ficheros determina el nombre de la clase, el identificador de clase y el número de partícula de esta clase. El conjunto de datos se encuentra en el directorio *imgs/SNR_high*.

Para poder entrenar el modelo es necesario cargar las imágenes de disco y convertirlas en tensores (arrays n-dimensionales). Las etiquetas de la clase a las que pertenece cada imagen se pueden extraer del nombre de las imágenes. Es probable que al leer las imágenes de disco se vayan leyendo secuencialmente para cada clase, este orden en las imágenes podría distorsionar el entrenamiento, por esto, una vez leídas, se recomiennda aleatorizar su orden mediante la funcionalidad que ofrece el paquete para machine learning de Python scikit-learn.