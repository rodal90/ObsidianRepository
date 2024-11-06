
**POLA: Principle of least atonishment (Principio por mínima sorpresa).

### 1. **Encriptar** (Encrypt)

- **Definición**: Es el proceso de convertir datos legibles en un formato ilegible utilizando un algoritmo y una clave. El propósito es proteger los datos, de manera que solo quienes tengan la clave puedan volver a leerlos (desencriptar).
- **Ejemplo**: Usar el algoritmo AES para encriptar mensajes.
- **Características**:
    - Necesita una clave para revertir el proceso (desencriptar).
    - Protección de la información durante el tránsito o almacenamiento.
    - Ejemplos de algoritmos: AES, RSA.

### 2. **Cifrar** (Cipher)

- **Definición**: "Cifrar" es sinónimo de "encriptar". En algunos contextos, se usa para describir específicamente la conversión de texto en un formato no legible usando algoritmos.
- **Diferencia**: En la práctica moderna, encriptar y cifrar se usan de manera intercambiable, pero en algunos contextos académicos, el cifrado puede referirse más al método o algoritmo (por ejemplo, un "cifrado" como RSA, que es el proceso de encriptar con una clave pública).

### 3. **Codificar** (Encode)

- **Definición**: Es el proceso de convertir datos en un formato diferente, pero no para seguridad, sino para transmisión o almacenamiento eficiente. No utiliza una clave y puede revertirse fácilmente.
- **Ejemplo**: Convertir caracteres de texto a Base64 para transmitirlos por HTTP.
- **Características**:
    - Propósito: legibilidad o transmisión eficiente.
    - Reversible sin necesidad de una clave.
    - Ejemplos: Base64, URL encoding.

### 4. **Hashing** (Hash)

- **Definición**: Es el proceso de transformar un conjunto de datos (texto, archivo, etc.) en una cadena de longitud fija mediante un algoritmo. El resultado (hash) es único para los datos, pero no está diseñado para ser reversible.
- **Ejemplo**: Usar el algoritmo SHA-256 para generar un hash de una contraseña.
- **Características**:
    - No reversible (no puedes obtener los datos originales desde un hash).
    - Utilizado para verificar la integridad de datos o como protección de contraseñas.
    - Ejemplos de algoritmos: MD5, SHA-256.

### 5. **Ofuscar** (Obfuscate)

- **Definición**: Es el proceso de modificar el código o datos para hacerlos difíciles de entender, pero sin cambiar su funcionalidad. El objetivo es dificultar la comprensión para evitar ingeniería inversa.
- **Ejemplo**: Cambiar nombres de variables en código fuente a cadenas sin sentido.
- **Características**:
    - No garantiza seguridad total.
    - Se usa para dificultar la lectura o análisis del código, no necesariamente para proteger los datos.

### Diferencias clave:

- **Encriptar/Cifrar** vs. **Codificar**: Encriptar/cifrar busca proteger datos para que solo puedan ser leídos por quien tenga la clave, mientras que codificar busca transformar datos para su transmisión o almacenamiento sin intención de seguridad.
- **Hashing**: No es reversible y se usa principalmente para verificar integridad o autenticidad.
- **Ofuscar**: Se enfoca en hacer más difícil la interpretación del código o los datos, pero no implica seguridad criptográfica fuerte como el cifrado.



