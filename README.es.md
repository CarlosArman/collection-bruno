<h1 align="center">collection-bruno 🧪🚀</h1>

<p align="center">
  <a href="https://github.com/CarlosArman/collection-bruno">
    <img src="https://img.shields.io/badge/Version-v1.0.0-blue" alt="Version" />
  </a>
  <a href="https://www.usebruno.com/">
    <img src="https://img.shields.io/badge/Bruno-API%20Client-6E56CF" alt="Bruno API Client" />
  </a>
  <a href="https://docs.usebruno.com/bru-cli/installation#npm">
    <img src="https://img.shields.io/badge/Bruno%20CLI-Docs-111827" alt="Bruno CLI Docs" />
  </a>
  <img src="https://img.shields.io/badge/Collections-Multi%20API-success" alt="Colecciones Multi API" />
  <img src="https://img.shields.io/badge/Status-Portfolio%20Ready-yellow" alt="Portfolio Ready" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Testing-API-1E88E5" alt="API Testing" />
  <img src="https://img.shields.io/badge/Execution-Desktop%20%7C%20CLI-informational" alt="Desktop and CLI Execution" />
  <img src="https://img.shields.io/badge/Variables-Dynamic%20%7C%20Runtime-F57C00" alt="Dynamic and Runtime Variables" />
  <img src="https://img.shields.io/badge/Reports-HTML-8A2BE2" alt="HTML Reports" />
  <a href="./LICENSE">
    <img src="https://img.shields.io/badge/License-Educational%20Use-blue" alt="License" />
  </a>
</p>

<p align="center"><b>🌐 Idioma</b></p>
<p align="center">
  <a href="./README.md">🇺🇸 English</a> &nbsp; | &nbsp; 🇪🇸 Español
</p>

<p align="center">
  Repositorio de colecciones de APIs de práctica diseñado para explorar, validar y automatizar requests usando <b>Bruno Desktop</b> y <b>Bruno CLI</b>, con environments reutilizables, variables dinámicas, variables runtime y generación de reportes HTML.
</p>

---

## 🎯 Por qué este proyecto importa

Este proyecto demuestra flujos prácticos de validación API usando **Bruno** como:

- cliente API ligero para validación interactiva
- herramienta CLI para ejecución reproducible desde consola
- forma de estructurar un workspace de colecciones multi-API
- complemento a frameworks de automatización basados en código como **Karate** y **Rest Assured**
- mecanismo simple de evidencia mediante reportes HTML

Es especialmente valioso como artefacto de portafolio QA porque muestra validación API fuera de frameworks code-first, manteniendo ejecución desde terminal, variables reutilizables y evidencia ligera.

---

## 🚀 Resumen del proyecto

Este repositorio contiene colecciones de práctica que pueden abrirse en **Bruno Desktop** o ejecutarse mediante **Bruno CLI**.

El objetivo es ofrecer un workspace reutilizable para:

- explorar APIs públicas
- validar requests y responses
- organizar environments y variables
- generar evidencia de ejecución con reportes HTML

🔗 **Repositorio:** https://github.com/CarlosArman/collection-bruno

---

## ✨ Qué demuestra este repositorio

### Valor funcional
- ✅ múltiples colecciones de APIs
- ✅ ejecución en Desktop + CLI
- ✅ configuración por environments
- ✅ variables runtime y dinámicas
- ✅ generación de reportes HTML

### Prácticas de ingeniería
- ✅ organización reutilizable de requests
- ✅ separación por environments
- ✅ generación dinámica de datos
- ✅ persistencia de variables entre requests
- ✅ ejecución orientada a terminal

### Valor para portafolio QA
- ✅ validación API con Bruno
- ✅ ejecución reproducible desde CLI
- ✅ organización clara de requests
- ✅ complemento útil a frameworks code-first de automatización API

---

## 📚 Colecciones incluidas

El workspace actual incluye estas colecciones:

