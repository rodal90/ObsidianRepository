
<?php

/* es como el includes pero si no existe el */

      require_once "cors.php";

      require_once "conn/connexion.php";

      $method = $_SERVER['REQUEST_METHOD'];

      switch($method){

        case "GET":

            $sqlCustomers = "SELECT * FROM `customers_tb` WHERE 1";

            $customersResult =mysqli_query($conn,$sqlCustomers);

            $customer = [];

            while($customer = mysqli_fetch_assoc($customersResult)){ /*el mysqli_fetch_assoc lo que hace es convertir lo que hemos sacado de sql es un objeto de php y lo convertimos  en un array asociativo*/

                $contacts = [];

                $sqlContacts = "SELECT * FROM customers_contacts_tb WHERE id_customer =".$customer['id'];

                $contactsResult = mysqli_query($conn,$sqlContacts);

                while($contact= mysqli_fetch_assoc($contactsResult)){

                    $contacts[]=$contact;
                }
                $customer["contacts"] = $contacts;

                $customers[]=$customer; //la siguiente posición libre del array la rellenas con el dato que te esta dando. Array asociativo es igual al map en java scrpit osea: (clave-valor la estructura)
            }
      }
?>


Este fragmento de código PHP está diseñado para manejar solicitudes HTTP, específicamente una solicitud GET, interactuando con una base de datos MySQL para obtener información de clientes y sus contactos asociados. Aquí te explico cada parte:

### 1. `require_once "cors.php";` y `require_once "conn/connexion.php";`

- **`require_once`**: Similar a `include`, pero la diferencia es que si el archivo no existe, se genera un error fatal, y si ya se incluyó previamente, no lo vuelve a incluir.
- **`cors.php`**: Es probable que este archivo esté gestionando los encabezados para permitir que el servidor acepte solicitudes desde otros dominios (Cross-Origin Resource Sharing - CORS).
- **`conn/connexion.php`**: Contiene la lógica de conexión a la base de datos. Esto es esencial para poder realizar consultas MySQL dentro del script.

### 2. `$method = $_SERVER['REQUEST_METHOD'];`

- **`$_SERVER['REQUEST_METHOD']`**: Obtiene el método HTTP de la solicitud. En este caso, se espera que sea una solicitud GET.

### 3. `switch($method){ case "GET": ... }`

- **`switch($method)`**: Se usa para manejar diferentes tipos de solicitudes HTTP, como GET, POST, etc. Aquí se está manejando el caso específico del método GET.

### 4. Consulta principal de clientes

php

Copiar código

``$sqlCustomers = "SELECT * FROM `customers_tb` WHERE 1"; $customersResult = mysqli_query($conn,$sqlCustomers);``

- **`$sqlCustomers`**: La consulta SQL selecciona todos los registros de la tabla `customers_tb`.
- **`mysqli_query($conn, $sqlCustomers)`**: Ejecuta la consulta en la base de datos utilizando la conexión `$conn`, que fue definida en `conn/connexion.php`.

### 5. Recorrido de resultados de clientes

php

Copiar código

`$customer = []; while($customer = mysqli_fetch_assoc($customersResult)){`

- **`mysqli_fetch_assoc($customersResult)`**: Convierte cada fila del resultado en un array asociativo de PHP. Es decir, cada columna de la tabla será accesible como un elemento del array con su nombre como clave.

### 6. Consulta de contactos asociados

php

Copiar código

`$contacts = []; $sqlContacts = "SELECT * FROM customers_contacts_tb WHERE id_customer =".$customer['id']; $contactsResult = mysqli_query($conn,$sqlContacts);`

- **`$sqlContacts`**: La consulta SQL selecciona todos los registros de la tabla `customers_contacts_tb` donde el campo `id_customer` coincide con el ID del cliente actual (extraído del array `$customer`).
- **`mysqli_query($conn, $sqlContacts)`**: Ejecuta la consulta de contactos para obtener los contactos relacionados con el cliente.

### 7. Recorrido de contactos

php

Copiar código

`while($contact= mysqli_fetch_assoc($contactsResult)){     $contacts[]=$contact; } $customer["contacts"] = $contacts;`

- **`mysqli_fetch_assoc($contactsResult)`**: Al igual que con los clientes, convierte cada fila de la tabla de contactos en un array asociativo.
- **`$contacts[] = $contact;`**: Añade cada contacto al array `$contacts`.
- **`$customer["contacts"] = $contacts;`**: Añade el array de contactos al array del cliente bajo la clave `"contacts"`, creando una estructura jerárquica donde cada cliente tiene un array de contactos.

### 8. Guardar el cliente con sus contactos

php

Copiar código

`$customers[]=$customer;`

- **`$customers[] = $customer;`**: Añade el array del cliente actual (que ahora incluye los contactos) al array `$customers`, que contendrá todos los clientes con sus respectivos contactos.

### En resumen:

Este código maneja una solicitud GET para obtener todos los clientes de la tabla `customers_tb`, y por cada cliente, obtiene sus contactos desde la tabla `customers_contacts_tb`. Los resultados se estructuran en arrays asociativos, donde cada cliente tiene una clave `"contacts"` que contiene un array con sus contactos.