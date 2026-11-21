# P2 - API de productos

En esta práctica hice una API con Node.js y Express. La API empieza con dos productos, un teclado y un mouse. Desde Postman puedo verlos, agregar otro producto, cambiar sus datos o eliminarlo.

## Cómo ejecutar el proyecto

Instala Node.js 18 o superior. Abre una terminal en la carpeta del proyecto y ejecuta estos comandos:

```bash
npm install
npm start
```

Si PowerShell bloquea `npm`, puedes usar `npm.cmd install` y `npm.cmd start`.

Cuando arranque el servidor, la API estará en `http://localhost:3000`.

## Rutas de la API

| Método | Ruta | Qué hace | Respuesta | Posibles errores |
|---|---|---|---|---|
| GET | `/api/productos` | Muestra todos los productos | `200` con la lista | — |
| GET | `/api/productos/:id` | Busca un producto por su ID | `200` con el producto | `404` |
| POST | `/api/productos` | Agrega un producto | `201` con el producto nuevo | `400` |
| PUT | `/api/productos/:id` | Cambia los datos de un producto | `200` con los datos actualizados | `400` o `404` |
| DELETE | `/api/productos/:id` | Elimina un producto | `204` con la respuesta vacía | `404` |

## Ejemplo

Al iniciar el servidor, si mando `GET http://localhost:3000/api/productos/1`, obtengo `200 OK` y aparecen los datos del teclado:

```json
{
  "id": 1,
  "nombre": "Teclado",
  "precio": 350,
  "stock": 10
}
```

## Pruebas en Postman

La colección de las ocho pruebas está en `P2_Productos.postman_collection.json`. Para repetirlas, importa ese archivo en Postman, inicia el servidor y envía las solicitudes del 01 al 08 en orden.

