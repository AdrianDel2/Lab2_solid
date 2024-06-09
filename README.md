# Tercera Iteración de Software para Hyun Seda

**Ingeniería de Software 2**

**Presentado por:**
- Juan Esteban Muñoz Gómez
- Laura Sofía Botina Montero
- Adrián Fernando Delgado Serna
- Felipe Armand Pino Sierra

**Profesor:**
WILSON LIBARDO PANTOJA YEPEZ

**Universidad del Cauca**
**Facultad de Ingeniería Electrónica y Telecomunicaciones**
**Ingeniería de Sistemas**
**Popayán junio 2024**

---

## Contenido
1. Tercera Iteración de Software para Hyun Seda
2. Introducción
3. Requisitos Funcionales
4. Prototipos y test de usabilidad
    - 4.1. Prototipos de interfaces
    - 4.2. Test de usabilidad
5. Requisitos no funcionales
    - 5.1. Atributo de calidad 1 (Performance)
    - 5.2. Atributo de calidad 2 (Seguridad)
    - 5.3. Atributo de calidad 3 (Modificabilidad)
    - 5.4. Tácticas de Arquitectura
6. Diagrama Entidad Relación
7. Arquitectura del sistema
8. Decisiones de arquitectura y su justificación
    - 8.1. Decisiones de arquitectura
    - 8.2. Estilo arquitectónico
        - 8.2.1. Arquitectura MVC
        - 8.2.2. Arquitectura de Microservicios
    - 8.3. Tipo de aplicación
    - 8.4. Tecnologías
9. URL del repositorio de GitHub

---

## Introducción
En este documento se presenta un análisis detallado del proyecto de Hyun Seda, una empresa dedicada a la producción de seda sostenible de calidad y respetuosa con el medio ambiente, que ha evolucionado su modelo de negocio hacia un enfoque digital con el objetivo de expandir su alcance y aumentar su visibilidad en el mercado.

Además, conscientes de la importancia de una presencia en línea sólida, Hyun Seda ha contratado servicios tercerizados para el desarrollo de un ecommerce y la gestión de productos. Si bien esta decisión inicial fue tomada para cubrir necesidades inmediatas, como la preparación para un evento importante, se ha identificado la necesidad de una solución a largo plazo que sea autónoma y rentable.

En este contexto, se propone el diseño e implementación de un sistema propio que no solo cumpla con los requisitos funcionales y no funcionales del negocio, sino que también garantice la eficiencia, seguridad y escalabilidad necesarias para el crecimiento continuo de Hyun Seda. Este documento abordará aspectos clave como la arquitectura del sistema, las tecnologías seleccionadas y las pruebas de usabilidad con el fin de proporcionar una guía integral para el desarrollo exitoso de esta iniciativa.

---

## Requisitos Funcionales
Se hace referencia a la hoja de cálculo de HistoriasEpicas HyunSeda de la plantilla de historias de usuario.

Haga CRTL + CLIC: Tercer reporte HE HyunSeda.xlsx

---

## Prototipos y test de usabilidad

### Prototipos de interfaces
A continuación se presentan algunos prototipos de las interfaces del software.

**Imagen 1. Prototipo de la interfaz del menú del producto. Elaboración propia.**

**Imagen 2. Prototipo de la interfaz agregar producto. Elaboración propia.**

**Imagen 3. Prototipo de la interfaz de la tienda Hyun Seda. Elaboración propia.**

**Imagen 4. Prototipo de la interfaz buscar producto. Elaboración propia.**

### Test de usabilidad
A continuación se presenta el prototipo de la vista previa de los productos de la tienda como tal:

Y aquí se adjuntan los enlaces a los videos donde se hace la prueba de usabilidad:
- Haga CLIC + CTRL: video1.mp4
- Haga CLIC + CTRL: video2.mp4

---

## Requisitos no funcionales
Los requisitos no funcionales identificados mediante la aplicación de un Mini-QAW en conjunto con el cliente son los siguientes:

1. **Performance:** Con el aumento de productos o la expansión del catálogo, existe el riesgo de que la base de datos se vea sobrecargada. Por lo tanto, se requiere una optimización eficiente para la carga de imágenes, archivos y otros recursos, garantizando así un rendimiento óptimo del sistema.

2. **Seguridad:** Hay tres roles distintos en el sistema. Es crucial contar con un sistema de autenticación que permita identificar a los usuarios mediante su correo electrónico y contraseña. Además, se necesita una gestión de roles que garantice que cada usuario tenga acceso únicamente a las funcionalidades correspondientes a su rol asignado.

3. **Modificabilidad:** Se requiere que el sistema sea altamente adaptable y capaz de migrar sin inconvenientes a diferentes entornos. Debe estar diseñado con un bajo acoplamiento y una alta cohesión para garantizar que los componentes puedan ser modificados de forma independiente y que los cambios realizados sean fácilmente comprensibles.

