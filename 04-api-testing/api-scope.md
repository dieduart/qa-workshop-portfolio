# API Testing — Alcance
## API
Swagger Petstore

## Alcance funcional
Gestión de mascotas (pet).

## Operaciones seleccionadas
| Método HTTP | Endpoint | Propósito |
|---|---|---|
|GET |/pet/{petId} |Busqueda de mascota específica por id |
|POST|/pet |Agrega una nueva mascota a la tienda |

## Justificación
Al ser una tienda de mascota, la gestión de mascotas es lo fundamental.

## Condiciones de prueba identificadas
Se realizan pruebas positivas y negativas:

**Pruebas positivas:**

Intentar obtener una mascota específica con el Metodo GET. Estatus 200.
Intentar agregar una mascota en el inventario con el Metodo POST. 

**Pruebas negativas:**
Intentar buscar una mascota que no exita con el Metodo GET. Estatus 404.
Intentar realizar un mal envío al inventario con el Metodo POST para ver si valida la estructura.

## Fuera de alcance
No se tendrán en cuenta los metodos PUT ni DELETE porque el inventario no debería sufrir cambios de descripción y tampoco a nivel de dato (borrado lógico), sino solo manejarse con cantidades disponibles.