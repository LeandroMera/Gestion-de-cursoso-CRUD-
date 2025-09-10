🖥️ Proyecto: Gestión de Productos y Cursos
Descripción

Este proyecto combina dos módulos principales:

CRUD de Productos (REST API): Permite gestionar productos mediante endpoints REST.

Gestión de Cursos (Frontend + CRUD): Permite gestionar cursos con interfaz web, incluyendo búsqueda, paginación y exportación a PDF y Excel.

Está desarrollado en Spring Boot, usando Spring Data JPA, Thymeleaf, Bootstrap y FontAwesome.

Tecnologías

Java 17+

Spring Boot

Spring Data JPA / Hibernate

Thymeleaf

Bootstrap 4.6

FontAwesome

iText (PDF)

Apache POI (Excel)

Base de datos H2 o MySQL

1. CRUD de Productos

Entidad Product:

id: Identificador único

name: Nombre del producto (único)

price: Precio del producto

fecha: Fecha de creación

antiguedad: Calculada a partir de la fecha

Repositorio ProductRepository:

CRUD básico + búsqueda de productos por nombre

Servicio ProductService:

Crear o actualizar productos verificando duplicados

Listar todos los productos

Eliminar productos por ID

Controlador ProductController:

Método	Endpoint	Función
GET	/api/v1/productos	Listar productos
POST	/api/v1/productos	Crear producto
PUT	/api/v1/productos	Actualizar producto
DELETE	/api/v1/productos/{id}	Eliminar producto por ID
2. Gestión de Cursos

Entidad Curso:

id: Identificador único

titulo: Nombre del curso

descripcion: Descripción

nivel: Nivel del curso

isPublicado: Estado de publicación

Controlador CursoController:

Listar cursos con búsqueda y paginación

Crear y editar cursos

Eliminar cursos

Exportar cursos a PDF y Excel

Repositorio CursoRepository:

CRUD básico + búsqueda paginada por título

Frontend con Thymeleaf:

Templates para listar, agregar y editar cursos

Fragmentos reutilizables (header, paginación)

Bootstrap y CSS personalizado para diseño moderno

Scripts para búsqueda, paginación y botones de acción

3. Funcionalidades

CRUD completo de productos y cursos

Mensajes de éxito/error para interacción con el usuario

Búsqueda y paginación de cursos

Exportación de cursos a PDF y Excel

Interfaz moderna con Bootstrap y FontAwesome

4. Instalación y Ejecución

Clonar el repositorio:

git clone https://github.com/tu-usuario/gestor-productos-cursos.git
cd gestor-productos-cursos


Configurar la base de datos en application.properties:

spring.datasource.url=jdbc:mysql://localhost:3306/tu_db
spring.datasource.username=root
spring.datasource.password=tu_password
spring.jpa.hibernate.ddl-auto=update


Ejecutar la aplicación:

./mvnw spring-boot:run


Acceder a la aplicación:

CRUD de Productos (API REST): http://localhost:8080/api/v1/productos

Gestión de Cursos (Frontend): http://localhost:8080/cursos

