
**Libro para Aprender Test Unitarios:**  ***Test Driven Development Frank Iglesias.***  9798732391385

Trucos: 
- para mover linea o todo los subrayada.   alt+ flechitas arriba abajo
- para copiar linea de código y moverlo  control+alt+flechitas arriba abajo

---
Xxx Datos que sirven: 
- Las bases de datos guardan fechas en formato Año, mes, día. En ese orden.  Cuando guardamos números o montos de dinero, guardamos por un lado la cantidad y por otro la moneda. 

- Windows, Show view nos deja activar o desactivar las ventanas que se nos muestran.

- si no hay ningún constructor crea uno vacío, cuando ya tenga un constructor Java no crea ninguno más.

---

**Extensiones**:  Eclipse Entrerprise Java, ResourceBundle, SonarLint(Malas prácticas o detecta errores o bugs, detecta code Smells), JSparrow(hace lo mismo que SonarLint,  bracketeer2(Sirve para que te ayude a detectar, si las llaves no está bien cerradas)
pom.xml  <--- Maven

**Refactoring**: Cambiar código que no es lo suficientemente bueno.

`pom.xml` es un archivo fundamental en proyectos de **Maven**, una herramienta de gestión de proyectos y automatización de compilación para proyectos Java. `pom.xml` (Project Object Model) define la configuración del proyecto y sus dependencias. A través de este archivo, Maven puede gestionar la construcción del proyecto, ejecutar pruebas, empaquetar la aplicación, y más.

Algunos de los elementos clave dentro de un archivo `pom.xml` son:

1. **`<groupId>`**: Identifica de manera única el proyecto dentro de un grupo o empresa (similar al paquete en Java).
2. **`<artifactId>`**: El nombre del proyecto (normalmente es el nombre del archivo que se genera, como un `.jar` o `.war`).
3. **`<version>`**: Especifica la versión del proyecto.
4. **`<dependencies>`**: Lista de bibliotecas externas y dependencias que el proyecto necesita.
5. **`<build>`**: Configura la manera en que Maven construirá el proyecto (plugins, compiladores, etc.).

lenguaje propio   <----- Gradle

Gradle es otra herramienta de automatización de compilación, similar a Maven, pero con más flexibilidad. A diferencia de Maven, Gradle utiliza un **lenguaje basado en scripts** para definir su configuración en lugar de un archivo XML. Los scripts de Gradle pueden escribirse en dos lenguajes:

1. **Groovy** (más común y predeterminado)
2. **Kotlin**

En Gradle, en lugar de usar un archivo `pom.xml` como en Maven, se usa un archivo llamado `build.gradle`. Este archivo define las configuraciones, dependencias y tareas del proyecto, pero en lugar de una estructura XML rígida, utiliza un enfoque más flexible y dinámico.

Ejemplo de build.gradle:

`plugins { id 'java' } group 'com.example' version '1.0-SNAPSHOT' repositories { mavenCentral() } dependencies { testImplementation 'junit:junit:4.12' } test { useJUnitPlatform() }`

### Elementos principales del archivo `build.gradle`:

1. **`plugins`**: Define los plugins que se utilizarán en el proyecto. Aquí se usa el plugin de Java.
2. **`group` y `version`**: Definen el identificador y la versión del proyecto, similares a `groupId` y `version` en Maven.
3. **`repositories`**: Especifica de dónde descargar las dependencias, como `mavenCentral()`, el repositorio central de Maven.
4. **`dependencies`**: Aquí se definen las dependencias del proyecto. En este ejemplo, JUnit se utiliza como dependencia de pruebas.
5. **`test`**: Configura cómo se ejecutan las pruebas. En este caso, se usa la plataforma de JUnit.


**i18n**    **internationalization**: **i18n** es una abreviatura de **"internationalization"** (internacionalización). Se llama así porque la palabra **"internationalization"** tiene 18 letras entre la primera "i" y la última "n".

### ¿Qué es la internacionalización?

La internacionalización (i18n) es el proceso de diseñar una aplicación de software de manera que pueda ser **adaptada fácilmente** a diferentes idiomas y regiones **sin cambios en el código fuente**. Esto implica:

1. **Separar el contenido de la lógica**: El texto, las imágenes y otros elementos específicos de una región (locales) no deben estar "hard-coded" (codificados directamente) en el código de la aplicación. En su lugar, se deben almacenar en archivos de recursos o bases de datos que se puedan cambiar según el idioma o región.
    
2. **Soporte para múltiples idiomas**: i18n asegura que una aplicación pueda admitir varios idiomas, incluidos idiomas con características específicas (como el chino, árabe, hebreo, etc.), que podrían requerir un tratamiento especial, como el manejo de escritura de derecha a izquierda.
    
3. **Adaptabilidad de formatos locales**: Además de traducir textos, i18n también abarca adaptar formatos locales de fechas, monedas, direcciones, y más, para que sean culturalmente adecuados para diferentes usuarios.



---

Ejercicio para hacer: 

Hacer un juego que se llama Fizz Buzz, donde si el número es:

Divisible x 3  --> Fizz
Divisible x 5 --> Buzz
Divisible x 3 y 5 --> Fizz Buzz
..............................................................
1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, Fizz Buzz


EJEMPLO RESUELTO: 

`public class FizzBuzzGame {`

`public List<String> generateFizzBuzzList() {`

`// aqui hemos declarado un Array para guardar los números. hacemos referencia a`

`// la variable y luego le ponemos add.`

`List<String> fizzBuzzList = new ArrayList<String>();`

`/*`

`* FIRST TRY`
`*`
`* for (int i = 1; i <= 100; i++) {`
`*`
`* if (i % 3 == 0 && i % 5 == 0 || i % 15 == 0) {`
`*`
`* fizzBuzzList.add("FizzBuzz");`
`*`
`* } else if (i % 3 == 0) {`
`*`
`* fizzBuzzList.add("Fizz");`
`*`
`* } else if (i % 5 == 0) { fizzBuzzList.add("Buzz"); } else {`
`*`
`* fizzBuzzList.add(String.valueOf(i)); }`
`*`
`* }`
`*/`

`for (int i = 1; i <= 100; i++) {`

`if (i % 15 == 0) {`

`fizzBuzzList.add("FizzBuzz");`

`} else if (i % 3 == 0) {`

`fizzBuzzList.add("Fizz");`

`} else if (i % 5 == 0) {`

`fizzBuzzList.add("Buzz");`

`} else {`

`fizzBuzzList.add(String.valueOf(i));`
`}`
`}`
`return fizzBuzzList;`

`}`

`public void showGeneratedFizzBuzzList() {`

`// con this. podemos llamar al metodo de arriba y como retorna la lista me va`

`// dar la lista.`

`System.out.println("La Lista contiene: " + this.generateFizzBuzzList());`
`}`
`}`



TAREA:  probar el código con 2 , 4 y 8
--------------------------------------

JVM =Java virtual machine

JRE = Java runtime environment

---
En la clase Main todo lo del arranque de la aplicación. Los nombres de clases empiezan con mayúsculas.

Tipos de formas de comentar:   // (comentario de una linea) , /* */ (comentario de varias líneas), /** */ (el JavaDoc va sacando lo del "" /** */ " y lo guarda en un fichero HTML).

//TODO para guardar la posición del código en la cual tenemos algo pendiente por hacer.


---
Principios SOLID.

-Principio de la responsabilidad única. Las clases deben hacer una sola cosa, y los métodos deben hacer una cosa.

----
Complejidad ciclomático:???