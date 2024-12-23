
1) Primer Ejercicio, era de dependiendo del array de strings que se pasara a una función distintos mensaje debían de salir.  No lo pude hacer solo. Pero si con chatgpt. De los conceptos que se usaron hubieron dos que no tenía muy claros:

      1- el primero era el de que el switch lo podes utilizar para comprobaciones al usar un booleano dentro por ejemplo: 

```javaScript   


const nombre = "ana";

switch (true) {
  case ["ana", "maria", "sol"].includes(nombre): // Evalúa si 'nombre' está en el array
    console.log("Hola ana, maria, sol, ¡gracias por venir!");
    break;
  case nombre === "Alice":
    console.log("Hola Alice!");
    break;
  default:
    console.log(`Hola ${nombre}, no te esperaba.`);
}```

Acá esta comprobando que el nombre o la variable que le estamos pasando esté incluida dentro de las opciones que le damos, en este caso ana si aparece en el array.

2- Luego tenemos el "includes"   El método **`includes`** es una función que pertenece a los arrays y cadenas de texto. Sirve para comprobar si un valor está presente en un array o una cadena. Retorna un booleano si el valor esta presente en el array o cadena de texto retorna true y si no está retorna false.

**Instrucciones del ejercicio:** 

Probablemente conozcas el sistema de "me gusta" de Facebook y otras páginas. Las personas pueden dar "me gusta" a publicaciones de blogs, imágenes u otros elementos. Queremos crear el texto que debe mostrarse junto a dicho elemento.

Implementa la función que reciba un array que contenga los nombres de las personas a las que les gusta un elemento. Debe devolver el texto que se muestra como se indica en los ejemplos:

```
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```

**Respuesta del ejercicio:**
```javaScript  
function likes(names) {
  if (names.length === 0) {
    return "no one likes this";
  } else if (names.length === 1) {
    return `${names[0]} likes this`;
  } else if (names.length === 2) {
    return `${names[0]} and ${names[1]} like this`;
  } else if (names.length === 3) {
    return `${names[0]}, ${names[1]} and ${names[2]} like this`;
  } else {
    return `${names[0]}, ${names[1]} and ${names.length - 2} others like this`;
  }```

**Explicación:**

en la función entra un Array al que le damos el nombre de "names", luego tenemos un "if" donde comparamos la longitud del Array con 0, si el Array esta vacío la longitud es 0 asi que si es estrictamente igual tiene que sacar el mensaje de que "no one like this".
En el 2ndo if hacemos la comparación de la longitud de names ("El Array") con 1 , como tiene un solo nombre la longitud seria 1 entonces el mensaje es : el nombre que este en la posición del "Array[0] likes this" osea el único nombre presente en el array.
En el 3er if hacemos la misma comparación estricta pero con la longitud de 2, entonces deber retornar: "el nombre que esta en la  posición[0] del array luego el nombre que esta en la  posición[1] like this".
En el 4to if hacemos la misma comparación pero con 3 en longitud, y retornamos: "el nombre que esta en la  posición[0] del array, luego el nombre que esta en la  posición[1] y luego el nombre que esta en la  posición[2]  like this".
Para el 5to no hacemos un "else if" sino un "else" común en el cual le pedimos que retorne:  "el nombre que esta en la  posición[0] del array, luego el nombre que esta en la  posición[1] y luego la longitud del Array -2 posiciones  par que de un valor numérico que sea el restante de los no nombrados que igual están dentro del 'Array like this'".


**re loco otras soluciones:**

1.

```javaScript  

function likes(names) {
  names = names || [];
  switch(names.length){
    case 0: return 'no one likes this'; break;
    case 1: return names[0] + ' likes this'; break;
    case 2: return names[0] + ' and ' + names[1] + ' like this'; break;
    case 3: return names[0] + ', ' + names[1] + ' and ' + names[2] + ' like this'; break;
    default: return names[0] + ', ' + names[1] + ' and ' + (names.length - 2) + ' others like this';
  }
}
```
Paso como dato por el switch los names.length, osea un numero y luego cada uno era el caso, en caso de ser 0 retorna el mensaje tal, si el length es 1 retorna el nombre en la posición tal del array, cabrón, esta era la solución que yo tenia en mente. Le da la opción a names de que si esta vacío o es falsely pueda convertirse en un array vacio para poder procesarlo.



2.

```javaScript  
function likes(names) {
  return { // todos estos son clave valor
    0: 'no one likes this',
    1: `${names[0]} likes this`, 
    2: `${names[0]} and ${names[1]} like this`, 
    3: `${names[0]}, ${names[1]} and ${names[2]} like this`, 
    4: `${names[0]}, ${names[1]} and ${names.length - 2} others like this`, 
  }[Math.min(4, names.length)] //de aca sale el número dependiendo de si el name length es mayor o menor a 4. compara los dos valores y selecciona el mínimo
}
```
**1. `function likes(names) { ... }`:**

- Declara una función llamada `likes` que acepta un parámetro: `names`. Se espera que `names` sea un array de strings (nombres de personas).

**2. `return { ... }[Math.min(4, names.length)]`:**

- Esta es la parte central de la función. Usa un objeto literal y acceso a propiedades mediante corchetes.
- **Objeto literal `{ ... }`:** Este objeto contiene pares clave-valor, donde las claves son números (0, 1, 2, 3, 4) y los valores son las cadenas de texto que se devolverán.
- **`Math.min(4, names.length)`:** Esta expresión calcula el mínimo entre 4 y la longitud del array `names`. Esto es crucial para manejar diferentes cantidades de nombres:
    - Si hay 0 nombres, `names.length` es 0, y `Math.min(4, 0)` devuelve 0.
    - Si hay 1 nombre, `names.length` es 1, y `Math.min(4, 1)` devuelve 1.
    - Si hay 2 nombres, `names.length` es 2, y `Math.min(4, 2)` devuelve 2.
    - Si hay 3 nombres, `names.length` es 3, y `Math.min(4, 3)` devuelve 3.
    - Si hay 4 o más nombres, `names.length` es 4 o más, y `Math.min(4, names.length)` devuelve 4.
- **`[ ... ]`:** Los corchetes se utilizan para acceder a una propiedad del objeto. El resultado de `Math.min(4, names.length)` se usa como la clave para acceder a la propiedad correspondiente del objeto.

3.

```javaScript  

function likes(names) {
  return names.length === 0 ? 'no one likes this' :
         names.length === 1 ? `${names[0]} likes this` :
         names.length === 2 ? `${names[0]} and ${names[1]} like this` :
         names.length === 3 ? `${names[0]}, ${names[1]} and ${names[2]} like this` :
         `${names[0]}, ${names[1]} and ${names.length - 2} others like this`
}
```
- **Parámetro `names`**:
    
    - Es un array que contiene los nombres de las personas a las que les gusta algo.
    - Por ejemplo: `["Alice", "Bob", "Charlie"]`.
- **Uso del operador ternario**:
    
    - El operador ternario tiene esta estructura:  
        `condición ? resultado_si_verdadero : resultado_si_falso`
    - Se pueden encadenar múltiples operadores ternarios para manejar varias condiciones.
- **Flujo de la función**:
    
    - Verifica el número de elementos en el array `names` usando `names.length`.
    - Devuelve un mensaje diferente según el número de elementos en el array.
----

