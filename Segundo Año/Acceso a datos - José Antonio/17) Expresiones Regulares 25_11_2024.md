#### **1. Validar un correo electrónico**

Permitir solo correos electrónicos con formato estándar.

regex

Copiar código

`^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$`

- Ejemplo válido: `usuario@gmail.com`
- Ejemplo no válido: `usuario@gmail`

---

#### **2. Validar un número de teléfono (formato internacional)**

Formato: Código de país opcional seguido por 9-15 dígitos.

regex

Copiar código

`^\+?\d{9,15}$`

- Ejemplo válido: `+34912345678` o `912345678`
- Ejemplo no válido: `+34-912345678`

---

#### **3. Aceptar solo letras (mayúsculas y minúsculas)**

regex

Copiar código

`^[a-zA-Z]+$`

- Ejemplo válido: `Hola`
- Ejemplo no válido: `Hola123`

---

#### **4. Aceptar solo números enteros positivos**

regex

Copiar código

`^\d+$`

- Ejemplo válido: `1234`
- Ejemplo no válido: `-1234`

---

#### **5. Contraseña con requisitos específicos**

Al menos una mayúscula, una minúscula, un número, un carácter especial, y entre 8-20 caracteres.

regex

Copiar código

`^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,20}$`

- Ejemplo válido: `Contraseña1!`
- Ejemplo no válido: `password`

---

#### **6. Validar una fecha (formato DD/MM/AAAA)**

Asegurarse de que los días y meses estén dentro de los rangos válidos.

regex

Copiar código

`^(0[1-9]|[12][0-9]|3[01])/(0[1-9]|1[0-2])/\d{4}$`

- Ejemplo válido: `25/11/2024`
- Ejemplo no válido: `31/13/2024`

---

#### **7. Validar una URL**

Permitir solo URLs válidas con o sin `http/https`.

regex

Copiar código

`^(https?:\/\/)?(www\.)?[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}(\/\S*)?$`

- Ejemplo válido: `https://www.ejemplo.com`
- Ejemplo no válido: `htp://ejemplo`

---

#### **8. Aceptar solo caracteres alfanuméricos y guiones bajos**

regex

Copiar código

`^\w+$`

- Ejemplo válido: `usuario_123`
- Ejemplo no válido: `usuario-123`

---

#### **9. Código postal (España, 5 dígitos)**

regex

Copiar código

`^\d{5}$`

- Ejemplo válido: `28001`
- Ejemplo no válido: `2800`

---

INTERFACE CON ARROBA ADELANTE: sirve para construir anotaciones: @interface. para crear nuestras propias expresiones regulares.

Se puede definir para que ámbito sirve la etiqueta que estamos creando. Ejemplos de ámbito de actuación o funcionamiento: Puede ser para clases, métodos, o atributos(variables).
También tenemos que decidir en que momento de la ejecución de nuestro programa debería de funcionar; si funciona en tiempo de ejecución o no ejecución. (Pre)

no retorna un verdadero o falso que nos diga si cumple o no cumple la validación. Máximo un mensajito diciendo que no esta es validado. 

Necesitamos la clase con el método que haga la validación por si misma.


