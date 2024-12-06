### **Ciclo de ejecución en Java**

1. **Fuente (Source)** → Código fuente escrito en un archivo `.java`.
2. **Compilador (Compiler)** → Convierte el código fuente a bytecode y lo almacena en un archivo `.class`.
3. **Bytecode** → Instrucciones intermedias independientes del sistema operativo.
4. **JVM (Java Virtual Machine)** → Interpreta el bytecode y lo ejecuta en la máquina local.

**Nota**: Los bytecodes son procesados exclusivamente por la máquina virtual Java (JVM).

---

### **Ediciones de Java**

1. **J2SE (Java 2 Standard Edition)**
    
    - Usado para aplicaciones de escritorio y soluciones generales.
    - Proporciona herramientas básicas como el JDK y el JRE.
2. **J2EE (Java 2 Enterprise Edition)**
    
    - Diseñado para aplicaciones empresariales y servidoras.
    - Incluye APIs clave:
        - **JDBC**: Java DataBase Connectivity, para interactuar con bases de datos.
        - **JTA**: Java Transaction API, para manejo de transacciones.
        - **JSP**: Java Server Pages, para la vista en aplicaciones web.
        - **JPA**: Java Persistence API, para manejar persistencia en bases de datos.
        - **RMI**: Java Remote Method Invocation, para ejecutar métodos de objetos remotos.
        - **JSF**: Java Server Faces, otra opción para la vista.
        - **SAX**: Simple API for XML, para manejo eficiente de datos XML.
3. **J2ME (Java 2 Micro Edition)**
    
    - Enfocado en dispositivos móviles y sistemas embebidos.

---

### **Herramientas de Java**

1. **JDK (Java Development Kit)**
    
    - Herramienta completa para desarrollar aplicaciones en Java.
    - Incluye el compilador, herramientas de depuración y el JRE.
2. **JRE (Java Runtime Environment)**
    
    - Entorno para ejecutar aplicaciones Java.
    - Contiene la JVM y las bibliotecas de clases requeridas.
3. **JIT (Just-In-Time Compiler)**
    
    - Compilador en tiempo de ejecución que convierte bytecode en código nativo para mejorar el rendimiento.

---

### **Arquitectura común en Java: MVC**

**MVC (Modelo-Vista-Controlador)**: Patrón de diseño usado para separar lógica de negocio, presentación y control.

- **Modelo**: Gestiona los datos y la lógica de la aplicación.
- **Vista**: Interfaz gráfica o de usuario que muestra los datos.
- **Controlador**: Gestiona la comunicación entre el modelo y la vista.

---

### **Por qué elegir Java?**

1. **Portabilidad**
    
    - El bytecode generado al compilar es independiente del sistema operativo.
    - Solo se necesita una JVM para ejecutarlo en cualquier plataforma.
2. **Compatibilidad con la Web**
    
    - Pionero en aplicaciones cliente-servidor usando protocolos HTTP.
3. **Compatibilidad cliente-servidor**
    
    - Soporta múltiples clientes trabajando con un único servidor mediante interfaces gráficas uniformes.
4. **Seguridad**
    
    - Modelo de seguridad "sandbox" que limita la interacción de aplicaciones con recursos no autorizados.

---

### **Persistencia en Java**

**Concepto**: La persistencia consiste en mantener los datos almacenados para que puedan ser recuperados posteriormente.

- **Frontend**: Utiliza `LocalStorage` y `SessionStorage` en navegadores.
- **Backend**: Se logra almacenando datos en bases de datos.

---

### **IDE comunes en Java**

1. **NetBeans**
    - IDE oficial, fácil de usar para principiantes y profesionales.
2. **Eclipse**
    - Popular por su extensibilidad y amplia comunidad.

---

### **Complemento: Diferencia entre desarrollo Web y de Escritorio**

