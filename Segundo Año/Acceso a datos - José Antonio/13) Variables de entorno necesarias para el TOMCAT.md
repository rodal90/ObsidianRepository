1)
![[Pasted image 20241021091349.png]]

Estas tiene que apuntar a donde tenemos el archivo de instalación de TOMCAT.


2)
![[Pasted image 20241021091429.png]]

Estos dos son las variables que apuntan al archivo de instalación de Java 21.

---

Apache Tomcat tiene una estructura de directorios específica, donde cada carpeta cumple una función importante. Aquí te explico para qué sirve cada una de las carpetas mencionadas en tu instalación de Apache Tomcat 10.1.31:

## Estructura de directorios

**Estructura de Directorios de Tomcat**

1. **bin**  
    Esta carpeta contiene los scripts y ejecutables necesarios para iniciar, detener y administrar el servidor Tomcat.  
    Archivos clave:
    
    - `startup.sh`: Inicia el servidor.
    - `shutdown.sh`: Detiene el servidor.
    - (Versiones .bat para Windows también disponibles).
2. **conf**  
    Contiene los archivos de configuración esenciales para Tomcat. Archivos importantes:
    
    - `server.xml`: Define la estructura del servidor (puertos, conectores, hosts virtuales).
    - `web.xml`: Configuraciones predeterminadas para todas las aplicaciones web.
    - `context.xml`: Configura el contexto global para las aplicaciones web.
3. **lib**  
    Almacena las bibliotecas JAR necesarias para que Tomcat funcione correctamente. Estas bibliotecas son compartidas por todas las aplicaciones desplegadas en el servidor.
    
4. **logs**  
    Aquí se guardan los archivos de registro (logs) generados por Catalina y las aplicaciones web. Estos logs son útiles para el diagnóstico de problemas y monitoreo del servidor.
    
5. **temp**  
    Se utiliza para almacenar archivos temporales generados durante el funcionamiento de Tomcat.
    
6. **webapps**  
    Es el directorio donde se despliegan las aplicaciones web. Los archivos WAR que coloques aquí serán desplegados automáticamente por Tomcat según su configuración.

    Que contiene y para que sirven las carpetas dentro de webapps:
    
7. **work**  
    Esta carpeta se usa para almacenar archivos temporales de trabajo, como los servlets compilados a partir de los JSPs de las aplicaciones web.


---

En tomcat-users.xml se puede modificar para que se habiliten los roles, descomentando. En la carpeta de config.

---

Si en el archivo POM no hay una etiqueta <packaging> significa que nuestro  proyecto será exportado en .JAR . si queremos que se auto ejecute, necesitamos que sea war, Agregando la etiqueta "packaging" asi se logra: <packaging>war</packaging>


Cuando damos exportar en file: 
![[Pasted image 20241021100808.png]]