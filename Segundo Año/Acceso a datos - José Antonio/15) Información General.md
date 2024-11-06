

En Spring, la clase `Model` se utiliza para pasar datos desde el controlador a la vista (por ejemplo, una página JSP, Thymeleaf, etc.). Actúa como un contenedor para almacenar atributos que luego pueden ser mostrados en la vista para renderizar contenido dinámico.

### Principales usos de `Model`

- **Compartir datos con la vista:** Al agregar atributos al `Model`, estos pueden ser accedidos y utilizados en la plantilla o página HTML para mostrar información al usuario.
- **Sincronización de datos en la petición:** Los atributos en el `Model` solo están disponibles durante la solicitud actual y desaparecen después de que se procesa la respuesta.

### Ejemplo de uso

En el código de tu controlador, puedes ver cómo se utiliza el `Model` para pasar información a la vista:

java

Copiar código

`@GetMapping("/loginGet") public String loginGet(Model model) {     model.addAttribute("login", loginService.newEntity());     return "loginPage"; }`

Aquí, `loginService.newEntity()` crea un nuevo objeto `Login`, que se agrega al `Model` con el nombre `"login"`. En la vista, puedes acceder a este atributo con el mismo nombre para llenar formularios o mostrar información.

### Funciones comunes de `Model`

- `addAttribute(String key, Object value)`: agrega un atributo con una clave específica que será accesible en la vista.
- `addAllAttributes(Map<String, ?> attributes)`: agrega múltiples atributos al `Model`.

En resumen, `Model` es una forma conveniente y temporal de transferir datos desde el controlador a la vista en una aplicación Spring MVC.