4. **Escalabilidad:** Se requiere que el sistema sea escalable para manejar un aumento significativo en el tráfico y la carga de trabajo a medida que crezca el número de usuarios y productos en la plataforma. Esto implica implementar una arquitectura que pueda escalar horizontalmente añadiendo más servidores o recursos según sea necesario para mantener el rendimiento del sistema.

### Atributo de calidad 1 (Performance)
- **Contexto:** Con el objetivo de ampliar su alcance y mejorar la visibilidad de sus productos, Hyun Seda ha implementado una landing page que ofrece información detallada sobre el proceso de producción, la historia de la seda y datos de contacto. Además, se creó temporalmente un blog para compartir noticias relevantes y aumentar la visibilidad.
- **Estímulo:** Un usuario realiza una acción en el sitio web como cargar una página, agregar un producto al carrito de compras o procesar un pedido.
- **Respuesta:** La plataforma en línea de Hyun Seda requiere una solución para gestionar el almacenamiento de archivos multimedia que evite que la base de datos aumente exponencialmente de tamaño por la carga de imágenes, proporcionando una experiencia de usuario fluida y sin demoras significativas.
- **Medición de la calidad:** Los criterios para evaluar el desempeño del sistema incluyen el tiempo de carga de la página principal y de productos, y la eficiencia en el manejo de archivos multimedia. La calidad se medirá mediante la rapidez y consistencia en la experiencia del usuario, así como la capacidad para mantener un rendimiento óptimo.
- **Resultado esperado:** Se espera que la plataforma en línea de Hyun Seda proporcione un rendimiento confiable y eficiente en todo momento. Los tiempos de carga deben ser rápidos y consistentes, asegurando que los usuarios puedan explorar productos, leer el blog y realizar compras de manera rápida y sin inconvenientes.

### Atributo de calidad 2 (Seguridad)
- **Contexto:** Hyun Seda gestiona el acceso a la edición de las características de su página web a través de la implementación de tres roles distintos: editor, administrador y super administrador.
- **Estímulo:** Un usuario interno accede al dashboard de empleados de Hyun Seda utilizando una cuenta y las credenciales correspondientes para iniciar sesión.
- **Respuesta:** El sistema debe garantizar que únicamente los usuarios registrados tengan acceso al dashboard de empleados. Una vez se ha iniciado sesión, se mostrarán las utilidades correspondientes al rol del usuario.
- **Medición de la calidad:** La calidad se mide por la efectividad en la autenticación, asegurando que solo los usuarios autorizados tengan acceso al dashboard y que cada tipo de usuario solo tenga acceso o capacidad de manipulación de lo que refiere a su jerarquía de usuario o la de un nivel jerárquico más profundo.
- **Resultado esperado:** El sistema garantiza que solo los usuarios autenticados y autorizados tengan acceso al dashboard que le corresponde con base en las credenciales ingresadas.

### Atributo de calidad 3 (Modificabilidad)
- **Contexto:** La empresa Hyun Seda ha desarrollado una página web para promocionar y vender sus productos. Desea asegurar que su página web sea altamente modificable, legible y adaptable a diferentes entornos.
- **Estímulo:** Un nuevo desarrollador se incorpora al equipo de Hyun Seda y necesita familiarizarse con el código y la arquitectura del sistema web existente para comenzar a trabajar en la implementación de nuevas características.
- **Respuesta:** El sistema debe ser concebido y construido con flexibilidad, permitiendo una adaptación sencilla a los cambios necesarios para incorporar nuevas funcionalidades y mejorar su portabilidad. Este objetivo se alcanzará mediante la aplicación rigurosa de los principios SOLID y garantizando una estructura bien organizada que mejore su legibilidad y mantenibilidad a lo largo del tiempo.
- **Medición de la calidad:** Los criterios para evaluar la modificabilidad del sistema incluyen la facilidad con la que los cambios pueden ser realizados sin impactar negativamente otras áreas del sistema, el tiempo y recursos necesarios para implementar dichos cambios, la habilidad de los desarrolladores para comprender y modificar el código existente, así como la estabilidad del sistema una vez que se han realizado las modificaciones.
- **Resultado esperado:** Se espera que el sistema de comercio electrónico se adapte fácilmente a los cambios necesarios para incorporar la nueva función de recomendaciones personalizadas. Estos cambios deben poder implementarse de forma rápida y eficiente, sin introducir errores o afectar negativamente la funcionalidad existente del sistema.

