# Capítulo V: Product Implementation

## 5.1. Software Configuration Management

La gestión de la configuración del software es un elemento crítico para asegurar la calidad, trazabilidad y consistencia durante todo el ciclo de desarrollo de Hairy Paws. En esta sección detallamos las herramientas, configuraciones y convenciones utilizadas para mantener un desarrollo organizado y eficiente.

### 5.1.1. Software Development Environment Configuration

Para garantizar la consistencia en el entorno de desarrollo entre todos los miembros del equipo, hemos establecido la siguiente configuración de herramientas:

**Gestión del Proyecto**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Trello | Gestión ágil del proyecto, Sprints y Product Backlog | https://trello.com |
| Miro | Diseño de diagramas colaborativos | https://miro.com |

**Diseño UX/UI**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Figma | Diseño de wireframes, mockups y prototipos | https://www.figma.com |
| Canva | Diseño alternativo para prototipos de alta fidelidad | https://www.canva.com |


**Desarrollo Frontend Web**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Node.js v22.14.0 | Entorno de ejecución JavaScript | https://nodejs.org |
| Angular CLI v19.0.0 | Framework para desarrollo web frontend | `npm install -g @angular/cli@19.0.0` |
| PrimeNG v19.0.10 | Biblioteca de componentes UI para Angular | `npm install primeng@19.0.10` |
| PrimeFlex v4.0.0 | Framework CSS responsivo | `npm install primeflex@4.0.0` |
| PrimeIcons v7.0.0 | Set de iconos | `npm install primeicons@v7.0.0` |
| WebStorm | IDE para desarrollo | https://www.jetbrains.com/es-es/webstorm/ |

**Desarrollo Frontend Mobile**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Flutter SDK v3.29.2 | Framework para desarrollo móvil multiplataforma | https://flutter.dev |
| Android Studio | IDE para desarrollo Android | https://developer.android.com/studio |
| Visual Studio Code + Flutter Extension | IDE alternativo para Flutter | https://code.visualstudio.com |

**Desarrollo Backend**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Node.js v22.14.0 | Entorno de ejecución JavaScript | https://nodejs.org |
| NestJS CLI v11.0.0 | Framework para desarrollo backend | `npm install -g @nestjs/cli@11.0.0` |
| MySQL v8.0 | Sistema de gestión de base de datos | https://www.mysql.com |
| MySQL Workbench | Herramienta visual para diseño de base de datos | https://www.mysql.com/products/workbench |
| Postman | Testing de APIs | https://www.postman.com |

**Testing**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Cypress | Framework de E2E testing | `npm install --save-dev cypress` |

**Despliegue**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Render | Plataforma de hosting y despliegue | https://render.com |

**Documentación**

| Software | Propósito | URL/Ruta de Descarga |
|----------|-----------|----------------------|
| Swagger/OpenAPI | Documentación de API | Integrado en NestJS |
| Markdown | Documentación de proyecto | Soportado nativamente en GitHub |

Cada miembro del equipo debe asegurarse de tener instaladas estas herramientas en las versiones especificadas para garantizar la compatibilidad y evitar problemas de integración.

### 5.1.2. Source Code Management

Para la gestión del código fuente utilizamos GitHub como plataforma principal, aplicando GitFlow como workflow de control de versiones. A continuación, se detallan los repositorios y las convenciones aplicadas.

**Repositorios**

| Producto | Repositorio URL |
|----------|-----------------|
| Landing Page | https://github.com/hairy-paws-4436/landing-page.git |
| Frontend Web Application | https://github.com/hairy-paws-4436/web-app.git |
| Mobile Applications | https://github.com/hairy-paws-4436/mobile-app.git |
| Backend API | https://github.com/hairy-paws-4436/backend.git |

**Implementación de GitFlow**

Nuestro workflow de GitFlow incluye las siguientes ramas:

1. **main**: Rama principal que contiene código de producción estable. Solo se fusiona mediante pull requests de `release` o `hotfix`.

2. **develop**: Rama de desarrollo donde se integran las características completadas. Es la base para las ramas de `feature`.

3. **feature/**: Ramas para desarrollar nuevas funcionalidades. Convención de nomenclatura:
   - `feature/[id-user-story]-[breve-descripcion]`
   - Ejemplo: `feature/US15-evaluation-requests`

4. **release/**: Ramas para preparar releases. Convención de nomenclatura:
   - `release/v[major].[minor].[patch]`
   - Ejemplo: `release/v1.0.0`

5. **hotfix/**: Ramas para correcciones urgentes en producción. Convención de nomenclatura:
   - `hotfix/v[major].[minor].[patch+1]`
   - Ejemplo: `hotfix/v1.0.1`


**Conventional Commits**

Seguimos la especificación de Conventional Commits para los mensajes de commit, facilitando la generación automática de changelogs y la comprensión del propósito de cada cambio:

- `feat`: Nueva funcionalidad
- `fix`: Corrección de error
- `docs`: Cambios en documentación
- `style`: Cambios que no afectan el significado del código (formato, espacios en blanco)
- `refactor`: Cambio de código que no corrige un error ni añade una característica
- `test`: Adición o corrección de pruebas
- `chore`: Cambios en el proceso de build o herramientas auxiliares

Ejemplo:
```
feat(adoption): implement request form validation

Add client-side validation to adoption request form to ensure all required fields are completed and properly formatted before submission.

Closes #42
```

### 5.1.3. Source Code Style Guide & Conventions

Hemos adoptado guías de estilo y convenciones estandarizadas para cada lenguaje y tecnología utilizada en el proyecto. Esto garantiza la coherencia y legibilidad del código a lo largo de toda la base de código.

**HTML & CSS**

Seguimos las guías de estilo de Google para HTML/CSS:

- Uso de 2 espacios para indentación
- Nombres de clases en lowercase con guiones (kebab-case): `adoption-form`
- Uso de comillas dobles para atributos HTML
- Priorización de clases sobre IDs
- Uso de HTML5 semántico (`<header>`, `<footer>`, `<main>`, etc.)
- Declaración del charset UTF-8

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hairy Paws</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header class="site-header">
    <nav class="main-navigation">
      <!-- Navigation content -->
    </nav>
  </header>
  <main class="main-content">
    <!-- Main content -->
  </main>
</body>
</html>
```

**TypeScript/JavaScript (Angular & NestJS)**

Seguimos las convenciones oficiales de Angular y las guías de estilo de Google para JavaScript:

- Nombres de variables y funciones en camelCase: `adoptionService`
- Nombres de clases en PascalCase: `AdoptionService`
- Nombres de interfaces en PascalCase con prefijo 'I': `IPetProfile`
- Nombres de constantes en UPPER_SNAKE_CASE: `MAX_UPLOAD_SIZE`
- Uso de tipos estrictos en TypeScript
- Evitar el uso de `any`
- Documentación con JSDoc para funciones y clases importantes

```typescript
/**
 * Service that handles pet adoption requests
 */
