
Se basan en el concepto de objetos. Los objetos son contenedores que pueden almacenar propiedades, métodos o ambos. JavaScript no tiene una sintaxis específica para definir clases como otros lenguajes de programación, pero puede crear objetos utilizando funciones constructoras.

Aquí hay un ejemplo simple de una clase en JavaScript:


`class Perro {`
`constructor(nombre) {` 
`this.nombre = nombre;` 
`}` 
`hablar() {` 
`console.log(this.nombre + " ladra.");`  
   `}` 
`comer() {`
`console.log(this.nombre + " se alimenta.");` 
   `}` 
`}` 
`const d = new Perro("Mitzie");` 
`d.hablar(); // Mitzie ladra.` 
`d.comer(); // Mitzie se alimenta.`

En este ejemplo, creamos una clase `Perro` con un constructor que acepta un parámetro `nombre`. También definimos dos métodos, `hablar` y `comer`. Luego, creamos una nueva instancia de la clase `Perro` con el nombre "Mitzie" y llamamos a los métodos `hablar` y `comer`.

### Herencia y superclases

Las clases en JavaScript también pueden heredar propiedades y métodos de otras clases utilizando la palabra clave `extends`. La clase que hereda se denomina clase derivada o subclase, y la clase de la que hereda se denomina clase base o superclase.

Aquí hay un ejemplo de herencia en JavaScript:

`class Animal {`
  `constructor(nombre) {`  
    `this.nombre = nombre;` 
  `}`  
  
  `hablar() {` 
  `console.log(this.nombre + " hace un ruido.");`  
    `}`
   `}` 
   `class Perro extends Animal {` 
   `hablar() {`  
   `super.hablar();`  
   `console.log(this.nombre + " ladra.");`  
   `}` 
   `}` 
    `const d = new Perro("Mitzie");` 
    `d.hablar(); // Mitzie hace un ruido. Mitzie ladra.`

En este ejemplo, creamos una clase `Animal` con un constructor y un método `hablar`. Luego, creamos una clase `Perro` que extiende `Animal` y sobre-escribe el método `hablar` para llamar al método `hablar` de la superclase `Animal` y luego agregar su propio comportamiento.

### Métodos estáticos

Las clases también pueden tener métodos estáticos, que se pueden llamar directamente en la clase en lugar de en una instancia de la clase. Los métodos estáticos no tienen acceso al contexto `this` y no se pueden llamar en una instancia de la clase.

Aquí hay un ejemplo de métodos estáticos en JavaScript:

`class Rectangulo {`
`constructor(ancho, alto){` 
`this.ancho = ancho;` 
`this.alto = alto;` 
   `}`
`static area(ancho, alto) {` 
`return ancho * alto;` 
   `}` 
`}` 
`console.log(Rectangulo.area(5, 10)); // 50`


**INFORMACION DE EL TRABAJO DE JAVASCRIPT DE LENGUAJE DE MARCAS 

Este código define una clase en JavaScript llamada `Categorias`. La clase tiene cuatro propiedades:

- `contenedor`: un elemento HTML que se crea dinámicamente en el constructor.
- `id`: un identificador único para la categoría.
- `nombre`: el nombre de la categoría.
- `imagen`: la ruta de la imagen asociada a la categoría.

El constructor de la clase (`constructor`) recibe un objeto `datos` que contiene los valores iniciales para las propiedades `id`, `nombre` e `imagen`. El constructor crea dinámicamente un elemento `div` con la clase `miniatura-categoria` y agrega dos elementos hijos: un párrafo (`p`) con el texto del nombre de la categoría y una imagen (`img`) con la ruta de la imagen asociada.

Además, el constructor agrega un listener de eventos al elemento `div` para que cuando se haga clic en él, se ejecute el método `ejecutar`.

El método `ejecutar` redirige a una página llamada `index.html` en la carpeta `listados` con un parámetro `id_categoria` que tiene el valor de la propiedad `id` de la categoría.

En resumen, esta clase se utiliza para crear elementos HTML que representan categorías con una imagen y un nombre, y que cuando se hace clic en ellos, redirigen a una página de listados con el identificador de la categoría seleccionada.
``
