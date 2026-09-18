## Capítulo IV: Product Design

### 4.1. Style Guidelines

#### 4.1.1. General Style Guidelines

#### 4.1.2. Web Style Guidelines

### 4.2. Information Architecture

#### 4.2.1. Organization Systems

#### 4.2.2. Labeling Systems

#### 4.2.3. SEO tags and Meta Tags

#### 4.2.4. Searching Systems

#### 4.2.5. Navigation Systems

### 4.3. Landing Page UI Design

#### 4.3.1. Landing Page Wireframe

#### 4.3.2. Landing Page Mock-up

### 4.4. Web Applications UX/UI Design

#### 4.4.1. Web Applications Wireframes
#### 4.4.2. Web Applications Wireflow Diagrams
#### 4.4.3. Web Applications Mock-ups
#### 4.4.4. Web Applications User Flow Diagrams

### 4.5. Web Applications Prototyping

### 4.6. Domain-Driven Software Architecture

La arquitectura de software de **SecurityBus** se diseñó aplicando los principios de Domain-Driven Design (DDD). A partir de las cinco épicas definidas en la sección 3.1 se identificaron los *bounded contexts* del sistema y se clasificaron según su valor estratégico para el negocio:

| Bounded Context                             | Clasificación DDD    | Épica relacionada | Responsabilidad                                                                                          |
| :------------------------------------------- | :-------------------- | :----------------- | :--------------------------------------------------------------------------------------------------------- |
| Gestión de Alertas de Emergencia             | **Núcleo (Core)**     | EPNN02              | Emisión, clasificación, difusión, reintento, escalamiento y registro de cada alerta. Es la razón de ser de la plataforma. |
| Gestión de Conductores y Servicios           | Apoyo (Supporting)    | EPNN01              | Identificación del conductor, habilitación, vínculo con la unidad y ciclo de vida del servicio.            |
| Monitoreo de Pasajeros y Ocupación           | Apoyo (Supporting)    | EPNN03              | Conteo de ocupantes, detección de sobrecapacidad y análisis de variaciones.                                |
| Landing Page informativa                     | Genérico              | EPNN04              | Contenido público orientado a visitantes.                                                                  |
| Web Services / API                           | Genérico (habilitador)| EPNN05              | Punto de entrada técnico que expone y protege los recursos del sistema.                                    |

Esta clasificación guía las decisiones de las siguientes tres secciones: el EventStorming de diseño profundiza en los tres contextos con lógica de negocio propia, mientras que los diagramas C4 sitúan a la plataforma completa dentro de su ecosistema técnico.

#### 4.6.1. Design-Level EventStorming

El EventStorming de nivel de diseño toma los *hotspots* identificados en el Big Picture EventStorming (sección 2.4) y los refina en comandos, agregados, eventos de dominio, políticas y modelos de lectura, siguiendo la notación de colores estándar. La Figura 4.1 muestra este refinamiento para los tres *bounded contexts* con lógica de negocio propia:

<p align="center">
  <img src="docs/assets/chapter-4/eventstorming-design-level.svg" alt="Design-Level EventStorming de SecurityBus" width="100%">
</p>

<p align="center"><em>Figura 4.1. Design-Level EventStorming — Gestión de Conductores y Servicios, Gestión de Alertas de Emergencia (dominio núcleo) y Monitoreo de Ocupación.</em></p>

**Gestión de Conductores y Servicios.** El conductor se autentica con su código vigente (US01) sobre el agregado `Conductor`, lo que produce el evento `Conductor Autenticado`. Antes de aceptar el comando `Abrir Servicio` (US02) sobre el agregado `Servicio`, una política verifica que la habilitación esté vigente (US14) y bloquea cualquier intento de operación simultánea del mismo conductor en otra unidad (US39). El servicio permanece abierto hasta que el conductor emite `Cerrar Servicio` (US25); ambos estados alimentan el modelo de lectura *Tablero de Flota / Seguimiento* que consulta la empresa (US26, US27, US43).