@Injectable({
  providedIn: 'root'
})
export class AdoptionService {
  private readonly API_URL = 'api/adoptions';
  
  constructor(private http: HttpClient) {}
  
  /**
   * Submit a new adoption request
   * @param adoptionRequest The adoption request data
   * @returns An observable with the created adoption request
   */
  submitRequest(adoptionRequest: IAdoptionRequest): Observable<IAdoptionRequest> {
    return this.http.post<IAdoptionRequest>(this.API_URL, adoptionRequest);
  }
}
```

**Dart (Flutter)**

Seguimos las convenciones oficiales de Dart y Flutter:

- Nombres de variables y funciones en camelCase: `petDetailScreen`
- Nombres de clases en PascalCase: `PetDetailScreen`
- Nombres de constantes en lowerCamelCase: `maxUploadSize`
- Evitar abreviaturas poco claras
- Organizar el código en carpetas por funcionalidad
- Comentarios dartdoc para clases y métodos públicos

```dart
/// A screen that displays detailed information about a pet
class PetDetailScreen extends StatefulWidget {
  /// The unique identifier of the pet
  final String petId;
  
  /// Creates a pet detail screen
  const PetDetailScreen({Key? key, required this.petId}) : super(key: key);
  
  @override
  _PetDetailScreenState createState() => _PetDetailScreenState();
}
```

**Gherkin (Archivos .feature)**

Seguimos las convenciones de Gherkin para especificaciones legibles:

- Escenarios enfocados en comportamiento, no en implementación
- Uso de lenguaje natural y orientado al negocio
- Etiquetas para categorizar escenarios
- Pasos claros y reutilizables
- Datos de ejemplo para escenarios outline

```gherkin
Feature: Pet Adoption Request

  @smoke @adoption
  Scenario: Submit valid adoption request
    Given I am logged in as an "adopter"
    And I am viewing the details of a pet with status "available"
    When I fill the adoption form with valid information
    And I submit the adoption request
    Then I should see a confirmation message
    And the pet status should change to "pending"
    
  @adoption
  Scenario Outline: Form validation for required fields
    Given I am logged in as an "adopter"
    And I am viewing the details of a pet with status "available"
    When I fill the adoption form without "<field>"
    And I try to submit the form
    Then I should see an error message for the missing field
    
    Examples:
      | field            |
      | phone            |
      | livingConditions |
      | previousPets     |
```

**Base de Datos (MySQL)**

Convenciones para diseño y consultas SQL:

- Nombres de tablas en plural y snake_case: `adoption_requests`
- Nombres de columnas en snake_case: `created_at`
- Claves primarias nombradas como `id`
- Claves foráneas con sufijo `_id`: `pet_id`
- Uso de índices para campos frecuentemente consultados
- Timestamps para auditoría: `created_at`, `updated_at`
- Consultas SQL formateadas con indentación clara

```sql
CREATE TABLE adoption_requests (
  id VARCHAR(36) PRIMARY KEY,
  pet_id VARCHAR(36) NOT NULL,
  adopter_id VARCHAR(36) NOT NULL,
  status ENUM('pending', 'approved', 'rejected') NOT NULL DEFAULT 'pending',
  contact_phone VARCHAR(15) NOT NULL,
  living_conditions TEXT NOT NULL,
  has_previous_pets BOOLEAN NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  FOREIGN KEY (pet_id) REFERENCES pets(id),
  FOREIGN KEY (adopter_id) REFERENCES users(id)
);
```

### 5.1.4. Software Deployment Configuration

La configuración de despliegue de nuestra solución está diseñada para facilitar la integración continua y el despliegue continuo (CI/CD) de todos los componentes de la aplicación.

**Landing Page**

- **Plataforma**: Render
- **Tipo de servicio**: Static Site
- **Repositorio fuente**: `hairy-paws-4436/landing-page`
- **Rama de producción**: `main`
- **Comando de construcción**: `npm run build`
- **Directorio de publicación**: `dist`
- **Configuración de dominio**: `https://hairy-paws-landing-page.onrender.com`

**Frontend Web Application**

- **Plataforma**: Render
- **Tipo de servicio**: Web Service
- **Repositorio fuente**: `hairy-paws-4436/web-app`
- **Rama de producción**: `main`
- **Comando de construcción**: `npm run build:prod`
- **Comando de inicio**: `npm run start:prod`
- **Directorio de publicación**: `dist`
- **Variables de entorno**:
  - `API_URL`: [URL del fronted desplegado]
  - `NODE_ENV`: `production`

**Mobile Applications**

- **Android**:
  - **Plataforma**: Google Play Store
  - **Proceso de compilación**: Flutter Build APK
  - **Comando**: `flutter build appbundle --release`
  - **Automatización**: GitHub Actions para builds automáticos

- **iOS**:
  - **Plataforma**: Apple App Store
  - **Proceso de compilación**: Flutter Build iOS
  - **Comando**: `flutter build ios --release`
  - **Automatización**: GitHub Actions para builds automáticos (requiere macOS runner)

**Backend API**

- **Plataforma**: Render
- **Tipo de servicio**: Web Service
- **Repositorio fuente**: `hairy-paws-4436/backend`
- **Rama de producción**: `main`
- **Runtime**: Node.js
- **Comando de construcción**: `npm run build`
- **Comando de inicio**: `npm run start:prod`
- **Variables de entorno**:
  - `DATABASE_URL`: Conexión a la base de datos MySQL
  - `JWT_SECRET`: Secreto para autenticación
  - `PORT`: Puerto de ejecución del servicio
  - `NODE_ENV`: `production`

**Base de Datos**

- **Plataforma**: MySQL en Render
- **Tipo**: MySQL
- **Versión**: 8.0
- **Configuración de respaldo**: Diario, retención de 7 días
- **Variables de conexión**:
  - `MYSQL_HOST`
  - `MYSQL_USERNAME`
  - `MYSQL_PASSWORD`
  - `MYSQL_DATABASE`
  - `MYSQL_PORT`

## 5.2. Product Implementation & Deployment

Esta sección detalla la implementación y despliegue de los diversos componentes de nuestra solución Hairy Paws, desde el landing page hasta las aplicaciones móviles y el backend API.

### 5.2.1. Sprint Backlogs

#### Sprint 1

**Sprint Planning 1**

| Sprint Planning Background | |
|---------------------------|---------------------------|
| Date | 2025-04-06 20:00 PM |
| Location | Sala de reuniones virtual - Google Meet |
| Prepared By | Randy Becker Rengifo Mirabal |
| Attendees | Aldo Alberto Baldeon Fabian, Max Anthony Paitan Pumacahua, Randy Becker Rengifo Mirabal, Fiorella Angela Vilca Valverde |
| Sprint 0 Review Summary | N/A - Primer Sprint |
| Sprint 0 Retrospective Summary | N/A - Primer Sprint |

