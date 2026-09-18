## Capítulo IV: Product Design

### 4.1. Style Guidelines

Las siguientes pautas de estilo definen los principales criterios visuales utilizados en el diseño de SecurityBus, con el objetivo de mantener una interfaz consistente y facilitar el trabajo conjunto entre diseño y desarrollo. Estas pautas contemplan aspectos como la identidad visual, paleta de colores, tipografía, espaciado, componentes e interacción.

El diseño de SecurityBus está orientado a transmitir seguridad, control y monitoreo, priorizando la claridad de la información y la rapidez de interpretación. Esto responde a la naturaleza de la plataforma, enfocada en la gestión y supervisión del transporte público.

#### 4.1.1. General Style Guidelines

Las decisiones generales de estilo se basan en los atributos que busca transmitir SecurityBus como producto: seguridad, precisión, modernidad y disponibilidad constante. A nivel visual, se toma como referencia el diseño de dashboards y sistemas de monitoreo, donde la información debe presentarse de manera clara y organizada.

**Branding y tono de comunicación**

La identidad visual de SecurityBus busca representar una plataforma tecnológica, confiable y eficiente, orientada a la supervisión y gestión del transporte público.

La aplicación busca transmitir las siguientes características:

+ Segura
+ Precisa
+ Moderna
+ Siempre activa

El tono de comunicación es serio, formal, respetuoso y sereno, debido al contexto de seguridad en el que se utiliza la plataforma. Por ello, se priorizan mensajes directos y claros, evitando expresiones informales o ambiguas.

**Color Palette**

La paleta de colores de SecurityBus utiliza principalmente tonos oscuros, acompañados de un verde neón como color principal de acento y rojo para situaciones críticas. Esta combinación busca reforzar la identidad tecnológica del producto y facilitar la identificación de acciones y alertas dentro de la interfaz.

|Color|Hex|Significado y justificación| Uso en la interfaz|Imagen|
|-----|---|---------------------------|-------------------|------|
|Negro| - |Se utiliza como color base debido a que transmite seriedad, profundidad y tecnología. También permite generar un entorno visual enfocado y con pocas distracciones. |Fondo principal y diferentes áreas de la interfaz. | ![Color Negro](/docs/assets/colors/negro.jpg)|
|Verde neón| #C3F400 |Es el color principal de acento. Su alta visibilidad permite destacar elementos importantes y transmite dinamismo e innovación. | Botones principales, indicadores y títulos.|![Color Verde Neón](/docs/assets/colors/verde-neon.jpg)|
|Verde secundario| #596D0B|Es el color principal de acento. Su alta visibilidad permite destacar elementos importantes y transmite dinamismo e innovación. | Elementos secundarios y variaciones de componentes.|![Color Verde Secundario](/docs/assets/colors/verde-secundario.jpg)|
|Rojo| - |Se utiliza para representar situaciones de emergencia, peligro o acciones que requieren atención inmediata. | Alertas y elementos críticos.|![Color Rojo](/docs/assets/colors/rojo.jpg)|

**Tipografía**

Para la interfaz se utilizan las familias tipográficas Space Grotesk e Inter, seleccionadas por su legibilidad y adaptación a entornos digitales.

+ Títulos: Space Grotesk Bold, 96 px.
+ Subtítulos: Space Grotesk Bold, entre 48 y 60 px.
+ Párrafos: Inter Light/Bold, entre 12 y 24 px.

Esta combinación permite establecer una jerarquía visual clara entre títulos, subtítulos y contenido informativo.

![Tipografia](/docs/assets/style-guidelines/Type.png)

**Spacing y Layout**

El diseño utiliza un sistema de espaciado consistente para mantener una distribución ordenada de los elementos. Las medidas empleadas para padding y spacing siguen múltiplos de 2 px.

+ Base unit: múltiplos de 2 px para padding y spacing.
+ Grid: márgenes de 24 px para mantener una distribución equilibrada.
+ Breakpoints: se considera un ancho de 1440 px y un alto de 1024 px como referencia para la versión web.

![spacing y layout](/docs/assets/style-guidelines/spacing.png)

**Componentes visuales**

Los principales componentes de la interfaz siguen criterios visuales consistentes:

+ Botones: verde para acciones principales, rojo para acciones críticas y gris para acciones secundarias.

![botones](/docs/assets/style-guidelines/button.png)
+ Cards: utilizadas para organizar información relacionada dentro de contenedores diferenciados.

![botones](/docs/assets/style-guidelines/cuadros.png)
+ Iconografía: se emplea un estilo simple y fácilmente reconocible para facilitar la identificación de acciones y funcionalidades.

![botones](/docs/assets/style-guidelines/icons.png)

**Principios de diseño**

