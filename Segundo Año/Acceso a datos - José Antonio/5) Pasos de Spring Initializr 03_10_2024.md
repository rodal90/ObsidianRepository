
Con esta herramienta podemos crear un esqueleto de proyecto completo. 


1) Entrar a Spring Initializr
2) Lado izquierdo características del proyecto y en el lado derecho tenemos las dependencias.
3) En este primer proyecto usamos Maven y Java, 
4) Diferencia entre SpringBoot: nos da cosas pre diseñadas de seguridad como login, nos da un servidor web o servidor de aplicaciones, ya preparado con Apache Tomcat y SpringFramework.
5) En Group ponemos el nombre del proyecto: ej. com.care, en Artifact: el nombre ej.Timmy. En Description: ej: de que va el proyecto.
6) Tipo de empaquetamiento, puede ser Jar o War.  War permite empaquetar ficheros java y ficheros de recursos, como videos fotos o audios y se auto despliega en el servidor de aplicaciones que sea. Jar son ficheros comprimidos como el Zip.
7) Luego del empaquetamiento seleccionamos la versión Java.
8) Ahora pasamos al lado derecho y seleccionamos las dependencias. (Las dependencias no agregan nada a la aplicaciones, son herramientas que nos ayudan a nosotros como desarrolladores).  -1. Spring Boot Dev Tool, nos ayuda a hacer cambios en caliente sin parar todo y volver a arrancar,  se puede desactivar. Buscar más info de cada una. 2. TemplateEngines: Nos sirven para hacer plantillas,3. Thymeleaf, nos permite hacer transiciones entre el mundo de back y front. Security_ Spring Security. 4.SQL.
9) Después de tener todas las dependencias generar el archivo. 


Pasos para abrir nuestro proyecto en Eclipse:

1) Luego de Descargado el Archivo, descomprimirlo.  Dentro:

                 Main: Código Final distribuidos en Java y Recursos(Static: Video,Audio,Fotos,etc). Dentro de esta Templets: todo html.  
             ++Todo lo que queramos alterar de Spring o de la configuracicion esta en Application properties en recursos.

                  Test: Testeo TDD
                  
2) Llevar el archivo descomprimido al workSpace: c://usuarios/manana/eclipse-workspace
3) Para importar , tenemos que abrir desde "File", luego "import", luego "Project from folder or archives", seleccionamos luego directorio para buscarlo y luego finalizamos.


Listado total de dependencias usadas en este proyecto:

- **Spring Boot DevTools**
- **Lombok**
- **Spring Web**
- **Spring Session**
- **Thymeleaf**
- **Spring Security**
- **JDBC API**
- **Spring Data JDBC**
- **Spring Data JPA**
- **H2 Database**
- **MySQL Driver**
- **Validation**
- **Java Mail Sender**



**Que es pom.xml: Sale lo que hemos seleccionado al momento de armar el proyecto en Spring Initializr, y en la parte de abajo están las dependencias. A través de esto va a buscar con Maven las dependencias y se asegura de que las versiones de todo sean compatibles.

en la barrita justo debajo cuando abrimos nuestro documento, tenemos la opción overview y alli podemos hacer cambios y ver el listado de dependencias. podemos agregar más si es necesario también.  "Dependencies", "Dependency", "Hierarchy" son otras opciones disponibles en esta barrita..

---
Para ejecutar utilizamos click derecho en el archivo del proyecto, y luego en "Run as", seleccionar la opción que dice "Spring Boot As".

Para poder ver nuestra página de login:  localhost:8080

"Whitelabel Error Page" es el mensaje que te dice que si paso pero que no hay página creada todavía.


Dentro de la consola que aparece abajo podemos ver que se inicializo la aplicación y cuando todavía no tenemos contraseña para el login, nos da una larga para que podamos entrar. Pasos para poder agregar tu propio usuario y contraseña: 

entramos en application.properties que se encuentra también dentro de la carpeta templates, y src/main/resources. alli a través de este código podemos asignar usuario y contraseña: 


`spring.application.name=timmy`

#`write everything on one line dont use anything else than letters`

`spring.security.user.name=pepe`

`spring.security.user.password=pepePass`




Luego esta el ponerle una landing page, o una pagina inicial. Pasos:

- Entrar a generator.ws .  Y hacer click en start now. (Las páginas de esta web son todas responsive porque están hechas en boostrap).
- Luego seleccionar la barra de navegación.
- Seleccionar navegadores y contenidos.
- Luego de crear la página de index y la página inicial o Master. Las copiamos o arrastramos a la carpeta , templates que esta en src/main/resources.


Distintos escenarios en lo que vamos a hacer correr la aplicaciones, normalmente hay por lo menos tres perfiles:

1) dev de development: Es un estado inicial para nosotros como desarrolladores. Este estado nos permite hacer pruebas de base de datos en memoria.  Aquí podemos usar Jar.
2) pre production: Es un estado inmediatamente al de producción. Entorno reducido con un servidor similar al de producción. F&f, entorno Friends and Family->Dárselo a personas dentro de la organización o compañía para que lo prueben y pueda haber Feedback. Aquí ya utilizaremos War, para poder trasladar recursos.
3) production: Es el estado en el cual ya se saca la apliación al servidor real.
