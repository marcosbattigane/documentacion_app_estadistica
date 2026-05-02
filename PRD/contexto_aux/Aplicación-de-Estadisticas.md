# Descripción General del proyecto

## Planteamiento del problema

El planteamiento del problema del sistema de análisis estadístico de básquet se centra en las **dificultades operativas y analíticas que enfrentan los entrenadores al momento de registrar y procesar la información** de sus partidos. Según las encuestas realizadas a los directores técnicos, los principales obstáculos actuales son:

1. **La carga manual de datos interfiere con el juego:** Registrar las estadísticas (ya sea en papel o en planillas como Excel) **demanda tener a una persona dedicada exclusivamente a esa tarea** o, en su defecto, provoca que el entrenador pierda la concentración en el partido por estar calculando porcentajes y llevando cuentas.
2. **Velocidad ante el ritmo frenético del básquet:** La dinámica tan rápida del deporte genera demoras importantes entre la carga de una estadística y la siguiente, dificultando un seguimiento en tiempo real.
3.  **Cálculo manual y falta de identificación de tendencias:** Los entrenadores pierden mucho tiempo al tener que **pasar el _boxscore_ de forma manual y calcular las estadísticas avanzadas por su cuenta**. Además, los métodos actuales no les permiten identificar numéricamente hacia dónde van las tendencias del juego ni detectar con rapidez los errores del equipo.
4.  **Falta de centralización y registros históricos:** Los técnicos manifiestan que **no hay un espacio virtual cómodo donde llevar el registro histórico** de las estadísticas, lo que dificulta comparar equipos rivales o evaluar la evolución de sus propios jugadores a lo largo del tiempo.
5.  **Herramientas inflexibles o aisladas:** Las aplicaciones existentes muchas veces no se adaptan al 100% a los sistemas de competencia locales, y los datos estadísticos que proveen otras plataformas (como "Ges deportivo") no se pueden integrar fácilmente sin trabajo manual.

Para dar solución a esta problemática, el proyecto plantea **desarrollar una aplicación de escritorio local utilizando Python y SQLite**. Este software buscará automatizar el flujo de trabajo de los entrenadores permitiéndoles crear sus clubes y categorías, registrar los partidos, y **absorber información automáticamente mediante la importación de planillas Excel**. De esta forma, el sistema integrará un motor de análisis que entregará **estadísticas acumuladas, métricas avanzadas (individuales y por equipo) y herramientas de visualización gráfica**, facilitando enormemente la toma de decisiones deportivas.

### Problema

1. **Ineficiencia en la captura**: Carga manual lenta y dependencia de plataformas externas ("Ges deportivo")
2. **Ceguera estadística**: Ausencia de cálculos automáticos de métricas avanzadas y comparativas
3. **Fragmentación y Accesibilidad**: Falta de un repositorio histórico centralizado que funcione sin internet

### Impacto operativo de los problemas

1. El entrenador pierde el foco táctico durante el juego y dedica demasiado tiempo post-partido a la transcripción
2. Decisiones deportivas basadas en intuición o datos básicos, perdiendo tendencias clave del rendimiento individual y grupal
3. Dispersión de datos (papel, Excel, apps); imposibilidad de trabajar en estadios con mala conectividad

### Linea base de los problemas

1. Carga manual > 20-40 min; 0% de automatización de importación de Excel
2. Uso de estadísticas tradicionales básicas; análisis avanzado realizado de forma manual o inexistente
3. 65% de usuarios requieren uso offline; datos aislados por partido sin acumulación histórica

## Vision del producto

La visión del producto del sistema de análisis estadístico es **desarrollar un software multiplataforma enfocado exclusivamente en facilitar el trabajo de los entrenadores de básquet, permitiendo su uso tanto en computadoras (PC/Notebook) como en dispositivos móviles (celulares y tablets)**.

El producto busca ser una herramienta integral, accesible desde cualquier dispositivo, que automatice el registro de datos y potencie la capacidad analítica del cuerpo técnico a través de los siguientes pilares:

