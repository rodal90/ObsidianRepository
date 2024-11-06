
SEGUNDA CLASE 23/09/2024:

SOLO LAS CLASES SE INICIA CON MAYÚSCULAS.


-Las pantalla todas en Kotlin se llaman Activity, y existe una llamada MainActivity.

-El **AppComptactActivity()** es para heredar retro compatibilidad.

-Al momento de diseñar utilizar márgenes para evitar superposición de componentes.

-Al dar un nombre al ID de los componentes, tiene que ser único.


Ejemplo de XML para análisis: 

`<?xml version="1.0" encoding="utf-8"?>`  
`<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"`  
    `xmlns:app="http://schemas.android.com/apk/res-auto"`  
    `xmlns:tools="http://schemas.android.com/tools"`  
    `android:id="@+id/main"`  
    `android:layout_width="match_parent"`  
    `android:layout_height="match_parent"`  
    `tools:context=".MainActivity">`  
  
    `<TextView        android:id="@+id/textView"`  
        `android:layout_width="100dp"`  
        `android:layout_height="37dp"`  
        `android:layout_marginTop="32dp"`  
        `android:text="Hello World!"`  
        `app:layout_constraintBottom_toBottomOf="parent"`  
        `app:layout_constraintEnd_toEndOf="parent"`  
        `app:layout_constraintStart_toStartOf="parent"`  
        `app:layout_constraintTop_toTopOf="parent"`  
        `app:layout_constraintVertical_bias="0.39" />`  
  
    `<Button        android:id="@+id/button2"`  
        `android:layout_width="wrap_content"`  
        `android:layout_height="wrap_content"`  
        `android:layout_marginStart="163dp"`  
        `android:layout_marginTop="104dp"`  
        `android:layout_marginEnd="158dp"`  
        `android:layout_marginBottom="260dp"`  
        `android:text="Botonazo"`  
        `app:layout_constraintBottom_toBottomOf="parent"`  
        `app:layout_constraintEnd_toEndOf="parent"`  
        `app:layout_constraintStart_toStartOf="parent"`  
        `app:layout_constraintTop_toBottomOf="@+id/textView" />`  
  
