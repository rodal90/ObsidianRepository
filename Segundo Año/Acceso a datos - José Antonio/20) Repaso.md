
Métodos(Funciones) y atributos(variables) deben ser generalmente declarados privados.

Los constructores, métodos , getter y setters la mayoria de veces se declaran public para poder construir objetos.


Los constructores solo serán privados cuando estemos haciendo una clase singleton (Solo una instancia de la clase). (Service, Controller,Repository solo creamos una instancia, spring gestiona los java-beans singletons (SpringBean). Delegamos el ciclo de vida a Spring)

En relación a las entities las hemos instanciado o creado nosotros, por eso no son clases singletons.


Set , List y colecciones abstracta.  Podemos usar el método "of" porque es estático.  Osea set es clase abstracta con métodos estáticos, por eso se puede usar sin instanciarla.

 Math también es abstracta y solo tiene atributos fijos o estáticos. (no hay variables, solo constantes). Métodos clean ex, los usas y los desechos solo te quedas con lo que devuelve. 

Ejemplos Math:

Math.sqrt(9) = 3  (Raiz cuadrada)
Math.pow(2,3) = 8 (Potencia)

---

Abstracción: Resume la utilidad que tienen los objetos de la vida real.     Para que es util, necesito conocer sus características(Variables, Atributos) y  comportamientos(Funciones, Métodos). 

Polimorfismo:  // Cursiva significa que es una clase Abstracta es una forma de representación.

Firma del método, no hay cuerpo pero que los hijos que lo hereden le den su propio cuerpo. El método  luego los hijos hacen con este método lo que les de la gana. 

Se puede tener  Métodos abstractos en clases concretas, no porque dejan de ser concretas.  

La clases abstractas pueden tener métodos abstractos (firmas que no te dicen como hacerlo) y métodos concretos que te dicen como hacerlo también.

El polimorfismo se basa en que una clase base (o superclase) puede definir métodos comunes, y las clases derivadas (o subclases) pueden implementar esos métodos de forma específica. Esto permite que el mismo método tenga diferentes comportamientos según el tipo de objeto que lo use.

### Ejemplo sencillo:

Piensa en el verbo **"comer"**. Todos los animales comen, pero cada uno lo hace de forma diferente:

1. Un **perro** puede comer huesos.
2. Un **gato** puede comer pescado.
3. Un **pájaro** puede comer semillas.

El "acto de comer" es el mismo, pero cómo se realiza depende del tipo de animal.

### Ventajas del polimorfismo:

1. **Código más flexible y reutilizable**: Puedes usar una sola referencia (como `Animal`) para trabajar con diferentes tipos de objetos.
2. **Facilita la extensión del programa**: Si agregas un nuevo tipo de animal, simplemente defines cómo se comporta, sin cambiar el resto del código.

----

Encapsulación: Caja negra, no necesito saber los detalles, solo necesito saber para que usarlo y saber que cuando lo use va a hacer lo que yo necesite. (Mientras menas cosas enseñemos mejor, reduce cantidad de errores y problemas de funcionamiento).

---
Herencia: Habilidad para crear super clases de las que luego descienden subclases o hijos que compartan todo lo que les a dado los padres.  

Si a la clase padre le pongo un método para que puedan heredar los get y set, y los hijos heredarían de la misma manera.

Los hijos pueden sobre-escribir los métodos de los padres, puede aprovechar la funcionalidad de mi padre y añadir lo que completa (sobre-escribir parcialmente). (Super.  "Hace lo del padre" antes o después puedo hacer lo que yo quiera).  Los hijos heredan les guste o no les guste todo lo del padre , es una dependencia muy grande y se le llama acomplamiento.
Los atributos se heredan todavía mas.

Un método abstracto es una característica de las clases abstractas que no tiene implementación en la clase base. Al heredarse en una subclase, tiene las siguientes características clave:

1. **Debe ser implementado obligatoriamente**:  
    Una subclase que herede de una superclase con métodos abstractos debe proporcionar una implementación concreta para esos métodos. Si no lo hace, la subclase también debe declararse como abstracta.
    
2. **Define un contrato**:  
    Un método abstracto actúa como un contrato que obliga a las subclases a implementar un comportamiento específico, asegurando una estructura común entre todas las clases que heredan de la superclase.
    
3. **No tiene cuerpo en la superclase**:  
    El método abstracto no tiene una implementación en la superclase, solo se define su firma (nombre, parámetros y tipo de retorno).
    
4. **Polimorfismo**:  
    Aunque las subclases implementen los métodos abstractos de manera específica, pueden ser referenciados a través de la superclase, lo que permite el uso de polimorfismo.

"ser" -> Herencia =>  cuando eres eso mismo pero un hijo.

"usar/tener" -> Composición  => un auto tiene motor, si entonces usa motor entonces se usa composición.

El Polimorfismo ejemplo: Si hacemos un bucle  para recorrer un Array list de objetos animales =>  pero al recorrer el bucle,  cuando usemos los métodos ( su comportamiento) el que usa es el del objeto específico. Por eso sale o lo que resuelve es la versión del hijo, porque esta puede ya ser una modificación del método o función del padre.  

---

Desventajas de composición (usar/tener): Tenemos que crear un objeto de la clase a la cual queremos acceder métodos y atributos.  Ventajas: No creas herencias inútiles. No hay polimorfismo directo.

Herencia(Soy) Ventajas: Nos permite usar polimorfismo.  Desventajas: Hay la posibilidad de crear herencias innecesarias.


Inversion de dependencia  a través de Interfaces. 

Ejemplo: el gato en vez de depender de la comida específica : Salchicha broccoli, etc. 

con las interfaces:  la Salchicha , el broccoli y el gato dependen de la interfaces, el método intermedio.

Las interfaces son mejores que las clases abstractas, porque heredar solo se puede de una clase, pero interfaces se puede implementar muchas. 
La herencia solo la queremos usar cuando sea realmente imprescindibles, si tenemos dudas usar composición. Pero si usamos composición como manejamos el polimorfismo ya que no se puede usar polimorfismo, pues invertimos las dependencias creando una interface intermedia. 

---

Buscar: 

Rombo vacío Agregación: Manera de diferenciar cuando tenemos dos entidades fuertes o cual es más débil.

Rombo lleno Composición: 

---

Como saber cuando es correcto he incorrecto usar herencia:

Cuando el hijo es el padre con pocas modificaciones, cuando hay mucha sobre-escritura entonces lo mejor es hacer una composición porque no son los mismo y lo más seguro es que una clase use a la otra más que ser.

Si la creación de un hijo genera la necesidad de hacer modificaciones del padre posiblemente no sea herencia.

Cuando solo hay un hijo del padre, lo mejor sería que sea una clase, no debería de haber herencia.

---
Cuando sucede que hay una explosión demográfica Hay que distinguir la tenencia, y parar la herencia de uso tenencia. 



----

SERVICIOS 09/01/2025

Los servicios son los que tienen el modelo de negocios.

---

Uso para autorizar el uso: 

Asume que hay un sistema con usuarios y roles. 

@Secured ({"USER","MANAGER"})
@RolesAllowed ({"USER","MANAGER"})
@PreAuthorize("hasRole"('USER') or hasRole('MANAGER')")


---

spring: 3 injections ways:

@Autowired

Constructors

Setters

---

Cuando es necesario utilizar un parámetro en el método o constructor, lo que se usa en test unitarios es ParameterResolver ("Resolutor de parámteros").



