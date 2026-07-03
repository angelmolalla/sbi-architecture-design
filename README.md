# 🏦 Arquitectura de Solución – Sistema de Banca por Internet (BP)

## Descripción

Este repositorio contiene la propuesta de arquitectura para el **Sistema de Banca por Internet (SBI)** de la entidad BP, desarrollada como respuesta al reto técnico para el cargo de **Arquitecto de Soluciones**.

La propuesta integra en una única arquitectura empresarial los requerimientos del **Sistema de Banca por Internet** y del **Sistema de Gestión de Notificaciones**, aplicando principios de arquitectura basada en eventos, resiliencia, escalabilidad, seguridad y alta disponibilidad.

---

## Alcance

La solución comprende el diseño arquitectónico de alto nivel de la plataforma, incluyendo:

- Análisis de requerimientos funcionales y no funcionales.
- Arquitectura lógica de la solución.
- Diagramas basados en el modelo C4.
- Diagramas de secuencia.
- Arquitectura de infraestructura.
- Selección y justificación de tecnologías.
- Patrones de arquitectura y diseño aplicados.

No forma parte del alcance la implementación del código fuente, el desarrollo de interfaces gráficas ni el despliegue de infraestructura física.

---

## Objetivos de la solución

La propuesta busca diseñar una arquitectura capaz de:

- Gestionar la autenticación segura de usuarios.
- Consultar productos financieros.
- Ejecutar transferencias bancarias.
- Procesar pagos.
- Gestionar clientes.
- Administrar notificaciones multicanal (Push, Email y SMS).
- Proporcionar una bandeja de notificaciones sincronizada.
- Garantizar resiliencia mediante los patrones Retry y Dead Letter Queue (DLQ).
- Cumplir con estándares y buenas prácticas de arquitectura empresarial.

---

## Estructura del repositorio

```text
📂 Reto-BP-Marcelo-Olalla
│
├── 📁 Diagramas
│   ├── Diagramas C4
│   ├── Diagramas de Infraestructura
│   └── Diagramas de Secuencia
│
├── Diagramas BP.drawio
├── Reto Técnico BP Marcelo Olalla.docx
└── README.md
```

---

## Arquitectura

La solución fue modelada utilizando el **modelo C4**, permitiendo representar la arquitectura desde diferentes niveles de abstracción.

Los artefactos incluidos son:

- **Nivel 1:** Diagrama de Contexto.
- **Nivel 2:** Diagramas de Contenedores.
- **Nivel 3:** Diagramas de Componentes.
- Diagramas de Secuencia.
- Diagrama de Infraestructura.

---

## Patrones de Arquitectura

Para satisfacer los requerimientos funcionales y no funcionales se aplicaron los siguientes patrones:

- Event-Driven Architecture (EDA)
- API Gateway
- Retry Pattern
- Dead Letter Queue (DLQ)
- Repository Pattern
- Publisher / Subscriber
- High Availability (HA)
- Horizontal Pod Autoscaler (HPA/KEDA)

---

## Tecnologías Propuestas

### Backend

- Java 21
- Spring Boot
- Spring Security
- Spring Kafka

### Mensajería

- Apache Kafka

### Bases de Datos

- Azure Cosmos DB for NoSQL
- Azure Database for PostgreSQL Flexible Server

### Contenedores

- Docker
- Kubernetes (AKS)

### Observabilidad

- Prometheus
- Grafana
- Azure Monitor
- SIEM

### Servicios Externos

- Azure Communication Services
- Firebase Cloud Messaging (FCM)
- Infobip

---

## Microservicios

### Sistema de Banca

- Seguridad
- Consultas
- Transferencias
- Pagos

### Sistema de Gestión de Notificaciones

- bp-msa-notification-management
- bp-msa-notification-preferences
- bp-msa-notification-email
- bp-msa-notification-push
- bp-msa-notification-sms
- bp-msa-notification-recovery

---

## Características de la Solución

- Arquitectura basada en microservicios.
- Arquitectura orientada a eventos mediante Apache Kafka.
- Escalamiento horizontal utilizando Kubernetes (HPA/KEDA).
- Alta disponibilidad y tolerancia a fallos.
- Persistencia de la bandeja de notificaciones.
- Gestión de preferencias (Opt-in / Opt-out).
- Procesamiento resiliente mediante Retry y Dead Letter Queue (DLQ).
- Preparada para soportar un alto volumen de notificaciones.

---

## Cumplimiento Normativo

Para efectos de esta propuesta se considera que la entidad BP opera en **Ecuador**, por lo que el diseño toma como referencia:

- Ley Orgánica de Protección de Datos Personales (LOPDP).
- Normativa de la Superintendencia de Bancos del Ecuador.
- ISO/IEC 27001.
- ISO/IEC 27017.
- ISO/IEC 27018.

---

## Autor

**Marcelo Olalla**

Ingeniero en Sistemas

Arquitecto de Soluciones