1. **Accesibilidad y flexibilidad:** Proveer "acceso desde cualquier dispositivo" para que el entrenador pueda utilizar la herramienta tanto en la cancha durante las prácticas o partidos (usando celular o tablet) como en su casa para un análisis más profundo (usando PC/Notebook).
2. **Gestión organizativa completa:** Permitir a los usuarios crear un perfil, registrar su club, y administrar todas las categorías, competencias y listas de buena fe de los equipos.
3. **Ingesta de datos automatizada y manual:** Además del registro manual de estadísticas partido a partido, el software absorberá e interpretará automáticamente información proveniente de planillas Excel generadas por aplicaciones externas (como "Ges deportivo"), eliminando la carga manual y la pérdida de tiempo.
4. **Generación de estadísticas avanzadas:** Contar con un motor de análisis que procese la información para entregar resúmenes y calcular estadísticas acumuladas, tradicionales y avanzadas, tanto a nivel individual como a nivel de equipo.
5. **Visualización y toma de decisiones:** Integrar herramientas para comparar equipos y jugadores, filtrar estadísticas y mostrar gráficos claros que permitan identificar tendencias, evaluando el rendimiento a corto, mediano y largo plazo para asisitir en la toma de decisiones estratégicas.

## Metas y No metas

**Metas:**

1.  **Gestión organizativa completa:** Desarrollar un sistema donde el entrenador pueda crear su usuario, administrar su club, y gestionar todas las categorías, competencias, equipos y listas de buena fe.
2.  **Automatización en la ingesta de datos:** Implementar un módulo para importar e interpretar automáticamente planillas de Excel generadas por herramientas externas (como "Ges deportivo"), extrayendo la información para evitar la carga manual de los partidos.
3.  **Procesamiento de estadísticas avanzadas:** Construir un motor de análisis que no solo registre estadísticas básicas, sino que genere resúmenes de los partidos y calcule estadísticas acumuladas, tradicionales y avanzadas, tanto a nivel individual como de equipo.
4.  **Herramientas visuales para análisis:** Proveer una interfaz con gráficos, filtros y herramientas de comparación entre jugadores y equipos rivales, diseñada específicamente para asistir al entrenador en la lectura del juego y la toma de decisiones.

**No metas (Límites del proyecto y lo que queda fuera de alcance inicialmente):**

1.  **Sobrecarga de complejidad inicial:** El documento del proyecto establece explícitamente como límite **"evitar incorporar características demasiado complejas desde el inicio"**. No es meta construir el sistema definitivo de una sola vez, sino enfocarse estrictamente en las funcionalidades mínimas y necesarias para entregar una primera versión funcional.
2.  **Interfaces tediosas o lentas:** Basado en el relevamiento a los directores técnicos, una gran parte prefiere una aplicación "Simple y rápida", destacando como requisitos la "baja complejidad" y la "carga fácil". Por ende, desarrollar flujos de trabajo engorrosos o pantallas sobrecargadas va en contra de la premisa fundamental de la aplicación.

## Metricas de éxito

A partir de las respuestas de las encuestas realizadas a los directores técnicos y los objetivos de las fases del proyecto, el éxito de la aplicación se medirá implícitamente por el cumplimiento de los siguientes indicadores:

1.  **Tiempo de carga de datos:** La gran mayoría de los entrenadores encuestados indicó que solo están dispuestos a dedicar entre "menos de 10 minutos" y "10 - 20 minutos" para cargar los datos de un partido. El éxito operativo dependerá de que la interacción con el sistema no supere este umbral de tiempo.
2.  **Tasa de automatización exitosa:** Ante la pregunta de qué tan importante es automatizar la carga de datos (por ejemplo, desde otras plataformas), casi la totalidad de los usuarios lo calificó con un 4 o un 5 (máxima importancia). Lograr importar la información de los archivos Excel de "Ges deportivo" de manera precisa y sin requerir la carga manual será una métrica clave del proyecto.
3.  **Adopción por usabilidad (Simplicidad):** Al consultarles sobre sus preferencias, la tendencia dominante es elegir una aplicación "Simple y rapida" por sobre una "Completa pero mas compleja". Las exigencias de "baja complejidad", "carga fácil" e "interfaz amigable e intuitiva" son factores determinantes para que los entrenadores elijan usar la herramienta.
4.  **Accesibilidad multiplataforma:** La aplicación debe operar sin inconvenientes en una variedad de pantallas. El éxito en este punto se basa en cubrir la demanda de "acceso desde cualquier dispositivo", ya que los técnicos planean usarla combinando Celulares, Tablets y Notebooks/PC, tanto en sus casas como en la misma cancha.
5.  **Impacto analítico en la planificación:** A nivel deportivo, el sistema será exitoso si logra resolver la falta de identificación de tendencias. Esto se medirá por la capacidad de la aplicación para entregar informes con comparaciones entre rivales, evolución de jugadores en el tiempo, gráficos claros y cálculos rápidos que brinden una ayuda real para las planificaciones a futuro.
