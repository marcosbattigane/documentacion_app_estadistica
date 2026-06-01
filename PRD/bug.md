---
name: Bug
about: Reportar un error o comportamiento inesperado en el sistema
title: "[Bug] - "
labels: bug
assignees: ""
---

## 🐛 Descripción del Bug

> Describe de forma clara y concisa qué comportamiento incorrecto se observó.

---

## 📋 Información General

| Campo              | Valor                                                              |
|--------------------|--------------------------------------------------------------------|
| **Severidad**      | 🔴 Crítico / 🟠 Alta / 🟡 Media / 🟢 Baja                        |
| **Módulo afectado**| Persistencia / Analítica / Ingesta / Auth / CLI / GUI / Reporting |
| **Capa afectada**  | Dominio / Aplicación / Infraestructura                            |
| **US relacionada** | US-[ID] (si se puede identificar)                                 |
| **Versión/Rama**   | `main` / `release/vX.Y` / `feature/…`                            |
| **Reproducible**   | Siempre / A veces / Una sola vez                                  |

---

## 🔁 Pasos para Reproducir

<!-- Secuencia mínima y exacta para ver el error -->

1. 
2. 
3. 
4. 

---

## ❌ Comportamiento Actual

<!-- Qué ocurre cuando se siguen los pasos anteriores -->

---

## ✅ Comportamiento Esperado

<!-- Qué debería ocurrir según las reglas de negocio o los criterios de aceptación -->

---

## 🌍 Entorno

| Campo            | Valor                                     |
|------------------|-------------------------------------------|
| **OS**           | Windows 10+ / Linux / macOS / Android    |
| **Python**       | 3.X.X                                     |
| **Versión app**  |                                           |
| **BD (esquema)** | schema_version = X                        |

---

## 📋 Logs Relevantes

<!-- Pega aquí el fragmento de log relacionado. Elimina datos sensibles antes de pegar. -->

```
[TIMESTAMP] [NIVEL] correlation_id=... mensaje de error
```

---

## 📸 Capturas de Pantalla

<!-- Si aplica, adjunta imágenes que ilustren el problema -->

---

## 🔍 Análisis Inicial (opcional)

<!-- Si ya tenés una hipótesis sobre la causa raíz, describila aquí -->

**Hipótesis:**

**Archivos sospechosos:**
- `src/.../`

---

## 🏷️ Criterio de Resolución

> Este bug se considera **Resuelto** cuando:

- [ ] El comportamiento descrito ya no es reproducible con los pasos indicados.
- [ ] Existe un test de regresión que valida el fix y falla sin el parche.
- [ ] El fix pasa el pipeline CI completo (lint + tests + cobertura).
- [ ] Si el bug involucra datos corruptos: procedimiento de migración/corrección documentado.

---

## 📎 Referencias

- Issue relacionado (US o Épica): #[issue]
- ADR involucrado (si aplica): ADR-00X
