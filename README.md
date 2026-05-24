
---

## ✨ Características

### Backend (dev1) - API REST
- ✅ **Crear tareas** - Endpoint POST `/api/tasks`
- ✅ **Listar tareas** - Endpoint GET `/api/tasks`
- ✅ **Actualizar tareas** - Endpoint PUT `/api/tasks/{id}`
- ✅ **Eliminar tareas** - Endpoint DELETE `/api/tasks/{id}`

### Frontend (dev2) - Interfaz Angular
- ✅ **Formulario de creación** - Crear nuevas tareas
- ✅ **Lista de tareas** - Visualizar todas las tareas con filtros
- ✅ **Edición de tareas** - Modificar tareas existentes
- ✅ **Eliminación de tareas** - Eliminar tareas del sistema

---

## 🛠️ Tecnologías Utilizadas

| Componente | Tecnología | Versión |
|----------|-----------|---------|
| Backend | Spring Boot | 3.x |
| Base de Datos | SQL Server | 2022 |
| Frontend | Angular | 16+ |
| Build Tool | Maven | 3.9+ |
| Lenguaje | Java | 17 |

---

## 📁 Estructura del Proyecto

```
gitFlow251s3_t06_be/
├── src/
│   ├── main/
│   │   ├── java/vallegrande/edu/pe/gitFlow251s3_t09_be/
│   │   │   ├── controller/          # Controllers REST
│   │   │   ├── model/               # Entidades
│   │   │   ├── repository/          # Acceso a datos
│   │   │   ├── service/             # Lógica de negocios
│   │   │   ├── exception/           # Manejo de excepciones
│   │   │   └── config/              # Configuraciones (CORS, etc)
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/                    # Tests unitarios
├── pom.xml                          # Dependencias Maven
└── README.md                        # Este archivo
```

## 🚀 Requisitos Previos

- **Java JDK 17** o superior
- **Maven 3.9+**
- **SQL Server 2022** (o Docker)
- **Angular CLI** (para frontend)
- **Node.js 16+** (para frontend)



## ⚙️ Configuración

### 1. Base de Datos
```bash
# Con Docker
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Password123@" \
  -p 1433:1433 --name sqlserver -d \
  mcr.microsoft.com/mssql/server:2022-latest
```

### 2. Backend - Variables de Entorno
Editar `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=task_manager
spring.datasource.username=sa
spring.datasource.password=Password123@
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

## 📦 Instalación y Ejecución

### Backend
```bash
# Compilar el proyecto
mvn clean install

# Ejecutar la aplicación
mvn spring-boot:run

# La API estará disponible en: http://localhost:8080/api/tasks
```

### Frontend
```bash
# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
ng serve

# Acceder en: http://localhost:4200
```

---

## 🔄 Gitflow y Conventional Commits

Este proyecto implementa:

- **Ramas principales:**
  - `main` - Producción
  - `develop` - Integración

- **Ramas de features:**
  - `feature/sp8-us1_createTasks` - Crear tareas (dev1)
  - `feature/sp8-us2_listTasks` - Listar tareas (dev2)
  - `feature/sp8-us5_updateTasks` - Actualizar tareas (dev1)
  - `feature/sp8-us6_eliminateTasks` - Eliminar tareas (dev2)

- **Commits con estándar Conventional:**
  - `feat(backend): agregar endpoint para crear tareas`
  - `fix(backend): corregir validación de estado`
  - `style(frontend): ajustar estilos de formulario`


## 📝 Endpoints de la API

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/tasks` | Obtener todas las tareas |
| POST | `/api/tasks` | Crear nueva tarea |
| PUT | `/api/tasks/{id}` | Actualizar tarea |
| DELETE | `/api/tasks/{id}` | Eliminar tarea |

### Ejemplo de Solicitud
```bash
# Crear tarea
curl -X POST http://localhost:8080/api/tasks \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Mi primera tarea",
    "description": "Descripción de la tarea",
    "status": "pendiente"
  }'
```
## ✅ Testing

```bash
# Ejecutar tests unitarios
mvn test

# Con cobertura
mvn test jacoco:report
```

---

## 👥 Equipo de Desarrollo

- **dev1** - Backend (Endpoints CRUD)
- **dev2** - Frontend (Interfaz de usuario)

---

## 📚 Recursos Adicionales

- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [Angular Documentation](https://angular.io/docs)
- [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Conventional Commits](https://www.conventionalcommits.org/)

---
