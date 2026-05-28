# 🎬 CineProyecto — API REST

¡Bienvenido a **CineProyecto**! Esta es una API REST robusta y moderna desarrollada con **Spring Boot** para la gestión de la cartelera de cines, salas, películas, funciones, clientes y la venta de entradas.

El proyecto cuenta con un frontend estático integrado (HTML/CSS/JS) que consume la API directamente, facilitando la visualización de la cartelera y la compra de tickets de forma interactiva y visual.

---

## 🛠️ Stack Tecnológico

El proyecto utiliza el siguiente conjunto de tecnologías y frameworks:

*   **Java 17** (JDK de soporte de largo plazo)
*   **Spring Boot 3.5.0** (Framework backend)
*   **Spring Data JPA & Hibernate** (Persistencia y mapeo objeto-relacional)
*   **Spring Data REST** (Exposición ágil de repositorios REST)
*   **Hibernate Envers** (Historial y auditoría de entidades de base de datos)
*   **MySQL** (Base de datos relacional)
*   **Lombok** (Generación automática de getters, setters y constructores)
*   **Gradle** (Gestión de dependencias y automatización de compilación)
*   **HTML5, CSS3 y Vanilla JavaScript** (Interfaz web del cliente)

---

## ⚙️ Configuración y Base de Datos

Para levantar el proyecto en tu entorno local, sigue estas instrucciones:

1.  **Levantar MySQL Server**: Asegúrate de tener una instancia de MySQL activa (por ejemplo, con XAMPP, Laragon o Docker).
2.  **Crear la base de datos**: Ejecuta la siguiente consulta SQL en tu gestor de base de datos (MySQL Workbench, phpMyAdmin, DBeaver, etc.):
    ```sql
    CREATE DATABASE cinecartelera;
    ```
3.  **Configurar credenciales**:
    *   Abre el archivo [application.properties](file:///c:/Users/maxid/Downloads/PROYECTOCINE/src/main/resources/application.properties) ubicado en `src/main/resources/`.
    *   Configura el usuario (`spring.datasource.username`) y la contraseña (`spring.datasource.password`) correspondientes a tu instalación local de MySQL.
4.  **Generación de tablas**: Al arrancar el proyecto, Hibernate creará de forma automática toda la estructura de tablas.
5.  **Carga de datos semilla (Sembrado)**:
    *   Con las tablas ya creadas, abre el archivo [data.sql](file:///c:/Users/maxid/Downloads/PROYECTOCINE/src/main/resources/data.sql) en tu gestor MySQL.
    *   Asegúrate de ejecutarlo sobre la base de datos `cinecartelera` (puedes anteponer `USE cinecartelera;` al inicio del script) para poblar los registros iniciales de cines, películas, funciones, salas y asientos.

---

## 🚀 Cómo Correr la Aplicación

1.  Clona el repositorio.
2.  Abre el proyecto en tu IDE preferido (como IntelliJ IDEA).
3.  Ejecuta la clase de arranque: `NuestraPrimeraApiRestApplication.java` dentro de `src/main/java/com/example/demo/`.
4.  Alternativamente, puedes compilar y arrancar la aplicación desde la consola de comandos utilizando Gradle:
    ```bash
    # En Windows (CMD/PowerShell)
    .\gradlew.bat bootRun

    # En Linux / macOS
    ./gradlew bootRun
    ```
5.  **Acceso a la interfaz gráfica**:
    Abre tu navegador y entra en:
    👉 **[http://localhost:9000/index.html](http://localhost:9000/index.html)**

---

## 🗺️ Endpoints Clave de la API

Los endpoints principales expuestos por la aplicación son:

### 🎟️ Registro de Compras (`/api/compras`)
*   **`POST /api/compras`**: Registra la compra de una entrada. Valida si el asiento está libre, si ya fue comprado, y crea el cliente si no existe en la base de datos.
    *   **Cuerpo de la Petición (JSON)**:
        ```json
        {
          "nombre": "María Gómez",
          "email": "maria@example.com",
          "funcionId": 2,
          "asiento": "B5"
        }
        ```

### 📊 Reporte de Ventas (`/api/ventas`)
*   **`GET /api/ventas`**: Retorna el listado consolidado de ventas, cruzando datos de clientes, películas, salas y precios mediante un DTO.

### 🌐 Recursos de Spring Data REST (CRUD General)
*   **`GET /api/cines`** - Lista de cines.
*   **`GET /api/peliculas`** - Lista de películas asociadas.
*   **`GET /api/salas`** - Lista de salas y salas VIP.
*   **`GET /api/funciones`** - Horarios de cartelera.
*   **`GET /api/entradas`** - Gestión de asientos y precios.
*   **`GET /api/clientes`** - Lista de clientes registrados.

---

## 📖 Documentación Javadoc del Código

El código de esta API está documentado técnicamente usando **Javadoc**. Los archivos de documentación HTML autogenerados se encuentran en el directorio principal `/javadoc`.

### Ver la documentación
Para consultar la descripción detallada de clases, métodos y relaciones, abre en tu navegador el siguiente archivo:
*   [javadoc/index.html](file:///c:/Users/maxid/Downloads/PROYECTOCINE/javadoc/index.html)

### Actualizar o regenerar el Javadoc
Si haces cambios en el código y deseas reconstruir la documentación técnica:
```bash
# Windows
.\gradlew.bat javadoc

# Linux/macOS
./gradlew javadoc
```
Esto recompilará los comentarios Javadoc y actualizará las páginas web en la carpeta `/javadoc` del proyecto.