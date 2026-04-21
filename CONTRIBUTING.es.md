# Guía de contribución

<p align="center">
  <a href="./README.es.md">⬅ Volver al README (Español)</a> •
  <a href="./README.md">⬅ Go to README in English</a> •
  <a href="./CONTRIBUTING.md">🇺🇸 View this guide in English</a>
</p>

Gracias por tu interés en contribuir.

Este repositorio está enfocado en **colecciones educativas de APIs** usando Bruno, con énfasis en claridad, reutilización y valor práctico para QA.

---

## 1. Principios de contribución

Al contribuir, sigue estos principios:

- claridad sobre complejidad
- uso de environments y variables reutilizables
- nombres claros de requests y carpetas
- valor educativo por encima de sobre-ingeniería
- actualización de documentación cuando cambie el comportamiento

---

## 2. Tipos de contribución útiles

- agregar nuevas colecciones de APIs públicas
- mejorar colecciones existentes
- optimizar uso de variables dinámicas y runtime
- agregar ejemplos de scripts
- mejorar documentación
- mejorar ejemplos de reportería

---

## 3. Flujo sugerido

1. Haz fork del repositorio
2. Crea una rama de feature
3. Agrega o mejora una colección
4. Actualiza la documentación si aplica
5. Abre un Pull Request con una explicación clara

---

## 4. Ejemplos de nombres de rama

```bash
feature/add-dummyjson-collection
feature/improve-booking-flows
docs/update-bruno-variables-guide
```

---

## 5. Expectativas para Pull Requests

Un buen Pull Request debe explicar:

- qué se agregó o cambió
- por qué se agregó
- qué colección o API se ve afectada
- si se actualizó la documentación

---

## 6. Buenas prácticas

- agrupa requests por dominio (Auth, Users, Products, etc.)
- centraliza URLs base en environments
- evita credenciales hardcodeadas
- reutiliza variables runtime cuando sea posible
- mantén las colecciones fáciles de entender
