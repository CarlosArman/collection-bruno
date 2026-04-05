# collection-bruno 🧪🚀

[![Bruno](https://img.shields.io/badge/Bruno-API%20Client-6E56CF?style=flat)](https://www.usebruno.com/)
[![Download Bruno](https://img.shields.io/badge/Download-Bruno-111827?style=flat)](https://www.usebruno.com/downloads)
[![Bruno CLI Docs](https://img.shields.io/badge/Bruno%20CLI-Docs-111827?style=flat)](https://docs.usebruno.com/bru-cli/installation#npm)

[![License](https://img.shields.io/badge/License-Educational%20Use-blue?style=flat)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/CarlosArman/collection-bruno?style=flat)](https://github.com/CarlosArman/collection-bruno/commits/main)
[![Repo Size](https://img.shields.io/github/repo-size/CarlosArman/collection-bruno?style=flat)](https://github.com/CarlosArman/collection-bruno)
[![Stars](https://img.shields.io/github/stars/CarlosArman/collection-bruno?style=flat)](https://github.com/CarlosArman/collection-bruno/stargazers)
[![Issues](https://img.shields.io/github/issues/CarlosArman/collection-bruno?style=flat)](https://github.com/CarlosArman/collection-bruno/issues)

**ES:** Repositorio con colecciones de APIs de práctica para explorar, probar y automatizar validaciones usando **Bruno (Desktop)** y/o ejecutar suites desde consola con **Bruno CLI**.  
**EN:** Repository with practice API collections to explore, test, and automate validations using **Bruno (Desktop)** and/or run suites from the terminal with **Bruno CLI**.

---

## 🌍 Languages / Idiomas

- [🇪🇸 Español](#-español)
- [🇺🇸 English](#-english)

---

# 🇪🇸 Español

## 📌 Colecciones incluidas

- **Reqres.in** → https://app.reqres.in/documentation
- **Swagger Petstore** → https://petstore.swagger.io/
- **Book Store API (DemoQA)** → https://bookstore.demoqa.com/swagger/
- **Simple Books API** → https://github.com/vdespa/introduction-to-postman-course/blob/main/simple-books-api.md
- **Restful Booker** → https://restful-booker.herokuapp.com/apidoc/index.html

---

## ✅ Requisitos

- Git
- Node.js LTS (recomendado para CLI, Node 18+)
- Bruno Desktop (si quieres usar interfaz gráfica)
- Bruno CLI (si quieres ejecutar desde consola y generar reportes)

---

## 🚀 Quick Start (Clonar → Instalar → Ejecutar → Reporte)

### 1) Clonar el repositorio

```bash
git clone https://github.com/CarlosArman/collection-bruno.git
cd collection-bruno
```

### 2) Instalar Bruno (Desktop)

1. Descarga Bruno desde: https://www.usebruno.com/downloads
2. Instálalo según tu sistema operativo.
3. Abre Bruno.
4. Selecciona **Open Collection**.
5. Elige la carpeta del repositorio o la carpeta raíz de la colección que quieras abrir.

### 3) Instalar Bruno CLI (Consola)

Guía oficial: https://docs.usebruno.com/bru-cli/installation#npm

Instalación rápida:

```bash
npm install -g @usebruno/cli
```

Verificar instalación:

```bash
bru --version
```

### 4) Ejecutar una colección completa desde la consola

Para correr una **colección completa**, navega al directorio raíz de esa colección y ejecuta:

```bash
bru run
```

Ejemplo:

```bash
cd collections/restful-booker
bru run
```

> Si tu repo no usa una carpeta `collections/`, ubica el folder que sea el **root** de la colección Bruno y ejecuta ahí `bru run`.

### 5) Generar un reporte HTML desde Bruno CLI

Para generar un reporte HTML legible, usa:

```bash
bru run --reporter-html nombreReporte.html
```

Ejemplo:

```bash
cd collections/restful-booker
bru run --reporter-html reporte-restful-booker.html
```

---

## 🧾 Opciones útiles de Bruno CLI

Ver ayuda:

```bash
bru run -h
```

Ejecutar en sandbox developer (si alguna colección requiere librerías externas o acceso al filesystem):

```bash
bru run --sandbox=developer
```

---

## 🧠 Variables en Bruno

Bruno soporta varios tipos de variables:

- **Environment Variables**
- **Collection Variables**
- **Folder Variables**
- **Request Variables**
- **Runtime Variables**
- **Prompt Variables**
- **Dynamic Variables**

### Orden de prioridad (de mayor a menor)
1. Runtime Variables
2. Request Variables
3. Folder Variables
4. Environment Variables
5. Collection Variables
6. Global Variables

---

## ✨ Variables dinámicas de Bruno

Las **variables dinámicas** permiten generar datos aleatorios automáticamente en tiempo de ejecución.  
La sintaxis es:

```text
{{$randomData}}
```

### Ejemplos comunes

```text
{{$randomFirstName}}
{{$randomLastName}}
{{$randomFullName}}
{{$randomEmail}}
{{$randomUserName}}
{{$randomUUID}}
{{$randomPhoneNumber}}
{{$randomCity}}
{{$randomCountry}}
{{$randomCompanyName}}
{{$randomJobTitle}}
{{$isoTimestamp}}
```

### Dónde se pueden usar
Puedes usarlas en:
- Body
- Query Params
- Path Params
- Headers
- Auth
- Scripts (con `bru.interpolate()`)

### Ejemplo en JSON body

```json
{
  "firstName": "{{$randomFirstName}}",
  "lastName": "{{$randomLastName}}",
  "email": "{{$randomEmail}}",
  "username": "{{$randomUserName}}",
  "id": "{{$randomUUID}}"
}
```

### Ejemplo en headers

```text
X-Request-Id: {{$randomUUID}}
X-User-Name: {{$randomFullName}}
```

### Ejemplo en query params

```text
?name={{$randomFirstName}}&city={{$randomCity}}
```

### Ejemplo en auth / credenciales

```json
{
  "username": "{{$randomUserName}}",
  "password": "{{$randomPassword}}"
}
```

---

## 🧪 Usar variables dinámicas dentro de scripts

Si quieres usar variables dinámicas dentro de un **Pre Request Script** o **Post Response Script**, usa `bru.interpolate()`:

```js
const firstName = bru.interpolate('{{$randomFirstName}}');
const email = bru.interpolate('{{$randomEmail}}');
const city = bru.interpolate('{{$randomCity}}');

console.log(firstName, email, city);
```

También puedes combinarlas con variables de environment o runtime:

```js
const fullMessage = bru.interpolate('Hola {{username}} desde {{$randomCity}}');
console.log(fullMessage);
```

---

## ✅ Ejemplos de variables dinámicas + runtime variables

### A) Guardar un token (Simple Books - CreateToken)

**Endpoint**
```http
POST https://simple-books-api.glitch.me/api-clients/
```

**Response típico**
```json
{
  "accessToken": "90f5767dd6bd1c1395d68b4346ac25dde92aab8a3531e57b0f2589610ba6f6eb"
}
```

**Script → Post Response**
```js
const data = res.body;
bru.setVar("simpleBooksToken", data.accessToken);
```

**Uso en requests siguientes**
```text
Authorization: Bearer {{simpleBooksToken}}
```

---

### B) Guardar un ID creado (Restful Booker)

**Endpoint**
```http
POST https://restful-booker.herokuapp.com/booking
```

**Body usando variables dinámicas**
```json
{
  "firstname": "{{$randomFirstName}}",
  "lastname": "{{$randomLastName}}",
  "totalprice": 100,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-04-10",
    "checkout": "2026-04-15"
  },
  "additionalneeds": "Breakfast"
}
```

**Response típico**
```json
{
  "bookingid": 1234,
  "booking": {
    "firstname": "John"
  }
}
```

**Script → Post Response**
```js
const data = res.body;
bru.setVar("bookingId", data.bookingid);
```

**Uso posterior**
```http
GET https://restful-booker.herokuapp.com/booking/{{bookingId}}
PUT https://restful-booker.herokuapp.com/booking/{{bookingId}}
DELETE https://restful-booker.herokuapp.com/booking/{{bookingId}}
```

---

### C) Guardar token de Auth y enviarlo como Cookie

**Endpoint**
```http
POST https://restful-booker.herokuapp.com/auth
```

**Body**
```json
{
  "username": "{{username}}",
  "password": "{{password}}"
}
```

**Script → Post Response**
```js
const data = res.body;
bru.setVar("token", data.token);
```

**Header**
```text
Cookie: token={{token}}
```

> Si tu API usa Bearer Token:
```text
Authorization: Bearer {{token}}
```

---

### D) Combinar variables dinámicas con runtime variables en Pre Request

```js
const firstName = bru.interpolate('{{$randomFirstName}}');
const lastName = bru.interpolate('{{$randomLastName}}');
const email = bru.interpolate('{{$randomEmail}}');

bru.setVar("randomFirstName", firstName);
bru.setVar("randomLastName", lastName);
bru.setVar("randomEmail", email);
```

Luego puedes reutilizarlas así:

```json
{
  "firstName": "{{randomFirstName}}",
  "lastName": "{{randomLastName}}",
  "email": "{{randomEmail}}"
}
```

---

## 🌱 Environments

Crea un **Environment** (por ejemplo: `local`, `qa`, `prod`) y define variables como:

```json
{
  "baseUrl": "https://restful-booker.herokuapp.com",
  "username": "admin",
  "password": "password123"
}
```

**Uso típico**
- URL: `{{baseUrl}}/booking`
- Auth: `{{username}}`, `{{password}}`
- Runtime vars: `{{token}}`, `{{bookingId}}`

---

## 🧪 Tests recomendados

- Validar status code esperado (`200`, `201`, `204`)
- Validar campos obligatorios (`id`, `token`, etc.)
- Validar tipos y valores
- Guardar variables desde response
- Reusar variables dinámicas entre requests

**Flujo sugerido para Restful Booker**
1. Auth → guardar `token`
2. Create Booking → guardar `bookingId`
3. Get / Update / Delete usando `{{bookingId}}`

---

## 🧱 Hecho con

- **Bruno Desktop**
- **Bruno CLI**
- **Node.js**
- **Git / GitHub**
- APIs públicas de práctica:
  - Reqres
  - Swagger Petstore
  - DemoQA Book Store
  - Simple Books API
  - Restful Booker

---

## ⭐ Buenas prácticas

- Usa nombres claros para requests  
  Ejemplo: `GET - List Users`, `POST - Create Booking`
- Agrupa por carpetas  
  Ejemplo: `Auth`, `Users`, `Bookings`
- Centraliza `baseUrl` y credenciales en environments
- Usa `bru.setVar()` para variables temporales
- Usa variables dinámicas para generar data de prueba única
- Genera reportes HTML para evidencia y CI

---

## 🤝 Contribución

1. Crea una rama:
```bash
git checkout -b feature/nueva-coleccion
```

2. Agrega o mejora la colección
3. Actualiza este README si aplica
4. Crea un Pull Request

---

[![License](https://img.shields.io/badge/License-Educational%20Use-blue?style=flat)](LICENSE)

## 📄 Licencia

Repositorio compartido principalmente con fines educativos.  
Para más información sobre permisos, limitaciones y uso, revisa el archivo [LICENSE](LICENSE).

---

# 🇺🇸 English

## 📌 Included Collections

- **Reqres.in** → https://app.reqres.in/documentation
- **Swagger Petstore** → https://petstore.swagger.io/
- **Book Store API (DemoQA)** → https://bookstore.demoqa.com/swagger/
- **Simple Books API** → https://github.com/vdespa/introduction-to-postman-course/blob/main/simple-books-api.md
- **Restful Booker** → https://restful-booker.herokuapp.com/apidoc/index.html

---

## ✅ Requirements

- Git
- Node.js LTS (recommended for CLI, Node 18+)
- Bruno Desktop (if you want the UI)
- Bruno CLI (if you want to run collections from terminal and generate reports)

---

## 🚀 Quick Start (Clone → Install → Run → Report)

### 1) Clone the repository

```bash
git clone https://github.com/CarlosArman/collection-bruno.git
cd collection-bruno
```

### 2) Install Bruno (Desktop)

1. Download Bruno from: https://www.usebruno.com/downloads
2. Install it for your OS.
3. Open Bruno.
4. Select **Open Collection**.
5. Choose the repository folder or the root folder of the collection you want to open.

### 3) Install Bruno CLI (Terminal)

Official guide: https://docs.usebruno.com/bru-cli/installation#npm

Quick install:

```bash
npm install -g @usebruno/cli
```

Verify installation:

```bash
bru --version
```

### 4) Run a full collection from terminal

To run an **entire collection**, navigate to that collection’s root directory and execute:

```bash
bru run
```

Example:

```bash
cd collections/restful-booker
bru run
```

> If your repo does not use a `collections/` folder, go to the Bruno collection **root folder** and run `bru run` there.

### 5) Generate an HTML report from Bruno CLI

To generate a human-readable HTML report, use:

```bash
bru run --reporter-html reportName.html
```

Example:

```bash
cd collections/restful-booker
bru run --reporter-html restful-booker-report.html
```

---

## 🧾 Useful Bruno CLI options

Show help:

```bash
bru run -h
```

Run in developer sandbox mode (if the collection needs external modules or filesystem access):

```bash
bru run --sandbox=developer
```

---

## 🧠 Variables in Bruno

Bruno supports several variable types:

- **Environment Variables**
- **Collection Variables**
- **Folder Variables**
- **Request Variables**
- **Runtime Variables**
- **Prompt Variables**
- **Dynamic Variables**

### Precedence order (highest to lowest)
1. Runtime Variables
2. Request Variables
3. Folder Variables
4. Environment Variables
5. Collection Variables
6. Global Variables

---

## ✨ Bruno Dynamic Variables

**Dynamic variables** let you generate random data automatically at runtime.  
The syntax is:

```text
{{$randomData}}
```

### Common examples

```text
{{$randomFirstName}}
{{$randomLastName}}
{{$randomFullName}}
{{$randomEmail}}
{{$randomUserName}}
{{$randomUUID}}
{{$randomPhoneNumber}}
{{$randomCity}}
{{$randomCountry}}
{{$randomCompanyName}}
{{$randomJobTitle}}
{{$isoTimestamp}}
```

### Where can they be used?
You can use them in:
- Body
- Query Params
- Path Params
- Headers
- Auth
- Scripts (with `bru.interpolate()`)

### Example in JSON body

```json
{
  "firstName": "{{$randomFirstName}}",
  "lastName": "{{$randomLastName}}",
  "email": "{{$randomEmail}}",
  "username": "{{$randomUserName}}",
  "id": "{{$randomUUID}}"
}
```

### Example in headers

```text
X-Request-Id: {{$randomUUID}}
X-User-Name: {{$randomFullName}}
```

### Example in query params

```text
?name={{$randomFirstName}}&city={{$randomCity}}
```

### Example in auth / credentials

```json
{
  "username": "{{$randomUserName}}",
  "password": "{{$randomPassword}}"
}
```

---

## 🧪 Using dynamic variables inside scripts

If you want to use dynamic variables inside a **Pre Request Script** or **Post Response Script**, use `bru.interpolate()`:

```js
const firstName = bru.interpolate('{{$randomFirstName}}');
const email = bru.interpolate('{{$randomEmail}}');
const city = bru.interpolate('{{$randomCity}}');

console.log(firstName, email, city);
```

You can also combine them with environment or runtime variables:

```js
const fullMessage = bru.interpolate('Hello {{username}} from {{$randomCity}}');
console.log(fullMessage);
```

---

## ✅ Dynamic variables + runtime variables examples

### A) Save a token (Simple Books - CreateToken)

**Endpoint**
```http
POST https://simple-books-api.glitch.me/api-clients/
```

**Typical response**
```json
{
  "accessToken": "90f5767dd6bd1c1395d68b4346ac25dde92aab8a3531e57b0f2589610ba6f6eb"
}
```

**Script → Post Response**
```js
const data = res.body;
bru.setVar("simpleBooksToken", data.accessToken);
```

**Use in following requests**
```text
Authorization: Bearer {{simpleBooksToken}}
```

---

### B) Save a created ID (Restful Booker)

**Endpoint**
```http
POST https://restful-booker.herokuapp.com/booking
```

**Body with dynamic variables**
```json
{
  "firstname": "{{$randomFirstName}}",
  "lastname": "{{$randomLastName}}",
  "totalprice": 100,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-04-10",
    "checkout": "2026-04-15"
  },
  "additionalneeds": "Breakfast"
}
```

**Typical response**
```json
{
  "bookingid": 1234,
  "booking": {
    "firstname": "John"
  }
}
```

**Script → Post Response**
```js
const data = res.body;
bru.setVar("bookingId", data.bookingid);
```

**Reuse**
```http
GET https://restful-booker.herokuapp.com/booking/{{bookingId}}
PUT https://restful-booker.herokuapp.com/booking/{{bookingId}}
DELETE https://restful-booker.herokuapp.com/booking/{{bookingId}}
```

---

### C) Save auth token and send it as Cookie

**Endpoint**
```http
POST https://restful-booker.herokuapp.com/auth
```

**Body**
```json
{
  "username": "{{username}}",
  "password": "{{password}}"
}
```

**Script → Post Response**
```js
const data = res.body;
bru.setVar("token", data.token);
```

**Header**
```text
Cookie: token={{token}}
```

> If your API uses Bearer Token:
```text
Authorization: Bearer {{token}}
```

---

### D) Combine dynamic variables with runtime variables in Pre Request

```js
const firstName = bru.interpolate('{{$randomFirstName}}');
const lastName = bru.interpolate('{{$randomLastName}}');
const email = bru.interpolate('{{$randomEmail}}');

bru.setVar("randomFirstName", firstName);
bru.setVar("randomLastName", lastName);
bru.setVar("randomEmail", email);
```

Then reuse them like this:

```json
{
  "firstName": "{{randomFirstName}}",
  "lastName": "{{randomLastName}}",
  "email": "{{randomEmail}}"
}
```

---

## 🌱 Environments

Create an **Environment** (for example: `local`, `qa`, `prod`) and define variables such as:

```json
{
  "baseUrl": "https://restful-booker.herokuapp.com",
  "username": "admin",
  "password": "password123"
}
```

**Typical usage**
- URL: `{{baseUrl}}/booking`
- Auth: `{{username}}`, `{{password}}`
- Runtime vars: `{{token}}`, `{{bookingId}}`

---

## 🧪 Recommended tests

- Validate expected status codes (`200`, `201`, `204`)
- Validate required fields (`id`, `token`, etc.)
- Validate types and values
- Save variables from responses
- Reuse dynamic variables across requests

**Suggested flow for Restful Booker**
1. Auth → save `token`
2. Create Booking → save `bookingId`
3. Get / Update / Delete using `{{bookingId}}`

---

## 🧱 Built With

- **Bruno Desktop**
- **Bruno CLI**
- **Node.js**
- **Git / GitHub**
- Public practice APIs:
  - Reqres
  - Swagger Petstore
  - DemoQA Book Store
  - Simple Books API
  - Restful Booker

---

## ⭐ Best Practices

- Use clear request names  
  Example: `GET - List Users`, `POST - Create Booking`
- Group requests into folders  
  Example: `Auth`, `Users`, `Bookings`
- Centralize `baseUrl` and credentials in environments
- Use `bru.setVar()` for temporary variables
- Use dynamic variables to generate unique test data
- Generate HTML reports for evidence and CI

---

## 🤝 Contributing

1. Create a branch:
```bash
git checkout -b feature/new-collection
```

2. Add or improve the collection
3. Update this README if needed
4. Create a Pull Request

---

[![License](https://img.shields.io/badge/License-Educational%20Use-blue?style=flat)](LICENSE)

## 📄 License

This repository is shared primarily for educational purposes.  
For more information about permissions, limitations, and usage, please review the [LICENSE](LICENSE) file.

---

## 🔗 Official Bruno Links

- Bruno Desktop download: https://www.usebruno.com/downloads
- Bruno CLI installation: https://docs.usebruno.com/bru-cli/installation#npm
- Run a collection with CLI: https://docs.usebruno.com/bru-cli/runCollection
- CLI options and reports (`--reporter-html`): https://docs.usebruno.com/bru-cli/commandOptions
- Runtime variables (`bru.setVar`): https://docs.usebruno.com/variables/runtime-variables
- Variables overview: https://docs.usebruno.com/variables/overview
- Dynamic variables: https://docs.usebruno.com/testing/script/dynamic-variables
- Vars Tab (Pre/Post): https://docs.usebruno.com/testing/script/vars
- JavaScript API Reference: https://docs.usebruno.com/v2/testing/script/javascript-reference