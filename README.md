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

## ⚙️ Cómo usar el AutoCRUD (Workflow del Examen)

Si la base de datos cambia (ej. añades una tabla nueva), sigue estos pasos estrictos para regenerar la API automáticamente:

### Paso 1: Generar Modelos (Reverse Engineering)
Este comando conecta con MySQL y crea los archivos en la carpeta `/models`.

```bash
npm run db:generate