- **Reqres**
- **Swagger Petstore**
- **BookStore**
- **Simple Books**
- **Booking**
- **DummyJson**
- **ServerRest**

APIs / referencias usadas en el workspace:

- **Reqres.in** → https://app.reqres.in/documentation
- **Swagger Petstore** → https://petstore.swagger.io/
- **Book Store API (DemoQA)** → https://bookstore.demoqa.com/swagger/
- **Simple Books API** → https://github.com/vdespa/introduction-to-postman-course/blob/main/simple-books-api.md
- **Restful Booker** → https://restful-booker.herokuapp.com/apidoc/index.html
- **DummyJSON** → https://dummyjson.com/
- **ServeRest API** → https://serverest.dev/?lang=es

---

## 🧰 Stack tecnológico

- **API Client:** Bruno Desktop
- **CLI:** Bruno CLI
- **Runtime:** Node.js
- **Versionado:** Git / GitHub
- **Modo de ejecución:** Desktop + Terminal
- **Salida de evidencia:** HTML reports

---

## 🏗 Estructura del proyecto

```bash
collection-bruno
├── Reqres/                      # Colección de Reqres
├── Swagger Petstore/            # Colección de Swagger Petstore
├── BookStore/                   # Colección de DemoQA Book Store
├── Simple Books/                # Colección de Simple Books API
├── Booking/                     # Colección de Restful Booker
├── DummyJson/                   # Colección de DummyJSON
├── ServerRest/                  # Colección de ServeRest API
├── docs/                        # Documentación adicional del proyecto
├── CHANGELOG.md                 # Historial de cambios en inglés
├── CHANGELOG.es.md              # Historial de cambios en español
├── CONTRIBUTING.md              # Guía de contribución en inglés
├── CONTRIBUTING.es.md           # Guía de contribución en español
├── README.md                    # Documentación principal en inglés
├── README.es.md                 # Documentación principal en español
└── LICENSE
```

---

## ⚙ Inicio rápido

### 1. Clonar el repositorio

```bash
git clone https://github.com/CarlosArman/collection-bruno.git
cd collection-bruno
```

### 2. Instalar Bruno Desktop

1. Descarga Bruno desde: https://www.usebruno.com/downloads
2. Instálalo según tu sistema operativo.
3. Abre Bruno.
4. Elige **Open Collection**.
5. Selecciona la carpeta del repositorio o el root de la colección que quieras usar.

### 3. Instalar Bruno CLI

Guía oficial de instalación:
https://docs.usebruno.com/bru-cli/installation#npm

Instalación rápida:

```bash
npm install -g @usebruno/cli
```

Verificar instalación:

```bash
bru --version
```

---

## ▶ Comandos principales

Para la referencia completa de comandos, revisa:
- **[docs/COMMANDS.es.md](./docs/COMMANDS.es.md)**
- **[docs/COMMANDS.md](./docs/COMMANDS.md)**

```bash
# Ejecutar una colección desde su carpeta raíz
bru run

# Generar un reporte HTML
bru run --reporter-html reporte.html

# Mostrar ayuda CLI
bru run -h

# Ejecutar usando developer sandbox
bru run --sandbox=developer
```

Ejemplo:

```bash
cd Booking
bru run --reporter-html booking-report.html
```

---

## 📊 Reportería y evidencia

Bruno CLI soporta generación de **reportes HTML**, ofreciendo evidencia ligera de ejecución.

```bash
bru run --reporter-html reporte.html
```

Esto es útil para:
- validar ejecución desde terminal
- conservar evidencia legible
- compartir resultados fácilmente

---

## 🧠 Estrategia de variables

Bruno soporta múltiples niveles de variables, incluyendo:

- Environment Variables
- Collection Variables
- Folder Variables
- Request Variables
- Runtime Variables
- Prompt Variables
- Dynamic Variables

Para ver ejemplos completos y uso práctico de variables, revisa:
- **[docs/VARIABLES.es.md](./docs/VARIABLES.es.md)**
- **[docs/VARIABLES.md](./docs/VARIABLES.md)**

