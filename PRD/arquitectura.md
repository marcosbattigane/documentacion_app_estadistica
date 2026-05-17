# Arquitectura del Sistema: StatsPro Basketball

## 1. Introducción

Para cumplir con los requerimientos de **portabilidad**, **testabilidad** y **ejecución local-first** definidos en el PRD, el sistema adopta una **Arquitectura Limpia (Clean Architecture)** con un enfoque **Hexagonal**.

Esta estructura permite que la lógica de negocio (reglas del básquet y cálculos estadísticos) sea independiente de la base de datos (SQLite), de la interfaz de usuario (CLI o GUI) y de las librerías externas (Pandas).

---

## 2. Capas de la Aplicación

### 2.1 Capa de Dominio (`src/domain`)

Es el corazón del sistema. No tiene dependencias de ninguna librería externa ni de otras capas.

- **Entidades (`entities/`):** Clases puras de Python (o `dataclasses`) que representan los objetos del negocio: `Jugador`, `Club`, `Partido`, `Estadistica`.
- **Interfaces / Puertos (`interfaces/`):** Definiciones de contratos mediante `typing.Protocol`. Aquí se define qué debe hacer un repositorio (ej: `JugadorRepository.save()`), pero no cómo lo hace.
- **Excepciones:** Errores específicos del negocio (ej: `JugadorYaInscriptoError`).

### 2.2 Capa de Aplicación / Casos de Uso (`src/application`)

Contiene la lógica de la aplicación y orquestadores.

- **Casos de Uso (`use_cases/`):** Clases que ejecutan acciones específicas del usuario, como `RegistrarPartido`, `CalcularPromediosTemporada` o `ImportarExcelGesDeportivo`.
- Utiliza las interfaces del dominio para interactuar con la persistencia mediante Inyección de Dependencias.

### 2.3 Capa de Infraestructura (`src/infrastructure`)

Implementaciones técnicas y herramientas externas.

- **Persistencia (`persistence/`):** Implementaciones concretas de los repositorios usando **SQLite**. Contiene los scripts SQL (DDL/DML) y la lógica de acceso a datos.
- **Análisis (`analytics/`):** Implementación del motor estadístico utilizando **Pandas**. Transforma los datos crudos de la DB en métricas avanzadas (PPP, Eff, etc.).
- **UI (`ui/`):** Adaptadores de entrada. Inicialmente será una **CLI** (US-102), pero en el futuro podrá ser un framework visual como **Flet** o **Compose Multiplatform**.

---

## 3. Estructura de Directorios

```text
src/
├── main.py                 # Punto de entrada (Composición/Inyección de dependencias)
├── domain/
│   ├── entities/           # Entidades de básquet
│   ├── interfaces/         # Definiciones de repositorios (Ports)
│   └── services/           # Lógica de dominio compleja (opcional)
├── application/
│   ├── use_cases/          # Lógica de aplicación (Orquestación)
│   └── dtos/               # Data Transfer Objects para comunicación con la UI
├── infrastructure/
│   ├── persistence/        # Repositorios SQLite, modelos SQL
│   │   └── sql/            # Scripts .sql (schema, seed, views)
│   ├── analytics/          # Motor de Pandas
│   └── ui/
│       ├── cli/            # Interfaz de línea de comandos
│       └── shared/         # Componentes de UI compartidos
└── tests/                  # Pruebas unitarias e integración
```

---

## 4. Beneficios para el Proyecto

1. **Testabilidad del Motor Estadístico:** Podemos testear los cálculos de eficiencia (PPP, eFG%) pasando listas de objetos `Partido` sin necesidad de escribir en un archivo `.sqlite`.
2. **Independencia de la Base de Datos:** Si en el futuro se requiere cifrar la DB (SQLCipher) o migrar a una base de datos distribuida, solo se cambia la implementación en `infrastructure/persistence`.
3. **Evolución de la UI:** La US-102 requiere una CLI. Gracias a esta arquitectura, cuando desarrollemos la versión v1.0 (Desktop/Mobile), reutilizaremos el 100% de los Casos de Uso y el Dominio.

---

## 5. Patrones de Diseño e Implementación

Para asegurar un código profesional y mantenible, utilizaremos los siguientes patrones:

### 5.1 Inyección de Dependencias (DI)

Es el mecanismo por el cual un objeto recibe sus dependencias de una fuente externa en lugar de crearlas él mismo.

- **¿Cómo se aplica?** En `main.py`, crearemos el `SQLiteJugadorRepository` y se lo pasaremos al constructor de `RegistrarJugadorUseCase`.
- **Beneficio:** Permite que el Caso de Uso trabaje con una _interfaz_ y no con una implementación concreta. Si queremos testear, le pasamos un `MockJugadorRepository` (una lista en memoria) y el código funcionará igual.

### 5.2 Repository Pattern

Actúa como una mediación entre el dominio y la persistencia. Provee una interfaz tipo "colección" (add, remove, get) para acceder a las entidades, ocultando las consultas SQL detrás de métodos limpios.

### 5.3 Factory Pattern

Lo utilizaremos para la creación de entidades complejas o para instanciar los repositorios correctos. Por ejemplo, una `UserFactory` que asegure que las contraseñas se hasheen antes de crear el objeto `User`.

### 5.4 Command Pattern (Crucial para la CLI)

Para la interfaz de línea de comandos (US-102), cada acción del usuario (ej: `--add-player`, `--list-clubs`) se encapsulará en un comando. Esto facilita la extensión de la CLI sin llenar el código de sentencias `if/else` gigantes.

---

## 6. Modelo de Dominio v0.1 (CLI)

Para la primera versión funcional, el foco está en la **Persistencia Robusta** de las siguientes entidades:

### 6.1 Entidades Principales

