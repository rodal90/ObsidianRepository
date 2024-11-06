Buscar más información

La Forma Normal de Boyce-Codd (FNBC) es una técnica avanzada de normalización de bases de datos que busca eliminar redundancias y mejorar la integridad de los datos. Es una versión más estricta de la Tercera Forma Normal (3FN) y se utiliza para optimizar el diseño de bases de datos relacionales[


La solución a forma normales siempre es la misma. Se resuelven igual. La solución es siempre una tabla más.

## Características principales

- Elimina dependencias funcionales no triviales de atributos que no son parte de una clave candidata[
    

- Requiere que todos los determinantes sean claves candidatas[
    
- Ayuda a reducir la redundancia de datos y evita anomalías de actualización[

## Criterios para FNBC

Una tabla está en Forma Normal de Boyce-Codd si cumple las siguientes condiciones:

1. Está en Tercera Forma Normal (3FN)[
    
    
2. Para cada dependencia funcional no trivial, el determinante debe ser una clave candidata[
    
    

En términos más simples, una tabla está en FNBC si está en 3FN y los únicos determinantes son claves candidatas[

## Importancia y aplicación

La FNBC es crucial para:

- Mejorar la eficiencia del diseño de bases de datos[
    
- Garantizar la consistencia lógica de los datos[
    
    .monografias.com/trabajos98/forma-normal-boyce-codd/forma-normal-boyce-codd).
- Minimizar la duplicación de información[
    
    
- Facilitar la actualización y mantenimiento de la base de datos[
    
## Implementación

Para implementar FNBC, a menudo es necesario descomponer las tablas que no cumplen con los criterios en tablas más pequeñas que sí los cumplan. Este proceso ayuda a:

- Disminuir las anomalías de actualización[
    
- Minimizar la duplicación de datos[
    
    
- Asegurar la coherencia lógica de la base de datos[
    



## Primera forma normal, 1FN

No hay grupos repetidos de columnas, ni una columna guarda múltiples valores. Por ejemplo, si de una persona queremos guardar varios teléfonos deberíamos crear una tabla de teléfonos y relacionarla con la tabla de usuarios.

En el caso del ejemplo los grupos repetidos de columnas implica que de una persona solo se pueden guardar hasta tres teléfonos como máximo, han de crearse las columnas por adelantado aunque no se usen y si hay que actualizar un teléfono no sabríamos en que campo de la tabla está obligando a realizar una consulta de actualización en los tres campos.

Las columnas con múltiples valores son difíciles de actualizar con sentencias SQL por el formato que emplea la columna para guardar el dato, en este caso utilizando una barra como separador.

![[Pasted image 20241031085504.png]]

## Segunda forma normal, 2FN

Cada columna de una tabla está relacionada con todas las columnas de la clave primaria y no solo por una combinación de parte de la clave primaria. En este caso en que se guarda las las persona que trabajan en una empresa, cumple la 1FN al no tener columnas repetidas ni múltiples valores en una columna pero no cumple la 2FN estando la clave primaria formada por los campos _id_persona_ e _id_empresa_ y el campo _direccion_empresa_ siendo solo dependiente del campo _id_empresa_.

En este caso el problema además de contener posibles inconsistencias en los valores de las direcciones es que si se quisiera actualizar la dirección de una empresa habría que actualizar todos los registros de los empleados y empresa.

![[Pasted image 20241031090017.png]]

## Tercera forma normal, 3FN

Cada columna de una tabla está relacionada directamente con las columnas de la clave primaria, no de forma transitiva a través de otro campo. En el mismo caso anterior que cumple la 2FN no cumple la tercera si el campo _horas semanales_ depende del puesto.

Podría haber inconsistencias de datos si dos personas tuviesen diferentes horas semanales para el mismo puesto.

![[Pasted image 20241031090000.png]]

Para evitar  errores de tipeo, normalmente le damos ya las opciones asi no hay posibilidad de error.

***Pensar en que estas identificando como erros en las tablas. Y memorizarlo.***