---

## 🌱 Environments

Un environment típico en Bruno puede centralizar valores como:

```json
{
  "baseUrl": "https://restful-booker.herokuapp.com",
  "username": "admin",
  "password": "password123"
}
```

Uso típico:
- `{{baseUrl}}`
- `{{username}}`
- `{{password}}`
- variables runtime como `{{token}}` o `{{bookingId}}`

---

## ⭐ Buenas prácticas

- Usa nombres claros para los requests
- Agrupa requests por dominio (Auth, Users, Bookings)
- Centraliza URLs base y credenciales en environments
- Usa `bru.setVar()` para variables runtime temporales
- Usa variables dinámicas para datos únicos
- Genera reportes HTML para evidencia desde CLI

---

## 🔗 Proyectos relacionados

Este repositorio forma parte de un **portafolio más amplio de automatización API**, mostrando distintos enfoques para validación y automatización:

- **[PetStore_Karate](https://github.com/CarlosArman/PetStore_Karate)** — Proyecto de automatización API con **Karate DSL**, integrado con **GitHub Actions** y **GitHub Pages** para ejecución CI y reportería pública.
- **[karate-serverest-api-automation](https://github.com/CarlosArman/karate-serverest-api-automation)** — Framework modular de automatización API construido con **Karate DSL** para **ServeRest**, enfocado en schemas reutilizables, variables runtime y estructura escalable.
- **[ReqresRestAssured](https://github.com/CarlosArman/ReqresRestAssured)** — Proyecto de automatización API code-first construido con **Java, Maven, JUnit 5, Rest Assured y Cucumber**, usando **Maven Cucumber Reporting** para generar evidencia de ejecución contra la **API Reqres**.

En conjunto, estos proyectos demuestran experiencia práctica en:
- validación API basada en requests (Bruno)
- automatización API con DSL (Karate)
- automatización API code-first (Rest Assured + Cucumber)

---

## 📚 Índice de documentación

### Documentación principal
- **[docs/COMMANDS.es.md](./docs/COMMANDS.es.md)** → Referencia de comandos (Español)
- **[docs/COMMANDS.md](./docs/COMMANDS.md)** → Commands reference (English)
- **[docs/VARIABLES.es.md](./docs/VARIABLES.es.md)** → Guía de variables en Bruno (Español)
- **[docs/VARIABLES.md](./docs/VARIABLES.md)** → Bruno variables guide (English)
- **[docs/ENVIRONMENT.es.md](./docs/ENVIRONMENT.es.md)** → Guía de entorno (Español)
- **[docs/ENVIRONMENT.md](./docs/ENVIRONMENT.md)** → Environment guide (English)
- **[docs/ARCHITECTURE.es.md](./docs/ARCHITECTURE.es.md)** → Guía de arquitectura (Español)
- **[docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md)** → Architecture guide (English)

### Documentación del repositorio
- **[CHANGELOG.es.md](./CHANGELOG.es.md)** → Historial de cambios (Español)
- **[CHANGELOG.md](./CHANGELOG.md)** → Project changelog (English)
- **[CONTRIBUTING.es.md](./CONTRIBUTING.es.md)** → Guía de contribución (Español)
- **[CONTRIBUTING.md](./CONTRIBUTING.md)** → Contribution guide (English)

---

## 📄 Licencia

Este repositorio se comparte principalmente con fines educativos.

Para más información sobre permisos, limitaciones y uso, revisa el archivo **[LICENSE](./LICENSE)**.

---

## 👨‍💻 Autor

**Carlos R.**  
QA | Test Automation Engineer

🔗 GitHub: https://github.com/CarlosArman

---

## ⭐ Nota final

Este repositorio está estructurado intencionalmente para demostrar cómo **Bruno** puede utilizarse para validación API estructurada, variables reutilizables y evidencia ligera desde CLI en flujos QA.
