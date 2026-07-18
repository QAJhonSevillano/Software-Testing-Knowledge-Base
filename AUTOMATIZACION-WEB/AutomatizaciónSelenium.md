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

2. Se procederá a realizar la configuración el archivo pom.xml, en el cual se configurarán las propiedades y dependencias que necesitemos utilizar en nuestro proyecto (Selenium, JUnit, Cucumber, Serenity, etc).

<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0007.png" width="800">
</p>

### Principales propiedades a utilizar
<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0008.png" width="500">
</p>

<p align="center">
  <img src="../assets/selenium/AUTOMATIZACION-WEB-0009.png" width="800">
</p>


## 🎓 SOCIALIZACIÓN DEL POR QUÉ USAR POSTMAN
<p align="center">
  
</p> 

## 🔹 OPCIONES DE CONSOLA DEL NAVEGADOR
