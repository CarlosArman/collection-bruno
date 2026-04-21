# Guía de Variables en Bruno

<p align="center">
  <a href="../README.es.md">⬅ Volver al README (Español)</a> •
  <a href="../README.md">⬅ Go to README in English</a> •
  <a href="./VARIABLES.md">🇺🇸 View this guide in English</a>
</p>

Este documento centraliza la estrategia de variables y ejemplos usados con las colecciones Bruno.

---

## 1. Tipos de variables en Bruno

Bruno soporta:

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

## 2. Variables dinámicas

Las variables dinámicas generan datos aleatorios en tiempo de ejecución.

Sintaxis:

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
- Body
- Query Params
- Path Params
- Headers
- Auth
- Scripts (con `bru.interpolate()`)

---

## 3. Ejemplos de uso

### JSON Body

```json
{
  "firstName": "{{$randomFirstName}}",
  "lastName": "{{$randomLastName}}",
  "email": "{{$randomEmail}}",
  "username": "{{$randomUserName}}",
  "id": "{{$randomUUID}}"
}
```

### Headers

```text
X-Request-Id: {{$randomUUID}}
X-User-Name: {{$randomFullName}}
```

### Query Params

```text
?name={{$randomFirstName}}&city={{$randomCity}}
```

### Credenciales / Auth

```json
{
  "username": "{{$randomUserName}}",
  "password": "{{$randomPassword}}"
}
```

---

## 4. Uso dentro de scripts

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

## 5. Variables runtime con `bru.setVar()`

### Guardar un token (Simple Books)

```js
const data = res.body;
bru.setVar("simpleBooksToken", data.accessToken);
```

Uso posterior:

```text
Authorization: Bearer {{simpleBooksToken}}
```

### Guardar un booking ID (Restful Booker)

```js
const data = res.body;
bru.setVar("bookingId", data.bookingid);
```

Reutilización:

```http
GET https://restful-booker.herokuapp.com/booking/{{bookingId}}
PUT https://restful-booker.herokuapp.com/booking/{{bookingId}}
DELETE https://restful-booker.herokuapp.com/booking/{{bookingId}}
```

### Guardar token de auth como Cookie

```js
const data = res.body;
bru.setVar("token", data.token);
```

Header:

```text
Cookie: token={{token}}
```

O, si aplica:

```text
Authorization: Bearer {{token}}
```

---

## 6. Environments

Ejemplo de environment:

```json
{
  "baseUrl": "https://restful-booker.herokuapp.com",
  "username": "admin",
  "password": "password123"
}
```

Uso típico:
- `{{baseUrl}}/booking`
- `{{username}}`
- `{{password}}`
- variables runtime como `{{token}}` y `{{bookingId}}`

---

## 7. Flujo recomendado de pruebas (Restful Booker)

1. Auth → guardar `token`
2. Create Booking → guardar `bookingId`
3. Get / Update / Delete usando `{{bookingId}}`
