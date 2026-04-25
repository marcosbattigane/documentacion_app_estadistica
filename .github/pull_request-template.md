# Pull Request — Documentación (ADRs / DER / Diccionario de Datos / PDR)

> [!IMPORTANT]
> Antes de pedir review:
>
> - linkeá la tarea/issue correspondiente (o dejá explícito el motivo del cambio)
> - asignate esta PR
> - compilá el/los PDF localmente (o en CI) y verificá que no haya errores/warnings relevantes
> - si tocás **ADRs**, asegurate de seguir el formato y el estado correcto (Proposed/Accepted/Deprecated/Superseded)
> - si tocás **DER** o **diccionario de datos**, asegurate de mantener consistencia con la versión vigente del modelo
> - adjuntá evidencia (PDF generado / captura / log de build)
> - borrá todo este bloque antes de abrir la PR

---

## Tipo de cambio (docs)

<!-- Marcá al menos una opción -->

- [ ] ADR (nuevo)
- [ ] ADR (actualización)
- [ ] DER / Modelo (diagrama)
- [ ] Diccionario de datos
- [ ] PDR (capítulo/sección)
- [ ] Corrección editorial (typos, redacción)
- [ ] Reorganización / estructura
- [ ] Build / CI de LaTeX
- [ ] Assets (imágenes, fuentes, bibliografía)
- [ ] Otro (describir)

---

## Issue / tarea relacionada

<!-- Recomendado: linkear la tarea o issue asociada.
Usar referencias como:
- Closes #12
- Fixes #8
- Related #21 -->

- Closes #
- Related #

---

## Resumen del cambio

<!-- TL;DR (2 a 5 líneas). Que se entienda sin leer el diff. -->

## Este PR

## Alcance y motivación

<!-- Qué se necesitaba documentar/cambiar y por qué. -->

## Contexto

## Motivación / problema

## Resultado esperado

---

## Cambios incluidos (lista concreta)

## <!-- Lista escaneable; idealmente con rutas -->

-
-

## Estructura / navegación (si aplica)

<!-- Si moviste/renombraste archivos o cambiaste el índice/TOC -->

- [ ] No aplica
- [ ] Actualicé índice / tabla de contenidos
- [ ] Actualicé referencias internas (\ref/\label) y links
- [ ] Actualicé la bibliografía (BibTeX/Biber)

## Detalle

---

## ADR (si aplica)

<!-- Completar solo si el cambio incluye ADRs -->

- [ ] No aplica
- [ ] ADR nuevo
- [ ] ADR actualizado
- [ ] Cambié estado (Proposed/Accepted/Deprecated/Superseded)

ADR(s) afectado(s)

- `docs/adr/ADR-XXXX-...tex` (o .md si corresponde)

Decisión / registro

- Decisión:
- Alternativas consideradas:
- Consecuencias / trade-offs:
- Referencias:

---

## DER / Modelo de datos (si aplica)

<!-- Completar si cambiaste el DER o el modelo -->

- [ ] No aplica
- [ ] Actualicé DER
- [ ] Cambié entidades/relaciones
- [ ] Cambié cardinalidades / constraints documentadas
- [ ] Alineado con diccionario de datos

Archivos / fuentes (ejemplos)

- Diagrama: `docs/der/...`
- Export: `docs/assets/...` (png/pdf/svg)
- Fuente editable (si existe): `docs/der/source/...`

Notas de consistencia

- Impacto en entidades:
- Impacto en relaciones:
- Inconsistencias conocidas (si las hay):

## Diccionario de datos (si aplica)

<!-- Completar si cambiaste el diccionario -->

- [ ] No aplica
- [ ] Agregué campos/atributos
- [ ] Cambié definiciones existentes
- [ ] Agregué reglas/validaciones
- [ ] Agregué ejemplos

Campos afectados (tabla opcional)

- Tabla/Entidad:
- Campo:
- Tipo:
- Descripción:
- Reglas:
- Ejemplo:

---

## Build LaTeX / PDF

<!-- Obligatorio: dejar evidencia de que compila -->

### Qué se generó

- [ ] No aplica (no hay PDFs en este repo)
- [ ] PDF principal (PDR)
- [ ] PDFs por módulo/capítulo
- [ ] Anexos

### Comando(s) usados

<!-- Pegá el comando exacto -->

```bash
# Ejemplo:
# make pdf
# latexmk -pdf -interaction=nonstopmode main.tex
```

### Resultado del build

- [ ] OK sin warnings
- [ ] OK con warnings no relevantes (justificar)
- [ ] Requiere acción (no debería mergearse)

## Warnings/errores relevantes (si hubo)

---

## Evidencia

<!-- Adjuntá pruebas verificables -->

- [ ] No aplica
- [ ] PDF adjunto / link a artifact de CI
- [ ] Capturas (secciones clave)
- [ ] Log del build (latexmk / make)
- [ ] Diff visual (si se usa alguna herramienta)

Links / artifacts

- PDF/Artifact:
- CI Run:
- Capturas:

## Checklist del autor (docs)

- [ ] Linkeé la issue / tarea (o expliqué el motivo del cambio)
- [ ] Me asigné esta PR
- [ ] El cambio tiene un objetivo claro y acotado
- [ ] No mezclé cambios no relacionados
- [ ] Revisé mi propio diff antes de pedir review
- [ ] Compilé LaTeX y verifiqué el/los PDF(s)
- [ ] No dejé referencias rotas (\ref, \cite, links)
- [ ] No dejé assets huérfanos o sin uso
- [ ] Mantengo consistencia de términos (glosario/nombres)
- [ ] Actualicé índice/TOC si correspondía
- [ ] Si aplica, mantuve DER ↔ diccionario ↔ texto del PDR consistentes

---

## Checklist de review

<!-- Ajustá roles según tu equipo -->

- [ ] Review editorial (claridad, ortografía, consistencia)
- [ ] Review técnica (ADRs: decisión y consecuencias)
- [ ] Review de datos (DER y diccionario: consistencia)
- [ ] Validación de build (PDF compila / artifacts OK)

Reviewer(s):

- R1:
- R2:
- R3:

---

## Notas para el reviewer

Orden sugerido de revisión:

1.
2.
3.

## Puntos donde quiero feedback

-

## Dudas abiertas
