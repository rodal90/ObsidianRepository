
![[Capas.png]]

1) Capa clientes es del front end.

2) Capas de Servicios y web (Servidor Web) es back end. Apache Web Server.

3) Capa lógica de negocios (Servidor de Aplicaciones) es back end.

4) Capa de base de datos (Base de datos) es back end.

Para una empresa primeriza lo primero es enfocarse en la tecnología móvil.

Cuando se hace algún tipo de interfaz es necesario tomar en cuenta la cantidad de tiempo de carga, para mantener al cliente. 

Base de datos tiene que ser útil para la gestión. 


Apache Web Server: Policía de Tráfico, recibe petición del cliente la procesa, si la tiene el la devuelve automáticamente y si el no la tiene la busca en las otras capas.  Regula el tráfico. 

Las páginas estáticas normalmente se guarda la información en el servidor web para que puedan dar respuestas más rápidas. 

DoS: Denegation of Service


Dependiendo del grado de complejidad de la petición de datos, el Servidor Web determinará con quien se comunica, ya sea directamente con la base de datos o a través de un Servidor de Aplicaciones. 

No confundir Apache web =Servidor de web con  Apache Tomcat = Servidor de Aplicaciones.

*Apache Tomcat

*Glass Fish

Uso de bases de datos en memoria, reduce tiempo de trabajo debido a que no es necesario hace modificaciones continuas dentro de tu verdadera base de datos. Es como un espacio de esbozo de tu base de datos antes de crear la verdadera.  Hay una que se llama H2.

Base de datos:

Diferencia entre CHAR y VARCHAR:

CHAR(5): significa que vas a tener un límite de 5 caracteres, pero también siempre dejara  los espacios pedidos que en este caso son 5, sea que los llenemos con caracteres o no.

VARCHAR(5): Malo en tiempo de acceso pero bueno para ahorrar espacios, malo para cuando necesitamos modificar la información, porque los espacios se adaptan a los caracteres iniciales. 

**Service Level Agreement (SLA):** Parte de la responsabilidad de aplicación, es la velocidad de respuesta de cada petición, hay que cumplir con los tiempos estipulados. 

Es un acuerdo a nivel de servicio, es un contrato entre un proveedor de servicios y un cliente que define los términos y expectativas del servicios prestado.

- **El nivel de servicio esperado**: Detalla las métricas y estándares que el proveedor debe cumplir.
- **Cómo se medirá el rendimiento**: Incluye las métricas y métodos para evaluar si se están cumpliendo los niveles de servicio.
- **Soluciones o sanciones:** Describe las acciones a tomar si no se alcanza los niveles acordados. 


tipo de variables en Java, numérico: byte, short, int, long.

Los wrappers dan mucha más flexibilidad y es lo que normalmente se usa.

**int** tipo simple tipo primitivo en minúscula, **Integer** es una clase y por lo tanto va por mayúscula. 
**long** (simple o primitivo)- **Long** (clase)
**char**(simple o primitivo)-**Character** (clase)
**float -Float**
**double-Double**
**boolean-Boolean**
**char[ ]**-el wrapper(envoltorio) seria un String
envuelve cualquier cosa mientras sea una clase-Optional: No sabes si es nulo o no es nulo lo que hay adentro. Puedo preguntar con Optional si hay dentro o no. Y así se evita caer en errores de null. Es una clase.  

*los arrays no son ni primitivos ni son tipo objeto.  ej. miArray.length es un atributo  y cuando tiene parentesis como miArray.size() es un???*

Ej. podemos hacer un Optional de una clase car.

Usamos los primitivos cuando tenemos muchos datos. 

Partes importantes de un Objeto:

**Atributos**: como Marca, color , Modelo  (siempre o casi siempre públicos, en algunos casos protegidos, y muy rara vez privados). Al ser privado solo puede ser visto desde la misma clase. Nunca dejar libres los atributos porque es mala práctica, siempre getters and setters.

**Ej.** Atributo password. Al tener getter or setter, yo puedo decidir quien y como se accede a estos datos.      **ej:**    
**1)** Aquí si le pasamos un atributo para que lo muestre
`public String getPassword(){`

            `return "***";`
`}`

**2)** Todos los setters son void porque no retornan nada, por eso se lo pasamos
`public void setPassword(String pass){`

`}`

**Métodos(comportamientos)**: verbos, encender, Acelerar Frenar. Lo que esta haciendo o lo que está dejando de hacer en determinado momento. (Esto público). Get -ver, Setter-modificar. Al ser público puede ser visto desde otra clase. 

El estado de un objeto lo determina el contenido y cada unos de sus atributos. 


Parte visible de una clase como por ejemplo sus atributos: Parte **pública o public (Interface)**.  