Las decisiones de diseño de SecurityBus se basan en los siguientes principios:

+ **Claridad**: presentar la información de forma comprensible.
+ **Jerarquía visual**: destacar los elementos de mayor importancia.
+ **Consistencia:** mantener uniformidad en colores, tipografías y componentes.
+ **Accesibilidad**: asegurar una adecuada legibilidad y contraste.
+ **Feedback inmediato**: proporcionar una respuesta visual ante las acciones realizadas por el usuario.

#### 4.1.2. Web Style Guidelines

Las reglas de estilo web de SecurityBus establecen los criterios visuales e interactivos utilizados en la aplicación para mantener una experiencia consistente y funcional.

La interfaz web se organiza de acuerdo con las principales funciones de la plataforma, priorizando la información relacionada con el monitoreo, seguridad y gestión de las unidades de transporte. Los elementos de navegación se mantienen visibles y diferenciados para facilitar el acceso a las diferentes secciones del sistema.

Asimismo, se utilizan componentes como cards, botones, indicadores y elementos de información para organizar los contenidos y evitar una presentación excesivamente cargada. Los elementos más relevantes, como alertas y estados críticos, presentan una diferenciación visual mediante el uso del color rojo.

Los botones y enlaces mantienen una apariencia consistente y proporcionan retroalimentación visual durante la interacción. De esta manera, el usuario puede identificar fácilmente las acciones disponibles y comprender el resultado de sus interacciones con el sistema.

### 4.2. Information Architecture
La arquitectura de información de SecurityBus define cómo se distribuyen, agrupan y presentan los contenidos de la plataforma para facilitar el acceso a las funciones principales. Su diseño considera las necesidades de los dos segmentos identificados: los conductores de transporte público y las empresas o consorcios responsables de supervisar sus unidades.

La estructura busca que cada usuario pueda encontrar la información y las acciones que necesita sin realizar recorridos innecesarios. Para ello, se consideran diferentes mecanismos de organización, etiquetado, búsqueda y navegación que mantienen una relación coherente entre la Landing Page y la aplicación web.

#### 4.2.1. Organization Systems

La organización de la información se establece de acuerdo con el tipo de contenido y con las actividades que realizan los usuarios dentro de SecurityBus.

- **Organización por segmento de usuario:** La plataforma diferencia las necesidades de los conductores y de las empresas o consorcios. El conductor se enfoca principalmente en acciones relacionadas con su seguridad y el reporte de incidentes, mientras que la empresa requiere información para supervisar unidades, conductores y situaciones reportadas.

- **Organización por función:** Las funcionalidades se agrupan según el objetivo que cumplen dentro de la plataforma. Entre ellas se encuentran el monitoreo GPS, las alertas de emergencia, el registro de incidentes, la gestión de conductores y la consulta de información de la operación.

- **Jerarquía de información:** En las vistas de supervisión se prioriza la información relacionada con situaciones de emergencia e incidentes, seguida de los datos operativos de las unidades y conductores. Esto permite que los eventos que requieren mayor atención puedan identificarse rápidamente.

- **Organización cronológica:** La información relacionada con incidentes y recorridos puede presentarse considerando el orden temporal de los registros, lo cual permite consultar acontecimientos recientes y revisar el historial de una unidad.

- **Organización por niveles:** La información parte de una vista general y permite acceder progresivamente a datos más específicos; por ejemplo, desde la supervisión general de unidades se puede llegar al detalle de una unidad o a los incidentes asociados a ella.

#### 4.2.2. Labeling Systems

El sistema de etiquetado utiliza nombres breves y fáciles de identificar para que los usuarios reconozcan rápidamente el propósito de cada sección y acción. Se mantiene principalmente el inglés en los elementos de interfaz, conforme a la implementación de la plataforma.

- **Etiquetas de navegación:**
    - Home: acceso a la página principal.
    - Features: muestra las principales funcionalidades de SecurityBus.
    - Statistics: presenta indicadores y datos relacionados con la supervisión de la operación.
    - Plans: permite consultar los planes de suscripción disponibles para empresas y consorcios.
    - Contact: proporciona un medio de comunicación con el equipo de SecurityBus.
    - Login: permite acceder a la aplicación web.
- **Etiquetas de acción:**
    - Get Started: inicia el proceso para comenzar a utilizar SecurityBus.
    - Choose Plan: permite seleccionar un plan de suscripción.
    - Report Incident: permite registrar o reportar un incidente.
    - View Details: permite consultar información detallada.
    Contact Us: dirige al usuario hacia los medios de contacto.
