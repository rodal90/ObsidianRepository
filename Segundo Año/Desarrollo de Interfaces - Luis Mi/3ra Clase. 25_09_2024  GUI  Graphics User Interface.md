
## **Front-End en Java (Interfaz Gráfica de Usuario - GUI)**

### **1. Contenedores y Componentes**

- **Contenedor**: En Java, un contenedor es un elemento gráfico que puede contener otros componentes. Un ejemplo es una ventana en sistemas operativos Windows.
- **Componentes**: Elementos interactivos como botones, cajas de texto, etiquetas (labels), casillas de verificación (checkbox), listas desplegables, campos de entrada, entre otros.
    - **Tipos de componentes**:
        - **Pesados (heavy)**: Dependen del sistema operativo para su apariencia y funcionamiento.
        - **Ligeros (lightweight)**: Programados en Java, independientes del sistema operativo, ofrecen mayor personalización.
    - **Componentes avanzados**: Ejemplo: `JTable` y otros interactivos.

---

### **2. Gestión de Eventos (SGE)**

- **Eventos**: Acciones como clics, desplazamientos del ratón o interacciones del teclado.
- **Modelos de Sistemas de Eventos**:
    - **Inference Model**: Modelo más simple.
    - **EDM (Event Delegation Model)**:
        - Más moderno y complejo.
        - Implica dos objetos:
            - **Source Object**: El objeto que produce el evento (botón, ventana, etc.).
            - **Listener Object**: El objeto que escucha y reacciona al evento. Implementa una interfaz Java (que define métodos vacíos o constantes).

---

### **3. Librerías para Interfaces Gráficas en Java**

- **AWT (Abstract Window Toolkit)**:
    
    - Usa componentes del sistema operativo, lo que le da una apariencia nativa.
    - Menos flexible estéticamente.
- **Swing**:
    
    - Componentes programados en Java, más personalizables y estéticamente flexibles.
    - Aún utiliza partes de AWT, como el paquete `java.awt.event` para manejar eventos.

**Importación de clases y paquetes**:

java

Copiar código

`import java.awt.*;          // Importa todas las clases de AWT (sin paquetes).   import java.awt.event.*;    // Importa todas las clases del paquete de eventos en AWT.`  

---

### **4. Métodos y Constructores**

- **Métodos estáticos (`static`)**:
    
    - No requieren la creación de un objeto para ser utilizados.
    - Se pueden llamar directamente desde la clase.
- **Constructores**:
    
    - Métodos especiales que comparten el nombre de la clase.
    - Se usan para inicializar variables y preparar el objeto al ser creado.

---

### **5. Interfaces en Java**

- Una interfaz define un contrato (conjunto de métodos abstractos y constantes) que una clase debe implementar.
- **Características principales**:
    - **Métodos abstractos**: Solo se declaran, sin implementación (hasta Java 8).
    - A partir de Java 8, pueden tener métodos con implementación (`default` y `static`).
    - Permiten herencia múltiple, ya que una clase puede implementar varias interfaces.

---

### **6. Clases Abstractas**

- Se declaran con la palabra clave `abstract`.
- Pueden tener métodos con implementación o métodos abstractos (sin cuerpo).
- Una clase hija debe implementar todos los métodos abstractos o declararse también como abstracta.

**Ejemplo de clase abstracta y herencia**:

java

Copiar código

```java 
abstract class Vehiculo {
    // Método abstracto.
    abstract void arrancar();  

    // Método con implementación.
    void detener() {  
        System.out.println("El vehículo se ha detenido.");
    }
}

class Coche extends Vehiculo {
    @Override
    void arrancar() {
        System.out.println("El coche ha arrancado.");
    }
}

public class Main {
    public static void main(String[] args) {
        Coche miCoche = new Coche();
        miCoche.arrancar();  // Implementación del método en la clase Coche.
        miCoche.detener();   // Método heredado de la clase Vehiculo.
    }
}




```
---

### **7. Polimorfismo: Sobrecarga y Sobrescritura**

- **Sobrecarga (`Overload`)**:
    
    - Un método o un operador tiene múltiples formas dependiendo de los parámetros o el contexto.
    - Ejemplo: El operador `+` se usa para sumar números y concatenar cadenas.
- **Sobrescritura (`Override`)**:
    
    - Una clase hija redefine un método heredado de una clase padre para modificar su comportamiento.

---

### **8. Modelo de Seguridad Sandbox**

- En Java, las aplicaciones no pueden realizar conexiones con servidores distintos al servidor de origen. Esto limita posibles riesgos de seguridad.

---

### **Comparación: Clases Abstractas vs Interfaces**

| **Aspecto**                | **Clase Abstracta**                         | **Interfaz**                                |
| -------------------------- | ------------------------------------------- | ------------------------------------------- |
| Métodos con implementación | Sí                                          | Solo desde Java 8 (`default`, `static`)     |
| Herencia                   | Una sola clase abstracta (herencia simple). | Puede implementar múltiples interfaces.     |
| Modificadores de acceso    | Permite `private`, `protected`, `public`.   | Todos los métodos son `public` (implícito). |


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