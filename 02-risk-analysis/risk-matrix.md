# Risk Matrix

| ID | Riesgo | Impacto | Probabilidad | Nivel | Tipo de Riesgo |
|----|--------|---------|--------------|-------|---------------|
| R1 |  [Falla en el cálculo del carrito: El sistema podría no actualizar el monto total al cambiar cantidades o procesar el checkout]| 5 | 3 | 15 | [Funcional] |
| R2 | [Incompatibilidad móvil: La interfaz de JPetStore no es responsiva, impidiendo que el cliente use los botones de navegación o checkout desde un celular.] | 2 | 5 | 10 | [Usabilidad] |
| R3 | [La web incrementa su tiempo de respuesta cuando hay varios usuarios simultáneos] | 4 | 4 | 16 | [Performance] |
| R4 | [Pérdida de sesión en Checkout: El usuario invitado se registra para poder confirmar la compra, pero el sistema limpia el carrito obligándolo a buscar los productos de nuevo.] | 2 | 4 | 8 | [Funcional] |
| R5 | [Exposivión de datos del usuario al momento de realizar la compra] | 4 | 4 | 16 | [Seguridad] |