El operador **Elvis** (`?:`) es una característica presente en varios lenguajes de programación, como Kotlin, y está diseñado para simplificar la evaluación de expresiones y valores predeterminados cuando un valor puede ser `null`.

### ¿Qué es el operador Elvis?

El operador **Elvis** (`?:`) se utiliza para proporcionar un valor predeterminado cuando una expresión o variable tiene el valor `null`. Su nombre proviene de la similitud con un rostro sonriente inclinado que recuerda al peinado de Elvis Presley.

---

### **Cómo funciona en Kotlin**

En Kotlin, el operador Elvis se usa de esta manera:

kotlin

Copiar código

`val resultado = expresion ?: valorPredeterminado`

- **`expresion`**: Es el valor que se evalúa.
- **`valorPredeterminado`**: Es el valor que se usa si `expresion` es `null`.

Si `expresion` no es `null`, el operador devuelve el valor de `expresion`. Si `expresion` es `null`, devuelve `valorPredeterminado`.

---

### **Ejemplos prácticos**

#### Ejemplo 1: Uso básico

kotlin

Copiar código

`val nombre: String? = null val mensaje = nombre ?: "Valor predeterminado"  println(mensaje) // Salida: "Valor predeterminado"`

#### Ejemplo 2: Sin el operador Elvis (más verboso)

Sin el operador Elvis, tendrías que escribir algo como esto:

kotlin

Copiar código

`val mensaje = if (nombre != null) nombre else "Valor predeterminado"`

Con el operador Elvis, el código es más limpio y directo.

---

### **Uso avanzado**

#### Asignación condicional

kotlin

Copiar código

`val longitud = nombre?.length ?: 0 println(longitud) // Si nombre es null, devuelve 0`

#### Lanzar excepciones

Puedes usar el operador Elvis para lanzar una excepción si un valor es `null`:

kotlin

Copiar código

`val nombre = null ?: throw IllegalArgumentException("El valor no puede ser null")`