/>`  
  
`</androidx.constraintlayout.widget.ConstraintLayout>`




**Carpetas:**

-App:

      1)Manifiest: Es lo que nos va definir las opciones que va tener disponibles nuestro proyecto android. (Aquí por ejemplo puedes encontrar las rutas a los iconos, he incluso te muestra si son los redondeados o cuadrados).

       2)res (recursos) => drawable: Aqui se guardan las imágenes del proyecto, o cualquier recurso visual. También se puede meter videos, etc.

         layout: Parte visual que estamos modificando, capa de presentación de la clase de Kotlin que generamos. 

       mipmap:_Iconos.

       Values: Colores, Strings y vas a encontra los Themes. Dentro del XML de themes en <style>, es donde podes cambiar los colores. Puedes personalizarl los colores, Y lo mejor sería hacer paletas de colores.  Aquí también encontras los strings (buscar que es string).
     

     3)Kotlin+java: donde esta el código.  Dentro encontramos la carpeta de core.dam.primerproyecto y la MainActivity, en MainActivity es donde vamos a hacer todas las clases (Capa lógica).

      4)Gradel Scripts: No es parte de la aplicación. Gradel va a compilar la parte de la aplicación. Se auto actualiza.




- **HDPI (Alta Densidad de Píxeles):** Generalmente alrededor de 240 DPI. Esta es una densidad común para teléfonos inteligentes de gama media. 72 x 72 WEBP.
- **MDPI (Densidad Media de Píxeles):** Generalmente alrededor de 160 DPI. Esta es una densidad más baja que se encuentra a menudo en dispositivos antiguos o económicos. 48 x 48 WEBP.
- **XHDPI (Densidad Extra Alta de Píxeles):** Generalmente alrededor de 320 DPI. Esta es una alta densidad común en teléfonos inteligentes emblemáticos. 96 x 96 WEBP.
- **XXHDPI (Densidad Extra-Extra Alta de Píxeles):** Generalmente alrededor de 480 DPI. Esta es una densidad extremadamente alta que se encuentra en algunos dispositivos de alta gama y tabletas. 72 x 72 WEBP.
- **XXXHDPI (Densidad Extra-Extra-Extra Alta de Píxeles):** Generalmente alrededor de 640 DPI. Esta es la densidad más alta actualmente disponible en dispositivos de consumo, que se encuentra a menudo en tabletas de pantalla grande y pantallas especializadas.72 x 72 WEBP.

**Formatos de imágenes:** 

***Imagen Raster***:  Formato que guarda los datos de la imagen formando una cuadricula de colores. Como se graba la imagen. 
En blanco y negro, se podría hacer de forma binaria, y si son más con RGB, etc.    

Formatos más comunes:

- **JPEG (JPG):**
    - **Características:** Altamente comprimido, lo que reduce el tamaño del archivo, pero puede causar pérdida de calidad en algunas áreas, especialmente con muchas ediciones. Ideal para fotografías.
    - **Usos:** Imágenes web, fotografías digitales, imágenes para redes sociales.
- **PNG:**
    - **Características:** Soporta transparencia, compresión sin pérdida (mantiene la calidad original), ideal para gráficos con bordes definidos y texto.
    - **Usos:** Logotipos, iconos, infografías, capturas de pantalla.
- **GIF:**
    - **Características:** Soporta animación, transparencia, pero con una paleta de colores limitada. Ideal para imágenes simples y animaciones cortas.
    - **Usos:** Banners publicitarios, emojis, animaciones cortas.
- **BMP:**
    - **Características:** Formato sin compresión, lo que resulta en archivos grandes. Ofrece una representación precisa de los colores.
    - **Usos:** Capturas de pantalla, imágenes sin pérdida de calidad.
- **TIFF:**
    - **Características:** Formato de alta calidad, sin pérdida, capaz de almacenar múltiples imágenes en un solo archivo.
    - **Usos:** Imágenes médicas, imágenes científicas, escaneos de alta resolución.
- **PSD:**
    - **Características:** Formato nativo de Adobe Photoshop, guarda capas y ajustes de edición.
    - **Usos:** Edición de imágenes profesionales, diseño gráfico.

**Meta data de una imagen:**

**Los metadatos de una imagen son como una etiqueta invisible que acompaña a una fotografía.** Esta etiqueta contiene información adicional sobre la imagen, más allá de los píxeles que componen la imagen visible. Es como un currículum de la foto, que detalla cómo y cuándo fue tomada, con qué cámara, y a veces incluso dónde.

SVG: **SVG (Scalable Vector Graphics)** es un formato de imagen basado en vectores, lo que significa que las imágenes están compuestas por líneas, curvas y formas matemáticas, en lugar de píxeles. Esto le otorga varias ventajas sobre los formatos de imagen raster como JPEG o PNG:

### Características de SVG:

- **Escalabilidad:** Los gráficos SVG se pueden escalar a cualquier tamaño sin perder calidad, ya que están definidos por fórmulas matemáticas. Esto los hace ideales para gráficos que deben verse bien en diferentes resoluciones y tamaños de pantalla.
- **Editabilidad:** Los archivos SVG son editables, lo que significa que puedes modificar sus elementos individuales (líneas, formas, colores) incluso después de haber creado el gráfico. Esto es especialmente útil para diseñadores y desarrolladores.
- **Compacto:** Los archivos SVG suelen ser más pequeños que los archivos raster equivalentes, ya que no contienen datos de píxeles. Esto los hace más eficientes para la transmisión y el almacenamiento.
- **Compatibilidad:** Los navegadores web modernos y muchos programas de diseño y edición de imágenes admiten SVG.

### Usos comunes de SVG:

- **Iconos:** Los SVG son ideales para crear iconos que se puedan escalar sin perder calidad, como los que se usan en sitios web y aplicaciones móviles.
- **Gráficos vectoriales:** Se utilizan para crear gráficos complejos, como logotipos, infografías y diagramas.
- **Animaciones:** Los SVG pueden ser animados utilizando JavaScript o CSS, lo que permite crear animaciones vectoriales interactivas.
- **Diseño web:** Los SVG se pueden incrustar directamente en el código HTML de una página web, lo que los hace más eficientes que usar imágenes raster.

### Ventajas de SVG sobre los formatos raster:

- **Escalabilidad:** Los SVG se pueden escalar sin pérdida de calidad.
- **Editabilidad:** Se pueden modificar y editar fácilmente.
- **Tamaño de archivo:** Generalmente son más pequeños.
- **Compatibilidad:** Son ampliamente compatibles con navegadores web y programas de diseño.


***Imagen Vector:*** Las imágenes vectoriales están compuestas por líneas, curvas y formas matemáticas.


### Raster

- **Definición:** Las imágenes raster están compuestas por una cuadrícula de píxeles, cada uno con un color específico.
- **Pros:**
    - Adecuadas para fotografías y imágenes con detalles realistas.
    - Ofrecen una amplia gama de colores y tonos.
    - Pueden ser editadas con precisión a nivel de píxel.
- **Contras:**
    - Pierden calidad cuando se escalan a tamaños mayores (efecto pixelado).
    - Generalmente tienen tamaños de archivo más grandes.
    - No son editables a nivel de forma o línea.

### Vector

- **Definición:** Las imágenes vectoriales están compuestas por líneas, curvas y formas matemáticas.
- **Pros:**
    - Escalan sin pérdida de calidad, independientemente del tamaño.
    - Tienen tamaños de archivo generalmente más pequeños.
    - Son editables a nivel de forma y línea.
    - Ideales para gráficos simples, logotipos y diseños técnicos.
- **Contras:**
    - Pueden ser más complejos de crear para imágenes realistas con muchos detalles.
    - Pueden tener limitaciones en la representación de degradados y texturas complejas.

 