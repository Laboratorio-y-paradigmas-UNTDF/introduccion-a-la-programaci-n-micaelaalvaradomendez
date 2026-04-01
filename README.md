[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/kv2H-9A5)
[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=23388605)
# TP 03 — Programación Funcional: TypeScript + Clojure
**Paradigmas y Lenguajes de Programación 2026 — UNTDF / IDEI**

## Objetivo

Implementar 50 ejercicios de programación funcional en dos lenguajes:
- **25 ejercicios en TypeScript** — estilo funcional puro, mostrando el contraste con el paradigma imperativo
- **25 ejercicios en Clojure** — funcional puro, con las estructuras persistentes e inmutables nativas de Clojure

---

## Restricciones de estilo — TypeScript

En todos los ejercicios TypeScript:

| ❌ Prohibido | ✅ Permitido |
|---|---|
| `let`, `var` | `const` siempre |
| `for`, `while`, `do...while` | `map`, `filter`, `reduce`, recursión |
| `.push()`, `.pop()`, `.splice()` | spread: `[...arr, nuevo]` |
| `.sort()` in-place sobre el parámetro | `[...arr].sort(comparador)` |
| Mutar objetos recibidos (`obj.x = y`) | spread: `{ ...obj, x: y }` |

---

## Estructura del Repo

```
tp03-funcional/
├── typescript/
│   ├── src/
│   │   └── index.ts          ← Implementá tus soluciones aquí
│   ├── tests/
│   │   ├── g1/ (TS-01 a TS-05 — Funciones Puras)
│   │   ├── g2/ (TS-06 a TS-10 — Inmutabilidad)
│   │   ├── g3/ (TS-11 a TS-18 — map/filter/reduce)
│   │   ├── g4/ (TS-19 a TS-22 — Composición y HOF)
│   │   └── g5/ (TS-23 a TS-25 — Contraste Imperativo vs Funcional)
│   ├── package.json
│   ├── tsconfig.json
│   └── jest.config.ts
└── clojure/
    ├── src/
    │   └── ejercicios/
    │       └── core.clj      ← Implementá tus soluciones aquí
    ├── test/
    │   └── ejercicios/
    │       ├── grupo1_test.clj
    │       ├── grupo2_test.clj
    │       ├── grupo3_test.clj
    │       ├── grupo4_test.clj
    │       └── grupo5_test.clj
    └── project.clj
```

---

## Dónde implementar

### TypeScript
Abrí `typescript/src/index.ts`. Cada función tiene un stub con `throw new Error("No implementado")`.  
Reemplazá el `throw` con tu implementación. **No modificar las firmas de las funciones.**

### Clojure
Abrí `clojure/src/ejercicios/core.clj`. Cada función tiene un stub con `(throw ...)`.  
Reemplazá el `throw` con tu implementación. **No modificar los nombres de las funciones.**

---

## Setup local

### TypeScript

**Requisitos:** Node.js 18+, npm

```bash
cd typescript
npm install
```

### Clojure

**Requisitos:** Java 11+, Leiningen

```bash
# Instalar Leiningen: https://leiningen.org/
cd clojure
lein deps   # descarga dependencias
```

---

## Ejecutar los tests localmente

### TypeScript — todos los tests

```bash
cd typescript
npx jest --no-coverage
```

### TypeScript — un grupo específico

```bash
cd typescript
npx jest tests/g1 --no-coverage   # G1: Funciones Puras
npx jest tests/g2 --no-coverage   # G2: Inmutabilidad
npx jest tests/g3 --no-coverage   # G3: map/filter/reduce
npx jest tests/g4 --no-coverage   # G4: Composición y HOF
npx jest tests/g5 --no-coverage   # G5: Contraste Imperativo
```

### TypeScript — un ejercicio específico

```bash
cd typescript
npx jest tests/g1/ts-01 --no-coverage --verbose
```

### Clojure — todos los tests

```bash
cd clojure
lein test
```

### Clojure — un grupo específico

```bash
cd clojure
lein test ejercicios.grupo1-test
lein test ejercicios.grupo2-test
lein test ejercicios.grupo3-test
lein test ejercicios.grupo4-test
lein test ejercicios.grupo5-test
```

---

## Cómo entregar

1. Aceptá el assignment desde el link que te mandó tu docente
2. GitHub va a crear un repo personal en tu cuenta dentro de la organización
3. Cloná tu repo:
   ```bash
   git clone https://github.com/UNTDF-LabProg/<tu-repo>
   ```
4. Implementá las soluciones en:
   - `typescript/src/index.ts`
   - `clojure/src/ejercicios/core.clj`
5. Hacé commit y push. GitHub Classroom ejecuta los tests automáticamente con cada push:
   ```bash
   git add -A
   git commit -m "feat: implementar ejercicios TS G1"
   git push
   ```
6. Verificá que aparecen los checks ✅ en la pestaña **Actions** de tu repo
7. **Antes del deadline:** asegurate de que tu último push fue antes de la fecha límite

---

## Puntuación

| Grupo | Ejercicios | Puntos |
|-------|------------|--------|
| TS-G1 Funciones Puras | TS-01 a TS-05 | 10 pts |
| TS-G2 Inmutabilidad | TS-06 a TS-10 | 10 pts |
| TS-G3 map/filter/reduce | TS-11 a TS-18 | 16 pts |
| TS-G4 Composición y HOF | TS-19 a TS-22 | 8 pts |
| TS-G5 Contraste | TS-23 a TS-25 | 6 pts |
| CLJ-G1 Funciones básicas | CLJ-01 a CLJ-05 | 10 pts |
| CLJ-G2 map/filter/reduce | CLJ-06 a CLJ-11 | 12 pts |
| CLJ-G3 HOF | CLJ-12 a CLJ-16 | 10 pts |
| CLJ-G4 Recursión | CLJ-17 a CLJ-20 | 8 pts |
| CLJ-G5 Colecciones | CLJ-21 a CLJ-25 | 10 pts |
| **Total** | | **100 pts** |

Cada grupo se evalúa como unidad: todos los tests del grupo deben pasar.

---

## Consejo

Implementá y testeá localmente antes de hacer push. El feedback de GitHub Actions aparece en minutos, pero es más eficiente trabajar localmente primero.

Para consultas: seguir el canal de la materia o las horas de consulta del auxiliar.
