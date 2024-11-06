
Al momento de crear un nuevo proyecto, normalmente al ponerle el nombre , automáticamente se agrega al nombre del paquete, en el nombre del paquete normalmente se pone primero el nombre de la empresa y luego el nombre del proyecto separado por un punto.

- con la vista de Android, se puede ver el manifiesto, y en Kotlin-java tienes el MainActivity
luego en la carpeta res. tienes el XML de la activity_main.xml.

![[Pasted image 20241008085639.png]]+MainActivity esta generada con un lado gráfico, en cambio con Kotlin class file generamos una clase pero no tiene una contraparte gráfica.
  +Para agregar una actividad se puede hacer con click derecho en la carpeta , luego en el listado seleccionar Activity y luego seleccionar el tipo de actividad

![[Pasted image 20241008090049.png]]

+ con el launcher activity podemos hacer que sea convierta en la clase main sea la que se cargue.  ![[Pasted image 20241008090242.png]]

- Navegar es ir de una actividad a otra o de una aplicación a otra.

---

Inicio de Actividad:

`package core.dam.repasoandroid`  
  
`import android.os.Bundle`  
`import androidx.activity.enableEdgeToEdge`  
`import androidx.appcompat.app.AppCompatActivity`  
`import androidx.core.view.ViewCompat`  
`import androidx.core.view.WindowInsetsCompat`  
  
`class AboutActivity : AppCompatActivity() {`  
    `override fun onCreate(savedInstanceState: Bundle?) {`  
        `super.onCreate(savedInstanceState)`  
        `enableEdgeToEdge()`  
        `setContentView(R.layout.activity_about)`  
        `ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->`  
            `val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())`  
            `v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)`  
            `insets`  
        `}`  
    `}`  
`}`

Explicación:

### 1. **package core.dam.repasoandroid**

- Define el paquete al que pertenece este archivo. Los paquetes organizan las clases y evitan conflictos de nombres. En este caso, el archivo está ubicado en el paquete `core.dam.repasoandroid`.

### 2. **import android.os.Bundle**

- Importa la clase `Bundle` del paquete `android.os`. Un `Bundle` se usa para pasar datos entre actividades y almacenar el estado de una actividad cuando es recreada (por ejemplo, después de un cambio de orientación).

### 3. **import androidx.activity.enableEdgeToEdge**

- Importa la función `enableEdgeToEdge()` que permite que la aplicación extienda el contenido hasta los bordes de la pantalla, utilizando el área debajo de las barras del sistema (barra de estado y barra de navegación) para mejorar el uso de la pantalla completa.

### 4. **import androidx.appcompat.app.AppCompatActivity**

- Importa `AppCompatActivity`, que es una clase base para actividades que proporcionan soporte de compatibilidad con versiones anteriores. Es una versión mejorada de `Activity`, y es necesaria si se quiere usar características modernas y mantener compatibilidad con versiones más antiguas de Android.

### 5. **import androidx.core.view.ViewCompat**

- Importa `ViewCompat`, una clase que proporciona utilidades de compatibilidad para trabajar con vistas, ofreciendo funciones para gestionar características disponibles en diferentes versiones de Android.

### 6. **import androidx.core.view.WindowInsetsCompat**

- Importa `WindowInsetsCompat`, que es una clase para gestionar el espacio ocupado por barras del sistema como la barra de estado y la barra de navegación. Proporciona una API más amigable para interactuar con estas barras y su espacio de forma consistente a lo largo de diferentes versiones de Android.

### 7. **class AboutActivity : AppCompatActivity() {**

- Define una clase llamada `AboutActivity` que extiende de `AppCompatActivity`. Esto significa que `AboutActivity` es una actividad de la aplicación que puede utilizar las funciones avanzadas de la librería de compatibilidad de Android.

### 8. **override fun onCreate(savedInstanceState: Bundle?) {**

- Sobrescribe el método `onCreate()`, que es llamado cuando la actividad es creada. El parámetro `savedInstanceState` contiene el estado previamente guardado de la actividad, si existe.

### 9. **super.onCreate(savedInstanceState)**

- Llama al método `onCreate()` de la clase `AppCompatActivity` para asegurar que se realice la configuración base necesaria para la actividad, como la inicialización de la interfaz gráfica y la restauración de cualquier estado guardado.

### 10. **enableEdgeToEdge()**

