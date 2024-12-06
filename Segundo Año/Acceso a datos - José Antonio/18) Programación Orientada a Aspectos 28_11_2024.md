
(Programación Transversal)

aspectos (aspects) = Elementos comunes que son transversales.

consejo (advice) = La acción  que hay que ejecutar de forma transversal.

punto de corte o pointcut = (El momento en el cual se va hacer) El lugar de nuestro código donde se debe ejecutar el advice. EJ. antes o después de ejecutar los saves.

punto de junte o join point =(El lugar exacto en el cual esta) La característica común, serian en un ejemplo los métodos save si queremos agregar un log en todos. Ej: Al rededor de los métodos save

Proxy (Intermediario o envoltorio) = aproximación es el objeto adicional + algo más. lo envuelve, y de hecho lo puede usar al objeto. a este Proxy ADP le ponemos los interceptores.

Interceptores = son los puntos que interrumpen la ejecución para hacer el advice primero, antes de que empiece a ejecutarse el método que seguía. Se puede interceptar antes, después o antes y después.



Esto es bastante aplicable a código relacionado con seguridad, como gestión de permisos.

Herramientas para gestionar : Aspect J en java (es la más completa) para programación orientada a aspectos.. Hay otras que tienen otras librerias, por ejemplo Spring tiene la suya que se llama Spring AOP ( Tiene menos especialización, hace menos cosas.

Se pueden usar las dos.


Weaving = Entretejer, se usa en este caso para decir que las clases se orientan de forma vertical pero los aspectos se usando de forma horizontal, creando un entretejido. 


---

Spring Framework en vez de spring Boot, esto se hace adicionalmente para activar el AOP.

@EnableAspectJAutoProxy(proxy TragetClass=true)

en cualquier @Config o en Web Security Config se puede poner esta anotación.

---
//@service, @respository y @controller vienen derivan de component como anotaciones. El Spring Bean es hecho con @Componenet.- "JavaBean(Normal)+Singleton = SpringBean.

//Que es un singleton : que solo vamos a dejar que haya una sola instancia.


Aspectos que les especializan para hacer determinadas cosas asi funcionan, si es un Spring Bean hace solo una instancia de la clases.


----

***Ejemplo***


`package com.core.timmy.aop;`
`import org.aspectj.lang.JoinPoint;`
`import org.aspectj.lang.annotation.Aspect;`
`import org.aspectj.lang.annotation.Before;`
`import org.springframework.stereotype.Component;`

`import lombok.extern.slf4j.Slf4j;`

`//@service, @respository y @controller vienen derivan de component como anotaciones. El Spring Bean es hecho con @Componenet.- "JavaBean(Normal)+Singleton = SpringBean.`

`//Que es un singleton`

`@Component`
`@Aspect //hace que pueda ser gestionada como programación orientada a objetos`
`@Slf4j`

`public class Monitor {`
`@Before("execution(* com.core.timmy.*.*.save*(..))")`
`private void aspectBeforeSave(JoinPoint joinPoint) {`
`log.info("Monitor aspectBeforeSave >"+ joinPoint.getSignature().toString());`
`}`
`}`

---
