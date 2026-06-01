---
name: Hito
about: Plantilla para el seguimiento de un Hito del proyecto
title: "[Hito] - "
labels: milestone
assignees: ""
---

## 🚀 Descripción del Hito

> Describe en 2-3 oraciones el objetivo estratégico del hito y qué capacidad nueva entrega al producto.

---

## 📋 Información General

| Campo               | Valor                          |
|---------------------|-------------------------------|
| **ID del Hito**     | H[N] (ej. H1, H2, H3…)       |
| **Versión objetivo**| v0.X / v1.0                   |
| **Esfuerzo total estimado** | ~XX días·persona      |
| **Épicas incluidas**| [cantidad]                    |
| **Historias incluidas** | [cantidad]                |

---

## 🎯 Objetivo del Hito

<!-- Qué debe ser verdad al finalizar este hito. Describe el estado del producto al cerrarlo. -->

---

## 🗂️ Épicas del Hito

| ID Épica | Nombre | Issues vinculados |
|----------|--------|-------------------|
| H[N]-E1  |        | #, #              |
| H[N]-E2  |        | #, #              |
| H[N]-E3  |        | #, #              |

---

## 📦 Historias de Usuario incluidas

<!-- Lista todas las US del hito con su enlace de issue -->

- [ ] #[issue] — US-[ID]: [Título]
- [ ] #[issue] — US-[ID]: [Título]
- [ ] #[issue] — US-[ID]: [Título]

---

## 🔗 Dependencias de Hito

<!-- ¿Este hito requiere que otro hito esté completo? -->

- Depende de: H[N-1] — [nombre del hito anterior]
- Bloquea: H[N+1] — [nombre del hito siguiente]

---

## ✅ Criterios de Finalización del Hito

> El hito se considera **Cerrado** cuando:

- [ ] Todas las historias de usuario incluidas tienen estado **Hecha** (DoD cumplido).
- [ ] El pipeline CI pasa en verde para la rama `release/vX.Y`.
- [ ] Los ADRs correspondientes al hito están aprobados y documentados.
- [ ] El catálogo de criticidad (`docs/catalogo-criticidad.md`) fue actualizado.
- [ ] Demo interna realizada y aprobada por el equipo técnico.
- [ ] `CHANGELOG.md` actualizado con los cambios del hito.

---

## 📎 Recursos y Referencias

<!-- Links a documentación relevante, ADRs, diagramas, etc. -->

- PRD: `PRD/Plan_Requerimientos_Producto_Pro.pdf`
- ADRs relacionados: ADR-00X, ADR-00X
