

**/* PASO NÚMERO 1*/
Inicializamos la función iniciar */ con `Init.`

  **/* PASO NÚMERO 2 */
Creamos una clase */

/*paso 2.1 inicializamos las variables con las claves que tenemos en el json como en java */

/*paso 2.2 Creamos un array nuevo como objeto para guardar en memoria. los valores se especifican en el constructor*/

**/*PAOS NUMERO 3 */
Creamos las demás variables que vamos a utilizar como: divs donde vamos a ir guardando la información, nota total o nota media o cualquier tipo de valor que se nos pida  */

**/*PASO NUMERO 4 */
Creamos el constructor */

/*paso numero 4.1 se adhieren las clases a los divs para poder usarlos en css. ej. `this.variable.classList.add`()*/

/* paso numero 4.2 se asignan los valores de las propiedades a los nuevos objetos alumno que creamos "`this`" es lo que se usa */

/*paso numero 4.3 se itera con un `forEach` para agregar cada elemento de la variable (propiedad) asignatura  al nuevo objeto.*/

/*asignatura es un parámetro o variable que representa cada elemento de la propiedad, es como el i del bucle `for` y por eso le decimos que agregue cada instancia resultado que encuentra una detrás de otra con el `push` */

  **/*PASO NUMERO 5 */
Creamos variables constantes donde guardamos objetos html para poder darles estilo y pintarlos dentro del html. */

/*paso numero 5.1 decimos que el nombre va a ser un contenido de texto y lo que tiene que recoger es `this.nombre` que a su ves es el nombre de alumno dentro del constructor.  */

   **/*PASO NUMERO 6 */ SIEMPRE USAR LOS NOMBRES QUE ESTAN EN EL JSON AL ITERAR DENTRO DEL ARRAY
Iteramos una ves más asignaturas  y en cada iteración creamos una div individual para cada asignatura, también le damos una `class` */

**/*PASO NUMERO 7 */ AQUI TAMBIEN SIEMPRE HACER REFERENCIA AL NOMBRE DEL JSON AL MOMENTO DE HACER LA CUENTA ARITMETICA PORQUE SON LOS DATOS DEL JSON LOS QUE SE ESTAN ITERANO Y SUMANDO O MUTIPLICANDO COMO EN EL EXAMEN 
Insertamos o usamos `append` para agregar dentro del contenedor el nombre y la nota 

/*paso numero 7.1 Insertamos en el div de clase `conteNotas` el contenedor donde guardamos el nombre y  la nota del alumno */

/*paso numero 7.2 Les decimos que la `notaTotal` que habíamos inicializado a cero va a ser igual a la suma de cada nota en asignaturas, los datos que guardamos en el array sumados.*/

 /*Acá le decimos que la nota media va a ser la suma de las notas en el array dividido la cantidad total de asignaturas que haya dentro del array. siempre se hace referencia con `this`. */

/*Creamos variable constante para guarda la `notaMedia` y mostrarla */

/*guardamos datos del alumno en `conteDatosAlumno` (`nombre,apellido,edad`) */

/*guardamos en el contenedor general el contenedor de datos de alumno, el contenedor de las notas y la nota media */

  **/*PASO NUMERO 8 */
  /*Salimos de la clase por fin creamos una variable constante para guardar la llamada al json.*/

**/*PASO NUMERO 9 */
/*Super IMPORTANTE, ahora vamos a hacer la parte de fetch que es para utilizar el json o una API sacar información o enviar información, y utilizarla para alimentar los objetos que creamos con el constructor*/

 /*Le pasamos al `fetch` la variable con la dirección del json */

**/*PASO NUMERO 10 */
/*Creamos la función para imprimir los pedidos en este caso se llama `printPedidos` */

/*creamos otra variable constante para seleccionar el div en el html donde vamos a guardar todo *

/*ahora iteramos con un `for each` */

/*Creamos otras constante para guardar IMPORTANTISIMO guardar por fin un nuevo objeto de la clase `lineasAlumnos`, el que diseñamos con el constructor. */

/*Saco la media para mostrarla con lo demás */
   
/*Agrego el contenedor General al contenedor del `index`. */


  /*va con `defer` en index.html */


           