- Esta función habilita el "Edge-to-Edge" (bordes a bordes), que permite que la aplicación extienda su contenido hasta debajo de las barras de estado y navegación, ofreciendo una experiencia de pantalla completa.

### 11. **setContentView(R.layout.activity_about)**

- Asigna el archivo de diseño `activity_about.xml` como la interfaz de usuario para esta actividad. Este archivo XML define el layout (diseño) que se mostrará cuando se cargue esta actividad.

### 12. **ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->**

- Añade un "listener" a la vista principal (`R.id.main`) para aplicar los `WindowInsets`, que son los márgenes que necesita la aplicación para respetar las áreas ocupadas por las barras del sistema. El listener responde a los cambios en el tamaño o visibilidad de estas barras.

### 13. **val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())**

- Obtiene los márgenes (insets) que ocupan las barras del sistema (barra de estado, barra de navegación, etc.) y los almacena en la variable `systemBars`. Estos márgenes indican cuántos píxeles del borde de la pantalla están ocupados por las barras del sistema.

### 14. **v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)**

- Ajusta el padding (relleno interno) de la vista para que su contenido no se superponga con las barras del sistema. El padding se establece utilizando los márgenes obtenidos anteriormente.

### 15. **insets**

- Finalmente, devuelve los insets después de haber ajustado el padding. Esto es necesario para que el sistema sepa que los insets se han aplicado correctamente.

Este código configura una actividad que aprovecha toda la pantalla y gestiona el espacio ocupado por las barras del sistema, ajustando dinámicamente el contenido.

---

Forma de cambiar el Layout de la actividad: convert view

![[Pasted image 20241008092737.png]]


+ Las constraints son los anclajes que ves de cada cosa, en este caso como como hay un TextView lo anclamos a los lados izquierda =start, derecha =end, arriba y abajo y le decimos que lo ancle a su padre que en este caso es el constraintLayout. 

---

### Diferencia entre un **dp** y un **pixel real**:

1. **Pixel real (px)**:
    
    - Es la unidad física que corresponde a un solo punto en la pantalla de un dispositivo. La cantidad de píxeles reales puede variar según la resolución de la pantalla.
    - Las pantallas con diferentes densidades de píxeles (por ejemplo, una pantalla de alta densidad como una retina display) tendrán más píxeles reales en la misma área física que una pantalla de baja densidad.
    - En este caso, el tamaño de los elementos de la interfaz puede variar considerablemente entre dispositivos si se utilizan solo píxeles reales para diseñar.
2. **Pixel de dispositivo (dp)**:
    
    - **dp** es una unidad abstracta que se escala automáticamente en función de la densidad de la pantalla.
    - 1 dp equivale a 1 píxel real en una pantalla de densidad media (**160 dpi**, también llamada **mdpi**).
    - La ventaja de utilizar dp es que Android ajusta automáticamente los valores para diferentes pantallas, asegurando que un elemento que mide 100 dp tendrá aproximadamente el mismo tamaño físico en pantallas de distintas densidades.

### ¿Cómo se compara un **dp** a un **pixel real**?

La relación entre **dp** y **px** depende de la **densidad de píxeles (dpi)** del dispositivo. Android clasifica los dispositivos en varias densidades comunes:

- **mdpi (160 dpi)**: 1 dp = 1 px (pantallas de densidad media)
- **hdpi (240 dpi)**: 1 dp ≈ 1.5 px (pantallas de alta densidad)
- **xhdpi (320 dpi)**: 1 dp ≈ 2 px (pantallas de muy alta densidad)
- **xxhdpi (480 dpi)**: 1 dp ≈ 3 px (pantallas de densidad extremadamente alta)
- **xxxhdpi (640 dpi)**: 1 dp ≈ 4 px (pantallas de densidad ultra alta)

### Ejemplo:

Si defines un botón de 100 dp:

- En una pantalla **mdpi (160 dpi)**, ocupará **100 píxeles reales**.
- En una pantalla **hdpi (240 dpi)**, ocupará **150 píxeles reales**.
- En una pantalla **xhdpi (320 dpi)**, ocupará **200 píxeles reales**.

Esto permite que el botón tenga el mismo tamaño físico (en centímetros, por ejemplo), aunque los píxeles reales varíen en función de la densidad de la pantalla.

***Fuentes:***

Las fuentes tipográficas se pueden clasificar en varios estilos, cada uno con sus características distintivas. Aquí te doy una descripción de los estilos más comunes:

### 1. **Fuentes Serif**

