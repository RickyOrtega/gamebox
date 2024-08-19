
# GameBox

**GameBox** es un portal de juegos en línea basado en microservicios, diseñado para ofrecer una experiencia de juego en tiempo real. El proyecto utiliza tecnologías modernas como Spring Cloud, Spring Boot, React, Redis, y WebSockets para proporcionar una plataforma escalable y de alto rendimiento.

## Tabla de Contenidos

- [Características](#características)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Configuración y Ejecución](#configuración-y-ejecución)
- [Contribuciones](#contribuciones)
- [Licencia](#licencia)

## Características

- **Portal de Juegos en Línea**: Múltiples juegos en tiempo real, incluyendo juegos de cartas y más.
- **Microservicios**: Cada juego se implementa como un microservicio independiente, lo que facilita la escalabilidad y el mantenimiento.
- **Escalabilidad**: Utiliza Redis y WebSockets para manejar conexiones concurrentes de manera eficiente.
- **Gestión Centralizada de Configuraciones**: Config Server basado en Spring Cloud.
- **Descubrimiento de Servicios**: Eureka Server para el registro y descubrimiento de microservicios.
- **API Gateway**: Enrutamiento de solicitudes y balanceo de carga con Spring Cloud Gateway.

## Tecnologías Utilizadas

- **Backend**:
    - Java 17
    - Spring Boot 3.3.2
    - Spring Cloud Gateway
    - Spring Cloud Netflix Eureka
    - Spring Cloud Config Server
    - Redis

- **Frontend**:
    - React
    - Next.js
    - Material-UI (MUI)
    - WebSockets

- **DevOps**:
    - Maven
    - Docker (futuro)
    - Jenkins (futuro)

## Estructura del Proyecto

```bash
gamebox/
├── config-server/         # Servidor centralizado de configuración
├── eureka-server/         # Servidor Eureka para descubrimiento de microservicios
├── api-gateway/           # API Gateway para enrutar solicitudes
├── README.md              # Este archivo
└── pom.xml                # POM principal del proyecto
```

Cada juego en GameBox está diseñado como un microservicio independiente, lo que permite añadir nuevos juegos de manera modular sin afectar a los demás. Estos microservicios se comunican entre sí y con otros componentes de la arquitectura a través del API Gateway.

## Configuración y Ejecución

### Requisitos Previos

- **Java 17** o superior
- **Maven 3.6+**
- **Git** (para clonar el repositorio)

### Clonar el Repositorio

```bash
git clone https://github.com/RickyOrtega/gamebox.git
cd gamebox
```

### Compilar y Levantar los Servicios

1. **Levantar el Config Server**:

    ```bash
    cd config-server
    mvn clean install
    mvn spring-boot:run
    ```

2. **Levantar el Eureka Server**:

    ```bash
    cd ../eureka-server
    mvn clean install
    mvn spring-boot:run
    ```

3. **Levantar el API Gateway**:

    ```bash
    cd ../api-gateway
    mvn clean install
    mvn spring-boot:run
    ```

### Configuración del Archivo `application.yml`

Asegúrate de que los archivos de configuración `application.yml` en cada microservicio estén correctamente configurados. Por ejemplo, el Config Server debería apuntar al repositorio Git donde se encuentran los archivos de configuración centralizados.

## Contribuciones

¡Las contribuciones son bienvenidas! Si tienes una idea para mejorar **GameBox** o encuentras algún error, por favor sigue estos pasos:

1. **Fork** este repositorio.
2. Crea una nueva rama con tu característica (`git checkout -b feature/nueva-caracteristica`).
3. Realiza tus cambios y haz un commit (`git commit -m 'Añadir nueva característica'`).
4. Haz push a la rama (`git push origin feature/nueva-caracteristica`).
5. Abre un **Pull Request**.

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para obtener más información.
