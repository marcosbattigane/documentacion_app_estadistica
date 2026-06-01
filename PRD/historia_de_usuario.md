---
name: Historia de Usuario
about: Plantilla para definir una Historia de Usuario del proyecto
title: "[US] - "
labels: user-story
assignees: ""
---

## 📝 Descripción

> Como **[rol]**, quiero **[funcionalidad]** para **[beneficio o resultado esperado]**.

---

## 📋 Información General

| Campo               | Valor                                                     |
|---------------------|-----------------------------------------------------------|
| **ID**              | US-[NNN]                                                  |
| **Épica**           | #[issue] — H[N]-E[M]: [Nombre de la épica]               |
| **Hito**            | #[issue] — H[N]: [Nombre del hito]                        |
| **Esfuerzo**        | XS (<1d) / S (1-2d) / M (3-5d) / L (6-10d)              |
| **Prioridad**       | Urgente / Alta / Media / Baja                            |
| **Dependencias**    | #[issue], US-[ID] (o `—` si no tiene)                    |
| **Capa principal**  | Dominio / Aplicación / Infraestructura                   |

---

## 🎯 Objetivo Funcional

<!-- Qué problema resuelve esta historia y qué capacidad habilita en el sistema. -->

---

## 📁 Archivos a Crear / Modificar

<!-- Lista cada archivo con su ruta completa y una descripción de su responsabilidad -->

| Archivo | Acción | Responsabilidad |
|---------|--------|-----------------|
| `src/.../.py` | Crear | |
| `src/.../.py` | Crear | |
| `tests/.../test_...py` | Crear | |

---

## ✅ Criterios de Aceptación

<!-- Cada AC debe ser verificable objetivamente. Usa la numeración AC1, AC2… -->

- [ ] **AC1.** 
- [ ] **AC2.** 
- [ ] **AC3.** 
- [ ] **AC4.** 

---

## ⚠️ Reglas de Negocio

<!-- Solo si aplican reglas del dominio específicas a esta historia. Eliminar sección si no aplica. -->

- 
- 

---

## 🧪 Testing Mínimo

<!-- Describe los tests requeridos para que esta US pueda considerarse Hecha -->

**Unitarios**
- [ ] 
- [ ] 

**Integración**
- [ ] 
- [ ] 

---

## 🏁 Definition of Done

> Esta historia está **Hecha** cuando:

- [ ] Código integrado en la rama principal sin conflictos.
- [ ] Tests unitarios e integración pasan en CI con cobertura ≥ umbral definido para el módulo.
- [ ] Se respeta la arquitectura de capas (sin imports cruzados entre `domain` e `infrastructure`).
- [ ] Si hay cambios SQL: vista/tabla versionada y cubierta por test de integración con datos semilla.
- [ ] Si persiste múltiples tablas: evidencia de transacción atómica y rollback probado.
- [ ] ADR correspondiente aprobado (si aplica).
- [ ] Métodos públicos nuevos documentados con docstring.
- [ ] Eventos de log relevantes implementados con `correlation_id`.
- [ ] Si incluye UI: validada manualmente en al menos dos plataformas.

---

## 📎 Recursos y Referencias

- Sección PRD: `Hito H[N] > Épica H[N]-E[M] > US-[NNN]`
- ADRs relacionados: ADR-00X
