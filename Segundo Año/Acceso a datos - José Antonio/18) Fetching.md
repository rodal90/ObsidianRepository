


**Fetching:** Hay dos formas la primera es eager  y lazy. 


Estamos hablando de que encadena las sentencias de todas las tablas que tenemos creadas.

entonces si usamos el eager Fetching si hay muchas tablas con sentencias puede suceder una efecto cascada y ejecutar todas las sentencias unas detrás de otras. Es una sola consulta pero arrastra todo lo que lleve al final.

con el Lazy fetching, No sobrecargas la base de datos al inicio y lo malo es que cuando lo necesites se tiene que hacer una segunda consulta.

Cuando usar eager o lazy?

cuando  la cardinalidad va hacia un ToOne, como un ManyToOne o un OneToOne, el valor por defecto del tipo de fetching es eager. (se identifica por que es normalmente un solo objeto).

Ahora si la cardinalidad va hacia Many, como ManyToMany o un OneToMany, el valor por defecto del tipo de fetching es lazy. (se identifica por que es normalmente son varios objetos, collection, list, set o map).


IMPORTANTE:

Set lo usamos cuando hablamos de muchos a muchos, o asegurarnos de que no puede tener repetidos, pero no respetan el orden.

Los list si respetan el orden, pero hay repetidos.


---------------------------------------------------------------------

Importante: Id autoincrementado lo mejor es que sean del tipo long