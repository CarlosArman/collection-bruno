# Commands Reference

<p align="center">
  <a href="../README.md">⬅ Back to README (English)</a> •
  <a href="../README.es.md">⬅ Ir al README en Español</a> •
  <a href="./COMMANDS.es.md">🇪🇸 Ver esta guía en Español</a>
</p>

This document contains the main Bruno CLI commands currently relevant for the repository.

---

## 1. Install Bruno CLI

```bash
npm install -g @usebruno/cli
```

Verify installation:

```bash
bru --version
```

---

## 2. Run a Collection

Navigate to the collection root and run:

```bash
bru run
```

### Example

```bash
cd Booking
bru run
```

> Replace `Booking` with the real collection root you want to execute.

---

## 3. Generate an HTML Report

```bash
bru run --reporter-html report.html
```

### Example

```bash
cd Booking
bru run --reporter-html booking-report.html
```

---

## 4. CLI Help

```bash
bru run -h
```

Use this to inspect execution flags, CLI options, and supported parameters.

---

## 5. Developer Sandbox

```bash
bru run --sandbox=developer
```

Use this only if a collection requires external modules or filesystem access.

---

## 6. Suggested Typical Flows

### Default execution

```bash
bru run
```

### Execution with HTML report

```bash
bru run --reporter-html report.html
```

### Explore CLI options first

```bash
bru run -h
```