Las fuentes con **serifas** tienen pequeños trazos decorativos al final de las letras. Se asocian generalmente con una apariencia más formal o tradicional.

- Ejemplos: **Times New Roman**, **Georgia**, **Garamond**.
- Características: Las serifas mejoran la legibilidad en textos largos impresos, ya que guían el ojo a lo largo de las líneas.
- Uso común: Libros, periódicos, documentos formales.

### 2. **Fuentes Sans Serif**

Estas fuentes **no tienen serifas** (es decir, carecen de los adornos en los bordes de las letras), lo que les da un aspecto más moderno y limpio.

- Ejemplos: **Arial**, **Helvetica**, **Verdana**, **Roboto**.
- Características: Son más simples y suelen preferirse para textos en pantallas, ya que son más fáciles de leer en tamaños pequeños.
- Uso común: Sitios web, aplicaciones, diseño gráfico moderno.

### 3. **Fuentes Monospace (Monoespaciadas)**

En las fuentes monoespaciadas, **cada carácter ocupa el mismo ancho**. Son muy utilizadas en programación y entornos técnicos.

- Ejemplos: **Courier**, **Consolas**, **Lucida Console**.
- Características: Cada letra ocupa el mismo espacio horizontal, lo que facilita la alineación de código y datos en columnas.
- Uso común: Entornos de programación, editores de texto para desarrolladores, representación de datos tabulares.

### 4. **Fuentes Handwriting (Escritura a mano)**

Estas fuentes están diseñadas para parecerse a la escritura manual.

- Ejemplos: **Comic Sans**, **Brush Script**, **Dancing Script**.
- Características: Estilos informales y personales, a veces cursivos.
- Uso común: Invitaciones, tarjetas informales, diseño gráfico creativo.

### 5. **Fuentes Display o Decorativas**

Las fuentes decorativas están diseñadas principalmente para destacar o llamar la atención en títulos y no son recomendadas para textos largos.

- Ejemplos: **Impact**, **Jokerman**, **Papyrus**.
- Características: Formas inusuales, creativas y extravagantes que pueden ser difíciles de leer en cuerpos de texto largos.
- Uso común: Títulos, logotipos, carteles.
----

Servicios: Fuentes de información. Se ejecutan en segundo plano, son algoritmos. Son funcionalidades en segundo plano. 

Proveedoras: Almacena y comparte datos entre aplicaciones.

intent: En Kotlin (y particularmente en Android), un **`Intent`** es un objeto que permite la comunicación entre diferentes componentes de una aplicación, como **actividades**, **servicios** o **receptores de difusión** (broadcast receivers). Sirve para varias cosas, como iniciar una nueva actividad, solicitar un servicio en segundo plano o incluso enviar datos entre componentes.

### Tipos de `Intent`:

1. **`Intent` explícito**: Se utiliza cuando quieres iniciar un componente específico de tu aplicación, por ejemplo, abrir una actividad particular.
    
    kotlin
    
    Copiar código
    
    `val intent = Intent(this, SegundaActividad::class.java) startActivity(intent)`
    
2. **`Intent` implícito**: Se usa cuando deseas realizar una acción pero no sabes cuál componente lo manejará. El sistema Android buscará la aplicación más adecuada para manejar la solicitud, por ejemplo, abrir un navegador o una aplicación de mensajería.
    
    kotlin
    
    Copiar código
    
    `val intent = Intent(Intent.ACTION_VIEW) intent.data = Uri.parse("http://www.google.com") startActivity(intent)`
    

### Usos comunes:

- **Iniciar una nueva actividad**: Como en el ejemplo anterior, los `Intent` explícitos se usan para abrir otra pantalla.
    
- **Enviar datos entre actividades**:
    
    kotlin
    
    Copiar código
    
    `val intent = Intent(this, SegundaActividad::class.java) intent.putExtra("clave", "valor") startActivity(intent)`
    
- **Iniciar servicios en segundo plano**:
    
    kotlin
    
    Copiar código
    
    `val intent = Intent(this, MiServicio::class.java) startService(intent)`
    
- **Enviar difusiones** (broadcasts):
    
    kotlin
    
    Copiar código
    
    `val intent = Intent("com.miapp.MI_ACCION") sendBroadcast(intent)`
    

Los `Intent` son fundamentales en Android para la navegación y la interoperabilidad entre aplicaciones y componentes dentro de una misma aplicación.