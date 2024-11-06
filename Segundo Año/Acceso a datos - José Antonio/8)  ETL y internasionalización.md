
**# Localization basics: What are t9n, l10n, i18n, g11n?**

En el mundo de la tecnología, es posible que te encuentres con algunos acrónimos confusos. Estas palabras basadas en números se llaman numerónimos. A menudo se usan para abreviar palabras largas. Solo toma la primera y la última letra, y cuenta las letras que hay en medio.

Vamos a profundizar en las explicaciones de cada abreviatura:

t9n = traducción  
l10n = localización  
i18n = internacionalización  
g11n = globalización

A primera vista, podrías pensar que todos significan más o menos lo mismo, pero no es el caso. Empecemos por el más sencillo.

### ¿Qué es t9n?

La **traducción** es simplemente el proceso de convertir texto de un idioma (idioma de origen) a otro (idioma de destino). Es una parte crucial del proceso de localización. La traducción desempeña un papel vital para hacer que el contenido sea accesible y comprensible para diversas audiencias en todo el mundo.

### ¿Qué es l10n?

La **localización** se refiere a la adaptación de un producto, aplicación o contenido para cumplir con los requisitos lingüísticos, culturales y de otro tipo de un mercado objetivo específico (un "locale") para estar disponible para tu audiencia objetivo.

El proceso de localización de software puede adoptar tres formas diferentes:

- **Localización en cascada**: rápida salida al mercado en tu idioma de origen porque la localización comienza después de que se hayan implementado todas las funciones y el producto esté lanzado.
    
- **Localización ágil**: mayor productividad y flexibilidad en tu flujo de trabajo de localización. La localización se incorpora en un ciclo de desarrollo ágil del producto y se realiza en ciclos de trabajo cortos (sprints).
    
- **Localización continua**: una versión mejorada de la localización ágil, la localización continua es un ciclo en curso. Se obtiene retroalimentación más rápido de todos los interesados y se reduce el riesgo de errores de localización al lanzar en muchos mercados al mismo tiempo.
    

### ¿Qué es i18n?

La **internacionalización** no es lo mismo que la localización de software.

“La internacionalización es el proceso de diseñar y desarrollar un producto o aplicación para que pueda ser localizado para diferentes culturas, regiones e idiomas. Dicho de otro modo, la internacionalización es lo que hace posible la localización”.

**I18n** es el primer paso para hacer que el software sea global. Los desarrolladores de software suelen ser los responsables de la internacionalización, mientras que los traductores se encargan de la localización. Antes de comenzar cualquier tarea de localización, asegúrate de terminar el trabajo de internacionalización primero.

La internacionalización implica una variedad de tareas, entre ellas:

- **Longitud del texto**: Al diseñar software, los desarrolladores deben tener en cuenta las diferencias de longitud entre los idiomas para garantizar que el texto traducido sea visible en las interfaces del software, incluso si es más largo que el original.
    
- **Símbolos de moneda y números**: Cada idioma tiene su propio sistema para escribir números y moneda, y el software debe ser capaz de manejar todos ellos.
    
- **Formatos de fecha y hora**: Diferentes países utilizan distintos formatos de fecha y hora, por lo que el software debe tenerlos en cuenta.
    
- **Codificación de caracteres**: La internacionalización debe ser capaz de manejar una amplia gama de escrituras, incluso algunas que no son latinas.
    
- **Dirección del idioma**: Es crucial que el software destinado a idiomas que se leen de derecha a izquierda (como el árabe, hebreo o persa) pueda manejar texto orientado en cualquier dirección.
    

### ¿Qué es g11n?

La **globalización** es el proceso de adaptar y vender productos de software a una audiencia internacional. Está relacionada con la estrategia general de tu empresa para hacer crecer el negocio a escala global. Seamos honestos: diseñar y crear software que responda fácilmente a los requisitos lingüísticos para todo el mundo puede ser un gran desafío.

### Conclusión

Para resumir, el mundo de la tecnología está lleno de numerónimos desconcertantes, que son abreviaturas basadas en números para palabras largas. Por ejemplo, t9n, l10n, i18n y g11n representan traducción, localización, internacionalización y globalización, respectivamente. Aunque pueden parecer similares a primera vista, cada abreviatura tiene su propio significado y desempeña un papel fundamental en hacer que el software sea accesible para audiencias diversas.


----


ETL = Extracción, transformación y carga. Es el proceso que las organizaciones impulsadas por datos utilizan para recopilar datos de distintas fuentes para luego reunirlos a fin de facilitar el descubrimiento, la generación de informes, el análisis y la toma de decisiones.

ELT= Extracción, carga y transformación. Depende de la complejidad del proceso de transformación.

A veces se puede encontrar una mezcla de los dos procesos.

Extracción: Durante la extracción, ETL identifica los datos y los copia desde sus orígenes, de modo de poder transportar y almacenar los datos de destino. Los datos pueden proceder de orígenes estructurados y no estructurados, estos información puede sacarse de documentos, correos electrónicos, aplicaciones de negocios, base de datos, equipos sensores, etc.

Transformación: Dado que los datos extraídos no están procesados en su formato original, se deben asignar y transformar a find de prepararlos para el almacén de datos final. en el proceso de transformación, ETL valida, autentica, des-duplica o agrega los datos de manera que los datos resultantes sean fiables y se pueden consultar.

Carga: ETL traslada los datos transformados al almacén de datos de destino. Este paso puede implicar la carga inicial de todos los datos de origen o puede ser la carga de los cambios incrementales en los datos de origen. Puede cargar los datos en tiempo real o en lote programados.

![[Drawing 2024-10-07 09.10.44.excalidraw]]