# Proyecto UD2 - Cliente de una API Rest

## Descripción del Proyecto
Este proyecto consiste en implementar un cliente para consumir la API REST desarrollada en Laravel. El proyecto se divide en dos partes principales: el backend desarrollado en Laravel y el frontend en Vue.js. El backend expone una serie de APIs que permiten realizar operaciones CRUD sobre diferentes recursos, y el frontend consume esas APIs y proporciona una interfaz de usuario.

## Estructura del Proyecto
El proyecto está estructurado de la siguiente manera:

```
Proyecto_UD2_AD_Sergio_Soria/
├── backend/     # Código del backend desarrollado en Laravel
└── frontend/    # Código del frontend desarrollado con Vue.js
```

- **`backend/`**: Contiene todo el código de Laravel, incluyendo las rutas para `Storage`, `Json`, y `CSV`.
- **`frontend/`**: Contiene el proyecto Vue.js que consume las APIs definidas en el backend.

## Requisitos del Proyecto

### Requisitos del Backend
- **PHP**: Versión 8.2 o superior.
- **Composer**: Para la gestión de dependencias de Laravel.
- **Docker**: Para levantar el entorno de desarrollo del backend.

### Requisitos del Frontend
- **Node.js**: Versión 16 o superior.
- **NPM**: Para la gestión de paquetes del proyecto Vue.js.
- **Vue CLI**: Para crear y ejecutar la aplicación Vue.js.

## Instrucciones para Levantar el Entorno de Desarrollo

### 1. Clonar el Repositorio
Primero, clona el repositorio del proyecto desde GitHub:

```sh
git clone https://github.com/SergioSoria12/Proyecto_UD2_AD_Sergio_Soria.git
```

### 2. Levantar el Backend con Docker
El backend de Laravel se levanta usando Docker para evitar problemas de configuración en diferentes entornos.

1. **Navegar a la Carpeta Raíz del Proyecto**:
   
   ```sh
   cd Proyecto_UD2_AD_Sergio_Soria
   ```

2. **Levantar el Backend**:

   ```sh
   docker-compose up -d --build
   ```

   Esto levantará el contenedor del backend en el puerto `8000`. Puedes verificar si está corriendo con el siguiente comando:

   ```sh
   docker ps
   ```

3. **Verificar el Backend**:
   Abre tu navegador y navega a `http://localhost:8000/api/hello` para asegurarte de que el backend está respondiendo correctamente.

### 3. Levantar el Frontend Vue.js
El frontend es un proyecto Vue.js que consume la API del backend.

1. **Navegar a la Carpeta `frontend`**:

   ```sh
   cd frontend
   ```

2. **Instalar las Dependencias**:

   ```sh
   npm install
   ```

3. **Levantar el Servidor de Desarrollo**:

   ```sh
   npm run serve
   ```

   Por defecto, el servidor se ejecutará en `http://localhost:8080`. Asegúrate de que el backend esté corriendo antes de probar el frontend.

### 4. Probar la Aplicación
- Abre `http://localhost:8080` en tu navegador para acceder al frontend.
- Selecciona una de las opciones del desplegable (`Json`, `Storage`, `Csv`)
- Prueba las operaciones (`Get Files`, `Store`, etc.) desde la interfaz de usuario para interactuar con el backend.

## Configuración del Entorno

### Configuración CORS
El backend Laravel tiene configurado CORS para permitir solicitudes desde el frontend en el puerto `8080`. Este archivo está ubicado en `backend/config/cors.php` y se ha configurado para permitir solicitudes desde `http://localhost:8080`.

### Archivos de Configuración
- **`Dockerfile`**: Configuración del entorno Docker para PHP y Laravel, ubicado en la carpeta `backend`.
- **`docker-compose.yml`**: Configura y levanta el contenedor para el backend.
- **`vue.config.js`**: Configuración para el servidor de desarrollo de Vue.js, donde se especifica el puerto `8080`.

## Comandos Rápidos
- **Levantar el Backend**: `docker-compose up -d --build`
- **Levantar el Frontend**: `npm run serve` (desde la carpeta `frontend`)
- **Limpiar Caché de Laravel**: `docker-compose exec backend php artisan config:cache`

## Notas
- Asegúrate de tener todos los servicios (backend y frontend) ejecutándose al mismo tiempo para probar la aplicación completa.
- Si necesitas cambiar el puerto del frontend, asegúrate de actualizar el archivo `cors.php` en el backend para permitir el nuevo puerto.
