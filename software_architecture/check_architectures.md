Analiza mi proyecto dentro de [nombre_del_proyecto] según la clasificación dentro de [clasificacion] de arquitecturas de software.

Considera estas condiciones:

* El frontend dentro de [frontend] y backend dentro de [backend] ya están conectados.
* El frontend consume una API real del backend.
* No considerar `localStorage` como persistencia principal de datos.
* Si `localStorage` existe, considéralo solo como detalle secundario de UI, por ejemplo tema visual.
* Separa la respuesta en 3 secciones:

  * Arquitectura general
  * Frontend
  * Backend

Usa exactamente el formato de respuesta dentro de [formato_respuesta].

[nombre_del_proyecto]
EL NOMBRE DEL PROYECTO
[nombre_del_proyecto] 

[frontend]
AQUÍ PEGO LA ESTRUCTURA Y CÓDIGO DEL FRONTEND
[/frontend]

[backend]
AQUÍ PEGO LA ESTRUCTURA Y CÓDIGO DEL BACKEND
[/backend]

[formato_respuesta]
# 1. Arquitectura general de [nombre_del_proyecto]

Explica brevemente cómo se comunica el sistema completo.

Incluye un diagrama simple en texto con este formato:

Frontend
↓ HTTP / REST
Backend API
↓ SQL / ORM / Driver
Database

Luego coloca una tabla con estas columnas de las que sigue y las que sigue parcialmente:

| Clasificación | ¿<nombre_del_proyecto> la sigue? | Por qué           |
| ------------- | -------------------------------: | ----------------- |
| ...           |                Sí / No / Parcial | Explicación corta |

## Resumen general

Incluye una estructura tipo árbol con las arquitecturas que sí sigue.

---

# 2. Frontend

Describe el frontend según la clasificación.

Incluye primero el flujo principal, por ejemplo:

routes
↓
components
↓
contexts
↓
providers
↓
services

Luego coloca una tabla con estas columnas de las que sigue y las que sigue parcialmente:

| Clasificación |        ¿La sigue? | Evidencia en el proyecto               | Qué es en corto |
| ------------- | ----------------: | -------------------------------------- | ---------- |
| ...           | Sí / Parcial | Carpeta, archivo, patrón o explicación | ... |

---

## Lo que más representa al frontend

Incluye una estructura tipo árbol con los estilos, patrones u organizaciones que más aplican al frontend.

---

## Variante exacta del frontend

Incluye una etiqueta corta como:

Component-Based React SPA
  
Luego incluye una descripción más completa como:

Component-Based React SPA (Single Page Application)

---

## Organización de código frontend

Indica si el frontend usa principalmente:

Package by Layer

o:

Package by Feature

y explica por qué.

---

## En términos de capas frontend

Incluye una estructura como esta:

Routes / Pages
Components
Providers / Contexts
Services
Models

Termina la sección indicando si el frontend sigue Clean Architecture estricta o que mezcla.

---

# 3. Backend

Describe el backend según la clasificación.

Incluye primero el flujo principal, por ejemplo:

routes
↓
controllers
↓
services
↓
repositories
↓
database

Luego coloca una tabla con estas columnas de las que sigue y las que sigue parcialmente:

| Clasificación |        ¿La sigue? | Evidencia en el proyecto               | Qué es en corto |
| ------------- | ----------------: | -------------------------------------- | ---------- |
| ...           | Sí / Parcial | Carpeta, archivo, patrón o explicación | ... |

---

## Lo que más representa al backend

Incluye una estructura tipo árbol con los estilos, patrones u organizaciones que más aplican al backend.

---

## Variante exacta del backend

Incluye una etiqueta corta como:

Layered Monolithic REST API

Luego incluye una descripción más completa como:

Monolithic REST API with N-Layer Architecture using API / Controller / Service / Repository / Database layers

---

## Organización de código backend

Indica si el backend usa principalmente:

Package by Layer

o:

Package by Feature

y explica por qué.

---

## En términos de capas backend

Incluye una estructura como esta:

Routes
Controllers
Services
Repositories
Database

Termina la sección indicando si el backend sigue Clean Architecture estricta o que mezcla.

---

# Conclusión corta

Termina con un resumen tipo árbol:

Arquitectura general
Frontend
Backend

Y finalmente agrega una frase final de este estilo:

> <nombre_del_proyecto> es una aplicación ecommerce full-stack de arquitectura ..., con frontend ..., y backend ...
[/formato_respuesta]

