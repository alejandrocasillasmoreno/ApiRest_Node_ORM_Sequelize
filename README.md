# API REST con AutoCRUD y Arquitectura MVC (Node.js + Sequelize)

Este proyecto implementa una API REST completa utilizando **Node.js, Express y Sequelize**. 
La característica principal es su sistema de **AutoCRUD**, capaz de leer la base de datos y generar automáticamente todo el código necesario (Modelos, Controladores, Servicios y Rutas) siguiendo una arquitectura MVC limpia.

## 📋 Requisitos Previos

* **Node.js** instalado.
* **XAMPP** (o cualquier servidor MySQL) corriendo en el puerto `3306`.
* **Postman** (para probar las peticiones POST, PUT y DELETE).

---

## 🚀 Instalación y Configuración

1.  **Clonar el repositorio:**
    ```bash
    git clone <TU_URL_DEL_REPO>
    cd ApiRest_Node_ORM_Sequelize
    ```

2.  **Instalar dependencias:**
    ```bash
    npm install
    ```

3.  **Configurar Base de Datos:**
    * Abre PHPMyAdmin (o tu gestor SQL).
    * Crea una base de datos llamada: `api_rest_db`.
    * Crea la tabla requerida para el examen (`Log`) con este SQL:
        ```sql
        CREATE TABLE Log (
            id INT AUTO_INCREMENT PRIMARY KEY,
            log VARCHAR(255) NOT NULL,
            createdAt DATETIME DEFAULT CURRENT_TIMESTAMP,
            updatedAt DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
        );
        ```

---

## ⚙️ Cómo usar el AutoCRUD
Una vez que existen los modelos, ejecuta el script de automatización para generar la estructura MVC (Controladores, Servicios y Rutas):
node autocrud.js

### Lanzar el Servidor
Para iniciar la API en modo desarrollo (con reinicio automático nodemon):
npm run dev
Y nos debera aparecer esto: http://localhost:3000

### Ejemplos de Endpoints
POST,/log,Crear un registro nuevo,
"{ ""log"": ""Mensaje de prueba"" }"

PUT,/log/:id,Actualizar registro existente,
"{ ""log"": ""Mensaje editado"" }"

DELETE,/log/:id,Eliminar registro

