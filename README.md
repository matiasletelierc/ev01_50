# 🚀 Sistema de Gestión de Proyectos - Laravel 11

## 📋 Descripción
Sistema completo de gestión de proyectos desarrollado con Laravel 11, que incluye tanto una API REST como una interfaz web para la administración de proyectos.

## ✨ Características

### 🔌 API REST
- **CRUD Completo** para proyectos
- **Autenticación JWT** 
- **Validaciones robustas**
- **Manejo de errores consistente**
- **Respuestas JSON estructuradas**

### 🌐 Interfaz Web
- **Dashboard intuitivo**
- **Formularios de creación y edición**
- **Autenticación de usuarios**
- **Navegación responsive**

### 🔒 Seguridad
- **JWT Tokens** para API
- **Middleware de autenticación**
- **Validación de datos**
- **Protección de rutas**

## 🛠️ Tecnologías Utilizadas
- **Laravel 11**
- **PHP 8.2+**
- **SQLite Database**
- **JWT Authentication (tymon/jwt-auth)**
- **Bootstrap 5**
- **Blade Templates**

## 📚 Endpoints de la API

### Autenticación
```
POST /api/register - Registrar usuario
POST /api/login    - Iniciar sesión
```

### Proyectos (Requiere autenticación)
```
GET    /api/proyectos      - Listar proyectos
POST   /api/proyectos      - Crear proyecto
GET    /api/proyectos/{id} - Mostrar proyecto
PUT    /api/proyectos/{id} - Actualizar proyecto
DELETE /api/proyectos/{id} - Eliminar proyecto
```

## 🚀 Instalación

### Pasos para levantar el proyecto después de clonar:

1. **Instalar dependencias:**
   ```bash
   composer install
   ```

2. **Configurar variables de entorno:**
   ```bash
   # Copiar contenido del .env.example en el archivo .env (generar localmente si no existe)
   cp .env.example .env
   php artisan key:generate
   ```

3. **Configurar Base de Datos:**
   - El proyecto está configurado para SQLite
   - La base de datos se crea automáticamente en `database/database.sqlite`

4. **Ejecutar migraciones y seeders:**
   ```bash
   php artisan migrate:fresh --seed
   ```

5. **Levantar el servidor:**
   ```bash
   php artisan serve
   ```

## 📖 Uso

### Interfaz Web
- Visita `http://127.0.0.1:8000`
- Regístrate o inicia sesión
- Gestiona proyectos desde el dashboard

### API Testing
1. Registra un usuario en `/api/register`
2. Haz login en `/api/login` para obtener el token JWT
3. Usa el token en el header: `Authorization: Bearer {token}`
4. Consume los endpoints de proyectos

## 🎯 Estructura del Proyecto

```
app/
├── Http/
│   ├── Controllers/
│   │   ├── Api/
│   │   │   └── ProyectoController.php  # API REST Controller
│   │   ├── ProyectoVistasController.php # Web Interface Controller
│   │   └── AuthController.php          # Autenticación JWT
│   └── Middleware/
│       └── JwtMiddleware.php           # JWT Middleware
├── Models/
│   ├── Proyecto.php                    # Modelo de Proyecto
│   └── User.php                        # Modelo de Usuario
```

## 🧪 Testing con Postman

1. **Registro de usuario:**
   - POST `http://127.0.0.1:8000/api/register`
   - Body: `{"name": "Test", "email": "test@test.com", "password": "password"}`

2. **Login:**
   - POST `http://127.0.0.1:8000/api/login`
   - Body: `{"email": "test@test.com", "password": "password"}`

3. **Usar endpoints protegidos:**
   - Agregar header: `Authorization: Bearer {token_obtenido}`

## 🔧 Configuración Adicional

- **JWT Secret:** Se genera automáticamente con el comando key:generate
- **Database:** SQLite configurado en .env
- **Middleware:** JWT aplicado a rutas de API protegidas

## 👨‍💻 Desarrollado con
- Laravel Framework
- JWT Authentication
- RESTful API Design
- MVC Architecture

