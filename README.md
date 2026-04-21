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
  <img src="https://img.shields.io/badge/Collections-Multi%20API-success" alt="Multi API Collections" />
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

<p align="center"><b>🌐 Language / Idioma</b></p>
<p align="center">
  🇺🇸 English &nbsp; | &nbsp; <a href="./README.es.md">🇪🇸 Español</a>
</p>

<p align="center">
  Repository of practice API collections designed to explore, validate, and automate requests using <b>Bruno Desktop</b> and <b>Bruno CLI</b>, with reusable environments, dynamic variables, runtime variables, and HTML report generation.
</p>

---

## 🎯 Why This Project Matters

This project demonstrates practical API validation workflows using **Bruno** as:

- a lightweight **API client** for interactive validation
- a **CLI-driven execution tool** for reproducible terminal runs
- a way to structure **multi-API collections** in a reusable workspace
- a complement to code-based automation frameworks such as **Karate** and **Rest Assured**
- a simple mechanism for execution evidence through **HTML reports**

It is especially valuable as a QA portfolio artifact because it shows practical API validation outside of code-first frameworks, while still supporting reusable environments, scripts, variables, and CLI-based evidence generation.

---

## 🚀 Project Overview

This repository contains practice API collections that can be:

- explored interactively with **Bruno Desktop**
- executed from terminal using **Bruno CLI**
- validated using environments, dynamic variables, runtime variables, and scripts
- documented through lightweight **HTML reports**

🔗 **Repository:** https://github.com/CarlosArman/collection-bruno

---

## ✨ What This Repository Demonstrates

### Functional Value
- ✅ Multi-API collections
- ✅ Desktop + CLI execution
- ✅ Environment-based configuration
- ✅ Runtime and dynamic variables
- ✅ HTML report generation

### Engineering Practices
- ✅ Reusable request organization
- ✅ Environment separation
- ✅ Dynamic test data generation
- ✅ Runtime variable persistence across requests
- ✅ Terminal-friendly collection execution

### QA Portfolio Value
- ✅ API validation with Bruno
- ✅ Reproducible CLI execution
- ✅ Clear request organization
- ✅ Useful complement to code-based API automation frameworks

---

## 📚 Included Collections

The current workspace includes these collections:

- **Reqres**
- **Swagger Petstore**
- **BookStore**
- **Simple Books**
- **Booking**
- **DummyJson**
- **ServerRest**

Reference APIs / sources used across the workspace:

- **Reqres.in** → https://app.reqres.in/documentation
- **Swagger Petstore** → https://petstore.swagger.io/
- **Book Store API (DemoQA)** → https://bookstore.demoqa.com/swagger/
- **Simple Books API** → https://github.com/vdespa/introduction-to-postman-course/blob/main/simple-books-api.md
- **Restful Booker** → https://restful-booker.herokuapp.com/apidoc/index.html
- **DummyJSON** → https://dummyjson.com/
- **ServeRest API** → https://serverest.dev/?lang=en

---

## 🧰 Tech Stack

- **API Client:** Bruno Desktop
- **CLI:** Bruno CLI
- **Runtime:** Node.js
- **Version Control:** Git / GitHub
- **Execution Mode:** Desktop + Terminal
- **Evidence Output:** HTML reports

---

## 🏗 Project Structure

```bash
collection-bruno
├── Reqres/                      # Reqres collection
├── Swagger Petstore/            # Swagger Petstore collection
├── BookStore/                   # DemoQA Book Store collection
├── Simple Books/                # Simple Books API collection
├── Booking/                     # Restful Booker collection
├── DummyJson/                   # DummyJSON collection
├── ServerRest/                  # ServeRest API collection
├── docs/                        # Additional project documentation
├── CHANGELOG.md                 # Project changelog
├── CHANGELOG.es.md              # Historial de cambios
├── CONTRIBUTING.md              # Contribution guide
├── CONTRIBUTING.es.md           # Guía de contribución
├── README.md                    # Main documentation in English
├── README.es.md                 # Main documentation in Spanish
└── LICENSE
```

---

## ⚙ Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/CarlosArman/collection-bruno.git
cd collection-bruno
```

### 2. Install Bruno Desktop

1. Download Bruno from: https://www.usebruno.com/downloads
2. Install it for your operating system.
3. Open Bruno.
4. Choose **Open Collection**.
5. Select the repository folder or the collection root you want to use.

### 3. Install Bruno CLI

Official installation guide:
https://docs.usebruno.com/bru-cli/installation#npm

Quick install:

```bash
npm install -g @usebruno/cli
```

Verify installation:

```bash
bru --version
```

---

## ▶ Main Commands

For the full command reference, see:
- **[docs/COMMANDS.md](./docs/COMMANDS.md)**
- **[docs/COMMANDS.es.md](./docs/COMMANDS.es.md)**

```bash
# Run a collection from its root folder
bru run

