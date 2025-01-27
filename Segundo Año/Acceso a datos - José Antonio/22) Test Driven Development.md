

No testear lo que el compilador ya te muestra que no funciona.

Hay que testear todos los servicios (aquí es donde el testing se tiene que hacer bien) y  controladores ( son tontos como html si lo hacemos bien, y en el testing lo que testeamos el mapeo de entrada o el mapeo de salid). (Impl).

TDD Test Driven Development. El test se escribe a priori, antes de que el código exista. Queremos testear el comportamiento del código, pero el mínimo posible. Los test guían el desarrollo. (Behavior Drive Development).

Tipos de Tests: ****Unitarios***(simulamos dependencias y conexiones,  esperamos ejecutar cientos o miles de test por segundo, queremos que siempre de el mismo resultado, que no sea aleatorio, no queremos que falle de vez en cuando), ****de integración*** ( se prueban conjuntos de unidades de software para verifica su comunicación y su acción combinada.  Habla con la base de datos, Se comunica a través de la red, Tira del sistema de archivos, actúa sobre la interfaz del usuario, necesitamos modificar el entorno para poder ejecutarlo), y ****de aceptación***().

Assert= aserción => quiero comprobar que es tal  cosa y lo es. (el test tiene que devolver lo que queremos que devuelva, en ese caso si devuelve es una aserción).

QA(Quality Assurance) Es  la prueba que se hace después para asegurar la calidad.

Tipos de Artefactos de Test

Unit Test: es un método o función que realiza un test unitario.
Test case: es una clase que agrupa varios tests
Test Suite: conjunto de test y/o test cases que se ejecutan juntos

Existen repositorios con Katas:   

Katalyst y Coding dojo.


La dependencia que hay que comprobar si esta para hacer los test es :
starter-test que tiene un scope test.

si el import es Jupiter es la versión 5. es la JUnit.


Cuando tenemos una clase de Test , solo desde donde señalemos va empezar a correr el programa.

Ventana de JUnit
Runs: significa el numero de test que se han hecho
Errors: los errores
Failures: No hay errores pero el test no a arrojado el dato que queríamos.



-------------------------------------------------------------------------
**Libros Metodología acerca de test unitario :** 

"Java Unit Testing with JUnit 5" -  Shekhar Gulati

Edit.Apress

"Aprende Test Driven Development"- Fran Iglesias


---
(Esta es una librería que nos faltaba)
SCrypt -> "bouncy castle"
--

//ir abandonando secured
Spring   <- @Secured   (antigua)

//usar RolesAllowed si no nos dejan usar Spring y solo anotaciones estándar.
Norma estándar  para java security   <- JSR-250 <- @RolesAllowed  (Esta bien, pero es más limitada)

