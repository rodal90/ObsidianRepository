
**Necesitamos una carpeta de "assets", dentro una de "`css`" y otra de "`js`". Fuera dejamos el json, que segura mente vamos a construir y el "`index`.`html`" de toda la vida.
Un total inicial de 4 archivos:
1) style.css que se conecta con un "link" a la carpeta en el `index`. `href`.
2) formulario.js que se conecta al `index` con un "`script`" `src`.
3) El index.html. 
4) el json  va adentro de assets pero fuera de las carpetas css o js.


"use strict"

console.log("colegio.js v.1.1")

  

/* PASO NÚMERO 1*/

/*Inicializamos la funcion iniciar */

initAlumnosListado();

function initAlumnosListado() {

    /* PASO NÚMERO 2 */

    /*Creamos una clase */

  

    class lineasAlumnos {

  

        /*paso 2.1 inicializamos las variables con las claves que tenemos en el json como en java */

  

        nombre = "";

        edad = "";

        apellido = "";

        /*Creamos un array nuevo como objeto para guardar en memoria. los valores se especifican en el constructor*/

        asignaturas = new Array; //new Array, array mayúscula

  

        /*PAOS NUMERO 3 */

        /*Creamos las demas variables que vamos a utilizar como: divs donde vamos a ir guardando la informacón, nota total o nota media o cualquier tipo de valor que se nos pida  */

        notaTotal = 0;

        notaMedia = 0;

        contenedorGeneral = document.createElement('div');

        conteDatosAlumno = document.createElement('div');

        conteNotas = document.createElement('div');

  

        /*PASO NUMERO 4 */

        /*Creamos el constructor */

        constructor(alumno) {//pasamos argumento alumnos, es lo que vamos a construir.

            /*paso numero 4.1 se adieren las clases a los divs para poder usarlos en css. ej. this.variable.classList.add()*/

            this.contenedorGeneral.classList.add('contGeneral');

            this.conteDatosAlumno.classList.add('contAlumnos');

            this.conteNotas.classList.add('contNotas');

            /* paso numero 4.2 se asignan los valores de las propiedades a los nuevos objetos alumno que creamos. this. es lo que se usa */

            this.nombre = alumno.nombre;

            this.apellido = alumno.apellido;

            this.edad = alumno.edad;

  

            /*paso numero 4.3 se itera con un forEach para agregar cada elemento de la variable (propiedad) asignatura  al nuevo objeto.*/

            /*asignatura es un parámetro o variable que representa cada elemento de la propiedad, es como el i del bucle for y por eso le decimos que agregue cada instancia resultado que encuentra una detras de otra con el push */

            alumno.asignaturas.forEach(respuesta => {

  

                this.asignaturas.push(respuesta)

  

            });

  

            /*PASO NUMERO 5 */

            /*Creamos variables constantes donde guardamos objetos html para poder darles estilo y pintarlos dentro del html. */

  

            const nombre = document.createElement("h2");/*agregamos clase al h2 */

            nombre.classList.add("nombre");/*decimos que el nombre va a ser un contenido de texto y lo que tiene que recojer es this.nombre que a su ves es el nombre de alumno dentro del constructor.  */

            nombre.textContent = this.nombre;

  

            const edad = document.createElement("h3");

            edad.classList.add("edad");

            edad.textContent = this.edad;

  

            const apellido = document.createElement("h3");

            apellido.classList.add("apellido");

            apellido.textContent = this.apellido;

  
          SUPER IMPORTANTE USAR LOS MISMOS NOMBRES AL MOMENTO DE ITERAR
            this.asignaturas.forEach(asignatura => {

                /*PASO NUMERO 6 */

                /*Iteramos una ves más asignaturas  y en cada iteración creamos una div individual para cada asignatura, tambien le damos una class */

                const asignaturaConst = document.createElement("div");

                asignaturaConst.classList.add("asignatura-container");

  

                const nombre = document.createElement("p");

                nombre.classList.add("nombre-asignatura");

                nombre.textContent = asignatura.nombre;

  

                const nota = document.createElement("p");

                nota.classList.add("nota-asignatura");
                   //SUPER IMPORTANTE USAR LOS MISMOS NOMBRES QUE HAY EN EL JSON 
                nota.textContent = asignatura.calificacion;

  

                /*PASO NUMERO 7 */

                /*Insertamos o usamos append para agregar dentro del contenedor el nombre y la nota */

                asignaturaConst.appendChild(nombre, nota)

  

                /*Insertamos en el div de clase conteNotas el contenedor donde guardamos el nombre y  la nota del alumno */

                this.conteNotas.append(asignaturaConst);

                /* Les decimos que la notaTotal que habiamos inicializado a cero va a ser igual a la suma de cada nota en asignaturas, los datos que guardamos en el array sumados.*/
        //SUPER IMPORANTE USAR LOS MISMOS NOMBRES QUE HAY EN JSON, CALIFICACION
                this.notaTotal += asignatura.calificacion;

            });

            /*Aca le decimos que la nota media va a ser la suma de las notas en el array dividido la cantidad total de asignaturas que haya dentro del array. simpre se hace referencia con this. */

            this.notaMedia = this.notaTotal / this.asignaturas.length;

  

            /*Creamos variable constante para guarda la notaMedia y mostrarla */

  

            const notaMedia = document.createElement('p');

            notaMedia.classList.add('nota-media');

            notaMedia.textContent = this.notaMedia;

            /*guardamos datos del alumno en conteDatosAlumno (nombre,apellido,edad) */

            this.conteDatosAlumno.append(nombre, apellido, edad);

            /*guardamos en el contenedor general el contenedor de datos de alumno, el contenedor de las notas y la nota media */

            this.contenedorGeneral.appendChild(this.conteDatosAlumno, this.conteNotas, notaMedia);

  

        }

  

    }

    /*PASO NUMERO 8 */

    /*Salimos de la clase por fin.Creamos una variable constante para guardar la llamada al json.*/

    const URLjson = "assets/cole.json";

  

    /*PASO NUMERO 9 */

    /*Super IMPORTANTE, ahora vamos a hacer la parte de fetch que es para utilizar el json o una API sacar información o enviar información, y utilizarla para alimentar los objetos que creamos con el constructor*/

    /*Le pasamos al fetch la variable con la direccion del json */

    fetch(URLjson).then(resp => {

        resp.json().then(alumnos => {

            printPedidos(alumnos);

        });

    });

  

    /*PASO NUMERO 10 */

    /*Creamos la función para imprimir los pedidos en este caso se llama printPedidos */

  

    function printPedidos(alumnos) {

        console.log(alumnos);

        /*creamos otra variable constante para seleccionar el div en el html donde vamos a guardar todo */

        const contenedor = document.querySelector(".superContenedor");

        /*ahora iteramos con un for each */

        alumnos.forEach(alumno => {

            /*Creamos otras constante para guardar IMPORTANTISIMO guardar por fin un nuevo objeto de la clase lineasAlumnos, el que diseñamos con el constructor. */

            const nuevoAlumno = new lineasAlumnos(alumno);

            /*Saco la media para mostrarla con lo demas */

            const media = document.createElement('strong');

            media.innerHTML = nuevoAlumno.notaMedia;

            /*Agrego el contenedor General al contenedor del index. */

            contenedor.append(nuevoAlumno.contenedorGeneral);

  

        });

            /*va con defer en index.html */

    };

  

};

