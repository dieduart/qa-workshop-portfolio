## Charter
Explorar el flujo del Carrito de compras y checkout. Para evaluar la persistencia de datos, actualización de stock y el cálculo correcto de montos.

## ÁREAS
**Plataforma:** JpetStore

**URL esploradas:**

https://petstore.octoperf.com/actions/Catalog.action

https://petstore.octoperf.com/actions/Cart.action?viewCart=

https://petstore.octoperf.com/actions/Order.action?newOrderForm=

https://petstore.octoperf.com/actions/Order.action

https://petstore.octoperf.com/actions/Order.action?newOrder=&confirmed=true

**Navegador** 

Brave 1.96.59 (Build oficial) (64 bits)
Chromium: 154.0.8037.58

## INICIO
Inicio de las pruebas: 11:00 hs AM
Tiempo estimado: 45 min.

## TESTER
Diego Duarte

## DESGLOSE DE TAREAS
Navegación por el catalogo.
Selección de mas de un producto para agregar al carrito.
Elminicación de item y modificación de cantidades en el carrito.
Logue con un usuario válido para la compra.
PAgo y confirmación de la compra.

## ARCHIVOS DE DATOS
Productos agregador al carrito:
Fish: Spotless Koi - Precio unitario: $18.50 - Stock: 65066 - Cantidad agregada al carrito: 65067.

Fish: Large Angelfish - Precio unitario: $$16.50 - Stock: "Agotado" - Cantidad agregada al carrito: 3.

Usuario/Contaseña: j2ee/j2ee

Tarjeta:	Visa
Número:	999 9999 9999 9999 * Fake number!
Válido hasta (MM/YYYY):	12/03

Orden Número: 248442 del 2026/09/25

## NOTAS DE PRUEBA

Se agregaron al carrito mas de un producto.
Se hicieron cambios en las cantidades para verificar si se actualizaban los totales.

Se hicieron pruebas de vaciar el carrito para ver si permitiía ir al modulo de caja o pago con un carrito vacío.

Se agregaron productos con una cantidad superior al stock visible.
Para lograr finiquitar la compra la plataforma nos obligaba a iniciar sesión con un usuario.

Me logueo con un usuario válido y finiquito la compra.

## LISTA DE RIESGOS 

El sistema actualiza el stock de mercaderías pero permite agregar al carrito productos con stock "agotados". Esto puede generar pedidos de mercaderías sin existencia ocasionando la necesidad en el futuro de cancelar el pedido y devolver el dinero al cliente y probacar que este último cambie de tienda y elimine su cuenta.

## DEFECTOS (BUGS) 

Falta de validación al momento de agregar productos en el carrito de compras. El sistema permite completar con éxito una orden de compra para productos que explícitamente figuran como "Agotados" o sin stock.

Pérdida de productos en el carrito al cerrar sesión. Si un usuario inicia sesión, añade un producto al carrito y luego cierra e inicia sesión nuevamente, el carrito de compras no guarda los productos.

Se visualiza información sencible del cliente en las órdenes de pago: Datos de la tarjeta de credito.

Información errónea en el histórico de ordenes confirmadas. Los horarios son incorrectos.

## INCIDENTES (ISSUES) 

No se está claro si el cliente necesariamente debe tener un usuario registrado pra realizar compras en la plataforma o debería poder realizar la compra sin estar registrado.



# Sesión 2

## Charter

Explorar el formulario de inicio de sesión (Login) y registro de cuentas.Para validar el manejo de accesos, el control de errores frente a credenciales inválidas y el bloqueo de usuarios.

## ÁREAS

**Plataforma:** JpetStore

**URL esploradas:**

https://petstore.octoperf.com/actions/Account.action?signonForm=

https://petstore.octoperf.com/actions/Account.action?newAccountForm=

**Navegador** 

Brave 1.96.59 (Build oficial) (64 bits)
Chromium: 154.0.8037.58

## INICIO

Inicio de las pruebas: 11:50 hs AM
Tiempo estimado: 45 min.

## TESTER

Diego Duarte

## DESGLOSE DE TAREAS
Ingreso al formulario de Login.

Iniciar Sesión con usuario válido.

Meter una contraseña incorrecta de un usuario válido.

Registrar un nuevo usuario.

Iniciar sesión exitósamente con el usuario nuevo.

ingresar mal la contraseña del usuario nuevo varias veces. Mas de 4 veces

## ARCHIVOS DE DATOS

Usuario válido utilizado: j2ee/j2ee
Usuarios nuevo registrados: (dieduart/123) y (d/d)

## NOTAS DE PRUEBA

Se realizaron pruebas en el flujo de inicio de sesión con datos correctos e incorrectos. El sistema valida la información y emite el siguiente mensaje cuando los datos son incorrectos: "Invalid username or password. Signon failed."

Permite registrar nuevos usuario llenando todos los campos del formulario sin ningún tipo de validación. La única condición es que ningún campo se encuentre vacío.

Se realizaron pruebas de fallos constantes y ningún usuario fue bloqueado.

## LISTA DE RIESGOS 

Se podría realizar 'N' intentos por descubrir una contraseña debido a que el usuario no se bloqueo por intentos fallidos.

Se pododría registrar usuario sin ningun tipo de información real o verificable ya que no exiten validaciones de ningún tipo al momento de llenar los campos del formulario de registro.

Se podría vulnerar la seguridad de los usuario ya que no existe seguridad al momento de crear una contraseña puesto que una constraseña de un solo dígito es aceptable.

## DEFECTOS (BUGS) 
El sistema no bloquea usuario tras varios intentos fallidos.

El sistema no tiene validaciones de seguridad para contraseñas mas seguras.

El sistema no valida un formato correcto para el email.

## INCIDENTES (ISSUES) 
No está claro si existen campos obligatorios o no en el formulario de registro de usuario, ya que lo que ocurre es un error "Estado HTTP 500 – Internal Server Error" al momento de dar click en el boton "Save Account Information" con campos del formulario sin infomación.

Sale el mismo error al momento de intentar crear un usuario que ya existe con exactamente los mismos datos.