//herederas de secure
Spring + SpFL <- @PreAuthorize  (La más moderna y mas potente (Spring + SpFL).



---

VOLVEMOS CON INFORMACION DE TEST UNITARIOS

Un Test = Un método. test => 1 única aserción (Assert)

Integer a=3;
assertTrue(a==3); 
assertTrue(a==4); 
assertFalse(a==3); 
assertNull(a); 
assertNotNull(a); 
assertNull(b); 

Recordar una cosa es el fallo y otra cosa es el error;
hasta que no eliminemos los errores no podemos valorar la aserción.
El error es previo al fallo.

assertEquals (a,3) El primer valor es el expected value, y el segundo es el valor real.
Se puede agregar un "tercer valor", que es un "fail message". 
El Equals me vale para objetos. El == igual igual en objetos lo que compara son punteros.

----

como crear una kata

1. Primero crear un Java Proyect, agregar nombre. 
2. El module-info no clickarlo. Luego darle next.
 3. Hacer click en Crete new source folder y crear una carpeta de test.
 4.  Luego le hacemos click al check box de (Allow output folders for source folders)
 5. Luego irse a la pestaña de librerias, marcamos sobre Classpath.
 6. Hay que añadir dos librerias un ahora y otra después de que este creado el proyecto,
 7. Hacer click en Add Library..  (Marcar JUnit y escoger su version al darle next)
 8. Después de esto le podemos dar finalizar.
 ----
Como cambiar el orden de las carpetas:

seleccionar buildpath / Configure BuildPath , y luego mover las carpetas como queremos.

---

despues de descargar lombock lo movemos a la carpeta del proyecto donde lo queremos, pero luego para referenciarlo como libreria hay que ir otra vez al buildpath, Configure BuildPath, luego a la pestaña de "Libreries" luego ir "Add JARs". Seleccionar de la carpeta de nuestro proyecto la libreria que queremos agregar.
No se borrar el tarro de lombok.jar. 

---
Lombok te deja meter getters como anotaciones y te los crea. 

Todo lo que queramos que se ejecute como test tiene que llevar la anotación @Test
----

Para crear la version de prueba de nuestra clase , por ejemplo FirstSyntax.java, seleccionamos  con click derecho el archivo y vamos a new, alli puede estar en others hasta abajo dentro de la carpet Java, Junit, JUnit Test Case. Si tenes la opcion tambien podes tener la opcion en el listado previo tambien.

Luego seleccionamos el JUnit version, luego cambiamos el Sourcefolder para que us la carpeta de test que creamos.

(El nombre de la version test de la clase debe tener Test o Spec al final).

Luego darle next.  y Finish. 
Ya nos añade un método que se llama test.  //con un assert que falla! 

Para correr los test no necesito arrancar la aplicacion completa, solo selecciono el método o desde donde quiero que empiece a correr y lo ejecuto con el "Run as" como en los otros.

El test no puede tardar segundo, sino milisegundos para ser valido. 


---

***La cruz blanca sobre fondo azul significa que el test esta hecho pero no superado***

***Si la cruz es blanca con fond verde significa que el test esta hecho y superado***

***Si la cruz blanca con fondo rojo significa que el test no fue hecho***

---

Para desactivar alguno de los métodos test que no queremos que correr lo hacemos con 
la anotación @Disabled("Desactivado porque sí")

---
Como son test unitarios, al momento de ejecutar un grupo de métodos test, se ejecutan en orden aleatorio, pero utilizando la siguiente etiqueta les podemos dar un orden de ejecución en caso de que sea necesario, por ejemplo si hay algún tipo de dependencia entre uno y otro. 

*Para que la anotación order funcione es necesario agregar una anotación a la clase entera, es esta: "@TestMethodOrder(OrderAnnotation.class)*
(vale cualquier numero, pero se aconseja por ejemplo ir de 10 en diez, porque de esa forma tienes espacio para  agregar métodos intermedios entre uno y otro, dentro del orden.)
@order

----
Métodos de test pueden tener constructores y parámetros

---
TestInfo testInfo => nos da información del test
Y el DisplayName nos da información del nombre

Si usamos DisplayName arriba del método que vamos a testear lo que te sale por consola es el mensaje que le pusiste a la anotación DisplayName: @DisplayName("check right value for attribute prueba")

Y si lo ponemos por encima de la clase aparece en la parte donde vemos si los test so correctos, con el nombre de el mensaje que hemos puesto. 


---


Anatomía de un test Un test mantenible no se parece a un script repleto de líneas de comandos. A ser posible sólo tiene tres bloques: la preparación, la ejecución y la validación. En inglés estas tres partes se identifican con las siglas AAA, lo que ayuda a recordarlas como Arrange, Act, Assert. Esta anatomía también la puedes encontrar nombrada como given, when, then. Si puedo conseguir que esos tres bloques sean de una sola línea, todavía mejor.


---


Dobles de prueba (Mocks) En esencia, son objetos o funciones que suplantan partes del código de producción. La necesidad de su uso surge cuando se quiere probar un artefacto que depende de otro. Una buena práctica a la hora de usarlos es no simular elementos de terceros. Es decir, si tienes que “mockear” una librería de terceros, crea un wrapper sobre ella y simula este último.


Tipos de dobles: Según la terminología de Gerard Mezaros y Martin Fowler, existen principalmente 5 tipos de dobles: Stubs, spies, mocks estrictos, fakes y dummies. 

DEFINICIONES: 

Stubs: Son muy simples, no tienen memoria, sino que devuelven una respuesta concreta. Se usan para comprobar consultas que no son directas, es decir que no solamente opera con los posibles argumentos que pueda tener la función sino que requiere de otra fuente de datos. Los stubs permiten reemplazar esa fuente de datos. Por ejemplo, para reemplazar una llamada a una API o a una base de datos.

Spies y Mocks estrictos Tanto los espías como los mocks estrictos son objetos que tienen memoria para registrar las llamadas que se les hacen. Estas llamadas las podemos consultar para verificar si el artefacto que queremos probar tiene el comportamiento esperado. Se usan para verificar comandos.

Dummies y fake objects Los dummies solo se necesitan para completar los datos de un test, por ejemplo la lista de parámetros de un método. No suelen ser muy comunes en sistemas bien diseñados Los fakes objects son implementaciones completamente funcionales, pero simplificadas. Ayudan a abaratar las pruebas porque simplifican la forma en que se hace la validación o bien se ejecutan más rápido que si la pieza fuese la real. Por ejemplo un repositorio en memoria.

---

27_01_2025

El  assertAll() se puede usar para varias aserciones en un solo test unitario cuando queremos testear lo mismo pero con distintos datos.

### **¿Cómo funciona `assertAll`?**

En lugar de detenerse en la primera afirmación fallida, como ocurre con las afirmaciones tradicionales, `assertAll` ejecuta todas las afirmaciones que contiene y reporta todas las fallas al final. Si todas las afirmaciones pasan, el test será exitoso.

**Firma del método:**

java

CopiarEditar

`static void assertAll(String heading, Executable... executables)`

- **`heading`**: Un título opcional que describe el grupo de afirmaciones.
- **`executables`**: Un vararg de expresiones que implementan la interfaz funcional `Executable`.

---

### **¿Por qué es válido usar `assertAll`?**

1. **Validación exhaustiva**: Permite verificar múltiples condiciones en una sola prueba sin detenerse en la primera falla.
2. **Más información en fallos**: Si múltiples condiciones fallan, muestra todos los errores en lugar de solo el primero. Esto facilita la depuración.
3. **Organización**: Agrupa de manera lógica afirmaciones relacionadas, mejorando la legibilidad del test.

---

### **Reglas para usar `assertAll`**

1. **Debe contener al menos una afirmación**: No tiene sentido llamarlo sin afirmaciones dentro.
2. **Las afirmaciones deben ser independientes**: Cada afirmación debe ser autónoma y no depender del resultado de otras.
3. **No afecta la lógica del test**: Si una afirmación falla, el resto se ejecuta, pero no cambia el flujo de ejecución fuera del test.
4. **Evitar lógica compleja dentro de los `Executable`**: Es mejor mantener las afirmaciones simples y claras.


```java

import static org.junit.jupiter.api.Assertions.*;

import org.junit.jupiter.api.Test;

class PersonTest {

    @Test
    void testPersonProperties() {
        Person person = new Person("Rodrigo", 30);

        assertAll("Validating person properties",
            () -> assertEquals("Rodrigo", person.getName(), "Name should be Rodrigo"),
            () -> assertTrue(person.getAge() > 18, "Age should be greater than 18"),
            () -> assertNotNull(person, "Person object should not be null")
        );
    }
}```
---

Ciclo de vida del API de JUnit 5 

- **@BeforeAll**: Configuración que se ejecuta una sola vez antes de todos los tests en la clase.
- **@BeforeEach**: Configuración que se ejecuta antes de cada test (para evitar efectos secundarios de otros tests).
- **@Test**: Define los tests unitarios.
- **@AfterEach**: Limpieza que se ejecuta después de cada test.
- **@AfterAll**: Limpieza que se ejecuta una sola vez después de la ejecución de todos los tests en la clase.

Algunas de estas tienen mas sentido para test de integración que los test unitarios. 

Ejemplos de uso: 

_class BookShelfTest {_

_@BeforeAll_

_static void connectDB() {_
_…_
_}_
// por ejemplo para cargar una lista de libros, pero si se modifican en alguno, ya esta viciado el dato, por eso que carguen todos con los mismos datos iniciales de los libros
_@BeforeEach_

_void initializeBookShelfWithDB() {_
_…_
_}_

_@Test_

_void shouldGiveBackAllBooksInShelf() {_

_…_

_}_

  //borrar la lista despues de cada test
_@AfterEach_

_void deleteShelfFromDB() {_

_…_

_}_

  //borrar todo me desconecto de la base de datos
_@AfterAll_

_static void closeConnectionDB() {_
_…_
_}_
_}_