**Sprint 1 Goal & User Stories**

| Sprint 1 Goal | Desarrollar el Landing Page y las bases fundamentales del sistema: registro e inicio de sesión |
|---------------|---------------------------------------------------------------------------------------------|
| Sprint 1 Velocity | 21 Story Points |
| Sum of Story Points | 21 Story Points |

**Sprint Backlog 1**


| User Story | Work-Item / Task | | | | | | |
|-----------|-----------------|-----------------|-----------------|-----------------|-----------------|-----------------|-----------------|
| **ID** | **Title** | **ID** | **Title** | **Description** |**Estimation (Hours)** | **Assigned To** | **Status** |
| US24 | Vista principal landing page | TK01 | Diseñar estructura HTML/CSS en Angular | Crear estructura base del landing page con HTML5 semántico y estilos CSS | 8 | Randy Rengifo | Done |
||| TK02 | Implementar secciones principales | Desarrollar hero section, secciones de beneficios y cómo funciona | 10 | Randy Rengifo | Done |
||| TK03 | Hacer responsive | Adaptar la página para diferentes dispositivos | 6 | Randy Rengifo | Done |
| US01 | Registro de usuario | TK06 | Diseñar formulario de registro | Crear UI para formulario de registro | 4 | Randy Rengifo | Done |
||| TK07 | Implementar frontend de registro | Desarrollar componente Angular para registro | 8 | Randy Rengifo | Done |
||| TK08 | Implementar API de registro | Crear endpoint de registro en NestJS | 10 | Randy Rengifo | Done |
||| TK09 | Implementar validaciones | Agregar validaciones de formulario | 6 | Randy Rengifo | Done |
| US02 | Inicio de sesión | TK10 | Diseñar página de login | Crear UI para formulario de login | 4 | Randy Rengifo | Done |
||| TK11 | Implementar frontend de login | Desarrollar componente Angular para login | 6 | Randy Rengifo | Done |
||| TK12 | Implementar API de autenticación | Crear sistema de autenticación con JWT | 10 | Randy Rengifo | Done |
||| TK13 | Implementar guard de rutas | Agregar protección de rutas basada en autenticación | 4 | Randy Rengifo | Done |

#### Sprint 2

**Sprint Planning 2**

| Sprint Planning Background | |
|---------------------------|---------------------------|
| Date | 2025-04-13 20:00 PM |
| Location | Sala de reuniones virtual - Google Meet |
| Prepared By | Randy Becker Rengifo Mirabal |
| Attendees | Aldo Alberto Baldeon Fabian, Max Anthony Paitan Pumacahua, Randy Becker Rengifo Mirabal, Fiorella Angela Vilca Valverde |
| Sprint 1 Review Summary | Se completó exitosamente el Landing Page y la funcionalidad de registro e inicio de sesión. El Product Owner destacó la calidad visual del landing y la fluidez del proceso de autenticación. |
| Sprint 1 Retrospective Summary | El equipo identificó que la estimación de tareas fue optimista en algunos casos. Se acordó mejorar la comunicación entre frontend y backend mediante una mejor documentación de APIs. También se decidió implementar un enfoque más incremental para las características complejas. |

**Sprint 2 Goal & User Stories**

| Sprint 2 Goal | Implementar todas las funcionalidades core de la aplicación: adopción, donaciones y gestión de eventos |
|---------------|------------------------------------------------------------------------------|
| Sprint 2 Velocity | 42 Story Points |
| Sum of Story Points | 42 Story Points |

**Sprint Backlog 2**