- **Etiquetas relacionadas con seguridad y operación:**
    - GPS Monitoring: supervisión de la ubicación de las unidades.
    - Panic Button: mecanismo para generar una alerta de emergencia.
    - Incident Log: registro de incidentes reportados.
    - Emergency Alerts: visualización de alertas generadas ante situaciones de emergencia.
    - Route History: consulta del historial de recorridos.

Estas etiquetas buscan mantener una relación directa entre el nombre de cada elemento y la acción o información que representa, reduciendo posibles confusiones durante la navegación.

#### 4.2.3. SEO tags and Meta Tags

Para SecurityBus se consideran etiquetas SEO y metadatos que permiten identificar correctamente la plataforma y describir su propósito, aplicados principalmente en la Landing Page para mejorar su presentación en buscadores, navegadores y plataformas que generan vistas previas de enlaces.

- Título de página, que incorpora el nombre del producto y una descripción breve de su finalidad:

```html
<title> SecurityBus - Public Transport Security </title>
```

- Codificación de caracteres, para representar correctamente el contenido de la plataforma:

```html
<meta charset = "UTF-8">
```

- Configuración responsive, que permite adaptar la visualización a distintos tamaños de pantalla:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- Descripción SEO, que resume la propuesta principal utilizando términos relacionados con seguridad, monitoreo y transporte público:

```html
<meta name="description" content="SecurityBus provides security and monitoring solutions for public transport companies, with GPS monitoring, emergency alerts and incident management.">
```

- Open Graph, que controla la información mostrada al compartir la Landing Page en redes sociales o servicios de mensajería:

```html
<meta property="og:title" content="SecurityBus - Public Transport Security">
<meta property="og:description" content="Improve public transport security with GPS monitoring, emergency alerts and incident management.">
<meta property="og:type" content="website">
```

- Favicon: se utiliza el ícono asociado a la identidad visual de SecurityBus para facilitar el reconocimiento de la página en las pestañas del navegador.

#### 4.2.4. Searching Systems

Los mecanismos de búsqueda están orientados principalmente a facilitar la localización de información operativa dentro de la aplicación web. Dado que la plataforma maneja múltiples unidades, conductores e incidentes, se consideran mecanismos que reduzcan el tiempo necesario para encontrar un registro específico:

- **Búsqueda por unidad:** permite localizar una unidad mediante información identificativa disponible en el sistema.

- **Búsqueda de conductores:** facilita la localización de un conductor registrado mediante su nombre u otra información asociada.

- **Filtrado de incidentes:** permite consultar los incidentes registrados según criterios como tipo, estado o periodo de registro.

- **Consulta de información específica:** una vez localizado un registro, el usuario accede a su información detallada sin recorrer manualmente todas las secciones de la plataforma.

Estos mecanismos facilitan el trabajo de las empresas y responsables de supervisión, especialmente cuando aumenta la cantidad de unidades, conductores o incidentes.

#### 4.2.5. Navigation Systems

SecurityBus organiza su navegación en función del contexto en el que se encuentra el usuario ya sea explorando la Landing Page o trabajando dentro de la aplicación y del tipo de acciones que cada segmento necesita realizar con mayor frecuencia.

- En la Landing Page, un navbar agrupa el acceso a las secciones informativas (Home, Features, Statistics, Plans, Contact) junto con el ingreso a Login, funcionando como punto de entrada general a la plataforma.

- Los CTA (Call to Action) distribuidos en la Landing Page funcionan como atajos hacia acciones puntuales como "empezar a usar el servicio", "revisar los planes disponibles" o "contactar al equipo" sin que el usuario tenga que buscarlas dentro del menú.

- Dentro de la aplicación, la navegación deja de girar en torno a contenido informativo y se reorganiza alrededor de las funciones de gestión y supervisión disponibles para el usuario autenticado.

- A nivel contextual, la interfaz habilita el paso de una vista general a una más específica: por ejemplo, de un listado de unidades se puede llegar al detalle de una unidad puntual, y de ahí a sus recorridos o incidentes asociados.

- A nivel de tareas, la estructura refleja las prioridades de cada segmento: para los conductores, las acciones de seguridad y reporte de incidentes quedan al frente; para las empresas y consorcios, se prioriza el acceso a supervisión, gestión y consulta de información operativa.

### 4.3. Landing Page UI Design

#### 4.3.1. Landing Page Wireframe

- Landing Page

1. Hero

![hero](/docs/assets/landing-page-wireframe/01_hero_inicio.png)

2. Metrics 

![hero](/docs/assets/landing-page-wireframe/02_metricas.png)

3. Features 

![hero](/docs/assets/landing-page-wireframe/03_caracteristicas.png)

4. How SecurityBus Works 

![hero](/docs/assets/landing-page-wireframe/04_como_funciona.png)

5. Plan for Consortia 

