## Capítulo V: Product Implementation, Validation & Deployment

### 5.1. Software Configuration Management

#### 5.1.1. Software Development Environment Configuration

Para establecer el entorno de desarrollo del software, se han seleccionado diferentes herramientas, plataformas y guías de trabajo. La siguiente tabla muestra cada recurso utilizado, junto con la finalidad que cumple dentro del proyecto y el medio mediante el cual se puede acceder a este.

| Proceso | Recurso o plataforma | Finalidad | Medio de acceso o Enlace |
|---------|----------------------|-----------|--------------------------|
|Especificación de requisitos|Convenciones Gherkin|Definir condiciones de aceptación y criterios funcionales de manera clara y precisa| [Guía Gherkin](https://cucumber.io/docs/gherkin/)
|Desarrollo Landing Page| Visual Studio Code | Desarrollar, modificar y optimizar el código fuente de la aplicación web|[Visual Studio Code](https://code.visualstudio.com/)|
|Administrador de versiones| Git | Controlar las modificaciones realizadas y administrar las diferentes versiones del proyecto|[Git](https://git-scm.com/)|
|Diseño de experiencia e interfaz| Figma | Elaborar prototipos y organizar visualmente la interfaz de usuario|[Figma](https://figma.com)|
|Publicación y despliegue| Github Pages | Publicar y alojar la página web para permitir su acceso en línea|[Github Pages](https://pages.github.com/)|
|Planificación y gestión del proyecto| Jira Software | Administrar el Product Backlog, planificar los Sprints y realizar el seguimiento de las actividades mediante una metodología ágil|[Jira](https://www.atlassian.com/es/software/jira)|
|Diagramas| PlantUML | Crear representaciones UML relacionadas con la estructura y funcionamiento del sistema|[PlantUML](https://plantuml.com/)|
|Modelado de procesos| UXPressia | Desarrollar herramientas de análisis UX enfocadas en las necesidades y experiencia del usuario|[UXPressia](https://uxpressia.com/)|

#### 5.1.2. Source Code Management

El control del código fuente se realizará mediante GitHub, utilizado como repositorio central para almacenar el proyecto y facilitar el trabajo colaborativo. Además de permitir que los integrantes trabajen sobre una misma base de código, esta plataforma proporciona un historial de las modificaciones realizadas, lo que permite identificar los cambios efectuados durante el desarrollo y mantener su trazabilidad.

Para organizar el proceso de desarrollo, el equipo ha establecido un flujo de trabajo que combina elementos de Git Flow con prácticas de GitHub Flow. Esta organización busca separar adecuadamente el desarrollo de nuevas funcionalidades, la integración de cambios y la gestión de versiones estables, permitiendo que el proyecto pueda incorporar progresivamente nuevas características sin perder el control sobre el código existente.

La estrategia de ramas definida para el proyecto se distribuye de la siguiente manera:

**main:** mantiene la versión estable del sistema que está preparada para ser desplegada.<br>
**develop:** funciona como rama de integración de los avances antes de incorporarlos a la versión estable.<br>
**feature/:** se emplea para desarrollar funcionalidades nuevas o realizar mejoras específicas.<br>
**hotfix/:** se utiliza para solucionar problemas urgentes encontrados en la versión desplegada.

El desarrollo de una nueva funcionalidad comienza creando una rama independiente a partir de develop. Esta forma de trabajo permite que cada modificación sea desarrollada de manera aislada, reduciendo la posibilidad de afectar otras partes del proyecto mientras se encuentra en proceso de implementación.

Una vez que la funcionalidad o corrección ha sido completada, el resultado se incorpora mediante un Pull Request. Antes de realizar la fusión, los demás integrantes pueden revisar los cambios efectuados. De esta manera, la integración no depende únicamente del desarrollador que realizó la modificación, sino que también incorpora una instancia de revisión colaborativa.

**Convención para los commits**

Como complemento al manejo de ramas, se utilizará Conventional Commits para mantener una estructura uniforme en los mensajes de confirmación. Esto permite reconocer rápidamente qué tipo de modificación se realizó y facilita la consulta posterior del historial del proyecto.

Los prefijos considerados son:

| Prefijo | Uso |
|---------|-----|
| **feat** | Incorporación de una nueva funcionalidad. |
| **fix** | Corrección de un error existente. |
| **docs** | Actualización o modificación de documentación. |
| **refactor** | Reorganización o mejora interna del código sin modificar su funcionalidad. |
| **style** | Cambios relacionados con el formato o estilo del código. |
| **test** | Creación o modificación de pruebas. |

**Esquema de versionado**

El proyecto también empleará Semantic Versioning, representado mediante el formato MAJOR.MINOR.PATCH. Este mecanismo permitirá identificar de forma ordenada la evolución de las versiones y diferenciar los cambios realizados según su impacto sobre el sistema.

En conjunto, el uso de GitHub, la estrategia de ramas, los Pull Requests, Conventional Commits y Semantic Versioning proporciona una estructura de trabajo que facilita el control de las modificaciones y la colaboración entre los integrantes. Asimismo, estas prácticas contribuyen a que el código pueda mantenerse y ampliarse de forma organizada durante las siguientes iteraciones del proyecto.

#### 5.1.3. Source Code Style Guide & Conventions
Para evitar diferencias innecesarias en la forma de desarrollar los distintos componentes del sistema, se establecen criterios comunes de programación. Estas reglas serán aplicadas a los lenguajes empleados en el proyecto: HTML, CSS, JavaScript y C#.

Una de las reglas generales consiste en utilizar el inglés para nombrar variables, clases, archivos, comentarios técnicos y elementos de la documentación interna. Con ello se busca mantener una nomenclatura uniforme y facilitar la comprensión del código independientemente del integrante que lo revise o modifique.

Las convenciones adoptadas toman como referencia buenas prácticas provenientes de Google Style Guides, MDN JavaScript, MDN JavaScript Guidelines y Microsoft C# Coding Conventions. También se consideran criterios relacionados con la accesibilidad y la legibilidad del código.

**HTML**

La construcción de la interfaz se realizará mediante HTML5 semántico, buscando que los elementos del documento tengan una organización lógica y que el contenido sea accesible.

Para ello, se tendrán en cuenta las siguientes reglas:

+ Las secciones principales utilizarán etiquetas semánticas como &lt;header&gt;, &lt;nav&gt;, &lt;main&gt;, &lt;section&gt;, &lt;article&gt; y &lt;footer&gt;.
+ Las etiquetas y atributos HTML se escribirán en minúsculas.
+ Todas las etiquetas deberán cerrarse correctamente.
+ Las imágenes incluirán el atributo alt para proporcionar información alternativa y favorecer la accesibilidad.
+ Cuando corresponda, las imágenes definirán sus dimensiones mediante width y height.
+ El documento HTML establecerá lang="en" en la etiqueta &lt;html&gt;.
+ Se incluirán elementos básicos de metadatos, entre ellos &lt;title&gt; y &lt;meta name="descripcion"&gt;.
+ Se evitará incorporar estilos y scripts directamente dentro del HTML cuando no sea necesario.

Ejemplo:
```HTML
<section class="hero-banner">
    <img src="banner.jpg" alt="Main promotional banner" width="1200" height="600">
</section>
```

**CSS**

Los estilos estarán organizados de manera modular, procurando que puedan reutilizarse y mantenerse con facilidad. Para la nomenclatura de las clases se utilizará kebab-case y se aplicará la metodología BEM (Block Element Modifier) para establecer una estructura coherente.

También se seguirán estos criterios:

+ Utilizar nombres de clases descriptivos.
+ Organizar las propiedades CSS siguiendo una secuencia lógica relacionada con el layout, box model, tipografía y apariencia visual.
+ Priorizar unidades relativas como rem, %, vh y vw.
+ No especificar unidades cuando el valor establecido sea cero.
+ Diseñar bajo un enfoque mobile-first para facilitar la adaptación a diferentes tamaños de pantalla.
+ Centralizar las variables reutilizables dentro de :root.

Ejemplo: 

```CSS
:root{ 
--primary-color: #2563eb; 
--secondary-color: #64748b; 
} 
.main-header{ 
    padding: 1rem; 
    background-color: var(--primary-color); 
}
```

**JavaScript**

En el caso de JavaScript, las convenciones estarán orientadas a mantener una estructura clara y facilitar la reutilización y modificación del código.

Se aplicarán las siguientes reglas:

+ Las variables y funciones utilizarán camelCase.
+ Las clases y constructores utilizarán PascalCase.
+ Para declarar variables se emplearán const y let, evitando var.
+ Las funcionalidades se distribuirán en archivos independientes de acuerdo con su responsabilidad.
+ Los eventos se gestionarán mediante addEventListener() en lugar de utilizar eventos directamente en el HTML.
+ Los comentarios se reservarán principalmente para explicar fragmentos cuya lógica sea compleja o poco evidente.
+ Los nombres de las funciones deberán describir la acción que realizan.

Ejemplo:

```JavaScript
const submitButton = document.querySelector("#submit-button"); 
function validateForm(){ 
    return true; 
}
```

**C#**

Para los componentes relacionados con el backend y la lógica de negocio se seguirán las convenciones recomendadas para C# por Microsoft.

Entre los principales criterios se encuentran:

+ Aplicar PascalCase a clases, métodos y propiedades.
+ Utilizar camelCase para variables locales y parámetros.
+ Nombrar los métodos mediante expresiones descriptivas que representen acciones.
+ Considerar el principio Single Responsibility Principle (SRP) para distribuir adecuadamente las responsabilidades.
+ Evitar líneas excesivamente extensas para facilitar la lectura.
+ Incorporar comentarios breves en métodos críticos cuando sea necesario.
+ Organizar los componentes utilizando las capas controllers, services, repositories y models.

Ejemplo:
```C#
public class UserService { 
    public bool ValidateCredentials(string userEmail, string password) { 
        return true; 
        } 
    }
```

**Gherkin**

Para expresar los criterios de aceptación y estructurar las pruebas funcionales se empleará Gherkin. Su utilización permitirá describir el comportamiento esperado del sistema mediante una estructura comprensible tanto para los integrantes técnicos como para los stakeholders.

Los escenarios deberán cumplir con las siguientes condiciones:

Seguir la estructura Given-When-Then.
Utilizar un lenguaje comprensible para personas sin conocimientos técnicos.
Contar con títulos específicos que permitan identificar fácilmente el escenario.
Emplear Scenario Outline cuando sea necesario representar diferentes casos que mantengan una estructura similar.

Ejemplo:

```gherkin
Feature: User Login 
Scenario: Sucessful login 
    Given the user is on the login page 
    When the user enters valid credential 
    Then the system should redirect to the dashboard
```

**Principios generales de codificación**

Además de las reglas específicas para cada lenguaje, el desarrollo se orientará mediante cinco principios generales:

+ Readability First: priorizar que el código pueda entenderse fácilmente.
+ Consistency: conservar criterios de desarrollo uniformes en toda la solución.
+ Modularity: separar las responsabilidades en módulos claramente definidos.
+ Scalability: mantener una estructura que pueda soportar el crecimiento futuro del sistema.
+ Maintainability: facilitar la corrección, modificación y evolución del código.

#### 5.1.4. Software Deployment Configuration

**Despliegue de la Landing Page**

La Landing Page será desarrollada utilizando HTML, CSS y JavaScript y posteriormente publicada mediante GitHub Pages. Para ello, primero será necesario mantener correctamente organizados los archivos dentro del repositorio remoto.

**Organización del repositorio**

El archivo index.html deberá encontrarse directamente en la raíz del repositorio, debido a que será utilizado como archivo inicial durante el proceso de publicación. Los recursos complementarios se distribuirán en carpetas independientes según su función, permitiendo diferenciar los estilos, scripts e imágenes y facilitando el mantenimiento posterior.

La estructura prevista será la siguiente:

```
/ 
|---index.html 
|---css/ 
|   |__ styles.css 
|---js/ 
|  |__ main.js 
|---assets/ 
|       |__ images/
```
**Configuración de GitHub Pages**

Una vez que los archivos se encuentren disponibles en el repositorio, se configurará GitHub Pages como servicio de publicación de la Landing Page.

La configuración contempla las siguientes acciones:

1. Acceder al repositorio del proyecto en GitHub.
2. Ingresar a Settings.
3. Seleccionar la sección Pages.
4. Establecer la rama main como fuente de publicación.
5. Seleccionar la carpeta raíz /root como directorio de despliegue.
6. Guardar la configuración.

Después de completar la configuración, GitHub realizará automáticamente el proceso necesario para generar y publicar el sitio.

**Acceso a la versión publicada**

Cuando el despliegue haya finalizado, GitHub proporcionará una dirección pública desde la cual será posible acceder a la Landing Page.

La estructura esperada de la dirección será:

```
https://<usernanme>.github.io/<repository-name>/
```

Esta dirección corresponderá al acceso público de la versión oficial del producto.

**Actualización del sitio**

El proceso de despliegue también contempla las futuras modificaciones realizadas por el equipo. Cada cambio efectuado en la Landing Page deberá registrarse mediante un nuevo commit y enviarse al repositorio.

Cuando los cambios sean incorporados a la rama principal, GitHub Pages actualizará automáticamente el contenido publicado. Así, la versión disponible en línea podrá mantenerse sincronizada con la versión estable más reciente del código fuente.


### 5.2. Landing Page, Services & Applications Implementation

#### 5.2.1. Sprint 1

##### 5.2.1.1. Spring Planning 1
Para este primer Sprint, el equipo estableció como objetivo principal la implementación y despliegue de la primera versión de la Landing Page.

| Campo | Detalle |
|-------|---------|
| Sprint # | Sprint 1 |
| Date | 2026-09-06 |
| Time | 05:00 PM |
| Location | Reunión virtual vía Google Meet |
| Prepared By | Pillaca Gonzales, Andy Saúl |
| Attendees | Justo Yauricasa, Alexander Paolo / Pillaca Gonzales, Andy Saúl /Alvarado Millan, Boris / Martinez Ramos, Bryan Felix / Nawrocki Loureiro, Ian Andre |
| Sprint N-1 Review Summary | Dado que este es el Sprint inicial del proyecto, no se cuenta con un ciclo anterior para revisión. En consecuencia, la implementación del producto comienza formalmente desde sus cimientos. |
| Sprint N-1 Retrospective Summary | Al tratarse de la iteración inicial, no se cuenta con un proceso de retrospectiva previo. No obstante, el equipo estableció el compromiso de asegurar una comunicación fluida y acatar los plazos previstos. |
| Sprint 1 Goal | Nos enfocamos en el desarrollo y lanzamiento de la primera versión de la Landing Page, orientada a comunicar nuestra propuesta de valor: mejorar la seguridad y monitorieo en el transporte público. Consideramos que transmite con claridad los beneficios del sistema a potenciales clientes, lo cual se validará cuando el sitio esté en línea, cuente con todas las secciones clave y permita una navegación fluida. |
| Sprint N Velocity | 09 |
| Sum of Story Points | 09 |

##### 5.2.1.2. Aspect Leaders and Collaborators

| Team Member | GitHub Username | Configuración del Repositorio y CI/CD (L/C) | Estructura Base del Landing Page (L/C) | Funcionalidades Interactivas (L/C) | Corrección de Contenido (L/C) |
|------------|-----------------|---------------------------------------------|----------------------------------------|-----------------------------------|-------------------------------|
| Alvarado Millan, Boris | borisalvaradomillanPE | L | C | C | C |
| Justo Yauricasa, Alexander Paolo | AlexanderrJusto | C | C | C | L |
| Martinez Ramos, Bryan Felix | BryanMR1 | C | L | L | C |
| Pillaca Gonzales, Andy Saúl | apillacag | C | C | C | L |
| Nawrocki Loureiro, Ian Andre | IanNaw | C | C | C | L |

##### 5.2.1.3. Sprint Backlog 1
Se presenta el desglose tecnico de las historias seleccionadas para esta iteracion inicial. El proposito prioritario del Sprint abarca el despliegue de la pagina de aterrizaje y el cimiento de la arquitectura tecnologica del proyecto. Seguidamente, se incluye la imagen del tablero de Trello y la tabla de estados correspondiente a los elementos de trabajo.

<img src="docs/assets/Cap5/EvidenciaTrello.png">

link: https://trello.com/invite/b/6aada76451c89821aa1c576d/ATTI9ede0c7d6fa24ae911466aeadaa1cec5C94715BC/sprint-1-astrobusteam 

| Sprint # | Sprint 1 | | | | | | |
|----------|----------|-|-|-|-|-|-|
| **User Story** | | **Work-item / Task** | | | | | |
| Story Id | Story Title | Task Id | Task Title | Task Description | Estimation (Hours) | Assigned To | Status (To-do / In-Process / To-Review / Done) |
| US29 | Segmento al que apunta la solución | T-01 | Segmento al que apunta | Mostramos a como y andonde apunta nuestro sistema. | 2 | Alvarado Millan, Boris | Done |
| US37 | Problemática del transporte en la landing page | T-02 | Problematica | Mostrar la desbentajas del traspodte publico sin nuestro aplicacativo. | 2 | Justo Yauricasa, Alexander Paolo | Done |
| US38 | Propuesta de valor en la landing page | T-03 | Propuesta de valor | Mostrar los valores que tiene nuestra aplicativo en el trasporte publico. | 1 | Martinez Ramos, Bryan Felix | Done |
| US45 | Beneficios del sistema en la landing page | T-04 | Beneficios | Mostrar los beneficios que tiene nuestra aplicativo en el trasporte publico. | 1 | Pillaca Gonzales, Andy Saúl | Done |
| US46 | Equipo detrás de la solución | T-05 | Equipo | Mostramos las soluciones que tene nuestro aplicatico en el traspote publico | 2 | Nawrocki Loureiro, Ian Andre | Done |
| US30 | Mision y vision de la startup | T-06 | Mision y vision | Mostromos la vision y mision en la Landing Page. | 1 | Pillaca Gonzales, Andy Saúl | Done |


##### 5.2.1.4. Development Evidence for Sprint Review

##### 5.2.1.5. Execution Evidence for Sprint Review

Durante el primer Sprint, la prioridad del equipo fue la implementación y el lanzamiento de la primera versión de la página. El propósito central fue posicionar la propuesta de valor en materia de seguridad para el transporte público mediante una estructura que abarca desde la presentación general y los beneficios, hasta testimonios, funcionalidades clave y canales de contacto. 

La Landing Page incluye las siguientes secciones:

- **Hero:** Sección inicial que presenta el mensaje principal "Protege tu ruta, asegura tu futuro" e incorpora los accesos "Empezar ahora" y "Ver características" para orientar al usuario hacia las principales opciones de la plataforma.

![Hero](docs/assets/Cap5/LP_Evidencia/Hero2.png)

- **Caracteristicas:** Presenta las funciones principales de SecurityBus, como la validación del conductor mediante código QR, el botón de pánico para situaciones de emergencia, el control de pasajeros a bordo y el seguimiento de la unidad durante el recorrido.

![Hero](docs/assets/Cap5/LP_Evidencia/Caracteristicas.png)

- **Funcionalidad** Expone de forma resumida el funcionamiento de SecurityBus, abarcando desde la verificación del conductor hasta las acciones previstas ante una situación de emergencia.

![Hero](docs/assets/Cap5/LP_Evidencia/Funcionalidad.png)

- **Navegacion:** Barra de navegación que facilita el acceso a las distintas secciones disponibles en la Landing Page de SecurityBus.

![Hero](docs/assets/Cap5/LP_Evidencia/Navegacion.png)

- **Estadistica:** Muestra datos relevantes que permiten contextualizar los principales problemas relacionados con la seguridad en el transporte público.

![Hero](docs/assets/Cap5/LP_Evidencia/Estadistica.png)

- **Interfaz:** Utiliza una apariencia moderna en modo oscuro, acompañada de elementos visuales y tonalidades contrastantes que refuerzan la identidad de SecurityBus.

![Hero](docs/assets/Cap5/LP_Evidencia/Interfaz.png)

Link a la Landing Page: [SecurityBus Landing Page](https://astrobusteam.github.io/SecurityBus-landing-page-aw/)

##### 5.2.1.6. Services Documentation Evidence for Sprint Review

En el Sprint 1 de SecurityBus, el desarrollo estuvo centrado únicamente en la construcción de la Landing Page estática. Durante esta etapa no se implementaron servicios web, por lo que aún no se dispone de endpoints que requieran documentación. El desarrollo y la documentación de estos servicios se abordarán en los siguientes Sprints.

##### 5.2.1.7. Software Deployment Evidence for Sprint Review

Las funcionalidades desarrolladas durante este Sprint comprenden tanto la estructura principal de navegación como distintos elementos destinados a mejorar la experiencia del usuario en la Landing Page de SecurityBus. Para su construcción se estableció una organización basada en componentes reutilizables, un sistema de enrutamiento y estilos globales alineados con la identidad visual definida previamente para el proyecto.

El proceso de desarrollo se gestionó mediante Git Flow, utilizando ramas específicas para trabajar las diferentes funcionalidades antes de incorporarlas al proyecto mediante pull requests. Esta metodología permitió mantener una adecuada organización del código y facilitar el trabajo colaborativo entre los integrantes del equipo de AstroBus, quienes participaron en las distintas actividades relacionadas con el desarrollo front-end.

Asimismo, se realizaron ajustes orientados al diseño responsive, buscando que la Landing Page pueda visualizarse correctamente en distintos tamaños de pantalla. También se consideraron aspectos relacionados con el rendimiento y la accesibilidad web, tomando como referencia los estándares WCAG para ofrecer una interfaz más accesible a los diferentes usuarios vinculados con la propuesta de SecurityBus.

- 1: Primera funcionalidad: Implementación de la sección Hero, encargada de presentar el propósito principal de SecurityBus, acompañada de indicadores relacionados con el impacto de la propuesta y botones de llamada a la acción.
- 2: Segunda funcionalidad: Desarrollo de la sección de Características, donde se presentan las seis funcionalidades principales del sistema: Verificación QR, Botón de Pánico, Conteo de Pasajeros, Monitoreo Real, Alertas Inteligentes y Soporte 24/7.
- 3: Tercera funcionalidad: Incorporación de la sección ¿Cómo funciona SecurityBus?, en la que se explica el funcionamiento general de la propuesta mediante cuatro etapas: Inicio de Turno, Monitoreo Constante, Alerta Inmediata e Intervención.

---

### Despliegue en GitHub Pages

1. Se creó el repositorio público en la organización de GitHub del equipo SecurityBus y se subió el código fuente de la landing page construida con React + Vite.
   
2. En el repositorio. Dentro de **Pages**, como origen de publicación, se guardaron los cambios para activar la publicación automática.
   
3. Se configuraron los archivos necesarios para que los assets funcionen correctamente bajo el subdominio de GitHub Pages.
   
4. Se creó el archivo de workflow para automatizar el build y despliegue mediante GitHub Actions cada vez que se realice un push a la rama
   
5. Una vez activado el despliegue, GitHub Pages generó la URL pública del sitio desde donde cualquier usuario puede acceder a la landing page de SafeBus sin necesidad de credenciales.
    
---

##### 5.2.1.8. Team Collaboration Insights during Sprint

Durante el Sprint 1, los integrantes del equipo AstroBus participaron de manera conjunta en el desarrollo de la Landing Page de SecurityBus, quedando sus aportes registrados mediante los commits realizados en el repositorio del proyecto. Las actividades fueron distribuidas entre los miembros del equipo, permitiendo avanzar de forma organizada en la implementación de las diferentes secciones, funcionalidades, contenido y aspectos visuales de la página.

Para administrar los cambios realizados durante el desarrollo, el equipo utilizó GitFlow como estrategia de control de versiones. El trabajo se realizó principalmente sobre la rama develop, utilizando ramas específicas para cada capitulo. 
Posteriormente, los cambios fueron integrados mediante Pull Requests, permitiendo revisar las modificaciones antes de incorporarlas a las ramas principales del proyecto.

![Contribuciones](docs/assets/Cap5/Contributions.png)

## Conclusiones

### Conclusiones y Recomendaciones

---

## Bibliografía

---

## Anexos

