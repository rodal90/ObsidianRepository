
Aquí están las cuatro acciones más comunes que desencadenan un **ActionEvent**:

1. **Clic en un botón**: Al hacer clic en un botón de la interfaz, el evento **actionPerformed** se activa. Este es uno de los eventos más comunes en las aplicaciones gráficas.
    
2. **Seleccionar un elemento en un menú**: Cuando el usuario selecciona una opción de un menú desplegable, se dispara el evento **actionPerformed** para esa opción en particular.
    
3. **Enviar un formulario**: Si hay un formulario con un botón de "Enviar" o "Aceptar", al pulsarlo se puede activar un evento **actionPerformed** para gestionar los datos introducidos.
    
4. **Presionar "Enter" en un campo de texto**: Al introducir un valor en un campo de texto y presionar la tecla "Enter", se dispara un **ActionEvent** que puede ser capturado por un **actionPerformed** para procesar el texto.


**Downcasting** es el proceso de convertir una referencia de una clase base (o superclase) a una clase derivada (o subclase) en un lenguaje de programación orientado a objetos, como Java.

En Java, cuando tienes un objeto de una clase base y sabes que en realidad es de una subclase, puedes realizar un **downcast** para tratar ese objeto como una instancia de la subclase. Sin embargo, el **downcasting** debe hacerse explícitamente, y si la conversión no es válida, puede lanzar una excepción de tipo `ClassCastException`.


**RECORDAR**: que en un Vector o ArrayList se puede guardar objetos de diferentes tipos. Y si defines específicamente un tipo de objeto solo puedes guardar objetos en un array que sean de ese tipo.

**En un ArrayList o Vector de objetos puedes añadir elementos, si es un Array común no puedes agregar más elementos**