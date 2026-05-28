🎬 CineProyecto — API REST
API REST desarrollada con Spring Boot para la gestión de una cartelera de cine. Permite consultar cines, películas, funciones, entradas y realizar compras de tickets.
🛠️ Tecnologías utilizadas

Java 17
Spring Boot 3.5
Spring Data JPA / Hibernate
Spring Data REST
MySQL
Lombok
Gradle

📋 Descripción
El sistema permite administrar la cartelera de uno o varios cines. Incluye gestión de películas por género, funciones con horarios, salas (incluyendo VIP), entradas con asientos y precios, y un flujo completo de compra de tickets para clientes.
⚙️ Configuración de la base de datos

Tener MySQL instalado y corriendo (por ejemplo con XAMPP)
Abrir MySQL Workbench y ejecutar:

sql   CREATE DATABASE cinecartelera;

Arrancar el proyecto desde IntelliJ — esto crea las tablas automáticamente
Una vez iniciado, abrir el archivo src/main/resources/data.sql en Workbench, agregar USE cinecartelera; al inicio y ejecutarlo con ⚡

🚀 Cómo correr el proyecto

Clonar el repositorio
Abrir con IntelliJ IDEA
Verificar credenciales de MySQL en src/main/resources/application.properties
Ejecutar NuestraPrimeraApiRestApplication.java

🌐 Interfaz web
Accedé a la interfaz visual desde:
👉 http://localhost:9000/index.html