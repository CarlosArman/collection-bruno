# Referencia de comandos

<p align="center">
  <a href="../README.es.md">⬅ Volver al README (Español)</a> •
  <a href="../README.md">⬅ Go to README in English</a> •
  <a href="./COMMANDS.md">🇺🇸 View this guide in English</a>
</p>

Este documento contiene los principales comandos de Bruno CLI actualmente relevantes para el repositorio.

---

## 1. Instalar Bruno CLI

```bash
npm install -g @usebruno/cli
```

Verificar instalación:

```bash
bru --version
```

---

## 2. Ejecutar una colección

Navega al root de la colección y ejecuta:

```bash
bru run
```

### Ejemplo

```bash
cd Booking
bru run
```

> Reemplaza `Booking` por la carpeta raíz real de la colección que quieras ejecutar.

---

## 3. Generar un reporte HTML

```bash
bru run --reporter-html reporte.html
```

### Ejemplo

```bash
cd Booking
bru run --reporter-html booking-report.html
```

---

## 4. Ayuda CLI

```bash
bru run -h
```

Úsalo para revisar flags de ejecución, opciones CLI y parámetros soportados.

---

## 5. Developer Sandbox

```bash
bru run --sandbox=developer
```

Úsalo solo si una colección requiere módulos externos o acceso al filesystem.

---

## 6. Flujos típicos sugeridos

### Ejecución por defecto

```bash
bru run
```

### Ejecución con reporte HTML

```bash
bru run --reporter-html reporte.html
```

### Revisar opciones CLI primero

```bash
bru run -h
```
