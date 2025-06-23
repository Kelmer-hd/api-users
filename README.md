# API REST con Spring Boot - Proyecto Básico

Una API REST simple desarrollada con Spring Boot que demuestra los conceptos fundamentales del framework.

## Descripción

Este proyecto es una API básica que permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre una entidad `Usuario`. Es ideal como primer proyecto para aprender Spring Boot.

## Tecnologías utilizadas

- **Java 17**
- **Spring Boot 3.1.0**
- **Spring Web**
- **Spring Data JPA**
- **H2 Database** (base de datos en memoria)
- **Maven**

## Estructura del proyecto

```
src/
├── main/
│   ├── java/
│   │   └── com/ejemplo/api/
│   │       ├── ApiApplication.java
│   │       ├── controller/
│   │       │   └── UsuarioController.java
│   │       ├── model/
│   │       │   └── Usuario.java
│   │       ├── repository/
│   │       │   └── UsuarioRepository.java
│   │       └── service/
│   │           └── UsuarioService.java
│   └── resources/
│       └── application.properties
└── test/
```

## Endpoints disponibles

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/usuarios` | Obtener todos los usuarios |
| GET | `/api/usuarios/{id}` | Obtener usuario por ID |
| POST | `/api/usuarios` | Crear nuevo usuario |
| PUT | `/api/usuarios/{id}` | Actualizar usuario existente |
| DELETE | `/api/usuarios/{id}` | Eliminar usuario |

## Ejemplo de uso

### Crear un usuario
```bash
POST /api/usuarios
Content-Type: application/json

{
  "nombre": "Juan Pérez",
  "email": "juan@ejemplo.com",
  "edad": 25
}
```

### Obtener todos los usuarios
```bash
GET /api/usuarios
```

## Configuración

### Prerrequisitos
- Java 17 o superior
- Maven 3.6 o superior

### Instalación

1. Clona el repositorio:
```bash
git clone https://github.com/tu-usuario/spring-boot-api-basica.git
cd spring-boot-api-basica
```

2. Compila el proyecto:
```bash
mvn clean compile
```

3. Ejecuta la aplicación:
```bash
mvn spring-boot:run
```

La aplicación se ejecutará en `http://localhost:8080`

## Base de datos

El proyecto utiliza H2 como base de datos en memoria. Puedes acceder a la consola de H2 en:
- URL: `http://localhost:8080/h2-console`
- JDBC URL: `jdbc:h2:mem:testdb`
- Usuario: `sa`
- Contraseña: (vacía)

## Archivo de configuración

El archivo `application.properties` contiene la configuración básica:

```properties
# Puerto del servidor
server.port=8080

# Configuración de H2
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=

# Consola H2
spring.h2.console.enabled=true

# JPA/Hibernate
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
```

## Próximos pasos

Para expandir este proyecto, puedes considerar:

- Agregar validaciones con `@Valid` y Bean Validation
- Implementar manejo de excepciones personalizado
- Agregar documentación con Swagger/OpenAPI
- Integrar una base de datos real (MySQL, PostgreSQL)
- Añadir tests unitarios y de integración
- Implementar seguridad con Spring Security
