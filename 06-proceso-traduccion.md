- [6. Proceso de Traducción, Máquinas Virtuales y Entornos de Ejecución](#6-proceso-de-traducción-máquinas-virtuales-y-entornos-de-ejecución)
  - [6.1. Proceso de Traducción: Compilación e Interpretación](#61-proceso-de-traducción-compilación-e-interpretación)
    - [6.1.1. Diferenciación entre Traducción, Compilación e Interpretación](#611-diferenciación-entre-traducción-compilación-e-interpretación)
    - [6.1.2. Fases de un Traductor (Compilador/Intérprete)](#612-fases-de-un-traductor-compiladorintérprete)
      - [1. Análisis Léxico (Scanner)](#1-análisis-léxico-scanner)
      - [2. Análisis Sintáctico (Parser)](#2-análisis-sintáctico-parser)
      - [3. Análisis Semántico](#3-análisis-semántico)
      - [4. Generación de Código Intermedio](#4-generación-de-código-intermedio)
      - [5. Optimización de Código](#5-optimización-de-código)
      - [6. Generación de Código Objeto](#6-generación-de-código-objeto)
      - [7. Enlazador (Linker) y Cargador (Loader)](#7-enlazador-linker-y-cargador-loader)
  - [6.2. Códigos Fuente, Objeto y Ejecutable](#62-códigos-fuente-objeto-y-ejecutable)
  - [6.3. Máquinas Virtuales y Entornos de Ejecución](#63-máquinas-virtuales-y-entornos-de-ejecución)
    - [6.3.1. Concepto de Máquina Virtual](#631-concepto-de-máquina-virtual)
    - [Funciones principales de una máquina virtual](#funciones-principales-de-una-máquina-virtual)
    - [6.3.2. Entornos de Ejecución (Runtime Environments)](#632-entornos-de-ejecución-runtime-environments)
    - [6.3.3. Frameworks](#633-frameworks)
    - [Ventajas de utilizar un framework](#ventajas-de-utilizar-un-framework)
    - [Inconvenientes](#inconvenientes)


# 6. Proceso de Traducción, Máquinas Virtuales y Entornos de Ejecución

> 💡 **Punto de partida:** ¿Alguna vez te has preguntado cómo tu código en Python o Java se convierte en algo que el procesador entiende? ¿Y por qué la misma aplicación puede funcionar en Windows, Linux y Mac? La respuesta está en los procesos de traducción y las máquinas virtuales.

> 💡 **¿Por qué me importa?**
> Porque cuando escribes `dotnet build` en tu proyecto C#, ocurren 50 cosas en milisegundos que este tema explica. Si entiendes el proceso de traducción, sabrás por qué tu código da ciertos errores, por qué compilar en Release es más rápido que en Debug, y qué es exactamente un archivo .dll.
> 
> 🔗 **Conexión con otros temas:** El Tema 05 clasificó los lenguajes por tipo de traducción. Este tema muestra CÓMO funciona esa traducción. El Tema 09 aplicará todo esto al proceso concreto de compilación de C# con Roslyn y CLR.

En el Punto 05 vimos los tipos de lenguajes y sus mecanismos de traducción. Ahora profundizaremos en **cómo funciona ese proceso** de principio a fin.

**Objetivos de aprendizaje:**

- Diferenciar entre compilación, interpretación y formas mixtas
- Conocer las 7 fases de un traductor
- Entender la diferencia entre código fuente, objeto y ejecutable
- Comprender qué es una máquina virtual y por qué existe
- Conocer los entornos de ejecución y frameworks más comunes

## 6.1. Proceso de Traducción: Compilación e Interpretación

Para que el ordenador entienda algo escrito en un lenguaje de programación, debe pasar por un proceso de traducción de código. La traducción de un programa escrito en un lenguaje de programación a un lenguaje de máquina se realiza mediante un **traductor**, que puede ser un **compilador** o un **intérprete**.

> 💡 **Analogía:** Imagina que tienes un libro en japonés y quieres leerlo. Tienes dos opciones:
> - **Compilar:** Traducir TODO el libro al español antes de leerlo (trabajo largo antes, lectura rápida después)
> - **Interpretar:** Leerlo con un traductor que te va traduciendo frase por frase mientras lees (más lento pero adaptable)

### 6.1.1. Diferenciación entre Traducción, Compilación e Interpretación

- **Traducción**: Es el proceso general de transformar código de un lenguaje a otro.
- **Compilación**: Proceso que traduce el código fuente completo a código objeto o binario ejecutable en un solo paso. Un ejemplo es el compilador de C.

```mermaid
graph LR
    A[Código Fuente C] -->|Compilador gcc| B[Código Máquina]
    B -->|10110001 10111011...| C[Ejecutable]
    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#4CAF50,color:#fff
```

- **Interpretación**: Proceso que traduce y ejecuta el código fuente línea a línea, o instrucción por instrucción, sin generar un archivo intermedio. Un ejemplo es el intérprete de JavaScript.

```mermaid
graph LR
    A[Código Fuente JS] -->|Intérprete Node.js| B[Traduce y ejecuta línea a línea]
    style A fill:#2196F3,color:#fff
    style B fill:#9C27B0,color:#fff
```

```mermaid
graph LR
    subgraph Compilación
        A[Código Fuente] --> B[Compilador]
        B --> C[Código Objeto]
        C --> D[Enlazador]
        D --> E[Código Ejecutable]
    end

    subgraph Interpretación
        F[Código Fuente] --> G[Intérprete]
        G --> H[Ejecución Directa]
    end

    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#9C27B0,color:#fff
    style D fill:#4CAF50,color:#fff
    style E fill:#3F51B5,color:#fff
    style F fill:#2196F3,color:#fff
    style G fill:#607D8B,color:#fff
    style H fill:#f44336,color:#fff
```

![Diagrama: Compilación vs Interpretación](/images/compilado_interpretado.jpeg)

| Característica | Compilación | Interpretación | Mixto |
|----------------|-------------|----------------|-------|
| **Traducción** | Todo de una vez | Línea a línea | Código intermedio + JIT |
| **Velocidad** | Rápida | Lenta | Media-buena |
| **Portabilidad** | Baja (por SO) | Alta | Alta |
| **Ejemplos** | C, C++, Go | Python, Ruby | Java, C# |
| **Ejecutable** | Sí (.exe) | No | No (.dll + MV) |

- **Mixto**: Algunos lenguajes utilizan ambos métodos, compilando a un código intermedio (bytecode) que luego es interpretado por una máquina virtual. Un ejemplo es Java y C#.

```mermaid
graph LR
    A[Código Fuente] --> B[Compilador]
    B --> C[Bytecode]
    C --> D[Máquina Virtual]
    D --> E[Ejecución]
    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#9C27B0,color:#fff
    style D fill:#4CAF50,color:#fff
    style E fill:#3F51B5,color:#fff
```

> 💡 **Ejemplo real:** En Java: `MiApp.java` → javac (compilador) → `MiApp.class` (bytecode) → java (JVM) → Ejecución en Windows, Linux, Mac.

> 📝 **Nota:** Python funciona así. Cuando ejecutas `python programa.py`, Python compila a bytecode (.pyc) y luego lo interpreta. Por eso la segunda ejecución es más rápida.

![Diagrama: Lenguaje Mixto](/images/lenguaje_mixto.png)

- **Transpilación**: Proceso que traduce código de un lenguaje de alto nivel a otro lenguaje de alto nivel de similar nivel de abstracción. Un ejemplo es TypeScript → JavaScript.

```mermaid
graph LR
    A[Código TypeScript] -->|Transpilador tsc| B[Código JavaScript]
    B -->|Navegador/Node.js| C[Ejecución]
    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#4CAF50,color:#fff
```

> 💡 **Ejemplo real:** TypeScript se usa porque ofrece tipos estáticos y más seguridad, pero los navegadores solo entienden JavaScript. El transpilador `tsc` o `Babel` resuelve esa brecha convirtiendo `.ts` a `.js`.

Otro ejemplo: React usa JSX (una mezcla de JavaScript y HTML) que se transpila a JavaScript puro con Babel. Los desarrolladores escriben JSX porque es más legible, y Babel lo convierte en llamadas a `React.createElement()` que el navegador entiende.

### 6.1.2. Fases de un Traductor (Compilador/Intérprete)

Un **traductor** es un programa que convierte el código escrito por un programador (código fuente) en un lenguaje que la máquina puede entender directamente (código máquina o código objeto). Este proceso no es una simple traducción palabra por palabra, sino que se lleva a cabo en varias fases bien definidas.

```mermaid
graph TD
    A[Código Fuente] --> B[Análisis Léxico]
    B --> C[Análisis Sintáctico]
    C --> D[Análisis Semántico]
    D --> E[Generación Código Intermedio]
    E --> F[Optimización]
    F --> G[Generación Código Objeto]
    G --> H[Enlazador]
    H --> I[Código Ejecutable]
    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#9C27B0,color:#fff
    style D fill:#4CAF50,color:#fff
    style E fill:#3F51B5,color:#fff
    style F fill:#f44336,color:#fff
    style G fill:#795548,color:#fff
    style H fill:#607D8B,color:#fff
    style I fill:#009688,color:#fff
```

> 📝 **Nota:** Entender estas fases os ayudará a comprender los mensajes de error del compilador. Si el error es "unexpected token", es léxico. Si es "syntax error", es sintáctico. Si es "incompatible types", es semántico.

![Diagrama: Fases de un Compilador](/images/fases_compilador.png)

#### 1. Análisis Léxico (Scanner)

Es la primera fase del proceso. El **analizador léxico** lee el código fuente carácter a carácter y lo agrupa en unidades lógicas llamadas **tokens**. Un token representa una unidad léxica, como una palabra clave (`if`, `while`), un identificador (`variableX`), un operador (`+`, `=`), o un literal (`"hola mundo"`, `123`). También se encarga de eliminar comentarios y espacios en blanco.

**Ejemplo:** La línea de código `int suma = a + 5;` sería descompuesta en los siguientes tokens:

- `int` (token de palabra clave - KEYWORD)
- `suma` (token de identificador - ID)
- `=` (token de operador de asignación - ASSIGN)
- `a` (token de identificador - ID)
- `+` (token de operador de suma - PLUS)
- `5` (token de literal numérico - NUMBER)
- `;` (token de delimitador - SEMICOLON)

> 💡 **Analogía:** El análisis léxico es como un niño aprendiendo a leer que primero identifica letras, luego sílabas y finalmente palabras completas. El scanner hace lo mismo: caracteres → palabras → tokens.

#### 2. Análisis Sintáctico (Parser)

Una vez que los tokens han sido identificados, el **analizador sintáctico** toma esta secuencia y comprueba que la estructura del programa sea gramaticalmente correcta. Este proceso genera una representación jerárquica del código, conocida como **Árbol Sintáctico (o Árbol de Análisis)**, también llamado AST (Abstract Syntax Tree). Si la secuencia de tokens no cumple con las reglas gramaticales del lenguaje, se genera un error de sintaxis.

Un AST es una estructura de datos en forma de árbol que representa la estructura gramatical del código. Por ejemplo, `x = 5 + 3` se convierte en un árbol donde la raíz es `=`, con hijo izquierdo `x` e hijo derecho una operación `+` con hijos `5` y `3`. El compilador trabaja con el AST, no con el código original.

**Ejemplo:** Para la expresión `a + 5`, el analizador sintáctico crearía un árbol donde el nodo superior es el operador `+`, con `a` y `5` como sus hijos.

```mermaid
graph TD
    A["(+)"] --> B["(a)"]
    A --> C["(5)"]
    style A fill:#4CAF50,color:#fff
    style B fill:#2196F3,color:#fff
    style C fill:#2196F3,color:#fff
```

**Errores típicos de sintaxis:**
- Paréntesis sin cerrar: `if (x > 5 { ... }`
- Punto y coma faltante: `console.log("hola")`
- Palabra clave mal escrita: `whille (true) { ... }`

> 📝 **Nota:** Cuando el compilador dice "Syntax error at line 10", está diciendo que los tokens no se pueden organizar en una estructura válida según las reglas del lenguaje.

#### 3. Análisis Semántico

En esta fase se verifica el "sentido" del programa, asegurando que las operaciones sean lógicamente coherentes y permitidas. El **analizador semántico** comprueba aspectos como:

- **Compatibilidad de tipos:** Se asegura de que no se estén realizando operaciones entre tipos de datos incompatibles (ej. sumar un número a una cadena de texto).

  ```csharp
  // Error semántico en C# (tipado fuerte)
  int resultado = "texto" + 5;  // Error: Cannot implicitly convert type 'string' to 'int'
  ```

  ```python
  # Python (tipado dinámico, pero igual verifica)
  resultado = "texto" + 5  # TypeError
  ```

- **Declaración de variables:** Verifica que todas las variables utilizadas hayan sido declaradas previamente.

  ```csharp
  // Error semántico en C#
  Console.WriteLine(x);  // Error: The name 'x' does not exist in the current context
  ```

- **Número y tipo de argumentos:** Comprueba que las llamadas a funciones tengan el número y tipo de argumentos correctos.

  ```csharp
  // Error semántico en C#
  static int Sumar(int a, int b) => a + b;

  Sumar(1, 2, 3);  // Error: Too many arguments, expected 2
  ```

Si el código supera esta fase, se garantiza que es válido y tiene un significado claro, aunque esto no asegura que funcione como el programador espera.

> 💡 **Consejo:** Un programa puede tener sintaxis correcta pero semántica incorrecta. "El gato come la televisión" es gramaticalmente correcto pero no tiene sentido.

#### 4. Generación de Código Intermedio

Antes de producir el código máquina final, muchos compiladores generan un **código intermedio**. Este es un lenguaje de bajo nivel, parecido al ensamblador, pero independiente de la arquitectura de la máquina de destino. Esta fase simplifica el diseño del compilador, ya que las optimizaciones pueden realizarse sobre este código genérico en lugar de sobre múltiples arquitecturas de máquina.

**Ejemplo:** Una expresión compleja como `x = a + 5 * y` podría traducirse a un código intermedio de tres direcciones:

```
t1 = 5 * y
t2 = a + t1
x = t2
```

> 📝 **Nota:** Java usa el "bytecode" como código intermedio. Es como un ensamblador universal que todas las JVMs pueden entender.

#### 5. Optimización de Código

Esta fase es opcional pero crucial para el rendimiento. El **optimizador** mejora el código intermedio (o, en algunos casos, el código final) para que el programa resultante sea más eficiente. El objetivo puede ser reducir el tiempo de ejecución, minimizar el tamaño del archivo o disminuir el consumo de memoria. Existen diversas técnicas de optimización, como la eliminación de código redundante o la sustitución de expresiones por resultados precalculados.

**Técnicas comunes de optimización:**

| Técnica | Antes | Después |
|---------|-------|---------|
| **Const folding** | `x = 3 + 5` | `x = 8` |
| **Dead code elimination** | Código inalcanzable | Eliminado |
| **Loop unrolling** | `for(i=0;i<4;i++)` | `a[0];a[1];a[2];a[3];` |
| **Inlining** | Llamada a función | Código inline |

Ejemplo real: si escribes `const int x = 5 + 3;`, el compilador detecta que es una constante y reemplaza directamente `x` por `8` en el código generado, sin calcularlo en tiempo de ejecución. Esto se llama propagación de constantes.

> 💡 **Dato:** El compilador de C (gcc) con optimización `-O3` puede hacer que tu código sea 10-100 veces más rápido que sin optimizar, pero el código resultante es casi imposible de entender para humanos.

#### 6. Generación de Código Objeto

En esta fase, el código intermedio (ya optimizado) se convierte en **código máquina** de la arquitectura específica (por ejemplo, x86, ARM). El resultado es un archivo binario que contiene instrucciones que la CPU puede ejecutar directamente. Sin embargo, este código aún no es un programa completo, ya que las referencias a funciones o datos de otras partes del programa o de librerías externas están representadas por etiquetas simbólicas.

#### 7. Enlazador (Linker) y Cargador (Loader)

- **Enlazador (Linker):** Es el programa que toma uno o más archivos de código objeto y los combina con las **librerías** y rutinas necesarias (como las funciones para entrada y salida) para crear un único **archivo ejecutable** completo. El enlazador resuelve las referencias simbólicas, asignando direcciones de memoria reales. En lenguajes como C, esto incluye las instrucciones del preprocesador (ej. `#include`), que se encargan de incluir el contenido de otros archivos antes de la compilación.

> 💡 **Analogía:** El enlazador es como un editor de un libro que combina los capítulos escritos por diferentes autores (módulos) con el índice y las referencias cruzadas para crear un libro completo y coherente.

Ejemplo práctico: cuando escribes `Console.WriteLine("Hola")` en C#, tu código no contiene la implementación de `WriteLine`. El linker resuelve esta referencia conectando tu código con la librería `System.Console.dll` que sí contiene esa función. Sin el linker, cada programa tendría que incluir todo el código de todas las librerías.

- **Cargador (Loader):** Aunque no es parte del compilador, es la fase final que se encarga de cargar el archivo ejecutable en la memoria RAM y prepara su ejecución cuando el usuario lo inicia.

## 6.2. Códigos Fuente, Objeto y Ejecutable

Durante el proceso de codificación, el código pasa por diferentes estados:

- **Código Fuente**: Es el archivo de texto legible escrito por los programadores en un lenguaje de programación de alto nivel. Contiene el conjunto de instrucciones necesarias. Este código no es directamente ejecutable por la máquina y debe ser traducido. Un aspecto importante es su licencia: puede ser **abierto** (disponible para estudiar, modificar, reutilizar) o **cerrado** (no se tiene permiso para editarlo).

- **Código Objeto (Intermedio)**: Es un archivo binario no ejecutable. Es el resultado de traducir (compilar) el código fuente a un código equivalente formado por unos y ceros. En Java, el código objeto se denomina **Bytecode**. Solo existe si el programa se compila. No es directamente inteligible por el ser humano ni por la computadora.

- **Código Ejecutable**: Es el archivo binario ejecutable directamente por la computadora. También conocido como **código máquina**. Se obtiene al enlazar los archivos de código objeto con ciertas rutinas y bibliotecas necesarias. El sistema operativo es el encargado de cargarlo en memoria RAM y ejecutarlo. Los programas interpretados no producen código objeto, el paso de fuente a ejecutable es directo.

> 📝 **Nota:** Extensiones típicas:
> - `.c`, `.cpp`, `.java`, `.py`, `.js`, `.php` (código fuente)
> - `.o`, `.obj` (código objeto)
> - `.exe`, `.app`, `.bin` (ejecutable)

```mermaid
graph LR
    A[Código Fuente<br/>.java, .py, .c] -->|Compilación| B[Código Objeto<br/>.class, .o]
    B -->|Enlazador| C[Código Ejecutable<br/>.exe, .app]
    A -->|Interpretación| D[Ejecución Directa]
    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#4CAF50,color:#fff
    style D fill:#9C27B0,color:#fff
```

> 💡 **Dato:** Cuando desarrollas en Java, trabajas con código fuente (.java). El compilador javac genera bytecode (.class). Cuando ejecutas `java MiClase`, la JVM carga el bytecode y lo interpreta/JIT-compila a código máquina nativo.

## 6.3. Máquinas Virtuales y Entornos de Ejecución

### 6.3.1. Concepto de Máquina Virtual

Una **máquina virtual (MV)** es un tipo especial de software cuya misión es separar el funcionamiento del ordenador de los componentes hardware instalados. Actúa como una capa de software de bajo nivel, haciendo de puente entre el bytecode de la aplicación y los dispositivos físicos del sistema. Esto garantiza la **portabilidad** de las aplicaciones, permitiendo desarrollarlas y ejecutarlas sobre cualquier equipo, independientemente de sus características hardware.

> 💡 **Analogía:** La máquina virtual es como un traductor universal que permite que tu programa hable "java" con el hardware que solo entiende "máquina".

### Funciones principales de una máquina virtual

- **Portabilidad:** Ejecutar el mismo código en diferentes sistemas operativos
- **Gestión de memoria:** Reservar y liberar memoria automáticamente (garbage collector)
- **Seguridad:** Aislar aplicaciones entre sí
- **Verificación:** Comprobar bytecode antes de ejecutar

Los **lenguajes mixtos o virtuales** (como Java o Python) compilan el código fuente a un código intermedio llamado **bytecode** (en Java), que luego es interpretado por la máquina virtual.

Sin máquinas virtuales, tendrías que compilar tu aplicación por separado para Windows, Linux y Mac. Con una MV, compilas una sola vez a código intermedio y el mismo ejecutable funciona en cualquier sistema operativo que tenga la MV instalada. Es como el traductor universal: tú hablas una vez y él traduce a cualquier idioma.

```mermaid
graph TB
    subgraph Aplicación
        A[Código Fuente<br/>HolaMundo.java]
    end
    subgraph Compilación
        B[Compilador javac]
    end
    subgraph Máquina Virtual
        C[Bytecode<br/>HolaMundo.class]
        D[JVM<br/>Interpreta y ejecuta]
    end
    subgraph Hardware
        E[Sistema Operativo<br/>Windows/Linux/Mac]
        F[Hardware<br/>CPU, RAM]
    end
    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#9C27B0,color:#fff
    style D fill:#4CAF50,color:#fff
    style E fill:#607D8B,color:#fff
    style F fill:#f44336,color:#fff
```

> 📝 **Nota:** Ejemplos de máquinas virtuales:
> - **JVM (Java Virtual Machine):** Java, Kotlin, Scala
> - **CLR (Common Language Runtime):** C#, VB.NET
> - **Python Virtual Machine:** Python
> - **BEAM:** Erlang, Elixir

> 🔗 **Ver Tema 09:** El proceso completo de C# se estudiará en detalle en el caso de estudio: desde `Program.cs` hasta ejecución.

![Diagrama: Máquina Virtual](/images/lenguaje_java.webp)

![img05](/images/lenguajes_traduccion.gif)

### 6.3.2. Entornos de Ejecución (Runtime Environments)

Un **entorno de ejecución** es un servicio de máquina virtual que sirve como base software para la ejecución de programas. Puede pertenecer al sistema operativo o instalarse como software independiente. Es un conjunto de utilidades que permiten la ejecución de programas. Se encarga de configurar la memoria principal, enlazar los archivos del programa con bibliotecas existentes y subprogramas creados, y depurar programas (comprobar errores semánticos).

El Entorno de Ejecución está formado por la máquina virtual y los **API's** (bibliotecas de clases estándar), que se distribuyen conjuntamente al necesitar ser compatibles. Funciona como intermediario entre el lenguaje fuente y el sistema operativo, ejecutando aplicaciones.

**Entornos de ejecución comunes:**

| Entorno | Lenguaje | Propósito |
|---------|----------|-----------|
| **JRE** (Java Runtime Environment) | Java | Ejecutar aplicaciones Java |
| **.NET 8/9/10 Runtime** | C# | Ejecutar aplicaciones .NET modernas |
| **Node.js** | JavaScript | Ejecutar JS en servidor |
| **Python Runtime** | Python | Ejecutar scripts Python |

> 📝 **Nota:** Cuando instaláis Python, estáis instalando el intérprete + la biblioteca estándar + el runtime. Sin esto, no podríais ejecutar programas .py.

### 6.3.3. Frameworks

Un **framework** (plataforma, entorno, marco de trabajo de desarrollo rápido de aplicaciones) es una estructura de ayuda para el programador, en base a la cual se pueden desarrollar proyectos sin partir desde cero. Es una plataforma software que define programas de soporte, bibliotecas, lenguajes interpretados, etc., ayudando a desarrollar y unir los diferentes módulos de un proyecto.

> 💡 **Analogía:** Un framework es como un kit de construcción de muebles IKEA. No tienes que diseñar las piezas desde cero, sigues las instrucciones del kit y lo montas.

### Ventajas de utilizar un framework

- **Desarrollo rápido de software**.
- **Reutilización de partes de código** para otras aplicaciones.
- **Diseño uniforme** del software.
- **Portabilidad de aplicaciones**, ya que los bytecodes generados pueden ser ejecutados sobre cualquier máquina virtual compatible.

### Inconvenientes

- **Curva de aprendizaje:** Tiempo para aprender el framework
- **Dependencia:** El código está acoplado al framework
- **Rendimiento:** Puede añadir overhead

Ejemplos de Frameworks son **.NET** (para Windows, con el ".Net framework" para la ejecución) y **Spring de Java** (conjuntos de bibliotecas para desarrollo y ejecución de aplicaciones).

**Frameworks por lenguaje:**

| Lenguaje | Frameworks populares |
|----------|---------------------|
| Java | Spring, Jakarta EE, Vaadin |
| Python | Django, Flask, FastAPI |
| JavaScript | React, Vue, Angular, Node.js |
| PHP | Laravel, Symfony, WordPress |
| C# | .NET, ASP.NET, Entity Framework |

---

**Resumen del punto:**

| Concepto | Descripción |
|----------|-------------|
| **Compilación** | Traduce TODO el código → ejecutable (rápido, C/C++) |
| **Interpretación** | Traduce y ejecuta línea a línea (lento, Python/JS) |
| **Mixto** | Compila a bytecode → máquina virtual (Java, C#) |
| **Análisis léxico** | Código → tokens |
| **Análisis sintáctico** | Tokens → árbol (¿es correcto?) |
| **Análisis semántico** | Árbol → ¿tiene sentido? |
| **Código fuente** | Tu archivo `.java`, `.py` |
| **Código objeto** | `.class`, `.o` (no ejecutable) |
| **Código ejecutable** | `.exe`, `.app` (la máquina lo entiende) |
| **Máquina virtual** | Capa que hace portable el código (JVM, CLR) |
| **Framework** | Kit de construcción reutilizable |

En el siguiente punto veremos las **herramientas de apoyo** al desarrollo: editores, IDEs y otras utilidades que facilitan nuestro trabajo diario como programadores.
