---
name: Épica
about: Plantilla para definir una Épica dentro de un Hito
title: "[Épica] - "
labels: epic
assignees: ""
---

## 🗂️ Descripción de la Épica

> Describe el conjunto de funcionalidades que agrupa esta épica y qué problema resuelve a nivel de módulo o capa del sistema.

---

## 📋 Información General

| Campo                  | Valor                                      |
|------------------------|--------------------------------------------|
| **ID de la Épica**     | H[N]-E[M] (ej. H1-E1, H2-E3…)            |
| **Hito al que pertenece** | #[issue del hito] — H[N]: [Nombre]    |
| **Capa principal**     | Dominio / Aplicación / Infraestructura     |
| **Esfuerzo estimado**  | ~XX días·persona                           |
| **Prioridad**          | Urgente / Alta / Media / Baja             |

---

## 🎯 Objetivo de la Épica

<!-- Qué capacidad técnica u operativa entrega esta épica al finalizar. -->

---

## 📦 Historias de Usuario incluidas

<!-- Lista las US que componen esta épica -->

- [ ] #[issue] — US-[ID]: [Título] · `[XS/S/M/L]`
- [ ] #[issue] — US-[ID]: [Título] · `[XS/S/M/L]`
- [ ] #[issue] — US-[ID]: [Título] · `[XS/S/M/L]`

---

## 🔗 Dependencias

<!-- Épicas o issues que deben completarse antes que esta -->

| Tipo        | ID / Issue          | Descripción                        |
|-------------|---------------------|------------------------------------|
| Depende de  | #[issue] / US-[ID]  | [Por qué bloquea]                  |
| Bloquea     | #[issue] / Épica    | [Qué se desbloquea al terminar]    |

---

## 🏗️ Módulos y Capas Afectados

<!-- Qué partes del sistema toca esta épica -->

```
src/
  domain/
    interfaces/     # ports definidos/modificados
    entities/       # entidades afectadas
  application/
    use_cases/      # casos de uso incluidos
    dtos/           # DTOs nuevos o modificados
  infrastructure/
    persistence/    # repositorios / SQL
    analytics/      # si aplica
    ui/             # si aplica
tests/
  unit/
  integration/
```

---

## ✅ Criterios de Finalización de la Épica

> La épica se considera **Cerrada** cuando:

- [ ] Todas las historias de usuario incluidas tienen estado **Hecha** (DoD cumplido).
- [ ] Los contratos de interfaz (ports) no tienen cambios pendientes de aprobación.
- [ ] Tests de integración de la épica pasan en CI.
- [ ] Cobertura alcanza el umbral definido en el catálogo de criticidad para los módulos afectados.

---

## 📎 Recursos y Referencias

- Sección PRD: `Hito [N] > Épica H[N]-E[M]`
- ADRs relacionados: ADR-00X
