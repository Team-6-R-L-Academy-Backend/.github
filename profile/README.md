<h1>Backend para E-commerce - Team 6 R.L. Academy</h1>

<p>Este es el backend para un e-commerce diseñado en un entorno de colaboración utilizando la metodología Agile Scrum. El proyecto es parte de un curso en el que los equipos de frontend y backend trabajaron en conjunto para desarrollar una solución de tienda en línea. Los servicios fueron desplegados para ser consumidos por aplicaciones frontend, implementando autenticación básica y utilizando Spring Security con un filtro personalizado para generar y verificar tokens JWT.</p>

## Arquitectura

![Diagrama de Arquitectura](https://drive.google.com/uc?export=view&id=108cMvBN2_YkJelG_fotMMbMRPrbQs4Bp)

## Pantallas y contratos

![Pantalla de Productos](https://drive.google.com/uc?export=view&id=10BirTizdYLkunm4B5Op8ujiacPR3Vq1N)
![Pantalla de Login](https://drive.google.com/uc?export=view&id=10CTPOiL6wcnKMxBlkcB-fepzW6TUh85p)
![Pantalla de Login](https://drive.google.com/uc?export=view&id=10HaRjStbj4-XLKuxaKmBK36NGWIaw_cC)


<h2>Descripción</h2>

<p>El proyecto tiene una arquitectura basada en microservicios, que permite la gestión de productos, usuarios, comentarios y ventas de una tienda en línea. Cada microservicio tiene su propia base de datos y está diseñado para ser independiente. La arquitectura sigue un enfoque sencillo, sin servidor de autenticación separado. En su lugar, la API de usuarios maneja el registro y login, generando tokens JWT que luego se utilizan para autenticar las solicitudes a otros microservicios.</p>

<h3>Microservicios Implementados:</h3>
<ul>
  <li><strong>API de Usuarios</strong>: Gestión de usuarios, registro, login y generación de tokens JWT.</li>
  <li><strong>API de Productos</strong>: Gestión de productos disponibles en la tienda, incluyendo filtros de búsqueda, paginación, carga de productos y manejo de imágenes para mostrar en la app móvil.</li>
  <li><strong>API de Comentarios</strong>: Servicio precargado con datos de prueba para permitir a la app móvil consumir y mostrar comentarios.</li>
  <li><strong>API de Métodos de Pago</strong>: Servicio básico precargado con datos de métodos de pago para consumo por parte de la app móvil.</li>
</ul>

<h3>Características Principales:</h3>
<ul>
  <li><strong>Autenticación con JWT</strong>: Login y registro básico en la API de usuarios, generación de tokens JWT que se utilizan para validar las solicitudes a otros microservicios.</li>
  <li><strong>Microservicios desacoplados</strong>: Cada API es independiente y está diseñada para gestionar su propia funcionalidad.</li>
  <li><strong>Seguridad</strong>: Integración de Spring Security con un filtro personalizado para manejar la autenticación.</li>
  <li><strong>API de Productos</strong>: Incluye filtros de búsqueda, paginación y manejo de imágenes para cargar y mostrar en la app móvil.</li>
  <li><strong>Despliegue en Render</strong>: Los microservicios fueron desplegados utilizando Render, para ser consumidos por las aplicaciones frontend.</li>
  <li><strong>Swagger</strong>: Implementado para la documentación interactiva de los endpoints de la API.</li>
  <li><strong>Postman</strong>: Utilizado para probar los endpoints localmente y en los servicios desplegados en Render.</li>
</ul>

<h2>Arquitectura</h2>

<p>El siguiente diagrama representa la arquitectura de la solución:</p>
<ol>
  <li><strong>Cliente</strong>: El cliente (navegador o aplicación móvil) realiza solicitudes HTTP que incluyen un token JWT.</li>
  <li><strong>Servidor</strong>: El servidor procesa las solicitudes mediante un filtro personalizado de Spring Security.</li>
  <li><strong>Microservicios</strong>: Cada microservicio maneja una parte específica del sistema, como se detalla anteriormente.</li>
</ol>

<h2>Tecnologías Utilizadas:</h2>
<ul>
  <li><strong>Java 17</strong> y <strong>Spring Boot</strong> para el desarrollo de microservicios.</li>
  <li><strong>Spring Security</strong> con tokens JWT para autenticación.</li>
  <li><strong>PostgreSQL</strong> como base de datos para todos los microservicios.</li>
  <li><strong>Swagger</strong> para la documentación interactiva de los endpoints.</li>
  <li><strong>MapStruct</strong> para el mapeo de entidades y DTOs.</li>
  <li><strong>Docker</strong> para contenedorización y despliegue.</li>
  <li><strong>Maven</strong> como gestor de dependencias.</li>
  <li><strong>Postman</strong> para las pruebas de los endpoints locales y desplegados.</li>
  <li><strong>GitHub</strong> con Git Flow para control de versiones y gestión de ramas.</li>
  <li><strong>Trello</strong> para la organización del backlog y las tareas.</li>
  <li><strong>Metodología Scrum</strong>: Sprints de dos semanas con entregas continuas.</li>
</ul>

<h2>Colaboración con Frontend</h2>

<p>Los equipos de frontend desarrollaron una app móvil en <strong>Android Studio</strong> utilizando <strong>Kotlin</strong> como lenguaje de programación. La API fue consumida principalmente por esta app móvil, que hacía uso de los microservicios desarrollados en este backend para la funcionalidad de la tienda en línea.</p>

<h2>Base de Datos</h2>

<p>La base de datos <strong>PostgreSQL</strong> fue desplegada en Render y se utilizó un gestor de bases de datos para conectarse y ejecutar scripts. Aunque no se usó <strong>Flyway</strong> para la gestión de migraciones, se llevó un seguimiento manual de los scripts de base de datos, que puedes encontrar en cada proyecto dentro del folder <code>scripts</code>, donde se registraron las modificaciones y actualizaciones realizadas.</p>

<h2>Instalación y Ejecución</h2>

<ol>
  <li><strong>Clonar el repositorio</strong>:
    <pre><code>git clone https://github.com/Team-6-R-L-Academy-Backend</code></pre>
  </li>
  <li><strong>Instalar dependencias y compilar cada microservicio</strong>:
    <pre><code>cd api-users
mvn clean install
mvn spring-boot:run</code></pre>
    <p>Repite estos pasos para cada microservicio.</p>
  </li>
  <li><strong>Probar los endpoints</strong>:
    <ul>
      <li><strong>Usuarios</strong>: <a href="http://localhost:8080/api/users">http://localhost:8080/api/users</a></li>
      <li><strong>Productos</strong>: <a href="http://localhost:8081/api/products">http://localhost:8081/api/products</a></li>
    </ul>
    <p>Cada servicio requiere un token JWT para acceder, excepto el login y registro de usuarios.</p>
  </li>
</ol>


<h2>Despliegue</h2>

<p>Los microservicios se pueden desplegar en Render. Para cada servicio:</p>
<ol>
  <li><strong>Generar la imagen Docker</strong>:
    <pre><code>docker build -t api-users .</code></pre>
  </li>
  <li><strong>Ejecutar los servicios en Render o localmente con</strong>:
    <pre><code>docker-compose up</code></pre>
  </li>
</ol>

