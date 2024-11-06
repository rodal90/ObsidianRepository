

![[Drawing 2024-10-10 08.44.12.excalidraw]]


En bases de datos relacionales, la **propagación** se refiere a cómo los cambios en los datos, como la actualización o eliminación de una fila, se transmiten o afectan a otras tablas que tienen relaciones con esa fila. Esto es particularmente importante en el contexto de las **claves foráneas** y las **restricciones referenciales**. Los tipos principales de propagación se suelen definir a través de acciones asociadas a las relaciones entre tablas. Aquí te explico las más comunes:

1. **CASCADE** (en cascada):
    - Cuando una fila en la tabla principal (tabla padre) es modificada o eliminada, los cambios se propagan automáticamente a las filas relacionadas en la tabla secundaria (tabla hija).
    - Ejemplo:
        - Si eliminas una fila en la tabla "Padres", todas las filas correspondientes en la tabla "Hijos" que dependan de ella también serán eliminadas.
        - Si actualizas una clave primaria en "Padres", las claves foráneas en "Hijos" también serán actualizadas.
2. **SET NULL**:
    - Si se elimina o actualiza una fila en la tabla padre, las claves foráneas de las filas correspondientes en la tabla hija se establecen en `NULL`.
    - Ejemplo:
        - Si eliminas una fila de "Padres", los registros relacionados en "Hijos" tendrán la clave foránea configurada como `NULL`.
        - Este tiene sentido como algo momentáneo o transitorio, pero en algún momento tendría que cambiarlo o asignar otro dato.
1. **SET DEFAULT**:
    - Similar a `SET NULL`, pero en este caso, en lugar de establecer `NULL`, se asigna un valor predeterminado (especificado por el usuario) a la clave foránea de la tabla hija.
    - Ejemplo:
        - Si eliminas un registro en "Padres", las claves foráneas en "Hijos" se establecen a un valor predeterminado, por ejemplo, un valor numérico o una cadena predeterminada.
2. **NO ACTION**:
    - No se realiza ninguna acción, pero esto implica que si intentas eliminar o actualizar una fila en la tabla padre que tiene filas relacionadas en la tabla hija, la operación fallará, ya que la integridad referencial se violaría.
    - Ejemplo:
        - Si intentas eliminar una fila en "Padres" que tiene referencias en "Hijos", obtendrás un error a menos que esas filas relacionadas en "Hijos" se eliminen o actualicen primero.
3. **RESTRICT**:
    - Similar a `NO ACTION`, impide la eliminación o actualización de la fila padre si hay filas relacionadas en la tabla hija. La diferencia con `NO ACTION` es que `RESTRICT` bloquea la acción inmediatamente antes de ejecutarla.


++IMPORTANTE CUANDO EMPEZAMOS A TRABAJAR EN UNA BASE DE DATOS NUEVA , ES NECESARIO LEER LA DOCUMENTACIÓN PARA ENTENER BIEN COMO FUNCIONAN LOS TIPOS DE PROPAGACIÓN EN ESE PROGRAMA QUE VAMOS A USAR. 


----

![[Pasted image 20241010101700.png]]


**Tipos de JOIN en SQL**

Hay varios tipos de JOIN en SQL, cada uno con su propio propósito y comportamiento:

**1. INNER JOIN:**

- **Propósito:** Devuelve filas que tienen valores coincidentes en ambas tablas.
- **Sintaxis:**
    
    SQL
    
    ```
    SELECT columna_nombre(s)
    FROM tabla1
    INNER JOIN tabla2
    ON tabla1.columna_nombre = tabla2.columna_nombre;
    ```
    

    
- **Ejemplo:**
    
    SQL
    
    ```
    SELECT clientes.id_cliente, pedidos.id_pedido
    FROM clientes
    INNER JOIN pedidos
    ON clientes.id_cliente = pedidos.id_cliente;
    ```
    
    
    
    Esta consulta devuelve el ID del cliente y el ID del pedido para todos los clientes que han realizado al menos un pedido.

**2. LEFT JOIN:**

- **Propósito:** Devuelve todas las filas de la tabla izquierda, incluso si no hay coincidencias en la tabla derecha.
- **Sintaxis:**
    
    SQL
    
    ```
    SELECT columna_nombre(s)
    FROM tabla1
    LEFT JOIN tabla2
    ON tabla1.columna_nombre = tabla2.columna_nombre;
    ```
    
    
    
- **Ejemplo:**
    
    SQL
    
    ```
    SELECT clientes.id_cliente, pedidos.id_pedido
    FROM clientes
    LEFT JOIN pedidos
    ON clientes.id_cliente = pedidos.id_cliente;
    ```
    
    
    
    Esta consulta devuelve todos los clientes, incluidos aquellos que no han realizado ningún pedido.

**3. RIGHT JOIN:**