| User Story | Work-Item / Task | | | | | | |
|-----------|-----------------|-----------------|-----------------|-----------------|-----------------|-----------------|-----------------|
| **ID** | **Title** | **ID** | **Title** | **Description** |**Estimation (Hours)** | **Assigned To** | **Status** |
| US10 | Búsqueda avanzada de mascotas | TK14 | Diseñar interfaz de búsqueda | Crear UI para filtros y resultados | 8 | Fiorella Vilca | Done |
||| TK15 | Implementar componentes de filtro | Desarrollar componentes Angular para filtros por especie, tamaño, edad y ubicación | 10 | Max Paitan | Done |
||| TK16 | Implementar API de búsqueda | Crear endpoints de búsqueda con filtros en NestJS | 12 | Aldo Baldeon | Done |
||| TK17 | Implementar paginación | Añadir paginación a resultados de búsqueda | 6 | Max Paitan | Done |
| US06 | Creación de perfil de mascota | TK18 | Diseñar formulario de mascota | Crear UI para formulario de creación de mascota | 6 | Fiorella Vilca | Done |
||| TK19 | Implementar carga de imágenes | Desarrollar componente para carga múltiple de imágenes | 8 | Randy Rengifo | Done |
||| TK20 | Implementar frontend de creación | Desarrollar componente Angular para creación de perfil | 10 | Max Paitan | Done |
||| TK21 | Implementar API de mascotas | Crear endpoints para gestión de mascotas | 12 | Aldo Baldeon | Done |
||| TK22 | Implementar validaciones | Agregar validaciones de formulario para campos obligatorios | 6 | Randy Rengifo | Done |
| US11 | Visualización detallada | TK23 | Diseñar página de detalle | Crear UI para vista detallada de mascota | 6 | Fiorella Vilca | Done |
||| TK24 | Implementar galería de imágenes | Desarrollar componente de galería con PrimeNG | 8 | Randy Rengifo | Done |
||| TK25 | Implementar frontend de detalle | Desarrollar componente Angular para visualización | 8 | Max Paitan | Done |
||| TK26 | Implementar API de detalle | Crear endpoint para obtener detalles completos | 6 | Aldo Baldeon | Done |
| US13 | Solicitud de adopción | TK27 | Diseñar formulario de solicitud | Crear UI para formulario de solicitud de adopción | 5 | Fiorella Vilca | Done |
||| TK28 | Implementar frontend de solicitud | Desarrollar componente Angular con validaciones | 8 | Randy Rengifo | Done |
||| TK29 | Implementar API de solicitudes | Crear endpoints para gestión de solicitudes | 10 | Aldo Baldeon | Done |
||| TK30 | Implementar notificaciones | Añadir sistema de notificaciones para adoptantes y dueños | 8 | Max Paitan | Done |
| US07 | Edición de perfil de mascota | TK31 | Diseñar interfaz de edición | Adaptar el formulario de creación para edición | 4 | Fiorella Vilca | Done |
||| TK32 | Implementar frontend de edición | Desarrollar componente Angular para modificación | 6 | Randy Rengifo | Done |
||| TK33 | Implementar API de actualización | Crear endpoint para actualizar datos de mascota | 5 | Aldo Baldeon | Done |
||| TK34 | Añadir validaciones específicas | Implementar reglas de validación para actualización | 4 | Max Paitan | Done |
| US20 | Registro de donación | TK35 | Diseñar interfaz de donación | Crear UI para registro de donaciones | 6 | Fiorella Vilca | Done |
||| TK36 | Implementar frontend de donación | Desarrollar componente para selección de items y cantidades | 8 | Randy Rengifo | Done |
||| TK37 | Implementar API de donaciones | Crear endpoints para registro de donaciones | 8 | Aldo Baldeon | Done |
||| TK38 | Implementar notificaciones a ONGs | Desarrollar sistema de alertas para nuevas donaciones | 6 | Max Paitan | Done |
| US21 | Confirmación de donación | TK39 | Diseñar interfaz de confirmación | Crear UI para gestión y confirmación de donaciones | 5 | Fiorella Vilca | Done |
||| TK40 | Implementar frontend de confirmación | Desarrollar componente para ONGs | 7 | Randy Rengifo | Done |
||| TK41 | Implementar API de confirmación | Crear endpoint para actualizar estado de donaciones | 6 | Aldo Baldeon | Done |
||| TK42 | Implementar notificaciones a donantes | Desarrollar sistema de agradecimiento automático | 5 | Max Paitan | Done |
| US22 | Publicación de eventos | TK43 | Diseñar interfaz de eventos | Crear UI para creación y gestión de eventos | 6 | Fiorella Vilca | Done |
||| TK44 | Implementar frontend de eventos | Desarrollar componente para ONGs | 8 | Randy Rengifo | Done |
||| TK45 | Implementar API de eventos | Crear endpoints para gestión de eventos | 8 | Aldo Baldeon | Done |
||| TK46 | Implementar calendario | Desarrollar vista de calendario y listado de eventos | 7 | Max Paitan | Done |
| US23 | Registro en eventos | TK47 | Diseñar interfaz de registro | Crear UI para inscripción en eventos | 5 | Fiorella Vilca | Done |
||| TK48 | Implementar frontend de inscripción | Desarrollar componente para usuarios | 7 | Randy Rengifo | Done |
||| TK49 | Implementar API de inscripción | Crear endpoints para gestión de participantes | 6 | Aldo Baldeon | Done |
||| TK50 | Implementar notificaciones y recordatorios | Desarrollar sistema de alertas para eventos próximos | 6 | Max Paitan | Done |
| US09 | Marcado de mascota como adoptada | TK51 | Diseñar interfaz de cambio de estado | Crear UI para actualizar estado de mascotas | 3 | Fiorella Vilca | Done |
||| TK52 | Implementar frontend de actualización | Desarrollar componente para cambio de estado | 5 | Randy Rengifo | Done |
||| TK53 | Implementar API de estado | Crear endpoint para actualizar estado de mascota | 4 | Aldo Baldeon | Done |
||| TK54 | Actualizar listados y búsqueda | Modificar componentes para filtrar mascotas adoptadas | 3 | Max Paitan | Done |
| US14 | Programación de visita | TK55 | Diseñar interfaz de programación | Crear UI para calendario y selección de fechas | 6 | Fiorella Vilca | Done |
||| TK56 | Implementar frontend de calendario | Desarrollar componente de programación | 8 | Randy Rengifo | Done |
||| TK57 | Implementar API de visitas | Crear endpoints para gestión de visitas | 7 | Aldo Baldeon | Done |
||| TK58 | Implementar notificaciones y recordatorios | Desarrollar sistema de alertas para visitas | 6 | Max Paitan | Done |

### 5.2.2. Implemented Landing Page Evidence

La implementación del Landing Page se realizó siguiendo las mejores prácticas de desarrollo web, con enfoque en experiencia de usuario y diseño responsivo.

**Capturas de la Implementación**

