<h1 align="center">
PASO A PASO BÁSICO PARA LA AUTOMATIZACIÓN DE UN PROYECTO, UTILIZANDO SELENIUM + JAVA + MAVEN + CUCUMBER(BDD) + SERENITY
</h1>

##  ESTRUCTURA BASE DEL PROYECTO, UTILIZANDO POM (PAGE OBJECT MODEL)

```text
ProyectoPrincipal/
├── pom.xml
├── serenity.properties
├── src/
│   ├── main/java/pe/tpidoweb/
│   │   ├── driver/
│   │   │   └── TPidoWebDriver.java        → Fábrica de WebDriver (Chrome/Firefox/Edge)
│   │   ├── menu/
│   │   │   └── MenuPrincipal.java         → Page Object del menú de navegación
│   │   └── pagina/
│   │       ├── base/
│   │       │   └── PaginaBase.java        → Clase padre de todos los Page Objects
│   │       ├── login/
│   │       │   ├── PaginaLogin.java
│   │       │   └── PaginaRegistro.java
│   │       └── pedido/
│   │           └── PaginaRegistrarPedido.java
│   └── test/
│       ├── java/pe/tpidoweb/
│       │   ├── clientes/insertar/
│       │   │   ├── RegistrarClientesStep.java   → Step Definitions
│       │   │   └── RegistrarClientesTest.java   → Runner (JUnit 5 Suite)
│       │   ├── pedidos/insertar/
│       │   │   ├── RegistrarPedidosStep.java
│       │   │   └── RegistrarPedidosTest.java
│       │   └── suite/
│       │       └── SuiteProductosTest.java      → Suite que agrupa ambos runners
│       └── resources/features/
│           ├── usuarios/insertar-usuarios.feature
│           └── pedidos/crear-pedido.feature 
```
## REGLA DE MAVEN:
- Todo lo que va en src/main/java es código de producción/librería (los Page Objects, en este caso, porque son reutilizables). 
- Todo lo que va en src/test/java es código de prueba (features, steps, runners).

<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0001.png" width="250">
</p> 


## 📌 ORDEN DE CREACIÓN EL PROYECTO DESDE 0

### Página de pruebas a utilizar
https://cmc86jstaling.pythonanywhere.com/

1. Lo primero que debemos realizar es crear un nuevo proyecto tipo MAVEN en el Ide de Eclipse.

<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0002.png" width="400">
</p>
<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0003.png" width="400">
</p>
<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0004.png" width="400">
</p>
<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0005.png" width="400">
</p>
<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0006.png" width="400">
</p>

2. Se procederá a realizar la configuración el archivo pom.xml, en el cual se configurarán las Propiedades, Dependencias y Builds que necesitemos utilizar en nuestro proyecto (Selenium, JUnit, Cucumber, Serenity, etc).

<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0007.png" width="800">
</p>

### Principales Propiedades a utilizar
<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0008.png" width="500">
</p>

<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0009.png" width="800">
</p>

### Principales Dependencias a utilizar
Las dependencias que necesitemos utilizar en nuestro proyecto, la podemos descargar desde: https://mvnrepository.com/

<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0010.png" width="800">
</p>

### Principales Builds a utilizar
Las builds que necesitemos configurar en nuestro proyecto, para el tema de ejecución de los Test y el proceso de Reportes.
<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0011.png" width="800">
</p>

Principalmente se usarán 2 builds en el proyecto base.
1. maven-failsafe-plugin: Ejecuta las clases que matchean los patrones **/*Test.java, **/Test*.java, **/*TestSuite.java, **/When*.java durante las fases integration-test y verify. Aquí es donde realmente se disparan los runners.

2. serenity-maven-plugin: genera el reporte HTML de Serenity (aggregate) en la fase post-integration-test, después de que Failsafe ejecuta las pruebas. 

## 🎓 SOCIALIZACIÓN DEL POR QUÉ USAR POSTMAN
<p align="center">
  
</p> 

## 🔹 OPCIONES DE CONSOLA DEL NAVEGADOR