![hero](/docs/assets/landing-page-wireframe/05_planes_consorcios.png)

6. SecurityBus Statistics 

![hero](/docs/assets/landing-page-wireframe/06_securitybus_statistics.png)

7. Elite Protection CTA 

![hero](/docs/assets/landing-page-wireframe/07_elite_protection_cta.png)

8. About The Team 

![hero](/docs/assets/landing-page-wireframe/08_about_the_team.png)

9. Product Gallery 

![hero](/docs/assets/landing-page-wireframe/09_product_gallery.png)

10. Footer 

![hero](/docs/assets/landing-page-wireframe/10_footer.png)

- Mobile Web Browser

![Mobile Web Browser](/docs/assets/landing-page-wireframe/Landing-page-wireframe-mobile.png)

#### 4.3.2. Landing Page Mock-up

- Landing Page

1. Hero

![hero](/docs/assets/landing-page-mockup/01_hero.png)

2. Metrics 

![hero](/docs/assets/landing-page-mockup/02_metrics.png)

3. Features 

![hero](/docs/assets/landing-page-mockup/03_features.png)

4. How SecurityBus Works 

![hero](/docs/assets/landing-page-mockup/04_how_securitybus_works.png)

5. Plan for Consortia 

![hero](/docs/assets/landing-page-mockup/05_plans_for_consortia.png)

6. SecurityBus Statistics 

![hero](/docs/assets/landing-page-mockup/06_securitybus_statistics.png)

7. Elite Protection CTA 

![hero](/docs/assets/landing-page-mockup/07_elite_protection_cta.png)

8. About The Team 

![hero](/docs/assets/landing-page-mockup/08_about_the_team.png)

9. Product Gallery 

![hero](/docs/assets/landing-page-mockup/09_product_gallery.png)

10. Footer 

![hero](/docs/assets/landing-page-mockup/10_footer.png)

- Mobile Web Browser

![Mobile Web Browser](/docs/assets/landing-page-mockup/Mockup-landing-page-mobile.png)

### 4.4. Web Applications UX/UI Design

#### 4.4.1. Web Applications Wireframes

En esta sección se presentan los wireframes elaborados para la plataforma SecurityBus. Estos constituyen una representación estructural de las interfaces y permiten definir la distribución de los elementos, la organización del contenido y la jerarquía de la información antes de incorporar los componentes visuales del diseño final.

El desarrollo de los wireframes contempla las principales interacciones de los usuarios con la plataforma, considerando de manera diferenciada las necesidades y objetivos correspondientes a los perfiles de consorcio o empresas de transporte público y conductores de trasnporte público. De esta manera, se establece una estructura que facilita la navegación y permite validar la organización de las funcionalidades del sistema.

![Web applications wireframes](/docs/assets/web-applications-ux-ui-design/wireframes/web-application-wireframes.png)