[clasificacion]
Architectural Styles
  Runtime Interaction Styles
    Communication Styles / Connector Styles
      Synchronous Communication
        Request Response
        Remote Procedure Call

      Asynchronous Communication
        Message Queue
        Publish Subscribe
        Event Streaming

      Shared Data Communication
        Shared Database Communication

    Runtime Structure Styles
      Client Server
      Pipe and Filter
      Event Driven
      Peer to Peer
      Data Centered Architecture
        Repository Architecture
        Blackboard Architecture

  Deployment / System Composition Styles
    Monolith
    Modular Monolith

    Tiered Architectures
      2-Tier Architecture
      3-Tier Architecture
      N-Tier Architecture

    Distributed Service Architectures
      Service Oriented Architecture
      Microservices

    Specialized Deployment / Execution Styles
      Serverless

  Internal Application Structure Styles
    Layered Architecture
      By Number of Logical Layers
        2-Layer Architecture
        3-Layer Architecture
        N-Layer Architecture

      Common Logical Layer Variants
        Presentation Business Data
        UI Business Data
        Presentation Application Domain Infrastructure
        Presentation Application Domain Persistence
        API Application Domain Infrastructure Persistence

      Layering Rule Variants
        Strict Layered Architecture
        Relaxed Layered Architecture
        Closed Layered Architecture
        Open Layered Architecture

    Component Based Architecture
    Microkernel / Plugin Architecture

  Frontend Rendering / Delivery Architecture Styles
    Single Page Application Architecture
    Multi Page Application Architecture
    Server Side Rendered Frontend Architecture
    Static Site Architecture
    Islands Architecture
    Micro Frontend Architecture

  Backend API / Processing Architecture Styles
    REST API Architecture
    GraphQL API Architecture
    RPC API Architecture
    WebSocket / Realtime Backend Architecture
    Webhook Based Backend Architecture

    Request Driven Backend
    Event Consumer Backend
    Background Worker Backend
    Scheduled Job Backend
    Batch Processing Backend
    Stream Processing Backend


Architectural and Application Patterns
  Boundary and Dependency Patterns
    Clean Architecture
    Hexagonal Architecture / Ports and Adapters
    Onion Architecture

  UI Architectural Patterns
    MVC
    MVP
    MVVM
    PAC
    HMVC

  Backend Application Patterns
    API Interface Patterns
      REST Resource Controller Pattern
      RPC Endpoint Pattern
      GraphQL Resolver Pattern
      WebSocket Gateway Pattern
      Webhook Handler Pattern

    Request Handling Patterns
      Controller Pattern
      Route Handler Pattern
      Middleware Pattern
      Filter Pattern
      Interceptor Pattern
      Front Controller Pattern
      Page Controller Pattern

    Business Logic Patterns
      Service Layer Pattern
      Application Service Pattern
      Use Case / Interactor Pattern
      Transaction Script
      Domain Model Pattern
      Table Module Pattern
      Domain Service Pattern
      Specification Pattern
      Policy Pattern

    Command and Query Handling Patterns
      Command Handler Pattern
      Query Handler Pattern
      CQRS Handler Pattern
      Mediator Pattern

    Data Access Patterns
      Repository Pattern
      DAO Pattern
      Active Record Pattern
      Data Mapper Pattern
      Table Data Gateway
      Row Data Gateway
      Query Object Pattern
      Unit of Work
      Identity Map
      Lazy Load

    Persistence and Transaction Patterns
      Database Transaction Pattern
      Optimistic Locking
      Pessimistic Locking
      Transactional Outbox
      Inbox Pattern
      Idempotency Pattern

    Data Transfer Patterns
      DTO Pattern
      Command Object Pattern
      Query Object Pattern
      Mapper / Assembler Pattern
      Serializer Pattern
      Presenter / Response Mapper Pattern

    Validation and Error Handling Patterns
      Input Validation Pattern
      Schema Validation Pattern
      Exception Handler Pattern
      Result Pattern
      Notification Pattern
      Error Response Pattern

    Security Patterns
      Authentication Middleware
      Authorization Guard
      Role Based Access Control
      Policy Based Authorization
      Session Management Pattern
      Token Based Authentication
      Refresh Token Pattern
      API Key Authentication
      CSRF Protection
      Rate Limiting

    Caching Patterns
      Cache Aside
      Read Through Cache
      Write Through Cache
      Write Behind Cache
      Distributed Cache
      Cache Invalidation Pattern

    Messaging and Job Patterns
      Producer Pattern
      Consumer Pattern
      Worker Pattern
      Job Queue Pattern
      Scheduled Job Pattern
      Competing Consumers
      Dead Letter Queue
      Retry Queue

    Observability Patterns
      Logging Pattern
      Audit Trail Pattern
      Metrics Pattern
      Distributed Tracing Pattern
      Health Check Pattern

    Configuration and Infrastructure Patterns
      Configuration Provider Pattern
      Environment Configuration Pattern
      Secrets Management Pattern
      Feature Toggle Pattern

    Dependency Management Patterns
      Dependency Injection
      Inversion of Control
      Composition Root

  Frontend Application Patterns
    State Management Patterns
      Provider Pattern
        React Context Provider
      Reducer Pattern
      Store Pattern
      Observer Pattern
      Flux Pattern

    Data Access Patterns
      Service Layer Pattern
      API Client Pattern
      Repository Pattern for Frontend
      Custom Hook Data Access Pattern
      Query / Cache Pattern

    Routing Patterns
      Client Side Routing
      Nested Routing
      Route Layout Pattern
      Protected Route Pattern

    Composition Patterns
      Component Composition
      Compound Components
      Higher Order Components
      Render Props
      Custom Hook Composition Pattern

  Distributed Systems / Integration / Data Consistency Patterns
    API Gateway
    Backend for Frontend
    CQRS
    Event Sourcing
    Saga
    Anti Corruption Layer
    Choreography
    Orchestration
    Asynchronous Request Reply
    Transactional Outbox
    Inbox Pattern
    Idempotent Consumer
    Competing Consumers
    Dead Letter Queue
    Sidecar
    Ambassador

  Resilience Patterns
    Circuit Breaker
    Retry
    Timeout
    Bulkhead
    Fallback

  Migration / Modernization Patterns
    Strangler Fig


