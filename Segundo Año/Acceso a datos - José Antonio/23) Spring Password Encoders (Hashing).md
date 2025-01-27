Todos estos son algoritmos hijos para poder hacer el Hash de contraseña de los campos que querramos.

NO USAR ESTOS:   MD4, MD5, SHA -1 , SHA -256, SHA-512 (No por mucho tiempo será seguro). MessageDigest( y sus variantes).    Se pueden seguir usando para asegurar que lo que se a bajado coinciden con el Hashing.

SI USAR:  **Estos están ordenados por preferencia** Argon2 , SCrypt (Estas necesitan la librería en bouncy-castle) , Pbkdf2 , BCrypt ( Spring by default).

seed = semilla => secret value. 

Se puede utiliza como fuente de entrada para el codificador.  Y puede ser como una palabra o puede ser también algo codificado a su vez. 

---

vamos a usar JASYPT(Java Simplified Encryption)que es especifica para ficheros de propiedades. ( Todas aquellas cosas de texto, Json, propiedades ,etc para que no se vea a simple vista en este caso las contraseñas de acceso a h2)


---- 

                                  THREAD
                Thread esta en javaLang y ya esta importado
1) Primera Forma de usar Thread:

usando el método start si se utiliza hilos,  aunque ponemos el método  run , hay que usar el método start. Cuando usemos el método con el nuevo objeto, hay que usar .start() en vez de  .run() si no no utilizara hilos.

```java
public class ThreadEjemplo extends Thread { 
public ThreadEjemplo(String str) { 
super(str); 
} 

public void run() { 
for (int i = 0; i < 10 ; i++)
System.out.println(i + " " + getName());
System.out.println("Termina thread " + getName());
} 

public static void main (String [] args) { 
new ThreadEjemplo("Pepe").start(); 
new ThreadEjemplo("Juan").start();
System.out.println("Termina thread main"); 
} 
} Si se compila y eje


```
Aquí lo que sucederia es que se ejecute los dos thread 10 veces y mostraría los nombres en la consola. Cuidado con que no se quede en bucle infinito.  Con los hilos todo comienza con el main pero si alguna ejecución de hilo no termina no termina el main tampoco. 

---
2) Segunda Forma un Interface runnable: ( Para poder usar varios, porque si extiende de una clase solo podemos extender de una sola clase).


```java
public class ThreadEjemplo implements Runnable { 
public void run() { 
for (int i = 0; i < 5 ; i++)
System.out.println(i + " " + 
				   Thread.currentThread().getName()); System.out.println("Termina thread " +
				    Thread.currentThread().getName());
				     } 
	public static void main (String [] args) { 
	new Thread (new ThreadEjemplo(), "Pepe").start();
	 new Thread (new ThreadEjemplo(), "Juan").start(); 
	 
	 System.out.println("Termina thread main");
	  }
	   }

```

---
Ciclo de vida de un Thread: 

Nacer: New thread (hasta que no llamamos al método start() no entra a correr)
Corriendo: Running
Muerto: Dead
No corre: No runnable (Espera se puede producir porque el procesador le deja en espera o porque hemos forzado que se quede en espera).


|                                                                                                            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `protected [Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html "class in java.lang")` | `[clone](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#clone--)()` // clona objetos simples, no va saber clonar objetos complejos. Para poder hacerlo funcionar de forma correct hace falta sobre-escribir el método clone().<br><br>Creates and returns a copy of this object.                                                                                                                                                                                                                       |
| `boolean`                                                                                                  | `[equals](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#equals-java.lang.Object-)([Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html "class in java.lang") obj)`<br><br>Indicates whether some other object is "equal to" this one.                                                                                                                                                                                                                                             |
| `protected void`                                                                                           | `[finalize](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#finalize--)()`   NO USARLO<br><br>Called by the garbage collector on an object when garbage collection determines that there are no more references to the object.                                                                                                                                                                                                                                                                          |
| `[Class](https://docs.oracle.com/javase/8/docs/api/java/lang/Class.html "class in java.lang")<?>`          | `[getClass](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#getClass--)()`<br><br>Returns the runtime class of this `Object`.                                                                                                                                                                                                                                                                                                                                                                           |
| `int`                                                                                                      | `[hashCode](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#hashCode--)()`<br><br>Returns a hash code value for the object.                                                                                                                                                                                                                                                                                                                                                                             |
| `void`                                                                                                     | `[notify](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notify--)()`<br><br>Wakes up a single thread that is waiting on this object's monitor.                                                                                                                                                                                                                                                                                                                                                        |
| `void`                                                                                                     | `[notifyAll](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notifyAll--)()`<br><br>Wakes up all threads that are waiting on this object's monitor.                                                                                                                                                                                                                                                                                                                                                     |
| `[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html "class in java.lang")`           | `[toString](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#toString--)()`<br><br>Returns a string representation of the object.                                                                                                                                                                                                                                                                                                                                                                        |
| `void`                                                                                                     | `[wait](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#wait--)()`<br><br>Causes the current thread to wait until another thread invokes the [`notify()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notify--) method or the [`notifyAll()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notifyAll--) method for this object.                                                                                                                                  |
| `void`                                                                                                     | `[wait](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#wait-long-)(long timeout)`<br><br>Causes the current thread to wait until either another thread invokes the [`notify()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notify--) method or the [`notifyAll()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notifyAll--) method for this object, or a specified amount of time has elapsed.                                                                |
| `void`                                                                                                     | `[wait](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#wait-long-int-)(long timeout, int nanos)`<br><br>Causes the current thread to wait until another thread invokes the [`notify()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notify--) method or the [`notifyAll()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#notifyAll--) method for this object, or some other thread interrupts the current thread, or a certain amount of real time has elapsed. |


VIENE EN EL EXAMEN: condición de carrera, entre dos que tiene que usar los mismo recursos.

La sincronización sirve para garantizar que los dos hilos no van intentar utilizar los mismos atributos o variables de clase al mismo tiempo.


Un hilo produce y el otro consume.  Se puede utilizar un while , para poder darle instrucciones de en que momento consumir lo que el otro hilo produce, es simplemente para organizarlo.


FIFO
LIFO

LIFO = PILAS(STACK)
FIFO= COLAS(QUEUE)

El método poll, lo mira pero tambien lo borra para que pueda meterse mas en caso del productor con el add!