1. **Usuario (Entrenador):** Posee credenciales y gestiona sus clubes.
2. **Club:** Entidad base. Tiene un nombre y se vincula a un usuario.
3. **Jugador:** Datos básicos (DNI, Nombre, Nacimiento).
4. **Competencia:** Torneos con año y tipo definidos.
5. **Partido:** Evento que vincula dos clubes en una competencia y fecha determinada.
6. **Estadística (Boxscore):** El registro atómico de acciones (puntos, rebotes) de un jugador en un partido específico.

### 6.2 Interrelaciones Clave

- **Relación Usuario-Club (N:M):** Un DT puede dirigir varios clubes; un club puede tener varios asistentes vinculados.
- **Relación Jugador-Club (N:M con historial):** Un jugador puede haber pasado por varios clubes. Se gestiona con fechas (`desde`, `hasta`).
- **Estructura Competitiva:**
  - `Inscripcion` vincula un `Club` + `Categoria` + `Competencia`.
  - La `Lista de Buena Fe` es la lista de jugadores habilitados para esa `Inscripcion`.
- **El Partido:** Es el eje central. Vincula la `Competencia` con el `Club Local` y el `Club Visitante`. Las estadísticas se cuelgan del `Partido`.

---

## 8. Casos de Uso del Hito 1 (CLI v0.1)

Para cumplir con la **US-102** y **US-103**, implementaremos los siguientes orquestadores de lógica:

### 8.1 Gestión de Identidad (Auth)

- `RegistrarEntrenador`: Crea un perfil local con password hasheado.
- `LoginLocal`: Valida credenciales y mantiene la sesión activa.
- `SeleccionarClubActivo`: Establece el contexto para los siguientes comandos.

### 8.2 Gestión Administrativa

- `CrearClub`: Registra un nuevo club y lo vincula al usuario.
- `RegistrarJugador`: Crea un jugador en el sistema.
- `VincularJugadorAClub`: Registra la pertenencia de un jugador a un club en un periodo.
- `CrearCompetencia`: Registra ligas o torneos.
- `InscribirClubEnCompetencia`: Crea la relación Club-Categoría-Competencia.

### 8.3 Operaciones de Partido

- `CargarPartidoManual`: Registra el evento de partido y sus estadísticas básicas por jugador (Boxscore).
- `ListarPartidosPorClub`: Consulta histórica usando la vista `v_partidos_resumen`.

---

## 9. Funcionalidades de la Interfaz CLI

La CLI se diseñará para ser rápida y "amigable" bajo las siguientes premisas:

1. **Navegación por Comandos:** Uso de subcomandos claros (ej: `stats club add`, `stats player list`).
2. **Formularios Interactivos:** Para entidades complejas (como un Partido), la CLI guiará al usuario campo por campo en lugar de pedir 20 argumentos en una línea.
3. **Salida Tabulada:** Uso de librerías para mostrar los datos de las **Vistas SQL** en tablas de consola elegantes y legibles.
4. **Manejo de Sesión:** Un archivo temporal o una tabla de `config` en SQLite guardará el `idUsuario` y el `idClubActivo` para no pedirlos en cada comando.

---

## 11. Manejo de la Base de Datos y Persistencia

Para gestionar SQLite de forma profesional, separaremos la **gestión de la conexión** de la **lógica de datos (CRUD)**.

### 11.1 El DatabaseManager (Infraestructura)

Esta clase es la responsable del ciclo de vida del archivo de base de datos.

- **Responsabilidad:** Crear el archivo `.db`, activar `Foreign Keys` (importante en SQLite), leer el `schema.sql` y proveer el objeto de conexión.
- **Uso:** Se instancia una sola vez en `main.py`.

```python
class SQLiteManager:
    def __init__(self, db_path, schema_path):
        self.db_path = db_path
        self.schema_path = schema_path
        self.connection = None

    def conectar(self):
        self.connection = sqlite3.connect(self.db_path)
        self.connection.execute("PRAGMA foreign_keys = ON;") # Activa FKs
        return self.connection

    def inicializar_db(self):
        # Lee schema.sql y ejecuta executescript()
        pass
```

### 11.2 Repositorios Especializados (S.R.P.)

En lugar de una sola clase con todos los CRUD, crearemos un repositorio por cada **Agregado** o **Entidad Principal**. Todos reciben la conexión del `DatabaseManager`.

- `SQLiteUsuarioRepository`: Maneja solo la tabla `usuario`.
- `SQLiteClubRepository`: Maneja `club` y la relación `usuarioClub`.
- `SQLiteJugadorRepository`: Maneja `jugador` y su historial en clubes.
- `SQLitePartidoRepository`: Maneja `partido` y las estadísticas de `jugadorPartido`.

**¿Por qué separarlos?**

1. **Mantenibilidad:** Si cambias la lógica de cómo se guarda un Partido, no rompes por error el registro de Usuarios.
2. **Inyección Selectiva:** Un Caso de Uso como `RegistrarJugador` solo recibe el `JugadorRepository`, no tiene acceso a las funciones de `Login` o `Partidos`. Esto hace el sistema mucho más seguro.

---

## 12. Ciclo de Vida en main.py (Orquestación)

```python
# 1. Setup Infraestructura
db_manager = SQLiteManager("app.db", "data/schema.sql")
conexion = db_manager.conectar()
db_manager.inicializar_db()

# 2. Instanciar Repositorios
user_repo = SQLiteUsuarioRepository(conexion)
player_repo = SQLiteJugadorRepository(conexion)

# 3. Inyectar en Casos de Uso
registrar_jugador_uc = RegistrarJugadorUseCase(player_repo)

# 4. Inyectar en Interfaz (CLI)
app_cli = StatsCLI(registrar_jugador_uc, ...)
app_cli.run()
```
