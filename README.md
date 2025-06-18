# Backend para E-commerce - Vital Crossfit

Este proyecto es el backend de una tienda online deportiva (Vital Crossfit) desarrollado con Node.js, Express y Sequelize como ORM para interactuar con una base de datos MySQL.

## Características principales

- API RESTful completa para gestión de productos, categorías, usuarios, carritos y órdenes
- Autenticación y autorización de usuarios
- Operaciones CRUD para todas las entidades
- Eliminación lógica (soft delete) para usuarios, productos y categorías
- Validación de datos tanto en frontend como en backend
- Manejo de errores detallado
- Documentación de API mediante endpoints bien estructurados

## Tecnologías utilizadas

- **Node.js**: Entorno de ejecución JavaScript
- **Express**: Framework para aplicaciones web
- **Sequelize**: ORM para interactuar con la base de datos MySQL
- **MySQL2**: Controlador para MySQL
- **bcrypt**: Para hashear contraseñas
- **cors**: Middleware para habilitar CORS
- **dotenv**: Para manejar variables de entorno
- **morgan**: Logger para las solicitudes HTTP

## Estructura del proyecto

```

backend_vital_crossfit/
├── src/
│ ├── config/
│ │ └── db/
│ │ └── connection.js
│ ├── controllers/
│ │ ├── carritoController.js
│ │ ├── categoriaController.js
│ │ ├── itemCarritoController.js
│ │ ├── itemOrdenController.js
│ │ ├── ordenController.js
│ │ ├── productoController.js
│ │ └── usuarioController.js
│ ├── models/
│ │ ├── Carrito.js
│ │ ├── Categoria.js
│ │ ├── ItemCarrito.js
│ │ ├── ItemOrden.js
│ │ ├── Orden.js
│ │ ├── Producto.js
│ │ ├── Usuario.js
│ │ └── index.js
│ ├── routes/
│ │ ├── carritoRoutes.js
│ │ ├── categoriaRoutes.js
│ │ ├── itemCarritoRoutes.js
│ │ ├── itemOrdenRoutes.js
│ │ ├── ordenRoutes.js
│ │ ├── productoRoutes.js
│ │ └── usuarioRoutes.js
│ └── servicios/
│ └── pruebaGenerica.js
├── .env.example
├── index.js
├── package.json
└── README.md

```

## Modelos de datos

El sistema contiene los siguientes modelos principales:

1. **Usuario**: Gestiona los usuarios del sistema (clientes y administradores)
2. **Producto**: Contiene los productos de la tienda
3. **Categoría**: Clasifica los productos
4. **Carrito**: Maneja los carritos de compra de los usuarios
5. **ItemCarrito**: Productos individuales dentro de un carrito
6. **Orden**: Pedidos realizados por los usuarios
7. **ItemOrden**: Productos individuales dentro de una orden

## Endpoints disponibles

### Usuarios

- `GET /usuarios/all` - Obtener todos los usuarios
- `GET /usuarios/activos` - Obtener usuarios activos
- `GET /usuarios/administradores` - Obtener usuarios administradores
- `GET /usuarios/:id` - Obtener un usuario por ID
- `POST /usuarios` - Crear un nuevo usuario
- `PUT /usuarios/:id` - Actualizar un usuario
- `DELETE /usuarios/:id` - Eliminar físicamente un usuario
- `PATCH /usuarios/:id` - Eliminación lógica (cambiar estado activo/inactivo)

### Productos

- `GET /productos/all` - Obtener todos los productos
- `GET /productos/activos` - Obtener productos activos
- `GET /productos/:id` - Obtener un producto por ID
- `POST /productos` - Crear un nuevo producto
- `PUT /productos/:id` - Actualizar un producto
- `DELETE /productos/:id` - Eliminar físicamente un producto
- `PATCH /productos/:id` - Eliminación lógica (cambiar estado activo/inactivo)

### Categorías

- `GET /categorias/all` - Obtener todas las categorías
- `GET /categorias/activos` - Obtener categorías activas
- `GET /categorias/:id` - Obtener una categoría por ID
- `POST /categorias` - Crear una nueva categoría
- `PUT /categorias/:id` - Actualizar una categoría
- `DELETE /categorias/:id` - Eliminar físicamente una categoría
- `PATCH /categorias/:id` - Eliminación lógica (cambiar estado activo/inactivo)

### Carritos

- `GET /carritos` - Obtener todos los carritos
- `GET /carritos/:id` - Obtener un carrito por ID
- `POST /carritos` - Crear un nuevo carrito
- `PUT /carritos/:id` - Actualizar un carrito
- `DELETE /carritos/:id` - Eliminar un carrito

### ItemsCarrito

- `GET /itemsCarrito` - Obtener todos los items de carrito
- `GET /itemsCarrito/:id` - Obtener un item de carrito por ID
- `POST /itemsCarrito` - Crear un nuevo item de carrito
- `PUT /itemsCarrito/:id` - Actualizar un item de carrito
- `DELETE /itemsCarrito/:id` - Eliminar un item de carrito

### Órdenes

- `GET /ordenes` - Obtener todas las órdenes
- `GET /ordenes/:id` - Obtener una orden por ID
- `POST /ordenes` - Crear una nueva orden
- `PUT /ordenes/:id` - Actualizar una orden
- `DELETE /ordenes/:id` - Eliminar una orden

### ItemsOrden

- `GET /itemsOrden` - Obtener todos los items de orden
- `GET /itemsOrden/:id` - Obtener un item de orden por ID
- `POST /itemsOrden` - Crear un nuevo item de orden
- `PUT /itemsOrden/:id` - Actualizar un item de orden
- `DELETE /itemsOrden/:id` - Eliminar un item de orden

## Configuración del entorno

1. Clona el repositorio
2. Instala las dependencias: `npm install`
3. Crea un archivo `.env` basado en `.env.example` y configura tus variables de entorno
4. Ejecuta el servidor en desarrollo: `npm run dev`
5. Para producción: `npm start`

## Variables de entorno

El proyecto requiere las siguientes variables de entorno (ver `.env.example`):

```

DB_NAME=nombre_base_de_datos
DB_USER=usuario_db
DB_PASSWORD=contraseña_db
DB_HOST=localhost
DB_PORT=3306
DB_DIALECT=mysql
PORT=3000
API_RAIZ=/api/v1

```

## Contribución

1. Haz un fork del proyecto
2. Crea una rama para tu feature (`git checkout -b feature/nueva-feature`)
3. Haz commit de tus cambios (`git commit -m 'Añade nueva feature'`)
4. Haz push a la rama (`git push origin feature/nueva-feature`)
5. Abre un Pull Request

## Licencia

Este proyecto está bajo la licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

## Autor

Carlos E Rodriguez