- **Propósito:** Devuelve todas las filas de la tabla derecha, incluso si no hay coincidencias en la tabla izquierda.
- **Sintaxis:**
    
    SQL
    
    ```
    SELECT columna_nombre(s)
    FROM tabla1
    RIGHT JOIN tabla2
    ON tabla1.columna_nombre = tabla2.columna_nombre;
    ```
    
    
    
- **Ejemplo:**
    
    SQL
    
    ```
    SELECT clientes.id_cliente, pedidos.id_pedido
    FROM clientes
    RIGHT JOIN pedidos
    ON clientes.id_cliente = pedidos.id_cliente;
    ```
    
    
    
    Esta consulta devuelve todos los pedidos, incluidos aquellos que no han sido realizados por ningún cliente.

**4. FULL OUTER JOIN:**

- **Propósito:** Devuelve todas las filas cuando hay una coincidencia en la tabla izquierda o derecha.
- **Sintaxis:**
    
    SQL
    
    ```
    SELECT columna_nombre(s)
    FROM tabla1
    FULL OUTER JOIN tabla2
    ON tabla1.columna_nombre = tabla2.columna_nombre;
    ```
    
    
    
- **Ejemplo:**
    
    SQL
    
    ```
    SELECT clientes.id_cliente, pedidos.id_pedido
    FROM clientes
    FULL OUTER JOIN pedidos
    ON clientes.id_cliente = pedidos.id_cliente;
    ```
    
    
    
    Esta consulta devuelve todos los clientes y todos los pedidos, incluidos aquellos que no han sido realizados por ningún cliente y aquellos que no han sido realizados para ningún cliente.

**5. SELF JOIN:**

- **Propósito:** Une una tabla consigo misma para encontrar relaciones dentro de la misma tabla.
- **Sintaxis:**
    
    SQL
    
    ```
    SELECT columna_nombre(s)
    FROM tabla1 AS t1
    JOIN tabla1 AS t2
    ON t1.columna_nombre = t2.columna_nombre;
    ```
    
   
    
- **Ejemplo:**
    
    SQL
    
    ```
    SELECT e1.id_empleado, e1.nombre, e2.nombre AS nombre_jefe
    FROM empleados AS e1
    JOIN empleados AS e2
    ON e1.id_jefe = e2.id_empleado;
    ```
    
    
    
    Esta consulta devuelve el ID del empleado, el nombre y el nombre del jefe para todos los empleados.

**Elección del tipo de JOIN adecuado:**

La elección del tipo de JOIN depende de los requisitos específicos de tu consulta. Considera los siguientes factores:

- **¿Qué datos quieres devolver?** ¿Quieres incluir todas las filas de ambas tablas o solo las filas que tienen valores coincidentes?
- **¿Cuál es la relación entre las tablas?** ¿Son relaciones uno a uno, uno a muchos o muchos a muchos?

Al comprender los diferentes tipos de JOIN y sus propósitos, puedes combinar eficazmente datos de varias tablas para obtener la información que necesitas.


---

Base de Datos SQL

No tocar estas bases de datos que MySQL utiliza como referencia en su funcionamiento: 

![[Pasted image 20241010104602.png]]


---

para hacer la conexión a base de datos modificamos la conexión en application.properties:

### 1. **spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver**

- **Propósito**: Esta línea especifica el controlador JDBC que se usará para conectar la aplicación con la base de datos MySQL.
- **Detalle**: `com.mysql.cj.jdbc.Driver` es el controlador (driver) para conectar con MySQL, parte del conector JDBC (Java Database Connectivity) de MySQL. El sufijo `.cj` se refiere a "Communications Java", que es el nuevo paquete del driver a partir de la versión 8.x de MySQL.

### 2. **spring.datasource.url=jdbc:mysql://127.0.0.1:3306/eventixpro?serverTimezone=Europe/Madrid&createDatabaseIfNotExist=true**

- **Propósito**: Esta es la URL de conexión que le dice a Spring cómo y dónde conectarse a la base de datos.
- **Desglose**:
    - `jdbc:mysql://`: Especifica que estamos usando JDBC con MySQL como protocolo de conexión.
    - `127.0.0.1`: Es la dirección IP del servidor de base de datos. `127.0.0.1` es la IP local (localhost), lo que significa que la base de datos está ejecutándose en la misma máquina donde está la aplicación.
    - `3306`: Es el puerto donde MySQL escucha por defecto.
    - `eventixpro`: Es el nombre de la base de datos con la que nos queremos conectar. Si no existe, la opción `createDatabaseIfNotExist=true` intentará crearla automáticamente.
    - `serverTimezone=Europe/Madrid`: Ajusta la zona horaria del servidor de la base de datos a la de Europa/Madrid para evitar problemas de desincronización temporal.
    - `createDatabaseIfNotExist=true`: Permite que MySQL cree la base de datos `eventixpro` si no está creada aún.

### 3. **spring.datasource.username=root**

- **Propósito**: Especifica el nombre de usuario para autenticar la conexión con la base de datos.
- **Detalle**: En este caso, el usuario es `root`, que es el nombre de usuario predeterminado con permisos completos en una instalación estándar de MySQL.

