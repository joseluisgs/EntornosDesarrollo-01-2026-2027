- [3. El Ciclo de Vida del Desarrollo de Software (Fases)](#3-el-ciclo-de-vida-del-desarrollo-de-software-fases)
  - [3.1. Concepto de Ciclo de Vida del Software](#31-concepto-de-ciclo-de-vida-del-software)
  - [3.2. Fases Principales del Desarrollo de una Aplicación Informática](#32-fases-principales-del-desarrollo-de-una-aplicación-informática)
    - [3.2.1. Fase Inicial (Planificación)](#321-fase-inicial-planificación)
    - [3.2.2. Análisis (Etapa de Análisis)](#322-análisis-etapa-de-análisis)
      - [3.2.2.1. Especificación de Requisitos](#3221-especificación-de-requisitos)
      - [3.2.2.2. Tipos de Requisitos](#3222-tipos-de-requisitos)
    - [3.2.3. Diseño](#323-diseño)
    - [3.2.4. Codificación (Implementación)](#324-codificación-implementación)
      - [3.2.4.1. Características deseables del código](#3241-características-deseables-del-código)
    - [3.2.5. Pruebas](#325-pruebas)
      - [3.2.5.1. Tipos de Pruebas](#3251-tipos-de-pruebas)
    - [3.2.6. Documentación](#326-documentación)
      - [3.2.6.1. Tipos de Documentos](#3261-tipos-de-documentos)
    - [3.2.7. Explotación (Despliegue)](#327-explotación-despliegue)
    - [3.2.8. Mantenimiento](#328-mantenimiento)
      - [3.2.8.1. Tipos de Mantenimiento](#3281-tipos-de-mantenimiento)
    - [3.2.9. Retirada del Software](#329-retirada-del-software)


# 3. El Ciclo de Vida del Desarrollo de Software (Fases)

---

> 💡 **Punto de partida:** ¿Alguna vez te has preguntado por qué algunos proyectos de software tienen éxito y otros fracasan estrepitosamente? La diferencia suele estar en si siguen un proceso estructurado o improvisan sobre la marcha.

En el Punto 02 vimos qué es el software y el hardware. Ahora veremos cómo se crea el software, cuáles son las fases de un proyecto y por qué es importante seguirlas.

**Objetivos de aprendizaje:**

- Definir qué es el ciclo de vida del software
- Identificar y describir las fases principales del desarrollo
- Comprender la importancia de cada fase
- Reconocer los tipos de mantenimiento de software

---

## 3.1. Concepto de Ciclo de Vida del Software

La serie de pasos a seguir para desarrollar un programa es lo que se conoce como **Ciclo de Vida del Software**. Cada etapa del ciclo de vida del software se explicará con más detalle, y el desarrollo de software es un proceso que conlleva una serie de pasos genéricos. Es un proceso que puede parecer muy complejo y que exige una gran coordinación y disciplina del grupo de trabajo que lo desarrolle.

> 💡 **Analogía:** El ciclo de vida del software es como el ciclo de vida de una persona: nace (se concibe la idea), crece (se desarrolla), se reproduce (se mantiene y evoluciona), y eventualmente muere (se retira). Cada etapa tiene sus propias necesidades y cuidados.

### ¿Por qué seguir un ciclo de vida?

Sin un ciclo de vida estructurado, los proyectos de software suelen fracasar. Según estudios de la industria:

- **El 70% de los proyectos de software fracasan** (están sobrecostados, llegan tarde o no cumplen requisitos)
- **Los errores en fases tempranas cuestan 10-100x más** si se descubren tarde
- **El mantenimiento representa el 60-80% del coste total** del software

> 📝 **Nota:** En vuestras prácticas de DAM vais a trabajar el ciclo de vida completo. Aunque sean proyectos pequeños, es fundamental que entendáis qué fase estáis trabajando en cada momento. Cuando entregáis código sin haberlo analizado antes, estáis "construyendo sin planos".

---

## 3.2. Fases Principales del Desarrollo de una Aplicación Informática

Independientemente del modelo elegido, siempre hay una serie de etapas que se deben seguir para construir software fiable y de calidad. Las fases principales, comúnmente aceptadas, son:

```mermaid
graph LR
    A[Planificación] --> B[Análisis]
    B --> C[Diseño]
    C --> D[Codificación]
    D --> E[Pruebas]
    E --> F[Documentación]
    F --> G[Explotación]
    G --> H[Mantenimiento]
    H --> I[Retirada]

    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#9C27B0,color:#fff
    style D fill:#4CAF50,color:#fff
    style E fill:#f44336,color:#fff
    style F fill:#607D8B,color:#fff
    style G fill:#3F51B5,color:#fff
    style H fill:#FF5722,color:#fff
    style I fill:#795548,color:#fff
```

> ⚠️ **Advertencia:** Las fases NO son necesariamente secuenciales en todos los modelos. En metodologías ágiles, por ejemplo, todas las fases se repiten en cada iteración (sprint).

![Diagrama: Fases del Desarrollo de Software](/images/fases_desarrollo.jpg)

---

### 3.2.1. Fase Inicial (Planificación)

En esta fase se establecen los **objetivos** del proyecto, se define su **alcance** y se realiza un **estudio de viabilidad y costes**. Es la fase más compleja, que precisa de expertos en planificación de proyectos y donde se desarrollan documentos importantes como el de viabilidad y estimación.

**Preguntas clave de esta fase:**
- ¿Qué queremos lograr?
- ¿Es técnicamente posible?
- ¿Tenemos recursos (tiempo, dinero, personal)?
- ¿Cuánto costará?
- ¿Cuándo estará listo?

**Documentos típicos:**
- Acta de constitución del proyecto
- Estudio de viabilidad
- Estimación de costes y plazos

> 💡 **Ejemplo real:** Antes de desarrollar Instagram, los fundadores analisaron: "¿La gente quiere compartir fotos con filtros?" "Sí, pero necesitamos servidores baratos y una app ligera". Sin este análisis, habrían invertido millones en un producto que nadie quería.

---

### 3.2.2. Análisis (Etapa de Análisis)

Esta es la primera fase y la de mayor importancia en el desarrollo del proyecto. Todo lo demás dependerá de lo bien detallada que esté, siendo también la más complicada ya que no está automatizada y depende en gran medida del analista que la realice.

En esta fase, se determina y define claramente las **necesidades del cliente** y se especifican los **requisitos** que debe cumplir el software a desarrollar. Lo fundamental es una buena comunicación entre el analista y el cliente para que la aplicación desarrollada cumpla con sus expectativas, es decir, necesitamos saber el "**qué**" hace nuestro software.

> 📝 **Nota:** "No asumas nada". Si el cliente dice "quiero una tienda online", debes preguntar: ¿qué productos? ¿pago con tarjeta? ¿incluye IVA? ¿qué pasa si no hay stock? ¿qué estadísticas quieres ver?

### 3.2.2.1. Especificación de Requisitos

La **especificación de requisitos** debe:

- Ser completa y sin omisiones.
- Ser concisa y sin trivialidades.
- Evitar ambigüedades, utilizando lenguaje formal.
- Evitar detalles de diseño o implementación.
- Ser entendible por el cliente.
- Separar requisitos funcionales y no funcionales.
- Dividir y jerarquizar el modelo.
- Fijar criterios de validación.

### 3.2.2.2. Tipos de Requisitos

- **Requisitos Funcionales**: Definen qué funciones tendrá que realizar la aplicación. Responden a preguntas como qué respuesta dará la aplicación ante todas las entradas o cómo se comportará en situaciones inesperadas. Por ejemplo, en una aplicación de cosmética, podría ser si desea que la lectura de productos se haga mediante códigos de barras, cómo se detallan las facturas, si se controlará el stock o si se operará con tarjetas de crédito.

**Ejemplo práctico (tienda online):**
| ID | Requisito | Prioridad |
|----|-----------|-----------|
| RF-01 | El sistema permitirá registrar nuevos usuarios | Alta |
| RF-02 | El sistema mostrará catálogo de productos | Alta |
| RF-03 | El sistema permitirá búsquedas por categoría | Media |
| RF-04 | El sistema enviará email de confirmación tras compra | Alta |

- **Requisitos No Funcionales**: Definen las características de calidad del sistema. Incluyen tiempos de respuesta del programa, legislación aplicable, tratamiento ante la simultaneidad de peticiones, etc.

**Ejemplos:**
- RNF-01: "El sistema responderá en menos de 2 segundos"
- RNF-02: "El sistema soportará 1000 usuarios simultáneos"
- RNF-03: "Cumple RGPD en el tratamiento de datos personales"

- **Requisitos de Información**: Detallan qué información se ofrecerá como salida y qué datos son necesarios como entrada para resolver el problema.

La culminación de esta fase es el documento de **Especificación de Requisitos del Software (ERS)**, que actúa como un contrato entre el cliente y el desarrollador.

> ⚠️ **Advertencia:** No confundir requisitos funcionales (qué hace el sistema) con requisitos de diseño (cómo lo hace). Ejemplo: "El sistema guardará los datos en una base de datos PostgreSQL" es un DETALLE DE IMPLEMENTACIÓN, no un requisito funcional.

---

### 3.2.3. Diseño

Durante esta fase, una vez que ya se sabe "qué" hay que hacer, el siguiente paso es definir "**cómo**" hacerlo. Se descompone y organiza el sistema en elementos componentes que pueden ser desarrollados por separado, especificando su interrelación y funcionalidad.

Las actividades habituales incluyen el diseño arquitectónico, el diseño detallado, el diseño de datos y el diseño de la interfaz de usuario. En este punto, se deben tomar decisiones importantes como las entidades y relaciones de las bases de datos, la selección del lenguaje de programación y la elección del Sistema Gestor de Base de Datos (SGBD). Los documentos generados son más técnicos. El resultado tras el diseño arquitectónico es el **Documento de arquitectura del software**, y tras el diseño detallado, la **Especificación de módulos y funciones**.

**Artefactos típicos del diseño:**
- Diagramas UML (clases, secuencia, casos de uso)
- Modelo entidad-relación de la base de datos
- Maquetas de interfaces de usuario
- Especificación de APIs

> 💡 **Analogía:** Si la fase de análisis responde "construiré una casa de 3 habitaciones con jardín", la fase de diseño responde "la cocina estará aquí, el salón tendrá 30m², usaremos ladrillo caravista, el fontanero entrará por aquí...".

---

### 3.2.4. Codificación (Implementación)

Esta etapa consiste en transformar o traducir los resultados obtenidos a un determinado lenguaje de programación. Se escribe el código fuente de cada componente, traduciendo los algoritmos definidos en la fase de diseño. Esta tarea la realiza el programador y debe cumplir exhaustivamente con los datos impuestos en el análisis y diseño.

### 3.2.4.1. Características deseables del código

1. **Modularidad**: Dividido en trozos pequeños.
2. **Corrección**: Que haga lo que se le pide.
3. **Facilidad de lectura**: Para facilitar su desarrollo y mantenimiento futuro.
4. **Eficiencia**: Que haga un buen uso de los recursos.
5. **Portabilidad**: Que se pueda implementar en cualquier equipo.

Durante esta fase, el código pasa por diferentes estados (código fuente, objeto, ejecutable). El resultado de esta fase es el **Código fuente**.

> 📝 **Nota:** Programar no es solo "escribir código". Un buen programador:
> - Lee código ajeno más que escribe código propio
> - Sigue convenciones y estándares
> - Comenta el "por qué", no el "qué" (el código ya dice qué hace)
> - Usa control de versiones (Git)
> - Pide revisiones de código (code review)

---

### 3.2.5. Pruebas

El principal objetivo de las **pruebas** es conseguir que el programa funcione incorrectamente para descubrir y corregir defectos. El programa debe ser sometido al máximo número de situaciones diferentes. Las pruebas son imprescindible para asegurar la validación y verificación del software construido.

> 💡 **Consejo:** "Si no has encontrado un bug, es que no has probado lo suficiente."

### 3.2.5.1. Tipos de Pruebas

- **Pruebas Unitarias**: Prueban, una a una, las diferentes partes del software y comprueban su funcionamiento por separado.
  
  *Ejemplo:* Probar que una función que suma dos números devuelve el resultado correcto.

- **Pruebas de Integración**: Se realizan una vez que las pruebas unitarias han sido exitosas, comprobando el funcionamiento del sistema completo con todas sus partes interrelacionadas.
  
  *Ejemplo:* Probar que el módulo de login se conecta correctamente con la base de datos de usuarios.

- **Pruebas Funcionales**: Validan que la aplicación hace lo que tiene que hacer, a menudo con la participación del cliente.
  
  *Ejemplo:* "Dado un usuario con cuenta, cuando hace login, entonces ve su panel de control".

- **Pruebas Estructurales**: Pruebas técnicas sobre el sistema (estrés, carga, integración, etc.).
  
  *Ejemplo:* ¿Cuántos usuarios simultáneos aguanta el servidor antes de caer?

- **Beta Test**: La prueba final que se realiza sobre el entorno de producción, en el entorno real del cliente y bajo un funcionamiento normal de su empresa.

Los resultados de las pruebas de unidades son **Módulos utilizables**, y de las pruebas de integración, un **Sistema utilizable**. Las pruebas del sistema culminan con un **Sistema aceptado**.

> 📝 **Nota:** En DAM trabajaréis con frameworks de testing como JUnit (Java), pytest (Python) o Jest (JavaScript). Unit testing NO es opcional, es parte del trabajo profesional.

---

### 3.2.6. Documentación

La **documentación** es vital para el desarrollo y mantenimiento del software. Todas las etapas en el desarrollo de software deben quedar perfectamente documentadas. Una correcta documentación permitirá la reutilización de parte de los programas en otras aplicaciones, especialmente si se desarrollan con diseño modular.

### 3.2.6.1. Tipos de Documentos

- **Guía Técnica (o Manual Técnico)**: Dirigida al personal técnico (analistas y programadores). Refleja el diseño, la codificación de los programas y las pruebas realizadas. Su objetivo es facilitar el desarrollo, las correcciones y el mantenimiento futuro.
  
  *Contenido típico:* Diagramas de arquitectura, diccionario de datos, manual de despliegue.

- **Guía de Uso (o Manual de Usuario)**: Dirigida a los usuarios finales (clientes). Describe la funcionalidad de la aplicación, cómo empezar a ejecutarla y ejemplos de uso. Su objetivo es dar a los usuarios toda la información necesaria para utilizar la aplicación.
  
  *Contenido:* Capturas de pantalla, tutoriales paso a paso, preguntas frecuentes.

- **Guía de Instalación (o Manual de Instalación)**: Dirigida al personal informático responsable de la instalación. Detalla los requerimientos software de la aplicación y la solución a posibles problemas. Su objetivo es garantizar una implantación segura, confiable y precisa.
  
  *Contenido:* Requisitos de sistema, pasos de instalación, configuración, resolución de problemas.

El resultado final es la **Documentación técnica y de usuario**.

> ⚠️ **Advertencia:** "Sin documentación, el código es tan útil como un contrato en un idioma que no entiendes."

---

### 3.2.7. Explotación (Despliegue)

La **explotación** es la fase en que los usuarios finales conocen la aplicación y comienzan a utilizarla. Implica la instalación, puesta a punto y funcionamiento de la aplicación en el equipo final del cliente. En esta fase, los programas son transferidos al computador del usuario, configurados y verificados. Es recomendable que los clientes estén presentes durante la instalación. También se pueden llevar a cabo las Beta Test en los equipos del cliente bajo cargas normales de trabajo. La configuración puede ser realizada por los propios usuarios con la guía de instalación o programarse automáticamente si el software es sencillo. Es un momento crítico del proyecto tenerlo todo preparado antes de la presentación al cliente.

**Términos relacionados:**
- **Deploy**: Despliegue de la aplicación en producción
- **Release**: Nueva versión puesta a disposición de usuarios
- **Entorno de producción**: Donde los usuarios reales usan el sistema

> 💡 **Dato:** Hoy en día, con metodologías DevOps, el despliegue puede ser automático (CI/CD). Aplicaciones como Netflix despliegan cientos de veces al día sin intervención humana.

---

### 3.2.8. Mantenimiento

La etapa de **mantenimiento** es la más larga de todo el ciclo de vida del software. Por su naturaleza, el software es cambiante y deberá actualizarse y evolucionar con el tiempo, adaptándose a mejoras de hardware y nuevas situaciones. Siempre surgen errores y la necesidad de nuevas versiones. El mantenimiento se define como el proceso de control, mejora y optimización del software.

### 3.2.8.1. Tipos de Mantenimiento

- **Correctivo**: Para corregir defectos o fallos encontrados en el software.
  
  *Ejemplo:* "El botón de login no funciona en Firefox versión 120".

- **Perfectivo**: Para mejorar la funcionalidad existente del software.
  
  *Ejemplo:* "El formulario de registro ahora muestra mensajes de error en tiempo real".

- **Evolutivo**: Para añadir nuevas funcionalidades solicitadas por el cliente o expansiones de código.
  
  *Ejemplo:* "Añadir integración con PayPal para pagos".

- **Adaptativo**: Para ajustar el software a nuevos entornos, tendencias del mercado o componentes hardware.
  
  *Ejemplo:* "Hacer la app compatible con iOS 17".

Los resultados del mantenimiento son **Informes de errores y control de cambios**.

> 📝 **Nota:** Cuando heredéis código de otros desarrolladores (en empresas o en GitHub), el 80% de vuestro trabajo será mantenimiento. Por eso es crucial que el código esté bien documentado y sea mantenible.

---

### 3.2.9. Retirada del Software

Esta fase ocurre cuando el software ha llegado al **final de su vida útil** y ya no resulta rentable seguir ampliándolo o manteniéndolo. En este punto, el ciclo puede comenzar de nuevo, ya sea comprando un nuevo software o desarrollando uno a medida.

**Señales de que un software debe retirarse:**
- Los costes de mantenimiento superan los beneficios
- El hardware ya no es compatible
- Las tecnologías usadas están obsoletas
- El software no cumple nuevas regulaciones legales

**Ejemplos reales:**
- Windows XP: Soporte terminado en 2014, pero muchas empresas lo usaron hasta 2019
- Flash Player: Adobe lo discontinuó en 2020 por razones de seguridad
- MySpace: En su momento fue la red social más grande; ahora está casi abandonada

---

**Resumen del punto:**

| Fase | Objetivo | Resultado |
|------|----------|-----------|
| **Planificación** | Definir objetivos y viabilidad | Estudio de viabilidad |
| **Análisis** | Conocer las necesidades del cliente | ERS (Especificación de Requisitos) |
| **Diseño** | Definir cómo se hará | Arquitectura y especificación |
| **Codificación** | Escribir el código | Código fuente |
| **Pruebas** | Encontrar errores | Sistema aceptado |
| **Documentación** | Explicar cómo funciona | Manuales |
| **Explotación** | Poner en producción | Aplicación funcionando |
| **Mantenimiento** | Evolucionar y corregir | Nuevas versiones |
| **Retirada** | Final de vida útil | Fin del ciclo |

En el siguiente punto veremos los **modelos y metodologías de desarrollo**, es decir, cómo se organizan estas fases en diferentes enfoques de trabajo.
