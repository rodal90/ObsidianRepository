
Es de Front.

1. Contenedor en esté caso de Java es una ventana Windows.
2.  Componentes: botones , caja de texto, labels, checkbox, listas desplegables, input, etc. hay dos tipos de componentes , los que saca del sistema operativo y los que programa en java. Los que sacan fuera del sistema operativo "ligeros" y los que programa en java se llaman "heavy". Componentes avanzados: Jtablet y otros, son interactivos.
3.  SGE Sistemas de gestión de eventos: como clicks, o cuando paso por encima o cuando tal cosas suceda has tal cosa.
                   Sistemas de eventos:
                   - Inference Model
                   - EDM: Es más moderno pero es un poco más complejo. Listeners, dos objetos implicados en cada evento (el source object puede ser por ejemplo un botón, ventana, etc. : es el que produce el evento y el listener object es el que lo escucha siempre es un objeto de una interface Java (esta clase solo contiene métodos vacíos o constantes)).

-  **Los métodos static hacen que no sea necesario crearse un objeto.

Hay dos librerias con las cuales podemos trabajar la interfaz gráfica:  

Libreria AWT: Abstract Window Toolkit saca del sistema operativo la apariencia de sus componentes.

Libreria Swing: Este se programa en Java, entonces nos da más libertad para cambiar todo lo estético. El paquete event que maneja todos los eventos, por ejemplo los "import" que es lo que se utiliza para importar la bibliotecas están en AWT asi que tendremos que usarla igual, aunque usemos en el diseño Swing.

import.java.awt.* -> Solo importa todas las clases, pero no los paquetes.
import.java.awt.event.* ->importa todas las clases del paquete `java.awt.event`. Este paquete contiene clases que permiten manejar eventos en interfaces gráficas de usuario (GUI), como acciones del teclado, clics de ratón, movimientos del ratón, y otros eventos relacionados con la interacción del usuario.

Constructor: Es un método que tiene el nombre de la clase, y normalmente se utiliza para inicializar las variables y 


**Interfaz**: En Java, una **interfaz** es una colección de métodos abstractos (métodos que no tienen implementación) y constantes que las clases pueden implementar. Las interfaces definen un contrato que cualquier clase que las implemente debe cumplir, pero no proporcionan la implementación de los métodos, solo las declaraciones. Una interfaz especifica qué debe hacer una clase, pero no cómo hacerlo.

### Características clave de una interfaz en Java:

1. **Declaración de métodos sin implementación**:
    
    - Los métodos en una interfaz no tienen cuerpo, lo que significa que no proporcionan detalles sobre cómo se realiza una tarea, solo que la tarea debe realizarse.

**Overload o sobrecargado**: Se aplica a métodos (Polimorfismo) y también se aplica a operadores (ej. =,!=.+ ( el + esta sobrecargado porque sirve para sumar y también para concatenar)).

***INFO: Dos objetos utilizarán interfaces para comunicarse entre ellos, y el núcleo será una clase privada.

----

### Corrección del enunciado:

1. **"Las clases abstractas deben tener por lo menos un método abstracto"**: Esto **no es obligatorio**. Una clase abstracta **puede tener cero o más métodos abstractos**. Es decir, puede que una clase abstracta no tenga ningún método abstracto, pero igualmente puede ser declarada como abstracta. Lo importante es que una clase abstracta **no puede ser instanciada directamente**.
    
2. **"Se define como Abstract"**: Una clase abstracta se declara con la palabra clave `abstract` en su definición, al igual que los métodos abstractos. Por ejemplo:
    
    java
    
    Copiar código
    
    `abstract class Animal {     abstract void hacerSonido();  // Método abstracto }`
    
3. **"El método tiene que ser redefinido, cuando hereda"**:
    
    - Si una clase hija hereda de una clase abstracta, **debe proporcionar implementaciones (redefinir)** todos los métodos abstractos que la clase abstracta tenga, a menos que también sea una clase abstracta.
    - Si no lo hace, entonces la subclase también deberá declararse como abstracta.
    
    Ejemplo:
    
    java
    
    Copiar código
    
    `abstract class Animal {     abstract void hacerSonido();  // Método abstracto, no tiene implementación }  class Perro extends Animal {     @Override     void hacerSonido() {         System.out.println("El perro ladra");     } }`
    
4. **"Como cuando una clase hereda de una interfaz, los métodos de la interfaz se redefinen"**:
    
    - Esto es correcto en parte. Cuando una clase implementa una interfaz, **debe proporcionar una implementación** para todos los métodos de la interfaz, ya que los métodos de la interfaz son siempre abstractos (excepto los métodos `default` o `static` introducidos a partir de Java 8).
    - En el caso de una clase abstracta, sin embargo, no necesariamente tiene que implementar todos los métodos abstractos de inmediato; puede dejar que la clase que herede de ella lo haga.

### Comparación entre clases abstractas e interfaces:

- **Clases abstractas**:
    - Pueden tener métodos abstractos y métodos con implementación.
    - Pueden tener campos (variables de instancia), y estos pueden tener diferentes modificadores de acceso (como `private`, `protected`, etc.).
    - Solo pueden extenderse de una clase abstracta a la vez (herencia simple).
- **Interfaces**:
    - Antes de Java 8, solo podían tener métodos abstractos. A partir de Java 8, pueden tener métodos con implementación mediante `default` o `static`.
    - Todos los métodos abstractos son implícitamente `public` y no pueden tener cuerpos (excepto los `default` y `static`).
    - Una clase puede implementar varias interfaces a la vez (herencia múltiple).

### Ejemplo de clases abstractas:

java



```java
abstract class Vehiculo {
    // Método abstracto
    abstract void arrancar();

    // Método con implementación
    void detener() {
        System.out.println("El vehículo se ha detenido.");
    }
}

class Coche extends Vehiculo {
    // Implementa el método abstracto
    @Override
    void arrancar() {
        System.out.println("El coche ha arrancado.");
    }
}

public class Main {
    public static void main(String[] args) {
        Coche miCoche = new Coche();
        miCoche.arrancar();  // Implementación de Coche
        miCoche.detener();   // Implementación heredada de Vehiculo
    }
}


```

[[Drawing 2024-09-25 09.12.51.excalidraw]]