### 4. **spring.datasource.password=root**

- **Propósito**: Esta línea define la contraseña para el usuario especificado en la línea anterior.
- **Detalle**: La contraseña también es `root`, que es la predeterminada si no ha sido cambiada. Sin embargo, es recomendable cambiarla para entornos de producción, ya que `root/root` es una combinación insegura.

### 5. **spring.sql.init.platform=mysql**

- **Propósito**: Esta propiedad le indica a Spring qué plataforma de base de datos se está utilizando.
- **Detalle**: En este caso, se establece como `mysql`, lo que ayuda a Spring a saber qué tipo de SQL se debe generar (si es necesario) en función de la base de datos MySQL.


Con estas configuraciones, tu aplicación Spring Boot puede conectarse a una base de datos MySQL que está ejecutándose localmente, crear la base de datos si no existe, y manejar el tiempo en función de la zona horaria especificada.

---

cuando tenemos cardinalidad muchos a muchos , podemos usar hibérnate para que nos creé la tercera tabla, y se recomienda siempre usar una relación unidireccional, lo que significa que solo en uno de los dos archivos .java donde tenemos los parámetros de creación de las tablas originales.

-----
Interfaces en Java: 

![[Pasted image 20241010125546.png]]

Al crear: springframewrok.data.jpa.repository.JpaRepostiory<User, String>  buscar el significado en chatgpt. con el código que hemos armado.


//INFORMACIÓN QUE HAY QUE REVISAR

Conceptos clave  
La interfaz central en la abstracción de repositorios de Spring Data es `Repository`. Esta toma la clase de dominio a gestionar, así como el tipo de identificador de la clase de dominio como argumentos de tipo. Esta interfaz actúa principalmente como una interfaz de marcador para capturar los tipos con los que trabajar y para ayudarte a descubrir interfaces que extienden esta. Las interfaces `CrudRepository` y `ListCrudRepository` proporcionan una funcionalidad avanzada de CRUD para la clase de entidad que se está gestionando.

### Interfaz CrudRepository

java

Copiar código

`public interface CrudRepository<T, ID> extends Repository<T, ID> {    <S extends T> S save(S entity);          Optional<T> findById(ID primaryKey);     Iterable<T> findAll();                   long count();                            void delete(T entity);                   boolean existsById(ID primaryKey);       // … más funcionalidades omitidas. }`

- Guarda la entidad dada.
- Devuelve la entidad identificada por el ID dado.
- Devuelve todas las entidades.
- Devuelve el número de entidades.
- Elimina la entidad dada.
- Indica si existe una entidad con el ID dado.

Los métodos declarados en esta interfaz se conocen comúnmente como métodos CRUD. La interfaz `ListCrudRepository` ofrece métodos equivalentes, pero estos devuelven una lista (`List`), donde los métodos de `CrudRepository` devuelven un iterable (`Iterable`).

También proporcionamos abstracciones específicas de tecnología de persistencia, como `JpaRepository` o `MongoRepository`. Estas interfaces extienden `CrudRepository` y exponen las capacidades de la tecnología de persistencia subyacente, además de las interfaces genéricas que no dependen de la tecnología de persistencia, como `CrudRepository`.

Además de `CrudRepository`, existen `PagingAndSortingRepository` y `ListPagingAndSortingRepository`, que agregan métodos adicionales para facilitar el acceso paginado a las entidades:

### Interfaz PagingAndSortingRepository

java

Copiar código

`public interface PagingAndSortingRepository<T, ID> {    Iterable<T> findAll(Sort sort);    Page<T> findAll(Pageable pageable); }`

Las interfaces de extensión dependen de ser compatibles con el módulo de almacenamiento real. Aunque esta documentación explica el esquema general, asegúrate de que tu módulo de almacenamiento admite las interfaces que deseas usar.  
Para acceder a la segunda página de `User` con un tamaño de página de 20, podrías hacer lo siguiente:

java

Copiar código

`PagingAndSortingRepository<User, Long> repository = // … obtener acceso a un bean Page<User> users = repository.findAll(PageRequest.of(1, 20));`

`ListPagingAndSortingRepository` ofrece métodos equivalentes, pero devuelve una lista (`List`) donde los métodos de `PagingAndSortingRepository` devuelven un iterable (`Iterable`).

Además de los métodos de consulta, la derivación de consultas para tanto contar (`count`) como eliminar (`delete`) también está disponible. La siguiente lista muestra la definición de la interfaz para una consulta derivada de conteo:

### Consulta Derivada de Conteo

java

Copiar código

`interface UserRepository extends CrudRepository<User, Long> {    long countByLastname(String lastname); }`

La siguiente lista muestra la definición de la interfaz para una consulta derivada de eliminación:

### Consulta Derivada de Eliminación

java

Copiar código

`interface UserRepository extends CrudRepository<User, Long> {    long deleteByLastname(String lastname);    List<User> removeByLastname(String lastname); }`

4o

--------------------------


com.core.timmy.service vamos a tener solo interfaces