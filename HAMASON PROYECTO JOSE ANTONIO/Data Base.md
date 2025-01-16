
Tables we need:

1) Roles =  Solo rol name

2) Users =  Nombre de usuario, email, teléfono, nombre completo, dirección, password, fecha de caducidad de la cuenta, fecha de caducidad de credenciales, si la cuenta esta activa (Enabled : True or false.) también otra columna de LockedAccount(True or false);

3) Users have roles = username (se puede repetir porque un usuario puede tener más de un role) , rolename.

4) Customers = id auto incrementado, nombre completo, email, telefono, direccion, numero de tarjeta de debito o crédito y fecha de caducidad.

5)  Products = id numérico autoincrementado, descripción, url fotos, precio (max 999,99 min 0), stock(valor mínimo 0), descuento a aplicar en porcentaje

6) Customers product eval =  id auto incrementado , valoracionClientes (muy malo ,malo, regular, bueno, muy bueno).

7) Family of products = id autoincrementado, Familia (Alimentación, electrónica, textil, joyeria, perfumeria) // una familia puede pertenecer a  varios productos pero un producto solo a una familia.

8) Orders: id numérico autoincrementado,  fecha de creación de pedido, estado del pedido(Progress o finished), nombre cliente hace pedido.

9) Providers: id autoincrementado, CIF, email, teléfono, nombre completo, dirección, familia de productos. ( Pensar bien como podrias asociar la familia de producto asociada a un proveedor con los productos específicos. )