### Atributo de calidad 4 (Escalabilidad)
- **Contexto:** Con el continuo crecimiento de la empresa Hyun Seda y su presencia en línea, se anticipa un aumento en el tráfico de usuarios y la carga de trabajo en la plataforma web.
- **Estímulo:** A medida que el número de usuarios que acceden a la plataforma aumenta, también lo hace la cantidad de productos en el catálogo y las transacciones que se procesan en el sistema.
- **Respuesta:** La arquitectura del sistema debe estar diseñada para escalar horizontalmente, permitiendo agregar más recursos o servidores según sea necesario para manejar el incremento en el tráfico y la carga de trabajo sin sacrificar el rendimiento ni la disponibilidad del sistema.
- **Medición de la calidad:** Los criterios para evaluar la escalabilidad del sistema incluyen la capacidad para manejar un incremento significativo en el número de usuarios y transacciones, el tiempo de respuesta del sistema bajo cargas elevadas y la efectividad de la solución de escalamiento implementada.
- **Resultado esperado:** Se espera que el sistema de comercio electrónico de Hyun Seda mantenga un rendimiento óptimo y una disponibilidad constante, incluso durante picos de tráfico y cargas de trabajo elevadas. La capacidad de escalar horizontalmente asegura que el sistema pueda crecer de manera eficiente con la demanda.

### Tácticas de Arquitectura

1. **Performance:**
   - Se utilizarán técnicas de caching y compresión para mejorar los tiempos de carga.
   - Se implementará una CDN (Content Delivery Network) para distribuir el contenido estático eficientemente.
   - Se utilizarán estrategias de paginación y carga diferida para manejar grandes volúmenes de datos.
   
2. **Seguridad:**
   - Se implementarán mecanismos de autenticación y autorización robustos.
   - Se utilizará cifrado para proteger datos sensibles.
   - Se establecerán políticas de gestión de acceso y roles basadas en principios de mínimo privilegio.
   
3. **Modificabilidad:**
   - Se aplicarán los principios SOLID para garantizar un diseño de software flexible y mantenible.
   - Se implementará una arquitectura modular que facilite la adición y modificación de componentes sin afectar el sistema en su totalidad.
   - Se utilizarán patrones de diseño como el de inyección de dependencias para mejorar la flexibilidad y la prueba del sistema.

4. **Escalabilidad:**
   - Se adoptará una arquitectura de microservicios que permita escalar componentes individuales según sea necesario.
   - Se implementará un balanceador de carga para distribuir el tráfico de manera eficiente.
   - Se utilizarán contenedores y orquestadores como Docker y Kubernetes para facilitar el escalamiento y la gestión de los servicios.

---

## Diagrama Entidad Relación
(Se muestra un diagrama E-R con las tablas y sus relaciones correspondientes).

---

## Arquitectura del sistema
La arquitectura del sistema se basará en una combinación de MVC (Model-View-Controller) y Microservicios para aprovechar los beneficios de ambos estilos arquitectónicos.

### Diagrama de Arquitectura del Sistema

**Imagen 5. Diagrama de arquitectura del sistema. Elaboración propia.**

---

## Decisiones de arquitectura y su justificación

### Decisiones de arquitectura
1. **Arquitectura MVC (Model-View-Controller):** Se ha decidido utilizar la arquitectura MVC para el desarrollo de la aplicación web debido a sus beneficios en la separación de responsabilidades y la facilidad de mantenimiento.
2. **Microservicios:** Se ha optado por una arquitectura de microservicios para permitir un desarrollo y despliegue más flexible y escalable de los componentes del sistema.

### Estilo arquitectónico

#### Arquitectura MVC
**Imagen 6. Diagrama MVC. Elaboración propia.**

El estilo arquitectónico MVC (Model-View-Controller) es utilizado para dividir la aplicación en tres componentes principales, cada uno de los cuales se encarga de una funcionalidad específica:
- **Modelo:** Gestiona los datos y la lógica del negocio.
- **Vista:** Se encarga de la presentación y la interfaz de usuario.
- **Controlador:** Maneja la entrada del usuario y actualiza el modelo y la vista en consecuencia.

#### Arquitectura de Microservicios
**Imagen 7. Diagrama de Microservicios. Elaboración propia.**

La arquitectura de microservicios permite que la aplicación esté compuesta por pequeños servicios autónomos que se comunican entre sí a través de APIs. Cada servicio se encarga de una funcionalidad específica, lo que facilita la escalabilidad y el mantenimiento del sistema.

### Tipo de aplicación
La aplicación será una plataforma de comercio electrónico que permitirá a Hyun Seda gestionar su catálogo de productos, procesar pedidos y proporcionar una experiencia de compra en línea a sus clientes.

### Tecnologías
Se utilizarán las siguientes tecnologías para el desarrollo del sistema:
- **Frontend:** React.js para la creación de interfaces de usuario interactivas y responsivas.
- **Backend:** Node.js con Express.js para la creación de APIs RESTful y la lógica del servidor.
- **Base de datos:** MongoDB para el almacenamiento de datos no relacionales y escalables.
- **Autenticación y Autorización:** JSON Web Tokens (JWT) para la gestión segura de sesiones y permisos de usuario.
- **Despliegue y Orquestación:** Docker y Kubernetes para la creación y gestión de contenedores.

---

## URL del repositorio de GitHub
[GitHub Repository](https://github.com/HyunSeda/ecommerce)

