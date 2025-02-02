# Gestor de Reservas - Proyecto en Spring Boot

## Descripción del Proyecto

El **Gestor de Reservas** es un proyecto basado en **Spring Boot** diseñado para ofrecer una solución escalable y funcional para la gestión de reservas. Sigue una arquitectura en capas que facilita la separación de responsabilidades, la escalabilidad y el mantenimiento del proyecto.

## Estructura del Proyecto

La estructura de la aplicación se organiza en **capas** según los principios del diseño modular:

### 1. Capa de Presentación (`Controller`)
- **Propósito**: Esta capa gestiona la interacción con el cliente o interfaz de usuario. Su principal responsabilidad es recibir las solicitudes HTTP, interpretar las peticiones y devolver las respuestas HTTP.
- **Ubicación**: `com.gestor_reserva.gestor.controller`
- **Componentes**:
  - Controladores REST para manejar rutas y exponer endpoints.
  - Validación de datos de entrada.

---

### 2. Capa de Servicio (`Service`)
- **Propósito**: Implementa la lógica de negocio de la aplicación. Esta capa actúa como intermediaria entre los controladores y el repositorio, asegurando la separación de lógica compleja del resto de las capas.
- **Ubicación**: `com.gestor_reserva.gestor.service`
- **Componentes**:
  - Métodos dedicados a procesar la lógica de cada funcionalidad.
  - Servicios que abstraen la lógica de negocio según las necesidades de la aplicación.

---

### 3. Capa de Persistencia (`Repository`)
- **Propósito**: Maneja la interacción con la base de datos. Utiliza Spring Data JPA para operar con las entidades de manera eficiente, desde consultas hasta manipulaciones.
- **Ubicación**: `com.gestor_reserva.gestor.repository`
- **Componentes**:
  - Interfaces marcadas con anotación `@Repository`.
  - Implementación de consultas básicas o personalizadas mediante Spring Data JPA.

---

### 4. Capa de Modelo/Dominio (`Entity`)
- **Propósito**: Contiene la representación de las entidades principales utilizadas en la aplicación. Corresponde al modelo relacional de la base de datos.
- **Ubicación**: `com.gestor_reserva.gestor.entity`
- **Componentes**:
  - Clases de entidades con anotaciones de JPA (`@Entity`, `@Table`, etc.).
  - Relación entre entidades (por ejemplo, `@OneToMany`, `@ManyToOne`).

---

### Esquema General de la Arquitectura en Capas

```plaintext
[Cliente/Front-End]
      ↓
[Controller]  <- Maneja la solicitud del cliente
      ↓
[Service]     <- Aplica lógica de negocio
      ↓
[Repository]  <- Interactúa con la base de datos
      ↓
[Base de Datos]
```

## Enfoque de Desarrollo

El proyecto se está desarrollando en base a las siguientes buenas prácticas:

### 1. **Spring Boot y JPA**
- Uso de Spring Boot con configuraciones automáticas mediante la anotación `@SpringBootApplication`.
- Uso de **Spring Data JPA** para operaciones en la base de datos.

### 2. **Estilo REST**
- Diseño de endpoints RESTful que siguen estándares HTTP para la comunicación con el cliente.
- Uso de anotaciones como `@RestController` para definir controladores REST.

### 3. **Desarrollo en Capas**
- Cada capa tiene una responsabilidad clara y específica.
- Las capas están desacopladas entre sí, utilizando estándares como la **Inyección de Dependencias (Dependency Injection)** de Spring para comunicación entre capas.

### 4. **Pruebas**
- Pruebas unitarias se desarrollan para el código de la lógica de negocio (capa `Service`).
- Pruebas de integración para verificar el correcto comportamiento de los endpoints.

### 5. **Base de Datos**
- Uso de entidades mapeadas en JPA para representar las tablas.
- Posibilidad de usar H2 (base de datos en memoria) para entornos de desarrollo y bases de datos relacionales como **MySQL** o **PostgreSQL** para entornos productivos.

---

## Instalación y Ejecución

1. **Pre-requisitos**:
   - JDK 17 o superior.
   - Maven 3.x.
   - Base de datos (opcional para desarrollo, H2 incluida por defecto).

2. **Pasos para ejecutar el proyecto**:
   - Clona el repositorio.
   - Configura las propiedades de la base de datos en `application.properties` (o `application.yml`).
   - Compila el proyecto con Maven:
     ```bash
     mvn clean install
     ```
   - Ejecuta la aplicación:
     ```bash
     java -jar target/nombre-del-jar.jar
     ```

---

## Aporte y Desarrollo

El proyecto se mantiene utilizando metodologías ágiles:
- **Scrum**: Sprints para planear y gestionar el desarrollo.
- **Control de Versiones**: Se utiliza **Git** para control de versiones junto con herramientas como **GitHub** o **GitLab**.

---

## Contribuciones
Las contribuciones están abiertas y se manejan a través de pull requests. Por favor, asegúrate de seguir el estándar de código y aportar con pruebas en los módulos modificados.
