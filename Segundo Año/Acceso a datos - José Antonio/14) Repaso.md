
1) Entities.
Estas son las entidades mas dos mas que nos da spring , con atributos y spring session.

![[Pasted image 20241024085251.png]]
las entity se conectan con la base de datos , cada entity debería de tener su correspondiente repositorio.



 2) Servicios.
 
 Dentro de los servicio

tenemos interfaces y  y implementaciones

interfaces
![[Pasted image 20241024085454.png]]

Implementaciones
![[Pasted image 20241024085524.png]]


3) Controladores.

Los controladores también los dividimos en dos:

en interfaces y implementaciones

Implementaciones
![[Pasted image 20241024085631.png]]
Interfaces
![[Pasted image 20241024085650.png]]


4) Configuraciones: 

Seguridad Web
Configuración modelo vista controlador.
Lenguajes

![[Pasted image 20241024085719.png]]


5) Recursos.

Todo lo que no es java se va a recursos:

![[Pasted image 20241024085917.png]]


---

Agregamos estas direcciones, para habilitar más funcionalidades en html y una de ellas es thymeLeaf, la cual nos permite utilizar direcciones relativas: 

![[Pasted image 20241024092306.png]]


Buscar que es y que significa lo siguiente!!!:

![[Pasted image 20241024094729.png]]


---

como se usa el log: 

![[Pasted image 20241024095915.png]]

se usa con info, warning, error. (cada uno es un nivel diferencie de advertencia, nivel de gravedad).

debug y trace: 

### **Debug**

- **Propósito**: El nivel **debug** se usa principalmente para registrar información detallada durante el desarrollo o la depuración. Los mensajes de este nivel generalmente contienen información útil para los desarrolladores cuando están resolviendo problemas o inspeccionando el comportamiento de una aplicación.
### . **Trace**

- **Propósito**: El nivel **trace** es aún más detallado que **debug**. Se utiliza para rastrear el flujo de ejecución de la aplicación en el nivel más granular posible. Este nivel de logging es útil para ver el comportamiento interno más fino del programa, como la entrada y salida de funciones o los detalles específicos de las decisiones tomadas en el código.

----
Explicación de cada parte de esta parte del código:  BUSCAR BIEN CADA PARTE

![[Pasted image 20241024100743.png]]

---

Especializaciones del Get: que sirve como pregunta y retornan un booleano: 

![[Pasted image 20241024101129.png]]

---

Le avisamos por ejemplo en el loginPage.html, que va a recibir un objeto login: 

![[Pasted image 20241024113149.png]]
por thymeLeaf se puede  hacer que html reciba el objeto.

![[Pasted image 20241024113357.png]]

Le hemos agregado los campos de username y password, y con el asterisco le decimos que son parte del objeto login que hemos puesto


---

STREAMS

Los steams no contienen datos, tampoco se utilizan para modificar datos en la fuente de origen. 
Se sirve de los colectores de datos para poder hacer su procesamiento. Se sirve de datos de terceros.

**

Y los procesos los realiza en una operación atómica:

**A realizar operaciones le llamamos consumir, cada operaciones que queremos que se haga sobre steam se le llama consumidor. 

![[Pasted image 20241024130941.png]]

La "p" en este caso sería un consumidor que imprime las persons.
No es una variable y a esa expresión la llamamos landa: 

p es tipo person, es uno de los objetos que contiene el stream. 

![[Pasted image 20241024131138.png]]


**  

Otro ejemplo donde se añaden todas las personas a la lista y luego se imprimen por pantalla:

**![[Pasted image 20241024131831.png]]

cuando declaro consumidor: lo que declaro es la intención que tiene de hacer algo, en este caso la intención del consumidor c1 es agregar elementos en result. "result::add".
El segundo consumidor c2 tiene intención de imprimir contenido. "System.out::println".

Lo que terminaríamos haciendo es metiendo en el ArrayList de result los elementos que vamos recorriendo de personas y aparte estaríamos imprimiendo los objetos dentro de persons.


**

**

### Filtrar

Se muestra cómo obtener las personas con edad mayor que 20

**

![[Pasted image 20241024132505.png]]

A los filtrados les llamamos Predicados, predicate. Se pueden guardar por fuera. como en el ejemplo.


**

**
SEGUNDO TIPO DE FILTRADO

Se pueden combinar predicados para crear lógicas (interesante forma de simular los if)

![[Pasted image 20241024133108.png]]

**

**

Podemos coger elementos de la lista que nos interesen, en este caso el que contenga “two”:


![[Pasted image 20241024133136.png]]

---



**

## Operadores intermedios y finales

Los operadores intermedios devuelven un stream, pero como los stream no albergan datos, en realidad por sí mismos no hacen algo; por tanto son declaraciones.

  
**

![[Pasted image 20241024133320.png]]
**

Se les llama en inglés: operaciones lazy (vagas) o intermediary operators (operadores intermedios)

**
![[Pasted image 20241024133345.png]]


**El siguiente código:**

![[Pasted image 20241024133454.png]]


**

Donde peek() se parece a un forEach() lo que lo diferencia es que devuelve un Stream, por lo tanto es un operador intermedio al igual que filter, por tanto ese código hace nada.

  

Para activar a los operadores intermedios se necesitan los operadores finales que son operadores que devuelven datos, como el forEach() por tanto el código quedaría:

**
![[Pasted image 20241024133520.png]]

Las instrucciones tienen un orden secuencial, asi que se van limitando.



**

De forma que peek() y filter () son intermedios, sólo procesan, y forEach() es el que activa ese proceso, y añade las personas a la lista.

  

## Operación Map

  

Aplica una función a cada elemento del Stream:

**![[Pasted image 20241024133809.png]]

**

Hemos visto 3 tipos de operaciones:

**![[Pasted image 20241024133836.png]]

**

Las consumidoras, forEach() (que es final) y peek() (que es intermedia).

Las de filtrado, filter() (intermedia)

Las de mapeo, map() y flatMap() (intermedias).

**