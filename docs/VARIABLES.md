# Bruno Variables Guide

<p align="center">
  <a href="../README.md">⬅ Back to README (English)</a> •
  <a href="../README.es.md">⬅ Ir al README en Español</a> •
  <a href="./VARIABLES.es.md">🇪🇸 Ver esta guía en Español</a>
</p>

This document centralizes the variable strategy and examples used with Bruno collections.

---

## 1. Variable Types in Bruno

Bruno supports:

- **Environment Variables**
- **Collection Variables**
- **Folder Variables**
- **Request Variables**
- **Runtime Variables**
- **Prompt Variables**
- **Dynamic Variables**

### Precedence Order (highest to lowest)
1. Runtime Variables
2. Request Variables
3. Folder Variables
4. Environment Variables
5. Collection Variables
6. Global Variables

---

## 2. Dynamic Variables

Dynamic variables generate random data at runtime.

Syntax:

```text
{{$randomData}}
```

### Common Examples

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

### Where They Can Be Used
- Body
- Query Params
- Path Params
- Headers
- Auth
- Scripts (with `bru.interpolate()`)

---

## 3. Example Usage

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

### Credentials / Auth

```json
{
  "username": "{{$randomUserName}}",
  "password": "{{$randomPassword}}"
}
```

---

## 4. Using Dynamic Variables Inside Scripts

If you want to use dynamic variables inside a **Pre Request Script** or **Post Response Script**, use `bru.interpolate()`:

```js
const firstName = bru.interpolate('{{$randomFirstName}}');
const email = bru.interpolate('{{$randomEmail}}');
const city = bru.interpolate('{{$randomCity}}');

console.log(firstName, email, city);
```

You can combine them with environment or runtime variables:

```js
const fullMessage = bru.interpolate('Hello {{username}} from {{$randomCity}}');
console.log(fullMessage);
```

---

## 5. Runtime Variables with `bru.setVar()`

### Save a Token (Simple Books)

```js
const data = res.body;
bru.setVar("simpleBooksToken", data.accessToken);
```

Use later:

```text
Authorization: Bearer {{simpleBooksToken}}
```

### Save a Booking ID (Restful Booker)

```js
const data = res.body;
bru.setVar("bookingId", data.bookingid);
```

Reuse later:

```http
GET https://restful-booker.herokuapp.com/booking/{{bookingId}}
PUT https://restful-booker.herokuapp.com/booking/{{bookingId}}
DELETE https://restful-booker.herokuapp.com/booking/{{bookingId}}
```

### Save Auth Token as Cookie

```js
const data = res.body;
bru.setVar("token", data.token);
```

Header:

```text
Cookie: token={{token}}
```

Or, if required:

```text
Authorization: Bearer {{token}}
```

---

## 6. Environments

Example environment:

```json
{
  "baseUrl": "https://restful-booker.herokuapp.com",
  "username": "admin",
  "password": "password123"
}
```

Typical usage:
- `{{baseUrl}}/booking`
- `{{username}}`
- `{{password}}`
- runtime vars such as `{{token}}` and `{{bookingId}}`

---

## 7. Recommended Test Flow (Restful Booker)

1. Auth → save `token`
2. Create Booking → save `bookingId`
3. Get / Update / Delete using `{{bookingId}}`