# Generate an HTML report
bru run --reporter-html report.html

# Show CLI help
bru run -h

# Run using developer sandbox
bru run --sandbox=developer
```

Example:

```bash
cd Booking
bru run --reporter-html booking-report.html
```

---

## 📊 Reporting and Evidence

Bruno CLI supports **HTML report generation**, providing lightweight execution evidence.

```bash
bru run --reporter-html report.html
```

This is useful for:
- validating execution from terminal
- keeping readable evidence
- sharing results easily

---

## 🧠 Variable Strategy

Bruno supports multiple variable scopes, including:

- Environment Variables
- Collection Variables
- Folder Variables
- Request Variables
- Runtime Variables
- Prompt Variables
- Dynamic Variables

For full variable examples and practical usage, see:
- **[docs/VARIABLES.md](./docs/VARIABLES.md)**
- **[docs/VARIABLES.es.md](./docs/VARIABLES.es.md)**

---

## 🌱 Environments

A typical Bruno environment can centralize values such as:

```json
{
  "baseUrl": "https://restful-booker.herokuapp.com",
  "username": "admin",
  "password": "password123"
}
```

Typical usage:
- `{{baseUrl}}`
- `{{username}}`
- `{{password}}`
- runtime variables such as `{{token}}` or `{{bookingId}}`

---

## ⭐ Best Practices

- Use clear request names
- Group requests by domain (Auth, Users, Bookings)
- Centralize base URLs and credentials in environments
- Use `bru.setVar()` for temporary runtime variables
- Use dynamic variables for unique request data
- Generate HTML reports for CLI evidence

---

## 🔗 Related Projects

This repository is part of a broader **API automation portfolio**, showing different approaches to API validation and automation:

- **[PetStore_Karate](https://github.com/CarlosArman/PetStore_Karate)** — API automation project using **Karate DSL**, integrated with **GitHub Actions** and **GitHub Pages** for CI execution and public reporting.
- **[karate-serverest-api-automation](https://github.com/CarlosArman/karate-serverest-api-automation)** — Modular API automation framework built with **Karate DSL** for **ServeRest**, focused on reusable schemas, runtime variables, and scalable test structure.
- **[ReqresRestAssured](https://github.com/CarlosArman/ReqresRestAssured)** — Code-based API automation project built with **Java, Maven, JUnit 5, Rest Assured, and Cucumber**, using **Maven Cucumber Reporting** for execution evidence against the **Reqres API**.

Together, these projects demonstrate practical experience with:
- request-based API validation (Bruno)
- DSL-driven API automation (Karate)
- code-first API automation (Rest Assured + Cucumber)

---

## 📚 Documentation Index

### Core docs
- **[docs/COMMANDS.md](./docs/COMMANDS.md)** → Commands reference (English)
- **[docs/COMMANDS.es.md](./docs/COMMANDS.es.md)** → Commands reference (Spanish)
- **[docs/VARIABLES.md](./docs/VARIABLES.md)** → Bruno variables guide (English)
- **[docs/VARIABLES.es.md](./docs/VARIABLES.es.md)** → Guía de variables en Bruno (Español)
- **[docs/ENVIRONMENT.md](./docs/ENVIRONMENT.md)** → Environment guide (English)
- **[docs/ENVIRONMENT.es.md](./docs/ENVIRONMENT.es.md)** → Guía de entorno (Español)
- **[docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md)** → Architecture guide (English)
- **[docs/ARCHITECTURE.es.md](./docs/ARCHITECTURE.es.md)** → Guía de arquitectura (Español)

### Repository docs
- **[CHANGELOG.md](./CHANGELOG.md)** → Project changelog (English)
- **[CHANGELOG.es.md](./CHANGELOG.es.md)** → Historial de cambios (Español)
- **[CONTRIBUTING.md](./CONTRIBUTING.md)** → Contribution guide (English)
- **[CONTRIBUTING.es.md](./CONTRIBUTING.es.md)** → Guía de contribución (Español)

---

## 📄 License

This repository is shared primarily for educational purposes.

For more information about permissions, limitations, and usage, review the **[LICENSE](./LICENSE)** file.

---

## 👨‍💻 Author

**Carlos R.**  
QA | Test Automation Engineer

🔗 GitHub: https://github.com/CarlosArman

---

## ⭐ Final Note

This repository is intentionally structured to demonstrate how **Bruno** can be used for structured API validation, reusable variables, and lightweight CLI-based execution evidence in QA workflows.
