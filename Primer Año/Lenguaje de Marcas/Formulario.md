
Es un archivo JavaScript que comienza con `"use strict" y console.log("script.js 1.1")`.
 *(siempre hay que acordarse de conectar a través de un script en el index.html).*


Iniciamos una función, como es la función de inicialización es una buena práctica utilizar `init`:

                     function initForm(){
                     
                     }
 Dentro de la  función de inicialización creamos la clase, en este caso la clase se llamara `RowProducto`:


                     class RowProducto{
                     }

Primero identificamos cada parte que necesitamos crear, ya sea botones , inputs, áreas de texto, labels, etc.  Luego guardamos en variables lo que vamos creando como aquí:

                       contenedor = document.createElement("div");

                          fieldSetName = document.createElement("fieldset");

                          fieldSetImporte = document.createElement("fieldset");
                          
                         labelName = document.createElement("label");

                         inputName = document.createElement("input");

                          labelImporte = document.createElement("label");

                          inputImporte = document.createElement("input");

Después de guardar los elementos que hemos creado en variables, ya podemos crear el `constructor`: 


                      constructor() {
   `this.contenedor.classList.add("row-producto");` es una línea de código que se utiliza para agregar una clase CSS al elemento `div` que se está creando en ese momento.

En resumen, `this.contenedor.classList.add("row-producto");` es una línea de código que se utiliza para agregar la clase CSS `row-producto` al elemento `div` que se está creando en ese momento. Esta clase CSS se utiliza para aplicar estilos al elemento `div` y hacer que se vea como una fila de productos en el formulario: 

            this.contenedor.classList.add("row-producto");

`this.labelName.textContent = "Nombre";` es una línea de código que se utiliza para establecer el texto del elemento `label` que se está creando en ese momento.

En resumen, `this.labelName.textContent = "Nombre";` es una línea de código que se utiliza para establecer el texto del elemento `label` a "Nombre". Esta línea de código se utiliza para mostrar el texto "Nombre" en la página web

            this.labelName.textContent = "Nombre";

            this.labelImporte.textContent = "Importe";

En resumen, `this.inputImporte.name="importe-producto";` es una línea de código que se utiliza para establecer un atributo `name` dentro de la etiqueta `inputImporte` y ponerle el nombre: `"importe-producto"`. Esta línea de código se utiliza para mostrar el texto "Nombre" en la página web:

            this.inputImporte.name="importe-producto";

            this.inputName.name="nombre-producto"

En las siguiente parte estamos metiendo dentro del `fieldSetName` el label y el input asociado al nombre, el `labelName` y el `inputName`:

            this.fieldSetName.append(this.labelName, this.inputName);

            this.fieldSetImporte.append(this.labelImporte, this.inputImporte);

En esta siguiente parte estamos metiendo dentro de el div contenedor los dos FieldSets:

            this.contenedor.append(this.fieldSetName, this.fieldSetImporte);
            
        }

Luego  creamos una variable para llamar a través de su id a el "`Form`" que se encuentra en el HTML (index.html), siempre recordar que cuando es un id es necesario poner  "`#`" antes del nombre del id, y llamarlo con el "`querySelector`":

                   const formulario = document.querySelector("#nota-pedido");

De la misma forma llamamos al `contenedorProductos` (el div dentro del cual van a aparecer los productos) a  través de su id: 

          const contenedorProductos = document.querySelector("#contenedor-productos");

y ahora el botón nuevo producto: 

       const botonNuevoProducto = document.querySelector("#anadir-producto");

Luego de guardar el botón en la variable `botonNuevoProducto`, es muy importante de que sí el botón se encuentra dentro de un formulario le hagamos el `preventDefault`:

            `botonNuevoProducto.addEventListener("click", e=>{`
                           e.preventDefault();
                           const newRow= new RowProducto();

             contenedorProductos.append(newRow.contenedor);




1. `botonNuevoProducto.addEventListener("click", e=>{...})`: Esta línea de código agrega un evento de clic al botón "Nuevo producto". Cuando se hace clic en el botón, se ejecutará la función anónima que se pasa como segundo argumento.
2. `e.preventDefault();`: Esta línea de código evita que se ejecute la acción predeterminada del evento de clic. En este caso, evita que se recargue la página web.
3. `const newRow= new RowProducto();`: Esta línea de código crea una nueva instancia de la clase `RowProducto`. Esta instancia se utiliza para crear una nueva fila de productos en el formulario.
4. `contenedorProductos.append(newRow.contenedor);`: Esta línea de código agrega el elemento `div` de la nueva fila de productos al contenedor principal de productos. Esto hace que la nueva fila de productos se muestre en la página web.
5. `//recordar siempre hacer referencia al contenedor, porque sino sale el objeto porque newrow es una classe objeto que es Rowprodcuto`: Esta línea de código es un comentario que recuerda al programador que siempre debe hacer referencia al elemento `div` de la nueva fila de productos, porque si no lo hace, se mostrará el objeto `RowProducto` en la página web en lugar de la fila de productos.


