

1)**View**:

/templates=>

/static =>ficheros css, ficheros js, imágenes videos.

/i18 => todo lo relacionado a traducción

/SQL =>Guardamos en formato script datos SQL, creación de tablas, modificación de datos.

2)**Controller**: Es el menú, recibe las peticiones y envía a cada parte de la aplicación lo que le corresponde. Se encuentra entre el servidor web y el servidor de aplicaciones. 

La parte del controlador la vamos a hacer en Java, dentro de sus directorios son estas: 
src/main/java, /controller, /controllerImpl

3)**Model**: Modelo de datos implica, las bases de datos y también implica el modelo de negocio, como se usan los datos dentro del día a día. Ej.(como se evalúan los peores clientes, los mejores, el empleado del mes, uso de recursos.)   En el servidor de aplicaciones es donde se aloja la parte del modelo de negocio. Requiere una programación.

- **Los entities: Es la clase que contiene como atributos  las columnas o estructura de la tabla. Tiene que existir simetría entre ellas. Cada entity sería una tabla.

***DTO Data Transfer Object:*** Es una versión recortada o ampliada del entity, con los datos realmente necesarios que necesitamos que viajen para resolver lo que tengamos que resolver. Ej.
cuando queremos recuperar un password:  necesitaríamos un DTO-1 //modificar password
DTO-2 //recordar password ,  DTO-3 // Fix password (2 veces pedimos el password).


- **Los Services son como se manejan. Son los casos de uso.

Lo de el modelo de negocios, va tener varios subdirectorios, entre ellos:
/service , /serviceImpl , data/model, data/dto

Los datos de base de datos se guardan en  /data/repository.


---
Unified Modeling Language (UML): Es un lenguaje de modelado estándar utilizado para visualizar, especificar, construir y documentar los componentes de sistemas de software. UML es ampliamente utilizado en el ámbito del desarrollo de software orientado a objetos, pero también puede aplicarse a otros tipos de sistemas.

### Principales características de UML:

1. **Visualización**: Ayuda a representar de manera gráfica la estructura y el comportamiento de un sistema, lo que facilita la comprensión entre equipos de desarrollo.
    
2. **Especificación**: Proporciona un conjunto de diagramas estándar para definir cómo debe comportarse el sistema o los objetos dentro del sistema.
    
3. **Construcción**: Puede servir de guía para la implementación del software, dado que ofrece una vista detallada de las clases, objetos, interacciones y flujo del sistema.
    
4. **Documentación**: UML facilita la creación de documentación técnica detallada del sistema, necesaria para su mantenimiento y futuras actualizaciones.
5. 
------------------------------------

1) empezamos creando las Entities, luego base de datos y luego los servicios.

Dentro de: src/main/java  , creamos tres paquetes:  la del dto, la del model y la de repositorio.

---
En java las fechas se han manejado de varias formas, pero actualmente se usan tres:

-LocalDate : Sin hora, en formato mes ,día, año o todas sus variaciones.
-LocalTime
-LocalDateTime
-Instant (Esta tiene un formato numérico de milisegundos contados a partir de 01/01/1970).

---

1)
![[Pasted image 20241007121429.png]]

Revisar y comentar un poco de esto que esta aquí.


--- 


2)
![[Pasted image 20241007121720.png]]

Buscar analizar, y describir.