Parte intermedia **protected**.

Parte que no se ven **private(Implementation)**.

**Escuelas de nombramiento:**

Snake case => nombre_de_pila

Camel case => nombreDePila (el primero para los atributos y métodos siempre minúsculo, si es nombre de clase si en Mayúscula la primera). Hay una excepción para las constantes: 

ej: `private final double PI=3.141592`; si es una constante con más de una palabra se escribe con todo en mayúsculas y separado con guion bajo ej: `MAXIMA_MUNICION`.

cuando se usa `final` como en Java, se puede declarar sin darle valor y luego en el código se puede asignar el valor. 

------------------------------------------------------------------------

Algunos los puedes declarar con y sin New. ej. `String string ="Pepe"`;
Algunos wrappers se pueden declarar si usar New. ej. `Integer entero=7`;

Conversiones de tipos en Java con Tipos:

```
String a Integer
Integer entero = Integer.valueOf(cadena); // o int entero = Integer.parseInt(cadena);
Ejemplo: Integer a = Integer.valueOf("900"); // o int b = Integer.parseInt("900");

Integer a String
String cadena = Integer.toString(entero); // o String cadena = String.valueOf(entero);
Ejemplo: String importe = Integer.toString(900); // o int entero = 900; String mensaje = String.valueOf(entero);

char a String
String cadena = Character.toString(char);
Ejemplo: char codigo = 'A'; String cadena = Character.toString(codigo);

String a char
char caracter = cadena.charAt(0); //Solo primer caracter
Ejemplo: String codigo = "E"; char caracter = cadena.charAt(0);

String a Double
double doble = Double.parseDouble(cadena);
Ejemplo: double doble = Double.parseDouble("900.1");

Double a String
String cadena = String.valueOf(doble);
Ejemplo: double totalDoble = 900.5; String totalString = String.valueOf(doble);

String a Float
float flotante = Float.parseFloat(cadena);
Ejemplo: float importe = Float.parseFloat("900.5");

Float a String
String cadena = Float.toString(flotante);
Ejemplo: String total = Float.toString(900.1f);

String a Boolean
Boolean boolean = Boolean.valueOf(cadena); // o boolean boolean = Boolean.parseBoolean(cadena);
Ejemplo: Boolean boolean = Boolean.valueOf("true"); // o boolean boolean = Boolean.parseBoolean("false");

Boolean a String
String cadena = String.valueOf(b); // o String cadena = Boolean.toString(b);
Ejemplo: boolean b = true; String cadena = String.valueOf(b); // o boolean b = false; String cadena = Boolean.toString(b);
```

todo deriva de Object:  Object no tiene atributos, pero tiene 12 métodos. Por eso no es necesario usar `extends`, porque todos los objetos derivan de Object quieran o no quieran, así que todos heredan de Object.

**No usar el método finalice. No vale para nada porque no sirve para forzar borrado, el recolector de basura se inicializa cuando se le da la gana**

Clase Object Constructor: Object() Métodos y Descripción:

- **clone()**: Crea y devuelve una copia de este objeto. Le cuesta clonar tipos que no sean primitivos.
- **equals(Object obj)**: Indica si algún otro objeto es “igual a” este. Funciona bien con tipos primitivos pero con objetos más complejos entiende que los dos punteros apuntan al mismo objeto en memoria.
- **finalize()**: Llamado por el recolector de basura en un objeto cuando la recolección de basura determina que no hay más referencias al objeto.
- **getClass()**: Devuelve la clase en tiempo de ejecución de este objeto.
- **hashCode()**: Devuelve un valor de código hash para el objeto.
- **notify()**: Despierta un solo hilo que está esperando en el monitor de este objeto.
- **notifyAll()**: Despierta a todos los hilos que están esperando en el monitor de este objeto.
- **toString()**: Devuelve una representación en forma de cadena del objeto.
- **wait()**: Hace que el hilo actual espere hasta que otro hilo invoque el método notify() o el método notifyAll() para este objeto.
- **wait(long timeout)**: Hace que el hilo actual espere hasta que otro hilo invoque el método notify() o el método notifyAll() para este objeto, o hasta que haya transcurrido una cantidad especificada de tiempo.
- **wait(long timeout, int nanos)**: Hace que el hilo actual espere hasta que otro hilo invoque el método notify() o el método notifyAll() para este objeto, o hasta que otro hilo interrumpa el hilo actual, o hasta que haya transcurrido una cierta cantidad de tiempo real.


Ejemplos :

   1)
   