[![image.png](https://i.postimg.cc/c1jSz000/image.png)](https://postimg.cc/14p2nx8j)
[![image.png](https://i.postimg.cc/4418K12M/image.png)](https://postimg.cc/nMCKgqJY)
[![image.png](https://i.postimg.cc/4nkNRgCL/image.png)](https://postimg.cc/FkpQ0wH3)
[![image.png](https://i.postimg.cc/kXKW6M55/image.png)](https://postimg.cc/bsYZ4hkX)
[![image.png](https://i.postimg.cc/mg4CQxcy/image.png)](https://postimg.cc/fJHVNrfV)
[![image.png](https://i.postimg.cc/cJ43bQBK/image.png)](https://postimg.cc/879sFf3D)
[![image.png](https://i.postimg.cc/xjk4Zm6F/image.png)](https://postimg.cc/t7jkZsQh)
[![image.png](https://i.postimg.cc/8kq0gC3k/image.png)](https://postimg.cc/XXk8wn4t)
[![image.png](https://i.postimg.cc/0yvXrBPL/image.png)](https://postimg.cc/1fWrjMgH)
[![image.png](https://i.postimg.cc/3Jmb8T5X/image.png)](https://postimg.cc/dLQ96g03)
[![image.png](https://i.postimg.cc/YCxnFzSj/image.png)](https://postimg.cc/4YmQktVT)
[![image.png](https://i.postimg.cc/bvCmCYkh/image.png)](https://postimg.cc/67ZVTXMj)

**Evidencia de Desarrollo**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|------------|--------|-----------|----------------|---------------------|------------------|
| hairy-paws/landing-page | main | 7a2e5fc | feat: implement landing page structure | Create base HTML structure for landing page with navigation and sections | 2025-04-03 |
| hairy-paws/landing-page | main | 6c7d9e2 | feat: create HOME section | Add HOME section detailing information and adoption process.| 2025-04-05|
| hairy-paws/landing-page | main | 6c7d9e2 | feat: create HOW IT WORKS section | Introduce HOW IT WORKS section with adoption process details.| 2025-04-05|
| hairy-paws/landing-page | main | 6c7d9e2 | feat: create WHY CHOOSE US section | Include WHY CHOOSE US section highlighting adoption benefits. | 2025-04-05|
| hairy-paws/landing-page | main | 6c7d9e2 | feat: create POPULAR PETS section | Develop POPULAR PETS section showcasing available pets. | 2025-04-05|
| hairy-paws/landing-page | main | 6c7d9e2 | feat: create TESTIMONIALS AND DOWNLOAD section | Add TESTIMONIALS AND DOWNLOAD section featuring user feedback and resources. | 2025-04-05|
| hairy-paws/landing-page | main | 9b3d8a1 | feat: add responsive styles | Implement responsive styles for all screen sizes using CSS Grid and Flexbox | 2025-04-04 |


**Tecnologías Utilizadas**

- Angular 19 como framework principal
- PrimeNG para componentes UI
- PrimeFlex para grid system responsivo
- Optimización de imágenes para rendimiento

**URL del Landing Page Desplegado**

[https://hairy-paws-landing-page.onrender.com](https://hairy-paws-landing-page.onrender.com/)

### 5.2.3. Implemented Frontend-Web Application Evidence

La aplicación web frontend se implementó utilizando Angular 19 con PrimeNG como biblioteca de componentes UI, enfocándose en ofrecer una experiencia de usuario fluida y accesible.

**Capturas de la Implementación**

[![image.png](https://i.postimg.cc/JhVwT89G/image.png)](https://postimg.cc/DSgYZ9fT)

[![image.png](https://i.postimg.cc/MZshCVCk/image.png)](https://postimg.cc/dDyHdkQn)

[![image.png](https://i.postimg.cc/sXtsRWL4/image.png)](https://postimg.cc/qhX9sN4N)

[![image.png](https://i.postimg.cc/4xJZZsWq/image.png)](https://postimg.cc/JGdS5VV5)

[![image.png](https://i.postimg.cc/C5TT2gZv/image.png)](https://postimg.cc/r0JPd7NW)

[![image.png](https://i.postimg.cc/D0Dp8dh8/image.png)](https://postimg.cc/T5VJsbp6)

[![image.png](https://i.postimg.cc/Pq46mkhG/image.png)](https://postimg.cc/LqJBpwnv)

[![image.png](https://i.postimg.cc/xTzt6mY3/image.png)](https://postimg.cc/N5Q6M5KK)

[![image.png](https://i.postimg.cc/tJVtm004/image.png)](https://postimg.cc/kRqbBpX0)

[![image.png](https://i.postimg.cc/nLRPytW4/image.png)](https://postimg.cc/2qWGWgry)

[![image.png](https://i.postimg.cc/tTn28nWb/image.png)](https://postimg.cc/8JDR65ZX)

[![image.png](https://i.postimg.cc/52Pg0Sm1/image.png)](https://postimg.cc/HryXv5KP)

[![image.png](https://i.postimg.cc/6QghV6Sm/image.png)](https://postimg.cc/4KvtsGX6)

[![image.png](https://i.postimg.cc/hvrxYKyg/image.png)](https://postimg.cc/BPjXLffw)

[![image.png](https://i.postimg.cc/W4kZvGW5/image.png)](https://postimg.cc/1gyX0qZF)

[![image.png](https://i.postimg.cc/MTwnJhjG/image.png)](https://postimg.cc/4K8fz2PC)

[![image.png](https://i.postimg.cc/28yVYd3n/image.png)](https://postimg.cc/tY0Xtx3g)

[![image.png](https://i.postimg.cc/g0V0sNBb/image.png)](https://postimg.cc/3yw7JCTt)

[![image.png](https://i.postimg.cc/8c5P1DkT/image.png)](https://postimg.cc/8J2VH2rY)

[![image.png](https://i.postimg.cc/NF5Y34bM/image.png)](https://postimg.cc/Fk52c0M5)

[![image.png](https://i.postimg.cc/1zsSmPMb/image.png)](https://postimg.cc/pmG4CwwB)

[![image.png](https://i.postimg.cc/zvsm91Vt/image.png)](https://postimg.cc/y3yrZthc)

[![image.png](https://i.postimg.cc/dVKP6wMD/image.png)](https://postimg.cc/7fXWYvZy)

[![image.png](https://i.postimg.cc/6qGgV1Yd/image.png)](https://postimg.cc/jntMtvV5)

[![image.png](https://i.postimg.cc/2Smj64SH/image.png)](https://postimg.cc/CzPprnDD)


**Evidencia de Desarrollo**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|------------|--------|-----------|----------------|---------------------|------------------|
| hairy-paws-4436/web-app | feature/auth-module | 2c4e8b5 | feat: implement authentication | Create login and registration components with JWT auth | 2025-04-07 |
| hairy-paws-4436/web-app | feature/pet-search | 8f7d3a9 | feat: add pet search page | Implement advanced search with filters and pagination | 2025-04-14 |
| hairy-paws-4436/web-app | feature/pet-detail | 1e9f4c6 | feat: create pet detail view | Add detailed view with image gallery and information | 2025-04-15 |
| hairy-paws-4436/web-app | feature/pet-form | 5a2b7d3 | feat: implement pet creation form | Add  form for creating pet profiles | 2025-04-16 |
| hairy-paws-4436/web-app | feature/adoption-request | 9c3e4b2 | feat: add adoption request | Implement adoption request form with validations | 2025-04-17 |
| hairy-paws-4436/web-app | feature/pet-edit | 3b6d2e7 | feat: add pet profile editing | Implement edit functionality for pet profiles | 2025-04-18 |
| hairy-paws-4436/web-app | feature/donations | 6a9f2d4 | feat: implement donation system | Add donation registration and management | 2025-04-21 |
| hairy-paws-4436/web-app | feature/events | 4c7d8e6 | feat: implement events system | Add event creation and management for NGOs | 2025-04-23 |

**Implementación de Funcionalidades Clave**

1. **Sistema de Autenticación**
   - Registro con codigo de verificación
   - Login con JWT
   - Recuperación de contraseña
   - Guards para rutas protegidas

2. **Búsqueda de Mascotas**
   - Filtros avanzados
   - Búsqueda por texto libre
   - Paginación y ordenamiento
   - Visualización en cuadrícula y lista

3. **Gestión de Perfiles de Mascotas**
   - Formulario
   - Carga múltiple de imágenes
   - Validaciones
   - Opciones de edición y actualización

4. **Proceso de Adopción**
   - Formulario de solicitud
   - Seguimiento de estado de solicitudes
   - Programación de visitas
   - Mensajería integrada entre partes

5. **Sistema de Donaciones**
   - Registro de intenciones de donación
   - Listado de necesidades de ONGs
   - Seguimiento de donaciones realizadas
   - Confirmación de entrega

6. **Gestión de Eventos**
   - Visualización de eventos programados
   - Registro en eventos
   - Calendario de actividades

**Tecnologías y Características Técnicas**

- Angular 19 como framework principal
- PrimeNG para componentes UI
- PrimeFlex para grid system responsivo
- Estado global con NgRx
- Interceptores HTTP para manejo de tokens y errores
- Lazy loading de módulos para optimización de rendimiento


**URL de la Aplicación Web Desplegada**

[https://app.hairypaws.com.pe]()

### 5.2.4. Implemented Native-Mobile Application Evidence

La aplicación móvil se desarrolló con Flutter para garantizar una experiencia nativa tanto en Android como en iOS, manteniendo la coherencia visual y funcional con la aplicación web.

**Capturas de la Implementación**

[![Screenshot-20250423-234043.png](https://i.postimg.cc/N0MythMQ/Screenshot-20250423-234043.png)](https://postimg.cc/TKz2j4gs)
[![Screenshot-20250423-234113.png](https://i.postimg.cc/g0TxkMX8/Screenshot-20250423-234113.png)](https://postimg.cc/g0TxkMX8)
[![Screenshot-20250423-234125.png](https://i.postimg.cc/yxFxjsfy/Screenshot-20250423-234125.png)](https://postimg.cc/yxFxjsfy)
[![Screenshot-20250423-234250.png](https://i.postimg.cc/KjX4tR5Y/Screenshot-20250423-234250.png)](https://postimg.cc/KjX4tR5Y)
[![Screenshot-20250423-234301.png](https://i.postimg.cc/sXGvBp78/Screenshot-20250423-234301.png)](https://postimg.cc/sXGvBp78)
[![Screenshot-20250423-234306.png](https://i.postimg.cc/FFcYNV9k/Screenshot-20250423-234306.png)](https://postimg.cc/FFcYNV9k)
[![Screenshot-20250423-234316.png](https://i.postimg.cc/ncGMQV9H/Screenshot-20250423-234316.png)](https://postimg.cc/ncGMQV9H)
[![Screenshot-20250423-234328.png](https://i.postimg.cc/HsgVx8xZ/Screenshot-20250423-234328.png)](https://postimg.cc/HsgVx8xZ)
[![Screenshot-20250423-234339.png](https://i.postimg.cc/P5fJbG11/Screenshot-20250423-234339.png)](https://postimg.cc/P5fJbG11)
[![Screenshot-20250423-234356.png](https://i.postimg.cc/t4rT2rzw/Screenshot-20250423-234356.png)](https://postimg.cc/t4rT2rzw)
[![Screenshot-20250423-234410.png](https://i.postimg.cc/jjmjrLmh/Screenshot-20250423-234410.png)](https://postimg.cc/jjmjrLmh)
[![Screenshot-20250423-234419.png](https://i.postimg.cc/8CjC3hK5/Screenshot-20250423-234419.png)](https://postimg.cc/8CjC3hK5)
[![Screenshot-20250423-234439.png](https://i.postimg.cc/26WSjCfN/Screenshot-20250423-234439.png)](https://postimg.cc/26WSjCfN)
[![Screenshot-20250423-234446.png](https://i.postimg.cc/SRpNJHy2/Screenshot-20250423-234446.png)](https://postimg.cc/SRpNJHy2)
[![Screenshot-20250423-234514.png](https://i.postimg.cc/G3kmZ3Qk/Screenshot-20250423-234514.png)](https://postimg.cc/G3kmZ3Qk)
[![Screenshot-20250423-234536.png](https://i.postimg.cc/L5B4fvXy/Screenshot-20250423-234536.png)](https://postimg.cc/L5B4fvXy)



# Evidencia de Desarrollo

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|------------|--------|-----------|----------------|---------------------|------------------|
| hairy-paws-4436/mobile-app | feature/project-setup | a5c1b92 | chore: initial project setup | Configure project structure, dependencies and theme | 2025-04-11 |
| hairy-paws-4436/mobile-app | feature/auth-screens | 4b7e2a3 | feat: implement authentication screens | Create login, registration and 2FA UI | 2025-04-11 |
| hairy-paws-4436/mobile-app | feature/core-architecture | 8d9f64c | feat: implement BLoC architecture | Set up BLoC pattern, repositories and services | 2025-04-12 |
| hairy-paws-4436/mobile-app | feature/pet-search | 2e8f7a1 | feat: add pet search functionality | Implement search with filters and results list | 2025-04-12 |
| hairy-paws-4436/mobile-app | feature/pet-detail | 7c5b3e9 | feat: implement pet detail view | Add detailed view with image gallery and adoption buttons | 2025-04-12 |
| hairy-paws-4436/mobile-app | feature/adoption-request | 9f6d2e1 | feat: implement adoption request flow | Add forms for adoption requests and visits | 2025-04-14 |
| hairy-paws-4436/mobile-app | feature/owner-dashboard | 6b3a7f9 | feat: create pet owner features | Add pet management for owners including add/edit/delete | 2025-04-14 |
| hairy-paws-4436/mobile-app | feature/ngo-integration | 3e5b8c2 | feat: implement NGO functionality | Add NGO registration, profile and donation screens | 2025-04-14 |
| hairy-paws-4436/mobile-app | feature/events-management | 1a2b3c4 | feat: add events functionality | Create events listing, details and creation screens | 2025-04-15 |
| hairy-paws-4436/mobile-app | feature/notifications | 5d4e3f2 | feat: implement notification system | Add notifications center with status updates | 2025-04-15 |
| hairy-paws-4436/mobile-app | feature/user-profile | 7g6h5i4 | feat: enhance user profile | Implement profile editing and password change | 2025-04-16 |
| hairy-paws-4436/mobile-app | feature/cache-optimization | 2k3l4m5 | perf: improve app performance | Implement caching to fix infinite loading issues | 2025-04-17 |
| hairy-paws-4436/mobile-app | feature/ui-improvements | 9n8m7l6 | feat: enhance UI components | Polish UI elements and add animations | 2025-04-18 |
| hairy-paws-4436/mobile-app | bugfix/navigation-issues | 5q6r7s8 | fix: resolve navigation bugs | Fix bottomNavigationBar issues and routing problems | 2025-04-18 |

### Características Implementadas

#### 1. Autenticación y Gestión de Usuarios
- Registro de usuarios con diferentes roles (adoptantes y propietarios)
- Inicio de sesión seguro
- Autenticación de dos factores para mayor seguridad
- Gestión de perfil de usuario
- Recuperación de contraseña

#### 2. Exploración y Búsqueda de Mascotas
- Listado de mascotas disponibles para adopción
- Filtros avanzados por especie, tamaño y otras características
- Búsqueda por texto para encontrar mascotas específicas
- Vista detallada de cada mascota con galería de imágenes
- Información completa sobre cada animal (edad, género, vacunas, etc.)

#### 3. Proceso de Adopción
- Solicitud de adopción directa desde la app
- Programación de visitas para conocer a las mascotas
- Seguimiento del estado de las solicitudes
- Notificaciones sobre actualizaciones de solicitudes

#### 4. Gestión para Propietarios
- Registro de mascotas para adopción
- Edición de información de mascotas
- Aprobación o rechazo de solicitudes de adopción
- Estadísticas de interacciones

#### 5. Integración con ONGs
- Listado de organizaciones sin fines de lucro
- Registro como ONG
- Donaciones a través de la aplicación
- Gestión de eventos de adopción

#### 6. Sistema de Eventos
- Calendario de eventos de adopción
- Creación y gestión de eventos por ONGs
- Registro para participación en eventos
- Visualización detallada de información de eventos

#### 7. Sistema de Notificaciones
- Notificaciones en tiempo real sobre actualizaciones
- Centro de notificaciones integrado
- Marcado de notificaciones como leídas
- Eliminación de notificaciones

### Arquitectura Técnica

La aplicación se ha implementado siguiendo una arquitectura limpia con separación de capas:

#### 1. Capa de Presentación
- **BLoC Pattern**: Implementación de la gestión de estado usando flutter_bloc para mantener una separación clara entre UI y lógica de negocio
- **Componentes Reutilizables**: Widgets personalizados como PetCard, NGOCard, EventCard, etc.
- **Navegación**: Sistema de enrutamiento centralizado usando Navigator 2.0

#### 2. Capa de Dominio
- **Repositorios**: Interfaces para acceder a los datos
- **Modelos**: Definición de entidades de negocio (Animal, User, NGO, Event, etc.)
- **BLoCs específicos**: Cada característica cuenta con su propio BLoC para gestionar su estado

#### 3. Capa de Datos
- **Servicios API**: Comunicación con el backend mediante HTTP
- **Repositorios**: Implementación de cachés para mejorar el rendimiento
- **Almacenamiento Local**: Persistencia de datos de sesión y configuraciones

### Tecnologías Utilizadas

- **Flutter 3.19.0**: Framework principal para desarrollo multiplataforma
- **flutter_bloc**: Biblioteca para gestión de estado
- **http**: Cliente HTTP para comunicación con la API REST
- **flutter_secure_storage**: Almacenamiento seguro para datos sensibles como tokens
- **get_it**: Inyección de dependencias
- **intl**: Internacionalización y formateo
- **image_picker**: Selección de imágenes para subir fotos de mascotas
- **url_launcher**: Apertura de URLs externas


### 5.2.5. Implemented RESTful API and/or Serverless Backend Evidence

El backend de la aplicación se implementó utilizando NestJS como framework, siguiendo una arquitectura de microservicios y principios de Clean Architecture para garantizar escalabilidad y mantenibilidad.

**Estructura del Proyecto**

[![image.png](https://i.postimg.cc/gcXVkCM2/image.png)](https://postimg.cc/hhnz25Wk)

**Evidencia de Desarrollo**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|------------|--------|-----------|----------------|---------------------|------------------|
| guardpets/hairy-paws-api | feature/auth-service | 5e8c3b1 | feat: implement authentication service | Create JWT-based auth with roles and permissions | 2025-01-25 |
| guardpets/hairy-paws-api | feature/users-module | 1d9f7e2 | feat: add users module | Implement CRUD operations for users management | 2025-01-27 |
| guardpets/hairy-paws-api | feature/pets-module | 3c8b5a4 | feat: create pets module | Add endpoints for pet profiles with search functionality | 2025-02-02 |
| guardpets/hairy-paws-api | feature/adoptions-module | 7b2e6f9 | feat: implement adoptions module | Create adoption request flow with status management | 2025-02-08 |
| guardpets/hairy-paws-api | feature/donations-module | 4a5d9c3 | feat: add donations module | Implement donation tracking for NGOs | 2025-02-14 |

**Implementación de Endpoints Principales**

1. **Autenticación**
   - `/auth/register` - Registro de usuarios
   - `/auth/login` - Inicio de sesión
   - `/auth/refresh` - Renovación de token
   - `/auth/forgot-password` - Recuperación de contraseña

2. **Usuarios**
   - `/users` - CRUD de usuarios
   - `/users/me` - Información del usuario actual
   - `/users/verify` - Verificación de cuenta

3. **Mascotas**
   - `/pets` - CRUD de mascotas
   - `/pets/search` - Búsqueda avanzada
   - `/pets/{id}` - Detalles de mascota específica
   - `/pets/{id}/images` - Gestión de imágenes

4. **Adopciones**
   - `/adoptions` - CRUD de solicitudes
   - `/adoptions/{id}/status` - Actualización de estado
   - `/adoptions/user` - Solicitudes del usuario actual

5. **ONGs**
   - `/ngos` - CRUD de ONGs
   - `/ngos/{id}/donations` - Donaciones por ONG
   - `/ngos/{id}/events` - Eventos por ONG

**Tecnologías y Características Técnicas**

- NestJS como framework principal
- TypeORM para interacción con base de datos
- JWT para autenticación
- MySQL como base de datos principal
- Redis para caché y gestión de sesiones
- Multer para manejo de archivos
- Swagger para documentación automática
- Jest para testing unitario e integración
- Docker para containerización

**Características de Seguridad**

- Protección contra CSRF
- Rate limiting para prevenir ataques de fuerza bruta
- Validación de inputs
- Hashing seguro de contraseñas con bcrypt
- Sanitización de datos
- Logs de seguridad y auditoría

### 5.2.6. RESTful API documentation

La documentación de la API se implementó utilizando Swagger/OpenAPI integrado con NestJS, proporcionando una documentación interactiva y actualizada automáticamente.

**Captura de la Documentación API**

[![image.png](https://i.postimg.cc/vB10ycgQ/image.png)](https://postimg.cc/zbrCSDFM)

[![image.png](https://i.postimg.cc/DzNcxnCR/image.png)](https://postimg.cc/67dR3Jxh)

[![image.png](https://i.postimg.cc/90dtXTWj/image.png)](https://postimg.cc/LgsZNJYy)

[![image.png](https://i.postimg.cc/7Zs1Lqyb/image.png)](https://postimg.cc/yDR3Q4xz)

[![image.png](https://i.postimg.cc/J4KZTR0K/image.png)](https://postimg.cc/LnYJ5KzZ)

**Endpoints Documentados**

## Authentication

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| POST   | /api/auth/register | Register a new user |
| POST   | /api/auth/login | Login |
| POST   | /api/auth/2fa/verify | Verify two-factor authentication code |
| POST   | /api/auth/2fa/enable | Enable two-factor authentication |
| GET    | /api/auth/profile | Get authenticated user profile |

## Users

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | /api/users/profile | Get authenticated user profile |
| PUT    | /api/users/profile | Update user profile |
| POST   | /api/users/change-password | Change user password |
| POST   | /api/users/deactivate | Deactivate user account |

## Animals

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | /api/animals | Get a list of available animals for adoption |
| POST   | /api/animals | Create a new animal |
| GET    | /api/animals/owner | Get the authenticated user's animals (owner) |
| GET    | /api/animals/{id} | Get details of an animal |
| PUT    | /api/animals/{id} | Update animal information |
| DELETE | /api/animals/{id} | Delete an animal |

## Adoptions

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| POST   | /api/adoptions | Request adoption or visit |
| GET    | /api/adoptions | Get adoption requests according to user role |
| GET    | /api/adoptions/{id} | Get adoption request details |
| PUT    | /api/adoptions/{id}/approve | Approve an adoption request |
| PUT    | /api/adoptions/{id}/reject | Reject an adoption request |
| PUT    | /api/adoptions/{id}/cancel | Cancel an adoption request |

## Notifications

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | /api/notifications | Get user notifications |
| POST   | /api/notifications/{id}/read | Mark notification as read |
| POST   | /api/notifications/read-all | Mark all notifications as read |
| DELETE | /api/notifications/{id} | Delete notification |

## NGOs

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | /api/ongs | Get list of NGOs |
| POST   | /api/ongs | Register a new NGO |
| GET    | /api/ongs/{id} | Get details of an NGO |
| PUT    | /api/ongs/{id} | Update NGO information |
| GET    | /api/ongs/user/me | Get the authenticated user’s NGO |

## Events

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | /api/events | Get list of events |
| POST   | /api/events | Create a new event |
| GET    | /api/events/{id} | Get event details |
| PUT    | /api/events/{id} | Update event information |
| DELETE | /api/events/{id} | Delete an event |

## Donations

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| POST   | /api/donations | Register a new donation |
| GET    | /api/donations | Get donations based on user role |
| GET    | /api/donations/{id} | Get donation details |
| PUT    | /api/donations/{id}/confirm | Confirm donation receipt |
| PUT    | /api/donations/{id}/cancel | Cancel a donation |

## Administration

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | /api/admin/users | Get user list |
| GET    | /api/admin/ongs | Get ONG list |
| POST   | /api/admin/users/{id}/verify | Verify a user |
| POST   | /api/admin/ongs/{id}/verify | Verify an ONG |
| DELETE | /api/admin/users/{id} | Delete a user |


**Ejemplo de Documentación para Endpoint de Búsqueda**

```json
[
  {
    "id": "80a9a6c2-367b-425f-9668-ce4044a2b062",
    "donorId": "d222dffc-a8e0-40f8-8dd6-023e7e425e8f",
    "ongId": "b509130e-48a2-4004-ab1c-c1e6691e1b5c",
    "type": "items",
    "status": "pending",
    "amount": null,
    "transactionId": "",
    "confirmationDate": null,
    "confirmedBy": null,
    "notes": "Donation for dog food",
    "receiptUrl": null,
    "createdAt": "2025-04-23T11:03:37.495Z",
    "updatedAt": "2025-04-23T11:03:37.495Z",
    "donor": {
      "id": "d222dffc-a8e0-40f8-8dd6-023e7e425e8f",
      "email": "owner@example.com",
      "firstName": "John",
      "lastName": "Doe",
      "phoneNumber": "987654322",
      "role": "owner",
      "status": "active",
      "verified": false,
      "address": "123 Example Ave, Lima"
    },
    "ong": {
      "id": "b509130e-48a2-4004-ab1c-c1e6691e1b5c",
      "name": "Happy Paws",
      "ruc": "20123456789",
      "description": "We are an organization dedicated to rescuing and adopting abandoned animals.",
      "logoUrl": "https://hairy-paws-uploads.s3.us-east-1.amazonaws.com/ongs/f80c3abf-961f-4901-85bf-8fd5b7e097ec.jpg",
      "address": "123 Main Ave, Miraflores, Lima",
      "phone": "987654321",
      "email": "contact@happypaws.org",
      "website": "https://www.happypaws.org",
      "verified": false
    },
    "items": [
      {
        "id": "5f881cf1-690b-418b-afd4-c16514c2f1fb",
        "donationId": "80a9a6c2-367b-425f-9668-ce4044a2b062",
        "name": "Dog food",
        "quantity": 51,
        "description": "Adult dog food, 3kg",
        "createdAt": "2025-04-23T11:03:37.510Z",
        "updatedAt": "2025-04-23T11:03:37.510Z"
      }
    ]
  }
]
```

**URL de la Documentación API**

[https://api.hairypaws.com.pe/docs]()

### 5.2.7. Team Collaboration Insights

**Gráfico de Contribuciones en GitHub**

[![image.png](https://i.postimg.cc/pVfnDMmL/image.png)](https://postimg.cc/YjS9HVN5)

**Distribución de Commits por Miembro**

[![image.png](https://i.postimg.cc/x1CJDktX/image.png)](https://postimg.cc/ykMY0NqK)

[![image.png](https://i.postimg.cc/FzNzP1Ys/image.png)](https://postimg.cc/WFYszNmQ)



## 5.3. Video About-the-Product

El video "About-the-Product" se creó para presentar Hairy Paws a potenciales usuarios y stakeholders, destacando el propósito, funcionalidades clave y beneficios de la plataforma a través de una demostración detallada del producto.

[![image.png](https://i.postimg.cc/7LWkTdNP/image.png)](https://postimg.cc/gw85CM51)

**Descripción del Video**

El video tiene una duración de 6:51 minutos y presenta de manera concisa y demostrativa la plataforma Hairy Paws. El presentador, acompañado por Karen como usuario potencial, realiza un recorrido completo por las diferentes funcionalidades de la aplicación.

El video comienza con una breve introducción donde se explica el propósito principal de Hairy Paws: facilitar la adopción de mascotas y canalizar donaciones a organizaciones afiliadas. A continuación, se muestra la aplicación en funcionamiento a través de una cuenta de demostración, recorriendo las siguientes características:

1. **Exploración de Mascotas**:
   - Visualización del catálogo completo de mascotas disponibles
   - Sistema de filtrado y ordenamiento por nombre, edad y otros criterios
   - Visualización detallada de cada mascota con información relevante

2. **Gestión de Mascotas para Dueños**:
   - Panel de mascotas registradas por el usuario
   - Formulario de registro con campos para información básica, estado de salud y carga de imágenes
   - Opciones para editar y eliminar perfiles de mascotas

3. **Sistema de Notificaciones**:
   - Alertas sobre solicitudes de adopción y visitas
   - Opciones para aceptar o rechazar solicitudes

4. **Organizaciones y Eventos**:
   - Directorio de ONGs registradas con información detallada
   - Calendario de eventos con filtrado por fechas
   - Proceso para registrarse como voluntario
   - Gestión de eventos para organizadores

5. **Sistema de Donaciones**:
   - Donaciones monetarias mediante transferencia bancaria
   - Donaciones de productos con registro detallado
   - Proceso de confirmación de donaciones recibidas por parte de las ONGs

6. **Gestión de Perfil**:
   - Configuración de cuenta y preferencias
   - Opción de autenticación de dos pasos con Microsoft Authenticator
   - Gestión de información para ONGs registradas

7. **Proceso de Adopción**:
   - Solicitud de visitas con selección de fecha
   - Formulario de solicitud de adopción
   - Sistema de aprobación por parte del dueño o la ONG

El video incluye la reacción y comentarios de Karen, quien destaca la facilidad de uso de la plataforma, la claridad de la información y la intuitividad de la interfaz. También plantea una pregunta sobre la posibilidad de realizar donaciones con tarjeta de crédito, a lo que se explica que actualmente solo se permiten transferencias bancarias por razones de seguridad.

**Enlaces del Video**

- [upc-pre-202501-1asi0732-4436-GuardPets-about-the-product-sprint-1-2](https://drive.google.com/file/d/1Q8gUcalHj9FDStFfwGf0pnmEkq3WHxXs/view?usp=sharing)


**Duración**: 6:51 minutos