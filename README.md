# PROYECTO FINAL - C#

-- Para esta API se utilizó la version .NET 6.0.

CRUD hecho con C# y .NET (NetCore). Aplique patrones como DTO, Repository, IoC, Inyección de dependencias y mapeos (Automapper). Como base de datos utilize MS SQL Server, y se versiono en Git.
Para este proyecto, utilice el metodo Scaffold de "Database First" partiendo de una base de datos que se me entrego.

---

-   [PROYECTO FINAL - C#](#proyecto-final---c)
    -   [Endpoints API](#endpoints-api)
    -   [Producto](#producto)
        -   [Get All Productos](#get-all-productos)
        -   [Get Producto By Id](#get-producto-by-id)
        -   [Get Productos By IdUsuario](#get-productos-by-idusuario)
        -   [Create Producto](#create-producto)
        -   [Update Producto](#update-producto)
        -   [Delete Producto](#delete-producto)
    -   [ProductoVendido](#productovendido)
        -   [Get All ProductosVendidos](#get-all-productosvendidos)
        -   [Get ProductoVendido By Id](#get-productovendido-by-id)
        -   [Get ProductosVendidos By IdUsuario](#get-productosvendidos-by-idusuario)
        -   [Create ProductoVendido](#create-productovendido)
        -   [Update ProductoVendido](#update-productovendido)
        -   [Delete ProductoVendido](#delete-productovendido)
    -   [Usuario](#usuario)
        -   [Get All Usuarios](#get-all-usuarios)
        -   [Get Usuario By Id](#get-usuario-by-id)
        -   [Get Usuario By Username](#get-usuario-by-username)
        -   [Login](#login)
        -   [Create Usuario](#create-usuario)
        -   [Update Usuario](#update-usuario)
        -   [Delete Usuario](#delete-usuario)
    -   [Venta](#venta)
        -   [Get All Ventas](#get-all-ventas)
        -   [Get Venta By Id](#get-venta-by-id)
        -   [Get Ventas By IdUsuario](#get-ventas-by-idusuario)
        -   [Create Venta](#create-venta)
        -   [Create Venta by IdUsuario](#create-venta-by-idusuario)
        -   [Update Venta](#update-venta)
        -   [Delete Venta](#delete-venta)

NuGets necesarias para esta API:

-   AutoMapper -versión 13.0.0
-   Microsoft.EntityFrameworkCore -versón 6.0.26
-   Microsoft.EntityFrameworkCore.SqlServer -versón 6.0.26
-   Microsoft.EntityFrameworkCore.Tools -versón 6.0.26
-   Swashbuckle.AspNetCore -versón 6.5.0

## Endpoints API

## Producto

### Get All Productos

Obtiene lista de todos los productos.

```http
  GET localhost:{su_puerto}/api/Producto
```

| Parametro | Tipo | Descripción                    |
| :-------- | :--- | :----------------------------- |
|           |      | **No se requieren parametros** |

-   URL: https://localhost:7104/api/Producto
-   Metodo GET
-   Parametros:
    Ninguno
-   Respuesta:
    -   200: Lista de todos los productos
    -   400, 404: Error

### Get Producto By Id

Obtiene el producto con el Id deseado.

```http
  GET localhost:{su_puerto}/api/Producto/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Producto/{id}
-   Metodo GET
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: Producto
    -   400 - 404: Error

### Get Productos By IdUsuario

Obtiene lista de todos los productos con el mismo idUsuario.

```http
    GET localhost:{su_puerto}/api/Producto/IdUsuario/{idUsuario}
```

| Parametro   | Tipo  | Descripción            |
| :---------- | :---- | :--------------------- |
| `IdUsuario` | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Producto/IdUsuario/{idUsuario}
-   Metodo GET
-   Parametros:
    Nombre (URl)
-   Respuesta:
    -   200: Lista de productos con el mismo IdUsuario
    -   400 - 404: Error

### Create Producto

Crea un producto.

```http
  POST localhost:{su_puerto}/api/Producto
```

| Parametro | Tipo                | Descripción             |
| :-------- | :------------------ | :---------------------- |
| Producto  | `ProductoCreateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/Producto
-   Metodo: POST
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: Producto
    -   400, 404, 409: Error

### Update Producto

Modifica un producto.

```http
  PUT localhost:{su_puerto}/api/Producto
```

| Parametro  | Tipo                | Descripción             |
| :--------- | :------------------ | :---------------------- |
| `Producto` | `ProductoUpdateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/Producto
-   Metodo: PUT
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: Producto
        -   400, 404, 409: Error

### Delete Producto

Elimina el producto.

```http
  DELETE localhost:{su_puerto}/api/Producto/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Producto/{id}
-   Metodo DELETE
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: Producto eliminado
        -   400, 404, 409: Error

## ProductoVendido

### Get All ProductosVendidos

Obtiene lista de todos los productos vendidos.

```http
  GET localhost:{su_puerto}/api/ProductoVendido
```

| Parametro | Tipo | Descripción                    |
| :-------- | :--- | :----------------------------- |
|           |      | **No se requieren parametros** |

-   URL: https://localhost:7104/api/ProductoVendido
-   Metodo GET
-   Parametros:
    Ninguno
-   Respuesta:
    -   200: Lista de todos los productos vendidos
    -   400, 404: Error

### Get ProductoVendido By Id

Obtiene el producto vendido con el Id deseado.

```http
  GET localhost:{su_puerto}/api/ProductoVendido/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/ProductoVendido/{id}
-   Metodo GET
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: ProductoVendido
    -   400 - 404: Error

### Get ProductosVendidos By IdUsuario

Obtiene lista de todos los productos que fueron vendidos por un mismo usuario. Primero recupera la lista de Productos con el mismo IdUsuario, y luego verifica cuales coinciden con el IdProducto de ProductoVendido.

```http
    GET localhost:{su_puerto}/api/ProductoVendido/IdUsuario/{idUsuario}
```

| Parametro   | Tipo  | Descripción            |
| :---------- | :---- | :--------------------- |
| `IdUsuario` | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/ProductoVendido/IdUsuario/{idUsuario}
-   Metodo GET
-   Parametros:
    Nombre (URl)
-   Respuesta:
    -   200: Lista de productos vendidos por el mismo usuario
    -   400 - 404: Error

### Create ProductoVendido

Crea un producto vendido.

```http
  POST localhost:{su_puerto}/api/ProductoVendido
```

| Parametro       | Tipo                       | Descripción             |
| :-------------- | :------------------------- | :---------------------- |
| ProductoVendido | `ProductoVendidoCreateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/ProductoVendido
-   Metodo: POST
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: ProductoVendido
    -   400, 404, 409: Error

### Update ProductoVendido

Modifica un producto vendido.

```http
  PUT localhost:{su_puerto}/api/ProductoVendido
```

| Parametro         | Tipo                       | Descripción             |
| :---------------- | :------------------------- | :---------------------- |
| `ProductoVendido` | `ProductoVendidoUpdateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/ProductoVendido
-   Metodo: PUT
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: ProductoVendido
    -   400, 404, 409: Error

### Delete ProductoVendido

Elimina el producto vendido.

```http
  DELETE localhost:{su_puerto}/api/ProductoVendido/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/ProductoVendido/{id}
-   Metodo DELETE
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: ProductoVendido eliminado
        -   400, 404, 409: Error

## Usuario

### Get All Usuarios

Obtiene lista de todos los usuarios.

```http
  GET localhost:{su_puerto}/api/Usuario
```

| Parametro | Tipo | Descripción                    |
| :-------- | :--- | :----------------------------- |
|           |      | **No se requieren parametros** |

-   URL: https://localhost:7104/api/Usuario
-   Metodo GET
-   Parametros:
    Ninguno
-   Respuesta:
    -   200: Lista de todos los usuarios
    -   400, 404: Error

### Get Usuario By Id

Obtiene el usuario con el Id deseado.

```http
  GET localhost:{su_puerto}/api/Usuario/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Usuario/{id}
-   Metodo GET
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: Usuario
    -   400 - 404: Error

### Get Usuario By Username

Obtiene el usuario con el username.

```http
  GET localhost:{su_puerto}/api/Usuario/UserName{username}
```

| Parametro  | Tipo     | Descripción            |
| :--------- | :------- | :--------------------- |
| `userName` | `string` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Usuario/UserName{username}
-   Metodo GET
-   Parametros:
    username (URL)
-   Respuesta:
    -   200: Usuario
    -   400 - 404: Error

### Login

Obtiene el usuario con el username y la contraseña.

```http
  GET localhost:{su_puerto}/api/Usuario/{username}/Login/{password}
```

| Parametro  | Tipo     | Descripción            |
| :--------- | :------- | :--------------------- |
| `userName` | `string` | **Requerido** por URL. |

| Parametro  | Tipo     | Descripción            |
| :--------- | :------- | :--------------------- |
| `password` | `string` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Usuario/{username}/Login/{password}
-   Metodo GET
-   Parametros:
    username (URL), password (URL)
-   Respuesta:
    -   200: Usuario
    -   400 - 404: Error

### Create Usuario

Crea un usuario.

```http
  POST localhost:{su_puerto}/api/Usuario
```

| Parametro | Tipo               | Descripción             |
| :-------- | :----------------- | :---------------------- |
| Usuario   | `UsuarioCreateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/Usuario
-   Metodo: POST
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: Usuario
    -   400, 404, 409: Error

### Update Usuario

Modifica un usuario.

```http
  PUT localhost:{su_puerto}/api/Usuario
```

| Parametro | Tipo               | Descripción             |
| :-------- | :----------------- | :---------------------- |
| `Usuario` | `UsuarioUpdateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/Producto
-   Metodo: PUT
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: Usuario
        -   400, 404, 409: Error

### Delete Usuario

Elimina el usuario.

```http
  DELETE localhost:{su_puerto}/api/Usuario/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Usuario/{id}
-   Metodo DELETE
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: Usuario eliminado
        -   400, 404, 409: Error

## Venta

### Get All Ventas

Obtiene lista de todas las ventas.

```http
  GET localhost:{su_puerto}/api/Venta
```

| Parametro | Tipo | Descripción                    |
| :-------- | :--- | :----------------------------- |
|           |      | **No se requieren parametros** |

-   URL: https://localhost:7104/api/Venta
-   Metodo GET
-   Parametros:
    Ninguno
-   Respuesta:
    -   200: Lista de todas las ventas
    -   400, 404: Error

### Get Venta By Id

Obtiene la venta con el Id deseado.

```http
  GET localhost:{su_puerto}/api/Venta/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Venta/{id}
-   Metodo GET
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: Venta
    -   400 - 404: Error

### Get Ventas By IdUsuario

Obtiene lista de todas las ventas con el mismo idUsuario.

```http
    GET localhost:{su_puerto}/api/Venta/IdUsuario/{idUsuario}
```

| Parametro   | Tipo  | Descripción            |
| :---------- | :---- | :--------------------- |
| `IdUsuario` | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Venta/IdUsuario/{idUsuario}
-   Metodo GET
-   Parametros:
    Nombre (URl)
-   Respuesta:
    -   200: Lista de ventas con el mismo IdUsuario
    -   400 - 404: Error

### Create Venta

Crea una venta.

```http
  POST localhost:{su_puerto}/api/Venta
```

| Parametro | Tipo             | Descripción             |
| :-------- | :--------------- | :---------------------- |
| Venta     | `VentaCreateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/Venta
-   Metodo: POST
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: Venta
    -   400, 404, 409: Error

### Create Venta by IdUsuario

Crea una venta a aprtir de una lista de productos. Ademas, por cada producto de la lista, crea un nuevo ProductoVendido con sus datos.

```http
  POST localhost:{su_puerto}/api/Venta/idUsuario
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| idUsuario | `int` | **Requerido** por URL. |

| Parametro       | Tipo                    | Descripción             |
| :-------------- | :---------------------- | :---------------------- |
| List<Productos> | `ProductoDtoParaVentas` | **Requerido** por body. |

-   URL: https://localhost:7104/api/Venta
-   Metodo: POST
-   Parametros:
    IdUsuario y lista de datos personales en formato Json (body)
-   Respuesta:
    -   200: Venta
    -   400, 404, 409: Error

### Update Venta

Modifica una venta.

```http
  PUT localhost:{su_puerto}/api/Venta
```

| Parametro | Tipo             | Descripción             |
| :-------- | :--------------- | :---------------------- |
| `Venta`   | `VentaUpdateDto` | **Requerido** por body. |

-   URL: https://localhost:7104/api/Venta
-   Metodo: PUT
-   Parametros:
    Datos personales en formato Json (body)
-   Respuesta:
    -   200: Venta
        -   400, 404, 409: Error

### Delete Venta

Elimina la venta.

```http
  DELETE localhost:{su_puerto}/api/Venta/{id}
```

| Parametro | Tipo  | Descripción            |
| :-------- | :---- | :--------------------- |
| `Id`      | `int` | **Requerido** por URL. |

-   URL: https://localhost:7104/api/Venta/{id}
-   Metodo DELETE
-   Parametros:
    Id (URL)
-   Respuesta:
    -   200: Venta eliminada
        -   400, 404, 409: Error

