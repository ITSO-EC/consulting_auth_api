# RESTful API Consulting

## Estructura de proyecto

```
src\
 |--config\         # Environment variables and configuration related things
 |--controllers\    # Route controllers (controller layer)
 |--docs\           # Swagger files
 |--middlewares\    # Custom express middlewares
 |--models\         # Mongoose models (data layer)
 |--routes\         # Routes
 |--services\       # Business logic (service layer)
 |--utils\          # Utility classes and functions
 |--validations\    # Request data validation schemas
 |--app.js          # Express app
 |--index.js        # App entry point
```

### API Endpoints

Lista de rutas disponibles:

**Rutas de autenticación**:\
`POST /v1/auth/register` - register\
`POST /v1/auth/login` - login\
`POST /v1/auth/refresh-tokens` - refresh auth tokens\
`POST /v1/auth/forgot-password` - send reset password email\
`POST /v1/auth/reset-password` - reset password\
`POST /v1/auth/send-verification-email` - send verification email\
`POST /v1/auth/verify-email` - verify email

**Rutas de usuario**:\
`POST /v1/users` - create a user\
`GET /v1/users` - get all users\
`GET /v1/users/:userId` - get user\
`PATCH /v1/users/:userId` - update user\
`DELETE /v1/users/:userId` - delete user

Para los metodos de "GET ALL", es posible usar los siguientes metodos para temas de paginación:
- `limit` - limit data\
- `sortBy` - (desc|asc)\
- `page` - (default = 1)\
Ej:
Url: `v1/users?limit=100`\
Response: usuarios (con un maximo de 100 datos)

## Manejo de errores

El middleware de manejo de errores envía una respuesta de error, que tiene el siguiente formato:

```json
{
  "code": 404,
  "message": "Not found"
}
```