Code Organization
  Basic Monolith Layouts
    Single File Monolith
    Flat Monolith

  Package by Layer
    Layered by Type
    Classic Layered Folders

  Package by Feature
    Vertical Feature Slices
    Route Colocated Feature Structure
    Feature Modules with Public API

  Domain-Oriented Organization
    Package by Domain
    Package by Bounded Context
    Package by Subdomain
    Package by Aggregate
    Domain Module with Internal Layers
    Screaming Architecture

  Hybrid Approaches
    Feature First with Internal Layers
    Domain Modules with Shared Kernel
    Route First with Shared Modules

  Backend Application Organization
    Controller Service Repository
    API Service Repository
    Controller Application Repository
    Controller Use Case Repository
    API Application Repository
    API Use Case Repository

  Common Backend Layered Implementation Variants
    Controller Service Repository
    Route Handler Service Repository
    API Service Repository
    Controller Application Service Repository
    Controller Use Case Repository
    Route Handler Use Case Repository
    Resolver Service Repository
    Consumer Service Repository
    Job Processor Service Repository
    Command Handler Repository
    Query Handler Repository

  Backend Clean / Hexagonal Organization
    Domain Application Infrastructure Interface Adapters
    Domain Use Cases Adapters Infrastructure
    Entities Use Cases Controllers Gateways Presenters
    Ports Adapters Domain Application Infrastructure

  Backend DDD Organization
    Bounded Context Based Organization
    Aggregate Based Organization
    Entity Value Object Repository Service Organization
    Domain Events Organization
    Shared Kernel Organization

  Backend Feature Organization
    Feature Controller Service Repository Model
    Feature Routes Handlers Services Repositories
    Feature Application Domain Infrastructure
    Feature Commands Queries Handlers Repositories

  Backend Infrastructure Organization
    Config Organization
    Database Organization
    Middleware Organization
    Auth Organization
    Validation Organization
    Error Handling Organization
    Logging Organization
    Queue Organization
    Jobs Organization
    Events Organization
    Schedulers Organization

  Frontend Application Organization
    Routes Components Services
    Pages Components Services
    Pages Components State Services
    Routes Components Contexts Services Models
    Pages Features Shared Services
    Routes Features Shared Services
    Features Components Hooks Services Models

  Common Frontend Layered Implementation Variants
    Page Component Service
    Route Component Service
    Page Component Hook Service
    Route Component Hook Service
    Page Component Context Service
    Route Component Context Service
    Page Feature Service
    Route Feature Service
    Page Component Store Service
    Route Component Store Service
    Page Component Hook Store Service
    Route Component Hook Store Service

  Frontend Component Organization
    Atomic Design
    Component First Organization
    Route Based Organization
    Feature Based Organization

  Frontend State Organization
    Context Based State Organization
    Provider Based State Organization
    Store Based State Organization
    Hook Based State Organization

  Frontend Service Organization
    Service Layer Organization
    API Client Organization
    Model Based Service Organization
    Repository Based Service Organization
[/clasificacion]