Ahora vamos con el botón enviar, creamos una variable para guardar el botón:

            const botonEnviar = document.querySelector("#submit");

**Lógica para enviar los datos del formulario: 

Iniciamos por utilizar `botonEnviar` y agregarle un evento "`click`" y dentro de una función anónima hacer el preventDefault para evitar que se refresque la página cuando le demos click, porque es parte del formulario:

    botonEnviar.addEventListener("click", e=>{

        e.preventDefault();

Esta línea de código utiliza el método `querySelector` para seleccionar el primer elemento en la página web que tenga el atributo `name` con el valor "`nombre-cliente`". El método `querySelector` devuelve un objeto `Element` que representa el elemento seleccionado.

        const nombreCliente=document.querySelector("[name='nombre-cliente']")

  //captura por atributo `name` .

Aquí también se hace los mismo pero se captura el primer elemento que tenga el atributo `name` con el valor "`cif-cliente`":

        const cifCliente= document.querySelector("[name='cif-cliente']")

  //acordarse que es el atributo `name` lo que vas a usar.

        console.log(nombreCliente.value, cifCliente.value);

Aquí asignamos a la variable productos  todos los objetos creados con el constructor y guardados en el div, contenedor con la clase "row-producto" que le agregamos con el classList.add:

**Super importante como es una clase parra llamarlo hay que poner el punto primero.

        const productos= document.querySelectorAll(".row-producto");

  //esto devuelve una lista de nodos

        console.log(productos);
        
//este array va contener mapas con clave valor.

`const productosFormulario = new Array();`

Esta línea de código crea una nueva matriz vacía llamada `productosFormulario`. Esta matriz se utilizará para almacenar los datos de los productos que se capturan en el formulario.

`//ahora vamos a capturar los datos`

Esta línea de código es un comentario que indica que a continuación se capturarán los datos de los productos en el formulario.

`productos.forEach(productos=>{...})`

Esta línea de código utiliza el método `forEach` para iterar sobre cada elemento en la matriz `productos`. El método `forEach` toma una función como argumento y la ejecuta para cada elemento en la matriz.

`const nombreProducto = productos.querySelector('[name="nombre-producto"]');`

Esta línea de código utiliza el método `querySelector` para seleccionar el primer elemento en el formulario que tenga el atributo `name` con el valor "nombre-producto". El método `querySelector` devuelve un objeto `Element` que representa el elemento seleccionado.

`const importeProducto = productos.querySelector('[name="importe-producto"]');`

Esta línea de código utiliza el método `querySelector` para seleccionar el primer elemento en el formulario que tenga el atributo `name` con el valor "importe-producto". El método `querySelector` devuelve un objeto `Element` que representa el elemento seleccionado.

`const productoMapa = { nombre: nombreProducto.value, importe: importeProducto.value }`

Esta línea de código crea un nuevo objeto llamado `productoMapa` que contiene dos propiedades: `nombre` y `importe`. Estas propiedades se asignan los valores de los campos de entrada del nombre y el importe del producto.

`productosFormulario.push(productoMapa);`

Esta línea de código agrega el objeto `productoMapa` a la matriz `productosFormulario`.

`console.log(nombreProducto.value);` `console.log(importeProducto.value);`

Estas líneas de código imprimen los valores de los campos de entrada del nombre y el importe del producto en la consola del navegador.

En resumen, esta parte del código captura los datos de los productos en el formulario y los almacena en la matriz `productosFormulario`. El código utiliza el método `forEach` para iterar sobre cada elemento en la matriz `productos`, y el método `querySelector` para seleccionar los campos de entrada del nombre y el importe del producto. Los valores de estos campos de entrada se almacenan en un nuevo objeto llamado `productoMapa`, que se agrega a la matriz `productosFormulario`. Finalmente, los valores de los campos de entrada del nombre y el importe del producto se imprimen en la consola del navegador.

        const productosFormulario =new Array();

//ahora vamos a capturar los datos

        productos.forEach(productos=>{

            const nombreProducto = productos.querySelector('[name="nombre-producto"]');

            const importeProducto = productos.querySelector('[name="importe-producto"]');

            const productoMapa = {

                nombre: nombreProducto.value,

                importe: importeProducto.value

            }

            productosFormulario.push(productoMapa)

            console.log(nombreProducto.value);

            console.log(importeProducto.value);

        })

  

    })