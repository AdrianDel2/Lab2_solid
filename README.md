# Segunda Iteración de Software para Hyun Seda

## Ingeniería de Software 2

### Presentado por:
- Juan Esteban Muñoz Gómez
- Laura Sofía Botina Montero
- Adrián Fernando Delgado Serna
- Felipe Armand Pino Sierra

### Profesor:
- WILSON LIBARDO PANTOJA YEPEZ

**Universidad del Cauca**  
**Facultad de Ingeniería Electrónica y Telecomunicaciones**  
**Ingeniería de Sistemas**  
**Popayán mayo 2024**

## Contenido

1. [Segunda Iteración de Software para Hyun Seda](#segunda-iteración-de-software-para-hyun-seda)
2. [Introducción](#introducción)
3. [Requisitos Funcionales](#requisitos-funcionales)
4. [Prototipos y test de usabilidad](#prototipos-y-test-de-usabilidad)
    1. [Prototipos de interfaces](#prototipos-de-interfaces)
    2. [Test de usabilidad](#test-de-usabilidad)
5. [Requisitos no funcionales](#requisitos-no-funcionales)
    1. [Atributo de calidad 1 (Performance)](#atributo-de-calidad-1-performance)
    2. [Atributo de calidad 2 (Seguridad)](#atributo-de-calidad-2-seguridad)
    3. [Atributo de calidad 3 (Modificabilidad)](#atributo-de-calidad-3-modificabilidad)
    4. [Tácticas de Arquitectura](#tácticas-de-arquitectura)
6. [Diagrama Entidad Relación](#diagrama-entidad-relación)
7. [Arquitectura del sistema](#arquitectura-del-sistema)
8. [Decisiones de arquitectura y su justificación](#decisiones-de-arquitectura-y-su-justificación)
    1. [Decisiones de arquitectura](#decisiones-de-arquitectura)
    2. [Estilo arquitectónico](#estilo-arquitectónico)
        1. [Arquitectura MVC](#arquitectura-mvc)
        2. [Arquitectura de Microservicios](#arquitectura-de-microservicios)
    3. [Tipo de aplicación](#tipo-de-aplicación)
    4. [Tecnologías](#tecnologías)
9. [URL del repositorio de GitHub](#url-del-repositorio-de-github)

## Introducción

En este documento se presenta un análisis detallado del proyecto de Hyun Seda, una empresa dedicada a la producción de seda sostenible de calidad y respetuosa con el medio ambiente que ha evolucionado su modelo de negocio hacia un enfoque digital con el objetivo de expandir su alcance y aumentar su visibilidad en el mercado.

Además, conscientes de la importancia de una presencia en línea sólida, Hyun Seda ha contratado servicios tercerizados para el desarrollo de un ecommerce y la gestión de productos. Si bien esta decisión inicial fue tomada para cubrir necesidades inmediatas, como la preparación para un evento importante, se ha identificado la necesidad de una solución a largo plazo que sea autónoma y rentable.

En este contexto, se propone el diseño e implementación de un sistema propio que no solo cumpla con los requisitos funcionales y no funcionales del negocio, sino que también garantice la eficiencia, seguridad y escalabilidad necesarias para el crecimiento continuo de Hyun Seda. Este documento abordará aspectos clave como la arquitectura del sistema, las tecnologías seleccionadas y las pruebas de usabilidad con el fin de proporcionar una guía integral para el desarrollo exitoso de esta iniciativa.

## Requisitos Funcionales

Se hace referencia a la hoja de cálculo de Historias Épicas HyunSeda de la plantilla de historias de usuario.  
Haga CRTL + CLIC: [Segundo reporte HE HyunSeda.xlsx](Segundo_reporte_HE_HyunSeda.xlsx)

## Prototipos y test de usabilidad

### Prototipos de interfaces

A continuación se presentan algunos prototipos de las interfaces del software.
![](https://github.com/AdrianDel2/Lab2_solid/blob/main/img/imagen1.png)
- **Imagen 1.** Prototipo de la interfaz del menú del producto. Elaboración propia.
- **Imagen 2.** Prototipo de la interfaz agregar producto. Elaboración propia.
- **Imagen 3.** Prototipo de la interfaz de la tienda Hyun Seda. Elaboración propia.
- **Imagen 4.** Prototipo de la interfaz buscar producto. Elaboración propia.

### Test de usabilidad

A continuación se presenta el prototipo de la vista previa de los productos de la tienda como tal:

Y aquí se adjuntan los enlaces a los videos donde se hace la prueba de usabilidad:  
Haga CLIC + CTRL: [video1.mp4](video1.mp4)  
Haga CLIC + CTRL: [video2.mp4](video2.mp4)

### Pruebas unitarias

Se presenta un resumen de las pruebas realizadas para el proyecto.

- **Imagen 5.** Captura de los test realizados para el software. Elaboración propia.

## Requisitos no funcionales

Los requisitos no funcionales identificados mediante la aplicación de un Mini-QAW en conjunto con el cliente son los siguientes:

### 1. Performance

- Contexto: Con el objetivo de ampliar su alcance y mejorar la visibilidad de sus productos, Hyun Seda ha implementado una landing page que ofrece información detallada sobre el proceso de producción, la historia de la seda y datos de contacto. Además, se creó temporalmente un blog para compartir noticias relevantes y aumentar la visibilidad.
- Estímulo: Un usuario realiza una acción en el sitio web como cargar una página, agregar un producto al carrito de compras o procesar un pedido.
- Respuesta: La plataforma en línea de Hyun Seda requiere una solución para gestionar el almacenamiento de archivos multimedia, evitando que la base de datos aumente exponencialmente de tamaño por la carga de imágenes, proporcionando una experiencia de usuario fluida y sin demoras significativas.
- Medición de la calidad: Los criterios para evaluar el desempeño del sistema incluyen el tiempo de carga de la página principal y de productos, y la eficiencia en el manejo de archivos multimedia. La calidad se medirá mediante la rapidez y consistencia en la experiencia del usuario, así como la capacidad para mantener un rendimiento óptimo.
- Resultado esperado: Se espera que la plataforma en línea de Hyun Seda proporcione un rendimiento confiable y eficiente en todo momento. Los tiempos de carga deben ser rápidos y consistentes, asegurando que los usuarios puedan explorar productos, leer el blog y realizar compras de manera rápida y sin inconvenientes.

### 2. Seguridad

- Contexto: Hyun Seda gestiona el acceso a la edición de las características de su página web a través de la implementación de tres roles distintos: editor (se encarga de hacer el CRUD de publicaciones para el blog), administrador (se encarga de la gestión de los productos así como del blog) y super administrador (posee los permisos del administrador y adicionalmente puede gestionar los demás usuarios (Administrador y Editor); por ende, solo se permite el ingreso de un Super Administrador).
- Estímulo: Un usuario interno accede al dashboard de empleados de Hyun Seda utilizando una cuenta y las credenciales correspondientes para iniciar sesión.
- Respuesta: El sistema debe garantizar que únicamente los usuarios registrados tengan acceso al dashboard de empleados. Una vez se ha iniciado sesión, se mostrarán las utilidades correspondientes al rol del usuario.
- Medición de la calidad: La calidad se mide por la efectividad en la autenticación, asegurando que solo los usuarios autorizados tengan acceso al dashboard y en general cada tipo de usuario solo tenga acceso o capacidad de manipulación de lo que refiere a su jerarquía de usuario o la de un nivel jerárquico más profundo. La tasa de éxito en la autenticación y la capacidad para prevenir accesos no autorizados son métricas clave.
- Resultado esperado: El sistema garantiza que solo los usuarios autenticados y autorizados tengan acceso al dashboard que le corresponde con base en las credenciales ingresadas.

### 3. Modificabilidad

- Contexto: La empresa Hyun Seda ha desarrollado una página web para promocionar y vender sus productos. Desea asegurar que su página web sea altamente modificable, legible y adaptable a diferentes entornos, conscientes de que esta capacidad será fundamental para facilitar futuras migraciones hacia nuevas plataformas web, aplicaciones móviles y otros entornos tecnológicos.
- Estímulo: Un nuevo desarrollador se incorpora al equipo de Hyun Seda y necesita familiarizarse con el código y la arquitectura del sistema web existente para comenzar a trabajar en la implementación de nuevas características.
- Respuesta: El sistema debe ser concebido y construido con flexibilidad, permitiendo una adaptación sencilla a los cambios necesarios para incorporar nuevas funcionalidades y mejorar su portabilidad. Este objetivo se alcanzará mediante la aplicación rigurosa de los principios SOLID y garantizando una estructura bien organizada que mejore su legibilidad y mantenibilidad a lo largo del tiempo.
- Medición de la calidad: Los criterios para evaluar la modificabilidad del sistema abarcan varios aspectos clave. Estos incluyen la facilidad con la que los cambios pueden ser realizados sin impactar negativamente otras áreas del sistema, el tiempo y recursos necesarios para implementar dichos cambios, la habilidad de los desarrolladores para comprender y modificar el código existente, así como la estabilidad del sistema una vez que se han realizado las modificaciones.
- Resultado esperado: Se espera que el sistema de comercio electrónico se adapte fácilmente a los cambios necesarios para incorporar la nueva función de recomendaciones personalizadas. Estos cambios deben poder implementarse de forma rápida y eficiente, sin introducir errores o afectar negativamente la funcionalidad existente del sistema.

### 4. Tácticas de Arquitectura

El equipo de trabajo del proyecto para Hyun Seda, ha propuesto el uso de las siguientes tácticas para la arquitectura del sistema web:

- **Performance**: 
  - Gestión eficiente de recursos: Se implementará la estrategia de lazy loading para la carga de imágenes y otros recursos multimedia, asegurando que se carguen solo cuando sean necesarios. Esto reducirá el tiempo de carga inicial de la página y mejorará la experiencia del usuario.
  - Caching y almacenamiento en caché: Se integrará un sistema de caching para almacenar temporalmente datos y respuestas frecuentes, lo que reducirá la carga en el servidor y mejorará la velocidad de respuesta de la página.

- **Seguridad**:
  - Autenticación y autorización: Se utilizarán protocolos de autenticación y autorización robustos, como OAuth2 y JWT (JSON Web Tokens), para garantizar que solo los usuarios autorizados puedan acceder a las áreas restringidas del sistema.
  - Encriptación de datos: Se implementará la encriptación de datos sensibles, tanto en tránsito como en reposo, utilizando algoritmos de encriptación avanzados como AES (Advanced Encryption Standard).

- **Modificabilidad**:
  - Modularidad y separación de responsabilidades: El sistema se diseñará con una arquitectura modular, aplicando el principio de separación de responsabilidades (SoC, por sus siglas en inglés), donde cada módulo o componente tendrá una responsabilidad específica y bien definida. Esto facilitará la introducción de cambios y mejoras sin afectar otras partes del sistema.
  - Documentación y comentarios: Se promoverá una documentación clara y detallada del código, junto con comentarios explicativos en las secciones más complejas, para facilitar la comprensión y modificación por parte de los desarrolladores.

## Diagrama Entidad Relación

En el siguiente diagrama se presentan las entidades principales y las relaciones entre ellas en el sistema de gestión de Hyun Seda.

- **Imagen 6.** Diagrama Entidad Relación del sistema de gestión. Elaboración propia.

## Arquitectura del sistema

La arquitectura propuesta para el sistema de Hyun Seda se basa en el uso de una arquitectura modular y escalable, que permita la integración de nuevas funcionalidades y la adaptación a futuros requerimientos del negocio.

## Decisiones de arquitectura y su justificación

### Decisiones de arquitectura

En el desarrollo del sistema para Hyun Seda, se han tomado las siguientes decisiones arquitectónicas fundamentales:

### Estilo arquitectónico

#### Arquitectura MVC

- **Contexto:** La empresa Hyun Seda busca desarrollar una página web moderna y funcional para promocionar y vender sus productos.
- **Estímulo:** Se requiere una solución que permita la separación clara de las diferentes responsabilidades del sistema, facilitando su desarrollo, mantenimiento y escalabilidad.
- **Respuesta:** Se opta por la implementación de una arquitectura MVC (Modelo-Vista-Controlador), que promueve la separación de las responsabilidades en tres componentes principales:
  - Modelo: Gestiona los datos y la lógica de negocio.
  - Vista: Presenta la información al usuario.
  - Controlador: Maneja la interacción del usuario y coordina las acciones entre el modelo y la vista.
- **Medición de la calidad:** La calidad de la implementación de la arquitectura MVC se evaluará mediante la facilidad de desarrollo y mantenimiento del sistema, la capacidad de escalabilidad y la claridad en la separación de responsabilidades entre los diferentes componentes.
- **Resultado esperado:** Se espera que la arquitectura MVC proporcione una base sólida y flexible para el desarrollo del sistema, facilitando su crecimiento y adaptación a futuros requerimientos.

#### Arquitectura de Microservicios

- **Contexto:** Hyun Seda desea asegurar que su página web sea altamente modificable, legible y adaptable a diferentes entornos.
- **Estímulo:** Se necesita una solución que permita la integración de nuevas funcionalidades de manera ágil y eficiente, sin afectar el funcionamiento de otras partes del sistema.
- **Respuesta:** Se opta por una arquitectura de microservicios, donde el sistema se divide en pequeños servicios independientes que se comunican entre sí a través de APIs.
- **Medición de la calidad:** La calidad de la arquitectura de microservicios se medirá mediante la facilidad de integración de nuevas funcionalidades, la flexibilidad en el desarrollo y la capacidad de escalar de manera independiente los diferentes servicios.
- **Resultado esperado:** Se espera que la arquitectura de microservicios permita una rápida adaptación a los cambios y la integración de nuevas funcionalidades sin afectar la estabilidad y el rendimiento del sistema.

### Tipo de aplicación

La aplicación desarrollada para Hyun Seda será una **Single Page Application (SPA)**, la cual permitirá una experiencia de usuario más fluida y rápida, al cargar una sola vez el contenido principal y actualizar de manera dinámica el contenido según las interacciones del usuario.

### Tecnologías

Para el desarrollo del sistema se han seleccionado las siguientes tecnologías:

- **Frontend:** React.js, una biblioteca de JavaScript para construir interfaces de usuario interactivas y componentes reutilizables.
- **Backend:** Node.js y Express.js, un entorno de ejecución de JavaScript y un framework para construir aplicaciones web y APIs.
- **Base de datos:** MongoDB, una base de datos NoSQL que permite el almacenamiento flexible y escalable de datos.
- **Autenticación y autorización:** OAuth2 y JWT (JSON Web Tokens), para garantizar la seguridad en el acceso al sistema.
- **Hosting y despliegue:** AWS (Amazon Web Services), una plataforma en la nube que ofrece servicios escalables y de alta disponibilidad para el alojamiento del sistema.

## URL del repositorio de GitHub

El repositorio de GitHub donde se encuentra el código fuente del proyecto se puede acceder a través del siguiente enlace: [GitHub Hyun Seda](https://github.com/HyunSeda/Proyecto-HyunSeda)