`main(){`
`int a=5;`
`int b=7;`
`//a y b está declarados en un bloque externo.`
`int c=sumar(a,b); //la lectura se haces siempre de derecha a izquierda, por eso primero se resuelve el resultado y se guarda en c el resultado`
`}`Al llegar a esta llave, se termina la ejecución de main y el garbage collector limpia la memoria de todas las variables guardadas en el main.
`// cuando hablamos de m y n nos referimos a copias de los valores de a y b, eso quiere decir que tiene su propio espacio en memoria, eso también quiere decir que cualquier modificación que hagamos en m o n no afectara o modificará los valores de a y b.` 
// este es un método
`private int sumar(int m, int n){`
`return(m+n);`
`}` Al llegar a esta llave el método desaparece de memoria. Llega el garbage collector. Las variables quedan unos milisegundos en un limbo y luego el garbage collector los borra.


2) 
        Si el objeto combustión deriva de el objeto car y car deriva obviamente de object, combustión tendría el total de métodos y  atributos de car y objetos más los suyos propios.

Polimorfismo: los objetos derivados de otro objeto por ejemplo combustión de car, puede comportarse bajo ciertas circunstancias como car porque ya lo trae en su herencia.  Cuando hay polimorfismo sus atributos individuales no se pueden utilizar en esa situación determinada, solo los de los padres o todos los que estén en una gerarquía superior de la cual ese objeto deriva.


main(){
int a=5;
int b=7;
//declaración de la clase
Car car1 = new Car();
}

Ej:
creamos primero un objeto combustion  y lo asignamos a car3 como que si fuera un objeto Car, así que su comportamiento será el de Car . Así que se puede agregar combustion con otros tipos de car si los demás tipos también derivan de Car y se comportan como Car. 

`Car car3 = new Combustion();`

Ej2:

*Una clase abstracta la creas porque crees que vas a tener varias clases que comparten atributos entre ellas. Las clases abstractas no son referenciables osea no se puede crear un objeto de esa clase.

puede existir un class genérico por encima de las opciones de car, con atributos que comparten esas otras clases,  y dejar los atributos específicos para las clases  específicas como combustion, hibrido, electico.

Cuando es abstracta la clase no se puede crear un objeto de esa clase o hacer referencia a ella. EJ.

ArrayList<Car>myList = new ArrayList <Car>();
myList.add(acá se haría referencia a las clases que si se pueden hacer referencia como combustion, hibrido o eléctrico, pero no la clase abstracta);

**Existe la clase List y esta tiene ArrayList, HashList,LinkedList lo son para hacer listas y lo único que cambia son sus métodos o algunos atributos que las hacen más apropiadas para determinados tipos de alistamientos.**


Ej3:

Sobrescribir se puede parcial o totalmente , si hacemos un toString() de Object nos da la dirección del puntero. Si hacemos un toString() de Car que es el hijo, nos da los atributos y si queremos nos da solo eso o 


Sobrecargar: cuando escribo dos métodos con el mismo nombre, devuelven lo mismo y del mismo tipo, pero tienen distintos parámetros. Quiero que haga ej:

Método arrancar:

ej1:
car1.arrancar();
car1.arrancar(int speed);
car1.arrancar(int speed,string,nombre);

ej2: con figuras geométricas, para buscar el área.

-------------------------------------------------------------------------------------------------------------
?? En cada ejecución los posicionamientos de los datos en memoria pueden cambiar y el del puntero también.

**cuando creamos una instancia de Car, la cantidad de atributos que tenga es la cantidad de espacios en memoria.
el puntero tiene la dirección del espacio donde se encuentra la información del coche.
Objetos instanciados de las clases se guardan en memoria en dos partes, la primera es que se reserva espacio para lo atributos y luego se crea un puntero que tiene adentro la dirección del espacio anterior donde están guardados los atributos.

Si no hay un new no hay objeto. ej:   Car car3; es un puntero en memoria sin ninguna dirección que apunta a nada.   si yo igual 
car3 = car1, entonces estaría apuntando con los dos punteros al mismo objeto que en este caso serian los atributos en memoria por ejemplo en la dirección 800. podemos obtener atributos .

main(){
int a=5,
Car //esto es un puntero//car1=new Car();
ShopCar //esto también es un puntero// shop=new ShopCar();

//Método add Car

}
//Método add Car
shop.addCar(car1); pasa la dirección del puntero ej. 800 

public void addCar(Car (car)){
this.carList.add(car);
}

si cambias algo abajo, como estas haciendo referencia con puntero, cualquier cambio que se haga incluso en métodos hace que el cambio ocurran en el objeto que esta siendo apuntado por todos los punteros.

cuidado con los parámetros porque dependen de si son clases o primitivos, por ejemplo Long como es clase pasa por referencia, si es primitivo se clona y tiene su propio valor.

