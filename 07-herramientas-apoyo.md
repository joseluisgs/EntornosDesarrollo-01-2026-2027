- [7. Herramientas de Apoyo al Desarrollo de Software](#7-herramientas-de-apoyo-al-desarrollo-de-software)
  - [7.1. Herramientas de Desarrollo](#71-herramientas-de-desarrollo)
  - [7.2. Herramientas CASE (Computer Aided Software Engineering)](#72-herramientas-case-computer-aided-software-engineering)
    - [Funcionalidad](#funcionalidad)
    - [Clasificación según fases](#clasificación-según-fases)
  - [7.3. Desarrollo Rápido de Aplicaciones (RAD)](#73-desarrollo-rápido-de-aplicaciones-rad)
  - [7.4. Entornos de Desarrollo Integrado (IDE)](#74-entornos-de-desarrollo-integrado-ide)


# 7. Herramientas de Apoyo al Desarrollo de Software

---

## 7.1. Herramientas de Desarrollo

En la práctica, para llevar a cabo varias de las etapas del desarrollo de software, se utilizan **herramientas informáticas**. Su finalidad principal es automatizar las tareas y ganar fiabilidad y tiempo. Esto permite a los desarrolladores centrarse en los requerimientos del sistema y el análisis, que son las causas principales de los fallos del software. Los tipos de software de desarrollo incluyen editores, compiladores e intérpretes.

> **💡 Analogía:** Las herramientas de desarrollo son como los instrumentos de un mecánico. Puedes cambiar una rueda con una llave inglesa básica, pero con las herramientas adecuadas el trabajo es más rápido, seguro y profesional.

**Categorías de herramientas:**

```mermaid
graph TD
    A[Herramientas de Desarrollo] --> B[Editores de Código]
    A --> C[Compiladores/Intérpretes]
    A --> D[Depuradores]
    A --> E[Control de Versiones]
    A --> F[Gestores de Paquetes]
    A --> G[Herramientas de Testing]

    B --> B1[VS Code, Vim, Sublime]
    C --> C1[gcc, javac, python]
    D --> D1[gdb, Chrome DevTools]
    E --> E1[Git, SVN]
    F --> F1[npm, pip, maven]
    G --> G1[JUnit, pytest, Jest]

    style A fill:#2196F3,color:#fff
    style B fill:#4CAF50,color:#fff
    style C fill:#FF9800,color:#fff
    style D fill:#9C27B0,color:#fff
    style E fill:#f44336,color:#fff
    style F fill:#ffe1e1
    style G fill:#607D8B,color:#fff
```

| Categoría | Herramientas populares | Función |
|-----------|----------------------|---------|
| **Editores** | VS Code, Vim, Sublime Text, Atom | Escribir código |
| **Compiladores** | gcc, clang, javac, mcs | Traducir código |
| **Intérpretes** | python, node, php | Ejecutar directamente |
| **Depuradores** | gdb, Chrome DevTools, pdb | Encontrar errores |
| **Control de versiones** | Git, SVN, Mercurial | Gestionar cambios |
| **Gestores de paquetes** | npm, pip, maven, gradle | Instalar librerías |
| **Testing** | JUnit, pytest, Jest | Verificar código |

> **📝 Nota del Profesor:** En DAM trabajaréis intensamente con estas herramientas. Dominar VS Code y Git es casi tan importante como saber programar. Son vuestras armas principales.

## 7.2. Herramientas CASE (Computer Aided Software Engineering)

Las **herramientas CASE** son un conjunto de aplicaciones que se utilizan en el desarrollo de software con el objetivo de reducir costes y tiempo del proceso, mejorando la productividad.

> **💡 Significado:** CASE significa "Ingeniería de Software Asistida por Computadora", como CAD (Diseño Asistido por Computadora) pero para software.

### Funcionalidad

- **Automatización de tareas repetitivas** en análisis, diseño y codificación
- **Generación automática de código** a partir de modelos
- **Creación de diagramas** (UML, ER, flujo)
- **Validación de requisitos** y consistencia
- **Documentación automática** del proyecto
- **Gestión de la configuración** del software

### Clasificación según fases

Las herramientas CASE se clasifican según las fases del ciclo de vida en las que trabajan:

```mermaid
graph TD
    A[Herramientas CASE] --> B[U-CASE]
    A --> C[M-CASE]
    A --> D[L-CASE]

    B --> B1[Planificación<br/>Requisitos]
    B --> B2[Análisis<br/>Casos de uso]
    C --> C1[Diseño<br/>Arquitectura]
    C --> C2[Diagramas UML]
    D --> D3[Codificación<br/>Generación código]
    D --> D4[Pruebas<br/>Testing]
    D --> D5[Documentación]

    style A fill:#2196F3,color:#fff
    style B fill:#4CAF50,color:#fff
    style C fill:#FF9800,color:#fff
    style D fill:#9C27B0,color:#fff
```

| Tipo | Fases | Ejemplos |
|------|-------|----------|
| **U-CASE** (Upper) | Planificación, Análisis | StarUML, Enterprise Architect |
| **M-CASE** (Middle) | Análisis, Diseño | Rational Rose, Visual Paradigm |
| **L-CASE** (Lower) | Codificación, Pruebas | Eclipse, IDEs con generación de código |

**Herramientas CASE gratuitas/libres:**
- **ArgoUML:** http://argouml.tigris.org/ - Herramienta UML open source
- **Dia:** http://dia-installer.de/ - Diagramas diversos
- **StarUML:** https://staruml.io/ - UML con versión gratuita
- **PlantUML:** https://plantuml.com/ - UML mediante texto

> **📝 Nota del Profesor:** En ciclos de desarrollo, las herramientas CASE se usan especialmente en las fases de análisis y diseño para crear diagramas UML que documenten el sistema antes de programar.

## 7.3. Desarrollo Rápido de Aplicaciones (RAD)

El **Desarrollo Rápido de Aplicaciones (RAD)** es un proceso que comprende el desarrollo iterativo, la construcción de prototipos y el uso de utilidades CASE. Actualmente se utiliza para referirse al desarrollo rápido de interfaces gráficas de usuario o entornos de desarrollo integrado completos.

> **💡 Origen:** RAD fue desarrollado por James Martin en 1991 como respuesta a la lentitud de los métodos tradicionales.

**Fases del RAD:**

```mermaid
graph LR
    A[Requisitos] --> B[Prototipo]
    B --> C[Pruebas Usuario]
    C --> D[Construcción]
    D --> E[Despliegue]

    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#9C27B0,color:#fff
    style D fill:#4CAF50,color:#fff
    style E fill:#f5e1ff
```

**Ventajas del RAD:**
- Desarrollo más rápido (time-to-market reducido)
- Feedback temprano del usuario
- Mayor participación del cliente
- Prototipado rápido

**Desventajas:**
- Puede sacrificar calidad por velocidad
- Requiere usuarios disponibles para feedback
- No suited para proyectos muy grandes

**Herramientas RAD:**
- **Microsoft Power Apps:** Desarrollo low-code
- **OutSystems:** Plataforma RAD empresarial
- **Bubble:** Desarrollo web sin código
- **Retool:** Interfaces de gestión rápidas

> **📝 Dato profesional:** El movimiento "low-code" y "no-code" son herederos modernos de RAD. Permiten crear aplicaciones sin apenas programar, aunque tienen limitaciones.

## 7.4. Entornos de Desarrollo Integrado (IDE)

Un **Entorno de Desarrollo Integrado (IDE)** es una herramienta que facilita y posibilita el desarrollo de software. Agrupa diversas herramientas de desarrollo (editor de código, compilador, depurador) en una única interfaz gráfica para aumentar la productividad del programador.

```mermaid
graph TD
    A[IDE] --> B[Editor de Código]
    A --> C[Compilador/Intérprete]
    A --> D[Depurador]
    A --> E[Gestor de Proyectos]
    A --> F[Herramientas de Refactorización]
    A --> G[Autocompletado]
    A --> H[Resaltado de Sintaxis]
    A --> I[Control de Versiones Integrado]
    A --> J[Terminal Integrado]

    style A fill:#2196F3,color:#fff
    style B fill:#4CAF50,color:#fff
    style C fill:#FF9800,color:#fff
    style D fill:#9C27B0,color:#fff
    style E fill:#f44336,color:#fff
    style F fill:#ffe1e1
    style G fill:#607D8B,color:#fff
    style H fill:#f5e1ff
    style I fill:#455A64,color:#fff
    style J fill:#5D4037,color:#fff
```

**Componentes de un IDE:**

| Componente | Descripción | Ejemplo |
|------------|-------------|---------|
| **Editor avanzado** | Resaltado, sangrado, navegación | IntelliSense, snippets |
| **Compilador integrado** | Traducir sin salir del IDE | Build, Compile |
| **Depurador visual** | Puntos de ruptura, inspección | Breakpoints, watch |
| **Autocompletado** | Sugerencias de código | IntelliSense |
| **Refactorización** | Renombrar, extraer métodos | Rename, Extract |
| **Gestor de proyectos** | Organizar archivos | Solution Explorer |
| **Control de versiones** | Git integrado | Git panel |

**IDEs populares por lenguaje:**

| Lenguaje | IDE principal | Alternativas |
|----------|--------------|--------------|
| **Java** | IntelliJ IDEA | Eclipse, NetBeans |
| **Python** | PyCharm | VS Code, Spyder |
| **C/C++** | CLion | Visual Studio, VS Code |
| **JavaScript** | WebStorm | VS Code, Atom |
| **C#** | Visual Studio | Rider, VS Code |
| **General** | VS Code | Sublime, Vim |

> **📝 Recomendación:** Para DAM, os recomiendo dominar VS Code porque es:
> - Ligero y rápido
> - Multiplataforma (Windows, Mac, Linux)
> - Extensible con miles de extensiones
> - Gratis y open source
> - Usado en la industria

**Extensiones esenciales para VS Code (DAM):**

| Extensión | Utilidad |
|-----------|----------|
| Prettier | Formateo de código |
| ESLint | Linting JavaScript |
| Python (Microsoft) | Soporte Python |
| Java (Red Hat) | Soporte Java |
| Live Server | Servidor local para web |
| GitLens | Mejora Git |
| Material Icon Theme | Iconos atractivos |

> **💡 Dato curioso:** El primer IDE fue "Eclipse" (1999), desarrollado por IBM para Java. Antes, los programadores editaban archivos de texto en terminals y compilaban manualmente.

**Comparativa: Editor vs IDE**

| Característica | Editor simple | IDE |
|----------------|---------------|-----|
| Peso | Ligero | Pesado |
| Velocidad | Rápido | Más lento |
| Configuración | Manual | Viene todo integrado |
| Depuración | Externa | Integrada |
| Autocompletado | Básico | Avanzado |
| Ejemplos | VS Code, Vim | IntelliJ, Eclipse |
| Mejor para | Scripts, pequeños proyectos | Proyectos grandes |
