
Material Design 3 es la tercera versión del lenguaje de diseño desarrollado por Google, enfocado en crear interfaces consistentes y atractivas para aplicaciones y sitios web. Se lanzó como una evolución de **Material Design 2**, con varias mejoras clave:

1. **Personalización**: Material Design 3 permite una mayor personalización, lo que facilita que las aplicaciones reflejen la identidad visual de una marca o las preferencias de los usuarios. Una de sus características más destacadas es **Material You**, que adapta la paleta de colores de la interfaz según el fondo de pantalla o los colores del sistema operativo Android.
    
2. **Nuevos componentes**: Introduce nuevos componentes visuales, como botones flotantes extendidos, paneles laterales mejorados y otros elementos que mejoran la experiencia del usuario.
    
3. **Enfoque en accesibilidad**: Se centra en crear interfaces más accesibles, con mejoras en contraste de colores, tipografías más legibles y tamaños de toque más amplios.

---

**Jetpack Compose** es un framework de Google para desarrollar interfaces de usuario (UI) en Android de manera declarativa. Es parte de la suite **Jetpack** y representa una nueva forma de crear aplicaciones Android, reemplazando o complementando el enfoque tradicional basado en XML con un enfoque más moderno y eficiente.

### Características clave de Jetpack Compose:

1. **Declarativo**: Con Jetpack Compose, describes cómo debería verse tu UI en función de su estado actual, y el sistema se encarga de actualizar la interfaz cuando ese estado cambia. En lugar de modificar vistas de forma imperativa, defines funciones que "componen" tu interfaz con base en los datos.
2. **Reutilización y composición**: La interfaz se construye utilizando funciones **@Composable**, que son bloques reutilizables de código que puedes combinar para crear interfaces complejas.
    
3. **Menos código**: Jetpack Compose permite reducir la cantidad de código necesario, eliminando XML y uniendo la lógica de UI y su representación visual en un mismo lugar, lo que facilita el mantenimiento y comprensión.
    
4. **Interoperabilidad**: Puedes integrar composables en aplicaciones Android que ya usan vistas tradicionales (XML) y viceversa, lo que permite migrar de manera gradual.
    
5. **Herramientas modernas**: Jetpack Compose se integra bien con las herramientas modernas de desarrollo de Android, como Android Studio, y soporta funciones como previsualizaciones en tiempo real, para que puedas ver cómo quedará tu UI mientras escribes el código.
    
6. **Material Design**: Compose incluye soporte nativo para Material Design (incluyendo Material Design 3), lo que facilita crear interfaces atractivas y consistentes con las pautas de diseño de Android.
    
7. **Gestión de estados simplificada**: Manejar el estado en Jetpack Compose es más sencillo gracias a su enfoque declarativo. El framework se encarga de observar cambios en los datos y actualizar las vistas de manera eficiente.

---

Un **Snackbar** en desarrollo de interfaces (UI) es un pequeño componente visual que muestra un mensaje breve en la parte inferior de la pantalla. Generalmente se utiliza para proporcionar **retroalimentación** o notificaciones no intrusivas al usuario, como cuando ocurre una acción, pero sin interrumpir la actividad actual.

### Características de un Snackbar:

1. **Brevedad**: Está diseñado para mostrar mensajes cortos y temporales.
2. **Posición**: Normalmente aparece en la parte inferior de la pantalla, aunque su ubicación puede variar en algunas plataformas o configuraciones.
3. **Desaparición automática**: Desaparece por sí mismo después de unos segundos, aunque también puede incluir una opción para que el usuario lo cierre manualmente.
4. **Acciones**: Puede tener botones interactivos (como "Deshacer"), lo que le permite al usuario responder rápidamente a la notificación, pero sin bloquear su flujo de trabajo.

### Usos comunes:

- Confirmar que se completó una acción (por ejemplo, "Archivo guardado").
- Mostrar mensajes breves sobre acciones fallidas o exitosas (como "Correo enviado" o "No se pudo conectar").
- Ofrecer acciones rápidas (como "Deshacer" después de eliminar un elemento).

---

