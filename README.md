
# README.md - Gestor de Reservas

## Descripción del Proyecto

El **Gestor de Reservas** es un proyecto desarrollado con **Spring Boot**, diseñado para la gestión eficiente y escalable de reservas. El enfoque principal del proyecto es implementar una estructura modular y una arquitectura en capas para facilitar el mantenimiento, la extensión y la reutilización del código.

## Estructura del Proyecto

La aplicación se basa en un diseño modular organizado en **capas**:

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
[Cliente (Frontend/Usuario Final)]
          ↓
[Controller]  <- Procesa solicitudes y envía respuestas HTTP
          ↓
[Service]     <- Contiene la lógica de negocio
          ↓
[Repository]  <- Gestiona operaciones con la base de datos
          ↓
[Base de Datos]
```

## Buenas Prácticas de Desarrollo

El desarrollo del proyecto sigue estas **mejores prácticas** para garantizar calidad y escalabilidad:

### 1. **Uso de Spring Boot y JPA**
- **Spring Boot**: Configuraciones automáticas gracias a la anotación `@SpringBootApplication`.
- **Spring Data JPA**: Framework para la manipulación eficaz de datos persistentes en la base de datos.

### 2. **Diseño RESTful**
- Implementación de endpoints siguiendo estándares REST para una comunicación uniforme y escalable.
- Uso de anotaciones clave como `@RestController` y convenciones HTTP (GET, POST, PUT, DELETE).

### 3. **Arquitectura en Capas**
- División estricta de responsabilidades por capa (Controller, Service, Repository y Entity).
- Uso del principio de **Inversión de Dependencias** con **Spring Dependency Injection** para el desacoplamiento de capas.

### 4. **Enfoque de Pruebas**
- **Pruebas Unitarias**: Creadas para validar la lógica de negocio en los servicios.
- **Pruebas de Integración**: Verifican la interacción entre controladores, servicios y repositorios.

### 5. **Gestión de Base de Datos**
- Implementación de **JPA** con entidades que reflejan la estructura de tablas relacionales.
- Bases de datos compatibles: H2 (desarrollo) y motores como **MySQL** o **PostgreSQL** (entornos productivos).

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

El proyecto se mantiene utilizando :
- **Control de Versiones**: Se utiliza **Git** para control de versiones junto con herramientas como **GitHub** o **GitLab**.

---

## Contribuciones
Las contribuciones están abiertas y se manejan a través de pull requests. Por favor, asegúrate de seguir el estándar de código y aportar con pruebas en los módulos modificados.
