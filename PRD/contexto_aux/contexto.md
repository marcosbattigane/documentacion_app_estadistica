# Contexto del proyecto

El presente proyecto tiene como objetivo el desarrollo de una aplicación orientada a la recolección, procesamiento y análisis de estadísticas en el ámbito del básquet formativo. Surge a partir de la necesidad de entrenadores y cuerpos técnicos de contar con una herramienta simple pero potente que permita registrar datos de juego y transformarlos en información útil para la toma de decisiones.

Actualmente, muchos equipos trabajan con datos dispersos o registros manuales poco estructurados, lo que dificulta el análisis sistemático del rendimiento individual y colectivo. En este contexto, el sistema busca centralizar la información, automatizar cálculos estadísticos (como eficiencia ofensiva, PPP, porcentajes de tiro, rebotes, entre otros) y facilitar la visualización de métricas relevantes.

El proyecto consiste en el desarrollo de un software de análisis estadístico para entrenadores de básquet, diseñado para ser ejecutado como una aplicación de escritorio local utilizando Python, SQLite y algun otro lenguaje que permita la construccion de la aplicacion. El sistema permitirá la gestión integral de clubes, categorías y competencias, con el diferencial crítico de permitir la importación automatizada de planillas Excel desde plataformas externas como "Ges deportivo". El equipo de desarrollo está compuesto por 2 ingenieros enfocados en "empaquetar el conocimiento" del área deportiva en una herramienta profesional

## Tareas de documentacion en curso

En esta etapa del proyecto, el foco está puesto en la ingeniería de requerimientos y la definición estructurada del sistema, abordando los siguientes aspectos:

### Descripción General del Producto

Se está trabajando en la definición conceptual del sistema, incluyendo:

#### Planteamiento del problema

Identificación de las limitaciones actuales en la gestión de estadísticas deportivas en básquet formativo. Los entrenadores enfrentan barreras operativas que limitan su capacidad de análisis:

- Interferencia en el juego: La carga manual en tiempo real distrae al entrenador o requiere personal exclusivo.
- Ritmo frenético: La velocidad del básquet genera demoras en la toma de datos manual.
- Ceguera estadística: Los métodos actuales (papel/Excel básico) no calculan métricas avanzadas automáticamente ni identifican tendencias claras.
- Fragmentación: Falta de un repositorio histórico centralizado para comparar rivales o la evolución de jugadores.

#### Visión del producto

Desarrollo de una herramienta accesible, intuitiva y enfocada en entrenadores, que permita mejorar el análisis del juego sin requerir conocimientos técnicos avanzados.

Desarrollar una herramienta integral y accesible que automatice el registro de datos y potencie la capacidad analítica del cuerpo técnico, permitiendo un análisis profundo tanto en la cancha como en el hogar

#### Metas y no metas

Delimitación del alcance del sistema, definiendo qué funcionalidades serán abordadas en esta primera versión (por ejemplo, carga de partidos, estadísticas básicas) y cuáles quedan fuera (como análisis avanzado con IA o integración con sensores).

- Metas: Gestión organizativa completa, automatización de ingesta de datos vía Excel, motor de estadísticas avanzadas y herramientas de visualización gráfica.
- No Metas: Se evitará la complejidad excesiva en la versión inicial (v0.1) y el desarrollo de interfaces sobrecargadas que atenten contra la rapidez exigida por el usuario

#### Métricas de éxito

Establecimiento de indicadores que permitan evaluar el impacto del sistema, como la frecuencia de uso, reducción del tiempo de análisis, o mejora en la toma de decisiones deportivas.

El éxito se medirá por un tiempo de carga de datos menor a 20 minutos, una alta tasa de éxito en la automatización de archivos Excel y la capacidad del sistema para entregar informes que impacten directamente en la planificación estratégica

### Perfiles de Usuario

Se están identificando y caracterizando los distintos tipos de usuarios del sistema, principalmente:

- Entrenadores de categorías formativas
- Asistentes técnicos
- Coordinadores deportivos

Para cada perfil se analizan sus necesidades, objetivos, nivel de conocimiento técnico y contexto de uso, con el fin de orientar el diseño del sistema hacia una experiencia centrada en el usuario.

El usuario central es el Entrenador o Analista Estadístico:

- Contexto: Dirigen desde Mini básquet hasta categorías Profesionales
- Necesidad: Buscan centralizar métricas tradicionales y avanzadas para evaluar el progreso y planificar entrenamientos
- Comportamiento: Prefieren herramientas de "carga fácil" y que operen sin conexión a internet, dado que la conectividad en los estadios suele ser inestable

### Definición y Estructura de Hitos del Proyecto

Se está organizando el desarrollo mediante una estructura jerárquica que incluye:

- Hitos: Grandes etapas del proyecto (por ejemplo, prototipo funcional, sistema de carga de datos, módulo de análisis).
- Épicas: Conjuntos de funcionalidades relacionadas dentro de cada hito.
- Historias de usuario: Descripciones concretas de funcionalidades desde la perspectiva del usuario final.

Esta estructura permite planificar el desarrollo de manera incremental, facilitando la gestión del trabajo y el seguimiento del progreso.

El proyecto se organiza en fases que evolucionan las capacidades técnicas del software:

- Hito v0.1 - Carga y Persistencia: Foco en el modelo de datos (DER) y la gestión de entidades (Club, Jugador, Competencia).
- Hito v0.2 - Motor de Análisis: Implementación del motor estadístico y la importación de datos externos
- Hito v1.0 - Visualización y Entrega: Interfaz de usuario final, gráficos comparativos y empaquetado para distribución

Estructura de cada Hito: Incluirá objetivos de versión, Decisiones Arquitectónicas (ADR), épicas divididas en historias de usuario con sus respectivos Criterios de Aceptación (AC) verificables, y la definición de "Hecho" (Definition of Done).

### Requisitos No Funcionales

Se están definiendo las características de calidad del sistema, que incluyen:

- Usabilidad: interfaz clara y fácil de usar para usuarios no técnicos.
- Rendimiento: tiempos de respuesta adecuados para carga y consulta de datos.
- Escalabilidad: posibilidad de crecer en cantidad de usuarios y datos.
- Mantenibilidad: código organizado que permita futuras mejoras.
- Portabilidad: capacidad de ejecutarse en distintos entornos (por ejemplo, escritorio o web).

Son restricciones obligatorias que rigen la calidad del sistema:

- Despliegue: Aplicación de escritorio local
- Rendimiento: Latencia mínima en la interfaz; carga de partido en menos de 20 minutos
- Disponibilidad: Funcionamiento offline garantizado
- Adaptabilidad: Interfaz funcional en múltiples tamaños de pantalla (Celular/PC)

### Investigación y Definición de Architecture Decision Records (ADRs)

Se está iniciando la investigación y documentación de decisiones arquitectónicas clave mediante ADRs. Estos documentos permiten justificar y registrar elecciones técnicas importantes, tales como:

- Tipo de arquitectura del sistema (monolítica vs modular).
- Tecnologías a utilizar (lenguaje, base de datos, framework).
- Estrategia de almacenamiento y procesamiento de datos.
- Diseño de la base de datos (modelo relacional basado en DER ya trabajado).

El objetivo es establecer una base sólida para el desarrollo, evitando decisiones improvisadas y facilitando la evolución del sistema a largo plazo.
