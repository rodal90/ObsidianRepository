## **1. Eventos más comunes que disparan un `ActionEvent`**

### **¿Qué es un `ActionEvent`?**

Un `ActionEvent` es un tipo de evento en Java que ocurre cuando el usuario realiza una acción específica en un componente interactivo. Este evento es capturado y gestionado por un método **`actionPerformed`** definido en la interfaz `ActionListener`.

### **Cuatro acciones comunes que disparan un `ActionEvent`:**

1. **Clic en un botón:**
    
    - Cuando el usuario hace clic en un botón de la interfaz, se genera un `ActionEvent`.
    - Método asociado: `actionPerformed`.
    - **Ejemplo:**
        
        java
        
        Copiar código
        
        `JButton boton = new JButton("Haz clic aquí"); boton.addActionListener(e -> System.out.println("Botón clickeado."));`
        
2. **Seleccionar un elemento en un menú:**
    
    - Al seleccionar una opción en un menú desplegable (`JMenu`), se dispara un `ActionEvent`.
    - **Ejemplo:**
        
        java
        
        Copiar código
        
        `JMenuItem menuItem = new JMenuItem("Abrir"); menuItem.addActionListener(e -> System.out.println("Opción del menú seleccionada."));`
        
3. **Enviar un formulario:**
    
    - Pulsar el botón "Enviar" o "Aceptar" en un formulario puede disparar un `ActionEvent` para procesar los datos.
    - **Ejemplo:**
        
        java
        
        Copiar código
        
        `JButton enviar = new JButton("Enviar"); enviar.addActionListener(e -> System.out.println("Formulario enviado."));`
        
4. **Presionar "Enter" en un campo de texto:**
    
    - Escribir en un campo de texto (`JTextField`) y presionar "Enter" genera un `ActionEvent` que se puede gestionar.
    - **Ejemplo:**
        
        java
        
        Copiar código
        
        `JTextField texto = new JTextField(20); texto.addActionListener(e -> System.out.println("Texto ingresado: " + texto.getText()));`
        

---

## **2. Downcasting en Java**

### **¿Qué es el Downcasting?**

El **downcasting** es la conversión explícita de un objeto de una clase base (superclase) a una clase derivada (subclase). Esto se hace para acceder a métodos y propiedades específicos de la subclase que no están presentes en la superclase.

### **Puntos importantes sobre el Downcasting:**

- **Necesidad de Downcasting:**  
    Cuando tienes una referencia de tipo genérico (superclase) y necesitas acceder a características específicas de una subclase.
    
- **Conversión explícita:**  
    Se usa la sintaxis `(Subclase)objeto` para realizar el downcasting.
    
- **Riesgos:**  
    Si el objeto no es realmente una instancia de la subclase, se lanza una excepción `ClassCastException`.
    

### **Ejemplo práctico:**

```java

class Animal {
    void hacerSonido() {
        System.out.println("El animal hace un sonido.");
    }
}

class Perro extends Animal {
    void ladrar() {
        System.out.println("El perro ladra.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal miAnimal = new Perro(); // Upcasting
        if (miAnimal instanceof Perro) {
            Perro miPerro = (Perro) miAnimal; // Downcasting
            miPerro.ladrar();
        } else {
            System.out.println("El objeto no es un perro.");
        }
    }
}
```

---

## **3. Colecciones en Java: Vector y ArrayList**

### **Diferencias entre `Array`, `ArrayList` y `Vector`:**

|**Aspecto**|**Array**|**ArrayList**|**Vector**|
|---|---|---|---|
|**Tamaño**|Fijo, no se puede cambiar después de definirlo.|Dinámico, permite agregar o eliminar elementos.|Dinámico, similar a `ArrayList`.|
|**Sincronización**|No aplica.|No está sincronizado (no es seguro en hilos).|Está sincronizado (seguro en hilos).|
|**Rendimiento**|Más rápido porque no tiene sobrecarga.|Más rápido que `Vector` en operaciones concurrentes.|Más lento debido a la sincronización.|
|**Tipos de datos**|Puede contener datos primitivos o referencias.|Solo objetos (se usa auto-boxing para primitivos).|Solo objetos.|

### **Notas clave sobre ArrayList y Vector:**

1. Puedes almacenar objetos de diferentes tipos en un `ArrayList` o `Vector`, pero si defines un tipo específico (genéricos), solo podrás añadir ese tipo.
    
    java
    
    Copiar código
    
    `ArrayList<String> lista = new ArrayList<>(); lista.add("Hola"); // Correcto lista.add(123);    // Error`
    
2. **Array vs. ArrayList:**
    
    - En un `Array`, no se pueden agregar más elementos después de su creación.
    - En un `ArrayList` o `Vector`, puedes agregar y eliminar elementos dinámicamente.

---

### **Complemento: Uso práctico de ActionEvent en combinación con ArrayList**

Un ejemplo práctico de cómo usar un `ActionEvent` y un `ArrayList` para manejar datos dinámicamente:

java

Copiar código
```java
import java.awt.event.*;
import javax.swing.*;
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Ejemplo de ActionEvent");
        JButton addButton = new JButton("Añadir elemento");
        JTextField inputField = new JTextField(15);
        ArrayList<String> lista = new ArrayList<>();
        
        addButton.addActionListener(e -> {
            String texto = inputField.getText();
            if (!texto.isEmpty()) {
                lista.add(texto);
                System.out.println("Elemento añadido: " + texto);
                inputField.setText("");
            } else {
                System.out.println("Introduce un valor.");
            }
        });
        
        frame.setLayout(new java.awt.FlowLayout());
        frame.add(inputField);
        frame.add(addButton);
        frame.setSize(300, 150);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}

```
Este ejemplo combina el uso de `ActionEvent` con un `ArrayList` para manejar eventos de entrada dinámica en una interfaz gráfica.