**Gestión de Alertas de Emergencia (dominio núcleo).** El conductor emite la alerta (US03) sobre el agregado `Alerta`; si no existe un servicio en curso, la alerta se descarta en el mismo paso. Una vez emitida, el sistema la procesa, le asocia la ubicación (US04, US42) y la clasifica por gravedad (US40) antes de difundirla a los destinatarios configurados (US33), lo que involucra al sistema externo de notificaciones. La central debe acusar recepción (US23); dos políticas gobiernan lo que ocurre si no lo hace: una reenvía la alerta cuando se vence el plazo (US24) y otra la escala cuando los reintentos se agotan (US41). El tiempo de respuesta se mide (US34) y todo el recorrido queda disponible en el *Historial de Emergencias* que consulta la empresa (US16).

**Monitoreo de Pasajeros y Ocupación.** Los sensores IoT reportan el ingreso y salida de pasajeros, lo que actualiza el conteo del agregado `Ocupación` (US06). Una política evalúa si se superó la capacidad máxima configurada y, de ser así, dispara el evento `Sobrecapacidad Detectada` (US17). En paralelo, el sistema analiza la ocupación para calcular promedios, detectar variaciones anómalas y comparar unidades (US35, US36, US44), publicando los resultados en el *Reporte de Ocupación* que consulta la empresa (US07, US28).

#### 4.6.2. Software Architecture Context Diagram

Siguiendo el modelo C4, el diagrama de contexto (Nivel 1) sitúa a la Plataforma SecurityBus frente a las personas que la usan y los sistemas externos de los que depende, sin exponer aún su estructura interna:

<p align="center">
  <img src="docs/assets/chapter-4/context-diagram-c4-l1.svg" alt="Diagrama de Contexto C4 Nivel 1 de SecurityBus" width="100%">
</p>

<p align="center"><em>Figura 4.2. Diagrama de Contexto (C4 — Nivel 1) de la Plataforma SecurityBus.</em></p>

Cuatro tipos de usuario interactúan con la plataforma: el **conductor**, que se autentica, abre y cierra su servicio y emite alertas desde la unidad; el **encargado de la empresa operadora**, que supervisa la flota y revisa alertas e historiales; el **visitante**, que explora la landing page para evaluar la propuesta de valor; y el **developer o sistema integrador**, que consume la API REST sin pasar por ninguna interfaz gráfica (EPNN05). La plataforma, a su vez, depende de tres sistemas externos: los **sensores de conteo IoT** embarcados en cada unidad, un **servicio de notificaciones** (SMS, push y correo) que distribuye las alertas a los destinatarios configurados, y un **proveedor de geolocalización** que entrega las coordenadas y el trazado del recorrido de cada unidad.

#### 4.6.3. Software Architecture Container Diagrams

El diagrama de contenedores (Nivel 2) descompone la Plataforma SecurityBus en sus unidades desplegables. Un API Gateway centraliza la autenticación y autorización de toda petición (US22, US50) y enruta el tráfico hacia cuatro microservicios, cada uno alineado a uno de los *bounded contexts* de la sección 4.6:

<p align="center">
  <img src="docs/assets/chapter-4/container-diagram-c4-l2.svg" alt="Diagrama de Contenedores C4 Nivel 2 de SecurityBus" width="100%">
</p>

<p align="center"><em>Figura 4.3. Diagrama de Contenedores (C4 — Nivel 2) de la Plataforma SecurityBus.</em></p>

Los tres clientes (la app móvil del conductor, el dashboard web de la empresa y la landing page) y el developer externo acceden siempre a través del API Gateway, nunca directamente a un microservicio. El **Servicio de Alertas de Emergencia**, alineado al dominio núcleo, se distingue de los demás por delegar sus reintentos y escalamientos (US24, US41) a una **Cola de Reintentos y Escalamiento**, que a su vez alimenta un **Despachador de Notificaciones** encargado de integrar con el servicio externo de SMS, push y correo. Los servicios de **Conductores y Servicios**, **Monitoreo de Ocupación** y **Contenido** siguen el mismo patrón: cada uno persiste su propio estado en una base de datos dedicada, evitando el acoplamiento entre *bounded contexts* a nivel de datos.

#### 4.6.4. Software Architecture Components Diagrams

### 4.7. Software Object-Oriented Design
#### 4.7.1 Class Diagrams

### 4.8. Database Design
#### 4.8.1. Database Diagrams