Trabajo elaborado en Figma: [Web Applications Wireframes](https://www.figma.com/design/dZGVlWuEfGy76GBO9a8nmO/SecurityBus?node-id=130-15&p=f&t=3KHRsRuGU2L8xZIc-0 'Web Applications Wireframes')

**1. Acceso y autenticación del conductor**
![Acceso y autenticación del conductor](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Acceso%20Conductor.png)

**2. Validación de identidad del conductor**
![Validación de identidad del conductor](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Validación%20de%20Identidad.png)

**3. Confirmación del acceso del conductor**
![Confirmación del acceso del conductor](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Acceso%20Autorizado.png)

**4. Panel principal del conductor**
![Panel principal del conductor](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Inicio.png)

**5. Inicio y configuración del servicio**
![Inicio y configuración del servicio](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Inicio%20de%20Servicio.png)

**6. Registro y monitoreo del conteo de pasajeros**
![Registro y monitoreo del conteo de pasajeros](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Conteo%20de%20Pasajeros%20Alerta.png)

**7. Alerta asociada al conteo de pasajeros**
![Alerta asociada al conteo de pasajeros](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Modal%20Alerta%20Límite%20de%20Pasajeros.png)

**8. Visualización de la ubicación de la unidad**
![Visualización de la ubicación de la unidad](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Ver%20Mapa.png)

**9. Generación de una alerta de emergencia**
![Generación de una alerta de emergencia](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Envío%20de%20Alerta.png)

**10. Confirmación de ubicación durante la emergencia**
![Confirmación de ubicación durante la emergencia](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Ubicación%20de%20Envío%20de%20Alerta.png)

**11. Confirmación del envío de la alerta**
![Confirmación del envío de la alerta](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Confirmación%20de%20Alerta.png)

**12. Resumen de la jornada de servicio**
![Resumen de la jornada de servicio](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20SafeBus%20Resumen%20Servicio.png)

**13. Finalización del turno del conductor**
![Finalización del turno del conductor](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20SafeBus%20Finalizar%20Turno.png)

**14. Supervisión general de las unidades**
![Supervisión general de las unidades](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Admin%20Centro%20de%20Control.png)

**15. Visualización y atención de una alerta**
![Visualización y atención de una alerta](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Admin%20Centro%20de%20Control%20con%20Alerta.png)

**16. Gestión de notificaciones e incidentes**
![Gestión de notificaciones e incidentes](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Admin%20Notificaciones.png)

**17. Gestión de conductores registrados**
![Gestión de conductores registrados](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Admin%20Gestión%20de%20Conductores.png)

**18. Asignación de conductores y unidades**
![Asignación de conductores y unidades](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Admin%20Asociación%20de%20Unidades.png)

**19. Consulta del historial de turnos**
![Consulta del historial de turnos](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Admin%20Historial%20de%20Turnos.png)

**20. Visualización de indicadores operativos**
![Visualización de indicadores operativos](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Admin%20Impacto%20en%20Números.png)

**21. Gestión y reenvío de alertas**
![Gestión y reenvío de alertas](docs/assets/web-applications-ux-ui-design/wireframes/Wireframe%20Grayscale%20-%20Gestión%20de%20Reenvíos.png)

#### 4.4.2. Web Applications Wireflow Diagrams

En esta sección se presenta la propuesta de Wireflows, elaborada a partir de los User Goals y las User Stories definidas para las aplicaciones incluidas en el alcance del proyecto SecurityBus.

**Task Flow 1: Autenticación y acceso del conductor**
Objetivo del usuario: Permitir que el conductor valide su identidad mediante código QR para iniciar su turno de forma segura y trazable.

Pasos del Task Flow:

1. Acceder a la pantalla de Acceso Conductor y escanear el código QR o ingresar el código de empleado.
2. El sistema valida las credenciales contra el registro central.
3. Confirmar la identidad y visualizar los datos del conductor y del vehículo asignado.
4. Iniciar turno desde la confirmación de acceso.

User Goal 1: Como conductor, quiero validar mi identidad antes de iniciar el servicio, para asegurar la trazabilidad del viaje.

User Persona: Conductor
El conductor accede a la pantalla de Acceso Conductor, escanea su credencial digital o ingresa su código de empleado y presiona "Verificar credenciales". El sistema muestra la pantalla de Validación de Identidad con el escaneo del QR; una vez validado, se presenta la tarjeta de confirmación con nombre, placa del vehículo y estado "Activo", habilitando el botón "Iniciar Turno".

![User Goal 1](docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf1_autenticacion_conductor.png)

Secuencia: Acceso Conductor → Validación de Identidad → Confirmación del acceso

**Task Flow 2: Inicio de servicio y monitoreo de pasajeros**
Objetivo del usuario: Permitir al conductor iniciar el servicio, monitorear su ruta y controlar el conteo de pasajeros en tiempo real.

Pasos del Task Flow:

1. Configurar el servicio: seleccionar vehículo y turno de trabajo.
2. Iniciar el servicio y acceder al panel principal.
3. Registrar el abordaje y bajada de pasajeros.
4. Recibir alerta si se excede la capacidad máxima.
5. Consultar la ubicación de la unidad en el mapa.

User Goal 2: Como conductor, deseo registrar el inicio del servicio, para dejar evidencia del recorrido.

User Persona: Conductor
Desde Inicio de Servicio, el conductor selecciona el vehículo y el turno (mañana/tarde/noche) y confirma "Iniciar Servicio". El sistema lo redirige al Panel principal (Inicio), donde ve distancia, tiempo, pasajeros y la ruta operada en tiempo real.

![User Goal 2](/docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf2a_inicio_servicio.png)

User Goal 3: Como sistema, deseo contabilizar los pasajeros a bordo y alertar cuando se supera la capacidad del vehículo, para evitar altercados y estimar el riesgo.

User Persona: Conductor
Desde el panel de Conteo de Pasajeros, el conductor registra abordajes (+) y bajadas (−). Si el conteo (62/60) supera la capacidad máxima, el sistema dispara el modal "Has alcanzado el límite de pasajeros", que el conductor reconoce con "OK". Desde el mismo panel puede acceder a Ver Mapa para visualizar la ubicación de la unidad y su ruta.

![User Goal 3](/docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf2b_conteo_pasajeros.png)

Secuencia: Inicio de Servicio → Panel principal (Inicio) → Conteo de Pasajeros → Alerta de límite de pasajeros → Ver Mapa

**Task Flow 3: Gestión de una alerta de emergencia**
Objetivo del usuario: Permitir al conductor iniciar el servicio, monitorear su ruta y controlar el conteo de pasajeros en tiempo real.

Objetivo del usuario: Permitir al conductor activar una alerta de pánico y a la central confirmar su recepción y ubicación.
Pasos del Task Flow:

1. Activar el botón de pánico (Panic Signal) ante una situación de riesgo.
2. Confirmar el envío de la alerta.
3. La central recibe la ubicación de la unidad en el mapa de operaciones.
4. La central confirma la recepción de la alerta.

User Goal 4: Como conductor, deseo enviar una alerta de emergencia, para notificar una situación de riesgo; como sistema, deseo notificar a la central de operaciones, para gestionar la emergencia.
User Persona: Conductor / Central de Operaciones
Al presionar "Panic Signal", el conductor ve el modal "¡Alerta enviada!" con coordenadas GPS, estado de notificación a central y audio remoto activo, pudiendo cancelar en 5 segundos. La central, en su mapa de operaciones, recibe el pin "SOS" con el popup "Alerta crítica – Unidad" y accede a "Ver detalles". Finalmente, el sistema de central confirma la alerta mediante los pasos "Alert Sent → Alert Received → Confirmed".

![User goal 4](/docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf3_alerta_emergencia.png)

Secuencia: Envío de Alerta → Ubicación de Envío de Alerta (vista central) → Confirmación de Alerta (central)

**Task Flow 4: Cierre de turno del conductor**
Objetivo del usuario: Permitir al conductor finalizar su turno dejando evidencia del servicio realizado.

Pasos del Task Flow:

1. Consultar el resumen del turno (distancia, tiempo, pasajeros, recaudación).
2. Completar el protocolo de cierre (checklist).
3. Confirmar la finalización del servicio.
Visualizar la confirmación de cierre exitoso.

User Goal 5: Como conductor, quiero finalizar mi turno de forma segura y con evidencia registrada, para garantizar la trazabilidad del servicio.
User Persona: Conductor
Al terminar la ruta, el panel muestra el Resumen de Servicio con los totales del turno y el checklist de protocolo de cierre. Al presionar "Finalizar Servicio" (acción irreversible), el sistema muestra el modal "Servicio finalizado correctamente", con opciones "Ver reporte" o "Salir".

![User Goal 5](/docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf4_cierre_turno.png)

Secuencia: Resumen de Servicio → Finalizar Turno (confirmación)

**Task Flow 5: Supervisión y atención de alertas (Administrador)**
Objetivo del usuario: Permitir a la central supervisar las unidades activas y atender alertas críticas en tiempo real.

Pasos del Task Flow:

1. Visualizar el mapa con las unidades activas.
2. Detectar una alerta activa sobre el mapa.
3. Gestionar notificaciones y destinatarios de la red de alertas.

User Goal 6: Como empresa, deseo conocer el estado de mis vehículos en operación y clasificar las alertas según su gravedad, para tener control operativo.
User Persona: Administrador / Central de Operaciones
Desde el Centro de Control, el administrador visualiza las unidades activas sobre el mapa de Lima. Cuando ocurre una emergencia, el mismo mapa resalta "Alerts: 1 Active". Desde Notificaciones, el administrador gestiona los destinatarios activos y simula el envío de alertas según prioridad (baja/media/urgente).

![User Goal 6](/docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf5_supervision_alertas_admin.png)

Secuencia: Centro de Control → Centro de Control con Alerta → Notificaciones

**Task Flow 6: Gestión de conductores y unidades**
Objetivo del usuario: Permitir administrar el registro de conductores y su asociación con los vehículos disponibles.

Pasos del Task Flow:

1. Consultar el listado de conductores registrados.
2. Revisar el detalle, licencias y línea de autorizaciones de un conductor.
3. Asociar un conductor disponible a un vehículo disponible.
4. Confirmar la asignación.

User Goal 7: Como sistema, deseo asociar un conductor a un vehículo, para asegurar la trazabilidad.
User Persona: Administrador
Desde Gestión de Conductores, el administrador revisa el listado y accede al detalle de un conductor (licencia, puntos, calificación, historial de autorizaciones). Desde Asignación de Unidades, selecciona un conductor disponible y un vehículo disponible, y confirma con "Confirmar Asignación", quedando reflejado en la tabla de asignaciones vigentes.

![User Goal 7](/docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf6_gestion_conductores_unidades.png)

Secuencia: Gestión de Conductores → Asignación de Unidades

Task Flow 7: Trazabilidad y reportes operativos (Administrador)
Objetivo del usuario: Permitir a la central consultar el historial de turnos, indicadores de impacto y gestionar el reenvío de alertas no confirmadas.

Pasos del Task Flow:

1. Filtrar y consultar el historial de turnos por ruta y fecha.
2. Visualizar los indicadores de impacto del sistema.
3. Revisar y reenviar alertas no confirmadas.

**User Goal 8**: Como empresa, deseo conocer la cantidad de personas en distintas unidades, para comparar la ocupación entre distintas rutas.
User Persona: Administrador
Desde Historial de Turnos, el administrador filtra por rango de fecha y ruta, revisando el log de operaciones, pasajeros transportados e incidentes de cada turno. Desde Impacto en Números consulta métricas globales (conductores verificados, alertas gestionadas, pasajeros protegidos). Desde Gestión de Reenvíos, monitorea alertas pendientes/críticas y reenvía las que no fueron confirmadas.

![User Goal 8](/docs/assets/web-applications-ux-ui-design/web-applications-wireflow-diagrams/tf7_trazabilidad_reportes_admin.png)

Secuencia: Historial de Turnos → Impacto en Números → Gestión de Reenvíos

#### 4.4.3. Web Applications Mock-ups

En esta sección se presentan los mockups desarrollados para la plataforma SecurityBus, los cuales permiten visualizar la propuesta de diseño de las interfaces con un mayor nivel de detalle. Estos incorporan elementos visuales como colores, tipografías, iconografía, componentes y distribución gráfica, con el propósito de representar de manera cercana la apariencia final de la plataforma.

Los mockups fueron elaborados considerando los principales perfiles de usuario de SecurityBus: los consorcios o empresas de transporte público y los conductores de transporte público. De esta manera, se busca que cada interfaz responda a las necesidades y funcionalidades correspondientes a cada perfil, al mantener una experiencia visual coherente y que facilite la interacción con el sistema.

![Web Application Mockups](docs/assets/web-applications-ux-ui-design/mockups/web-application-mockup.png)

Trabajo elaborado en Figma: [Web Application Mockups](https://www.figma.com/design/dZGVlWuEfGy76GBO9a8nmO/SecurityBus?node-id=0-1&p=f&t=rfW5UFtjZ6xjUzo9-0 'Web Application Mockups')

**1. Acceso y autenticación del conductor**
![Acceso y autenticación del conductor](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20Acceso%20Conductor.png)

**2. Validación de identidad del conductor**
![Validación de identidad del conductor](docs/assets/web-applications-ux-ui-design/mockups/Validacion%20De%20Identidad.png)

**3. Confirmación del acceso del conductor**
![Confirmación del acceso del conductor](docs/assets/web-applications-ux-ui-design/mockups/Validacion%20De%20Identidad-1.png)

**4. Panel principal del conductor**
![Panel principal del conductor](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus-%20Inicio.png)

**5. Inicio y configuración del servicio**
![Inicio y configuración del servicio](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20Inicio%20de%20Servicio.png)

**6. Registro y monitoreo del conteo de pasajeros**
![Registro y monitoreo del conteo de pasajeros](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20Inicio%20de%20Servicio.png)

**7. Alerta asociada al conteo de pasajeros**
![Alerta asociada al conteo de pasajeros](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20Conteo%20de%20Pasajeros%20Alerta%20US17-1.png)

**8. Visualización de la ubicación de la unidad**
![Visualización de la ubicación de la unidad](docs/assets/web-applications-ux-ui-design/mockups/Ver%20Mapa.png)

**9. Generación de una alerta de emergencia**
![Generación de una alerta de emergencia](docs/assets/web-applications-ux-ui-design/mockups/Envio%20de%20Alerta.png)

**10. Confirmación de ubicación durante la emergencia**
![Confirmación de ubicación durante la emergencia](docs/assets/web-applications-ux-ui-design/mockups/Ubicacion%20de%20Envio%20de%20Alerta.png)

**11. Confirmación del envío de la alerta**
![Confirmación del envío de la alerta](docs/assets/web-applications-ux-ui-design/mockups/SSecurityBus%20-%20Confirmación%20de%20Alerta.png)

**12. Resumen de la jornada de servicio**
![Resumen de la jornada de servicio](docs/assets/web-applications-ux-ui-design/mockups/SafeBus%20-%20Resumen%20Servicio.png)

**13. Finalización del turno del conductor**
![Finalización del turno del conductor](docs/assets/web-applications-ux-ui-design/mockups/SafeBus%20-%20Finalizar%20Turno.png)

**14. Supervisión general de las unidades**
![Supervisión general de las unidades](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus-ADMIN-CENTRO%20DE%20CONTROL.png)

**15. Visualización y atención de una alerta**
![Visualización y atención de una alerta](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20ADMIN-CENTRO%20DE%20CONTROL-ALERTA.png)

**16. Gestión de notificaciones e incidentes**
![Gestión de notificaciones e incidentes](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20ADMIN-NOTIFICACIONES.png)

**17. Gestión de conductores registrados**
![Gestión de conductores registrados](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20ADMIN-GESTION%20DE%20CONDUCTORES.png)

**18. Asignación de conductores y unidades**
![Asignación de conductores y unidades](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20ADMIN-ASIGNACION%20DE%20UNIDADES.png)

**19. Consulta del historial de turnos**
![Consulta del historial de turnos](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus-%20ADMIN-HISTORIAL%20DE%20TURNOS.png)

**20. Visualización de indicadores operativos**
![Visualización de indicadores operativos](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20ADMIN-IMPACTO%20DE%20NUMEROS.png)

**21. Gestión y reenvío de alertas**
![Gestión y reenvío de alertas](docs/assets/web-applications-ux-ui-design/mockups/SecurityBus%20-%20Gestión%20de%20Reenvíos.png)

#### 4.4.4. Web Applications User Flow Diagrams

**User Flow 1: Autenticación e inicio de servicio del conductor**

Relacionado al User Goal 1: Como conductor, quiero validar mi identidad mediante código QR antes de iniciar mi turno, para asegurar la trazabilidad del servicio.
El conductor accede a la pantalla de Acceso Conductor, escanea su credencial digital o ingresa su código de empleado. El sistema muestra la pantalla de Validación de Identidad con el escaneo del QR; una vez validado, se presenta la confirmación de acceso autorizado con la transmisión activa hacia central, habilitando el turno.

![Goal 1](/docs/assets/web-applications-ux-ui-design/web-applications-user-flow-diagrams/uf1_goal1_autenticacion.png)

Relacionado al User Goal 2: Como conductor, quiero configurar e iniciar mi servicio, para dejar registro del recorrido que voy a realizar.
Desde Inicio de Servicio, el conductor selecciona el vehículo y el turno de trabajo y confirma "Iniciar Servicio". El sistema lo redirige al Panel Principal (Dashboard), donde visualiza distancia, tiempo, pasajeros y la ruta operada en tiempo real.

![Goal 2](/docs/assets/web-applications-ux-ui-design/web-applications-user-flow-diagrams/uf1_goal2_inicio_servicio.png)

**User Flow 2: Monitoreo de pasajeros y atención de emergencias**

Relacionado al User Goal 3: Como sistema, deseo contabilizar los pasajeros a bordo y alertar cuando se supera la capacidad del vehículo, para evitar altercados y estimar el riesgo.
Desde el panel de Conteo de Pasajeros, el conductor registra abordajes y bajadas. Si el conteo supera la capacidad máxima, el sistema dispara la alerta "Has alcanzado el límite de pasajeros". Desde el mismo panel puede acceder a Ver Mapa para visualizar la ubicación de la unidad en ruta.

![Goal 3](/docs/assets/web-applications-ux-ui-design/web-applications-user-flow-diagrams/uf2_goal3_conteo_pasajeros.png)

Relacionado al User Goal 4: Como conductor, deseo enviar una alerta de emergencia, para notificar una situación de riesgo; como sistema, deseo notificar a la central de operaciones, para gestionar la emergencia.
Al presionar el botón de pánico, el conductor ve la confirmación "¡Alerta enviada!" con coordenadas GPS y estado de notificación a central. La central, en su mapa de operaciones, recibe el pin "SOS" con los detalles de la unidad y confirma la alerta mediante el protocolo "Alert Sent → Alert Received → Confirmed".

![Goal 4](/docs/assets/web-applications-ux-ui-design/web-applications-user-flow-diagrams/uf2_goal4_alerta_emergencia.png)

**User Flow 3: Cierre de turno del conductor**

Relacionado al User Goal 5: Como conductor, quiero finalizar mi turno de forma segura y con evidencia registrada, para garantizar la trazabilidad del servicio.
Al terminar la ruta, el panel muestra el Resumen de Servicio con los totales del turno y el checklist de protocolo de cierre. Al presionar "Finalizar Servicio", el sistema muestra la confirmación "Servicio finalizado correctamente".

![Goal 5](/docs/assets/web-applications-ux-ui-design/web-applications-user-flow-diagrams/uf3_goal5_cierre_turno.png)



### 4.5. Web Applications Prototyping

### 4.6. Domain-Driven Software Architecture

#### 4.6.1. Design-Level EventStorming
#### 4.6.2. Software Architecture Context Diagram
#### 4.6.3. Software Architecture Container Diagrams
#### 4.6.4. Software Architecture Components Diagrams

### 4.7. Software Object-Oriented Design
#### 4.7.1 Class Diagrams

### 4.8. Database Design
#### 4.8.1. Database Diagrams