1. **Desarrollo Web**
    
    - Se ejecuta en navegadores web.
    - Usa tecnologías como **JSP** y **Servlets**.
    - Generalmente requiere un servidor web (como Apache Tomcat).
2. **Desarrollo de Escritorio**
    
    - Ejecutado directamente en sistemas operativos.
    - Utiliza bibliotecas gráficas como **AWT** o **Swing**.

---

### **Conceptos adicionales**

1. **Drivers JDBC**
    
    - **Tipos de drivers**:
        1. Driver tipo 1: Puente JDBC-ODBC (obsoleto).
        2. Driver tipo 2: Usa bibliotecas nativas específicas del sistema.
        3. Driver tipo 3: Traductor entre protocolos cliente-servidor.
        4. Driver tipo 4: Driver puro Java, el más usado por su portabilidad.
2. **Applet vs Bash**
    
    - **Applet**: Miniaplicación que se ejecuta en navegadores web (obsoleto en Java moderno).
    - **Bash**: Scripts de línea de comandos que se ejecutan en sistemas operativos basados en Unix.

[[Diferencia entre desarrollo Web y Escritorio]]



---

### **Correcciones y aclaraciones**

1. **JIT (Just-In-Time Compiler)**
    
    - No genera un archivo `.exe`.
    - Es un componente de la JVM que optimiza el bytecode convirtiéndolo en código nativo en tiempo de ejecución, para mejorar el rendimiento.
2. **JRE no es el JDK**
    
    - El JRE es **parte del JDK**, pero no incluye herramientas como el compilador o herramientas de desarrollo.
    - El JDK (Java Development Kit) incluye todo lo necesario para desarrollar y ejecutar aplicaciones Java: JRE + herramientas de desarrollo.
3. **Sandbox Security Model**
    
    - Es un concepto válido, pero su explicación requiere claridad:  
        La "sandbox" es un entorno restringido donde se ejecutan aplicaciones Java (como applets), impidiendo que realicen acciones no autorizadas, como acceder al sistema de archivos del usuario o conectarse a servidores externos no permitidos.
4. **Applets**
    
    - Java applets son **obsoletos** desde hace años y no se utilizan en la práctica moderna, ya que los navegadores han eliminado el soporte para Java plugins. Se recomienda no incluir applets como algo relevante.
5. **Persistencia**
    
    - Es correcta la idea, pero en el desarrollo moderno, en el backend se suele usar frameworks de persistencia como **Hibernate** (implementa JPA) para interactuar con bases de datos de manera eficiente.
6. **IDE: NetBeans y Eclipse**
    
    - Son correctos, pero deberías considerar mencionar **IntelliJ IDEA**, que es muy popular hoy en día para desarrollo profesional.
7. **MVC (Modelo-Vista-Controlador)**
    
    - Es un patrón ampliamente usado en Java, pero recuerda que en aplicaciones modernas de Java (por ejemplo, con frameworks como **Spring**), el enfoque puede incluir patrones más complejos como MVVM o arquitecturas basadas en microservicios.

### **Conceptos adicionales actualizados**

1. **Desarrollo moderno en Java**
    
    - Hoy en día, las aplicaciones empresariales utilizan **Spring Boot**, **Jakarta EE** (sucesor de J2EE), y microservicios para simplificar y escalar el desarrollo.
2. **J2SE, J2EE, J2ME**
    
    - Estas nomenclaturas (J2SE, J2EE, J2ME) ya no se utilizan oficialmente.
        - **J2SE** ahora se conoce simplemente como **Java SE** (Standard Edition).
        - **J2EE** es ahora **Jakarta EE**.
        - **J2ME** es ahora menos relevante debido al auge de tecnologías como Android (que usa un derivado de Java).
3. **Clientes/Servidores**
    
    - Aunque Java sigue siendo una excelente opción para desarrollo cliente-servidor, el desarrollo web moderno tiende a usar frameworks como Spring (backend) junto con tecnologías frontend como Angular, React o Vue.js.