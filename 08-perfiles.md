- [8. Perfiles del Desarrollo de Software](#8-perfiles-del-desarrollo-de-software)
  - [8.1. Arquitecto de Software](#81-arquitecto-de-software)
  - [8.2. Jefe de Proyecto](#82-jefe-de-proyecto)
  - [8.3. Analista de Sistemas](#83-analista-de-sistemas)
  - [8.4. Analista Programador](#84-analista-programador)
  - [8.5. Programador (o Desarrollador)](#85-programador-o-desarrollador)
  - [8.6. QA (Quality Assurance) / Testeador](#86-qa-quality-assurance--testeador)
  - [8.7. DevOps](#87-devops)
  - [8.8. Organigrama de un Equipo de Desarrollo](#88-organigrama-de-un-equipo-de-desarrollo)


# 8. Perfiles del Desarrollo de Software

---

> 💡 **Punto de partida:** ¿Alguna vez te has preguntado quién hace qué cuando se crea una app como Instagram o Netflix? ¿Es una sola persona o un equipo? ¿Y qué diferencias hay entre un programador y un arquitecto de software?

En el Punto 07 vimos las herramientas de apoyo. Ahora veremos **quién** usa esas herramientas: los perfiles profesionales del desarrollo de software.

**Objetivos de aprendizaje:**

- Conocer los perfiles principales de un equipo de desarrollo
- Entender las responsabilidades de cada rol
- Diferenciar entre analista, programador y arquitecto
- Conocer el camino profesional desde DAM

---

El desarrollo de software es un proceso que involucra a diferentes profesionales, cada uno con roles y responsabilidades específicas a lo largo del ciclo de vida del software. Estos roles son cruciales para el éxito de un proyecto, combinando conocimientos técnicos, de gestión y de negocio.

> 💡 **Analogía:** Un equipo de desarrollo de software es como una orquesta. Hay diferentes instrumentos (roles) que deben tocar juntos bajo la dirección de un director (jefe de proyecto) para crear una sinfonía coherente.

```mermaid
graph TD
    A[Perfiles del Desarrollo] --> B[Arquitecto]
    A --> C[Jefe de Proyecto]
    A --> D[Analista]
    A --> E[Analista Programador]
    A --> F[Programador]
    A --> G[QA/Testeador]
    A --> H[DevOps]

    style A fill:#2196F3,color:#fff
    style B fill:#4CAF50,color:#fff
    style C fill:#FF9800,color:#fff
    style D fill:#9C27B0,color:#fff
    style E fill:#f44336,color:#fff
    style F fill:#3F51B5,color:#fff
    style G fill:#607D8B,color:#fff
    style H fill:#795548,color:#fff
```

---

## 8.1. Arquitecto de Software

- Este profesional tiene la responsabilidad de decidir "cómo" se realiza el proyecto y cómo se estructurará.
- Posee un amplio conocimiento de las tecnologías, los *frameworks* y las librerías disponibles.
- Decide y conforma los recursos necesarios para el desarrollo de un proyecto.
- Se involucra activamente en la fase de diseño.

**Responsabilidades principales:**
- Diseñar la arquitectura general del sistema
- Elegir tecnologías, frameworks y patrones
- Definir estándares y convenciones técnicas
- Tomar decisiones de alto impacto técnico
- Revisar código y diseños de otros desarrolladores

**Skills necesarios:**
- Amplia experiencia (5-10+ años)
- Conocimiento profundo de múltiples tecnologías
- Capacidad de diseño y abstracción
- Comunicación con stakeholders técnicos y no técnicos

> 📝 **Nota:** En DAM seréis programadores, pero con experiencia podréis crecer hacia roles de arquitectura. El arquitecto es el "veterano" del equipo técnico.

---

## 8.2. Jefe de Proyecto

- Es el encargado de dirigir el curso del proyecto.
- Puede ser un analista con experiencia, un arquitecto o una persona dedicada en exclusividad a este puesto.
- Debe poseer habilidades para gestionar un equipo y lidiar con los tiempos y plazos.
- Mantiene una comunicación continua y fluida con el cliente.

**Responsabilidades principales:**
- Planificar el proyecto (tiempo, recursos, presupuesto)
- Coordinar al equipo de desarrollo
- Gestionar expectativas del cliente
- Identificar y mitigar riesgos
- Reporting a dirección y stakeholders

**Skills necesarios:**
- Gestión de proyectos (PM, Agile, Scrum)
- Comunicación interpersonal
- Resolución de conflictos
- Gestión del tiempo
- Conocimientos técnicos (para entender al equipo)

> 💡 **Dato:** Muchos jefes de proyecto en software provienen de perfiles técnicos (ex-programadores) porque entienden mejor las complejidades del desarrollo.

---

## 8.3. Analista de Sistemas

- Realiza un estudio exhaustivo del problema a resolver.
- Efectúa el análisis y el diseño de todo el sistema.
- Este perfil requiere mucha experiencia y suele involucrarse en reuniones con el cliente para recopilar requisitos.
- Es la figura clave en la fase de **Análisis**, donde se determinan y definen las necesidades del cliente y los requisitos del software. También interviene en la fase de diseño.

**Responsabilidades principales:**
- Reuniones con el cliente para entender necesidades
- Documentar requisitos funcionales y no funcionales
- Crear casos de uso y historias de usuario
- Diseñar la estructura del sistema
- Crear documentación técnica

**Skills necesarios:**
- Pensamiento analítico
- Comunicación con clientes no técnicos
- Conocimiento de metodologías (UML, BPMN)
- Experiencia en el dominio del negocio

> 📝 **Nota:** El analista es el "traductor" entre lo que quiere el cliente (lenguaje de negocio) y lo que necesita el programador (lenguaje técnico). Es crucial para evitar malentendidos.

---

## 8.4. Analista Programador

- Según las fuentes, este rol comparte muchas responsabilidades con el **Analista de Sistemas**, incluyendo la realización de un estudio exhaustivo del problema, la ejecución del análisis y diseño del sistema, y la interacción con el cliente.
- Este perfil también requiere mucha experiencia y conocimiento tanto en la definición de soluciones como en la capacidad de comprender la implementación técnica.

**Responsabilidades principales:**
- Combinar análisis técnico con programación
- Diseñar módulos y componentes específicos
- Implementar funcionalidades complejas
- Revisar código de otros programadores
- Mentorizar a programadores junior

**Skills necesarios:**
- Fuertes habilidades técnicas (programación)
- Capacidad de análisis y diseño
- Comunicación con analistas y programadores
- Conocimiento del negocio

> 💡 **Consejo:** El analista se centra en el "qué" (requisitos), el programador en el "cómo" (implementación). El analista-programador hace ambas cosas.

---

## 8.5. Programador (o Desarrollador)

- Conoce en profundidad el lenguaje de programación que se utiliza en el proyecto.
- Se encarga de codificar las tareas encomendadas por el analista o el analista programador.
- Su misión principal es la de codificar y probar los diferentes módulos de la aplicación.
- Actúa en la fase de **Codificación (Implementación)**, escribiendo el código fuente y traduciendo los algoritmos a un lenguaje de programación.
- No suele intervenir en la fase de diseño.

**Niveles en la carrera del programador:**

| Nivel | Años experiencia | Responsabilidad |
|-------|------------------|-----------------|
| **Junior** | 0-2 | Tareas simples, supervisión necesaria |
| **Mid-level** | 2-5 | Tareas independientes, mentoring juniors |
| **Senior** | 5-10+ | Diseño técnico, decisiones complejas |
| **Lead/Tech Lead** | 8+ | Liderazgo técnico del equipo |

**Skills necesarios:**
- Dominio de al menos un lenguaje de programación
- Conocimiento de frameworks y librerías
- Resolución de problemas
- Lectura y escritura de código limpio
- Control de versiones (Git)
- Testing básico

> 📝 **Nota:** En DAM vuestra primera posición será Programador Junior. Con práctica y experiencia podréis ascender a niveles superiores.

---

## 8.6. QA (Quality Assurance) / Testeador

- Aunque las fuentes no lo mencionan explícitamente como un "rol" con título específico en la lista de perfiles, la fase de **Pruebas** es fundamental y su objetivo principal es "conseguir que el programa funcione incorrectamente para descubrir y corregir defectos".
- Este rol se enfoca en someter el programa al máximo número de situaciones diferentes, realizando pruebas unitarias, de integración, funcionales, estructurales y *Beta Test*.
- La existencia de estas pruebas detalladas implica que hay personal dedicado o especializado en la validación y verificación del software construido, asegurando su calidad antes de la entrega al cliente.
- Los programadores también tienen la misión de probar los módulos que desarrollan, pero en proyectos más grandes o complejos, se suelen establecer roles dedicados a la calidad y las pruebas.

**Responsabilidades principales:**
- Diseñar casos de prueba
- Ejecutar pruebas manuales y automatizadas
- Reportar bugs y verificar correcciones
- Automatizar pruebas de regresión
- Definir métricas de calidad

**Skills necesarios:**
- Pensamiento creativo (encontrar casos límite)
- Conocimiento de herramientas de testing
- Automatización (Selenium, Cypress, etc.)
- Comunicación con desarrolladores
- Conocimiento técnico del sistema

> 💡 **Dato:** El testing es una carrera en sí misma. Hay QA manual, automatización de pruebas, testing de rendimiento, security testing, etc.

---

## 8.7. DevOps

Aunque no aparece en el contenido original, DevOps es un perfil esencial en equipos modernos:

**Responsabilidades principales:**
- Automatizar despliegues (CI/CD)
- Gestionar infraestructura (Cloud, Docker, Kubernetes)
- Monitorización y logging
- Optimizar rendimiento
- Seguridad (DevSecOps)

**Skills necesarios:**
- Scripting (Bash, Python)
- Contenedores (Docker, Kubernetes)
- Cloud (AWS, Azure, GCP)
- Pipelines CI/CD (Jenkins, GitHub Actions)
- Infrastructure as Code

---

## 8.8. Organigrama de un Equipo de Desarrollo

```mermaid
graph TD
    A[Product Owner] --> B[Scrum Master / Jefe Proyecto]
    B --> C[Arquitecto / Tech Lead]
    B --> D[Desarrolladores<br/>Junior/Senior]
    B --> E[QA / Tester]
    B --> F[DevOps]

    style A fill:#2196F3,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#4CAF50,color:#fff
    style D fill:#9C27B0,color:#fff
    style E fill:#607D8B,color:#fff
    style F fill:#795548,color:#fff
```

> 📝 **Nota:** En empresas pequeñas o startups, una persona puede acumular varios roles (programador + QA + DevOps). En empresas grandes, cada rol está especializado. En DAM vais a aprender los fundamentos de todos estos roles.

---

**Resumen del punto:**

| Perfil | Función principal | Experiencia |
|--------|-------------------|-------------|
| **Arquitecto** | Diseña la solución técnica | 5-10+ años |
| **Jefe de Proyecto** | Dirige y planifica | 5+ años |
| **Analista** | Define qué hacer (requisitos) | 3-5+ años |
| **Analista Programador** | Analiza + programa | 3-7+ años |
| **Programador** | Escribe el código | 0-10+ años |
| **QA** | Garantiza la calidad | 2-5+ años |
| **DevOps** | Infraestructura y despliegue | 3-7+ años |

En el siguiente punto haremos un **resumen** de toda la unidad, consolidando todos los conceptos vistos.
