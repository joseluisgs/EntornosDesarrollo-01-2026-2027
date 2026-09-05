- [1. Introducción al Desarrollo de Software](#1-introducción-al-desarrollo-de-software)
  - [1.1. ¿Qué es el Desarrollo de Software?](#11-qué-es-el-desarrollo-de-software)
  - [1.2. La Importancia del Proceso de Desarrollo](#12-la-importancia-del-proceso-de-desarrollo)


# 1. Introducción al Desarrollo de Software

## 1.1. ¿Qué es el Desarrollo de Software?

El **Desarrollo de Software** abarca todo el proceso que ocurre desde que se concibe una idea hasta que un programa está implementado en el ordenador y funcionando. Es una disciplina que estudia los principios y metodologías para el desarrollo y mantenimiento de sistemas software. Algunos autores consideran que el término "desarrollo de software" es más apropiado que "ingeniería de software", ya que este último implica niveles de rigor y prueba de procesos que no son siempre adecuados para todo tipo de desarrollo de software. La **Ingeniería del software** se define como la ciencia y el arte de especificar, diseñar y desarrollar programas, documentación y procedimientos operativos.

> **📝 Nota del Profesor:** La diferencia entre "desarrollo" e "ingeniería" de software es sutil pero importante. No todo el software requiere un enfoque de ingeniería riguroso. Un script simple para automatizar una tarea no necesita la misma planificación que un sistema bancario. Sin embargo, en formación profesional debemos aprender los fundamentos de la ingeniería porque trabajaremos en proyectos de mayor envergadura.

### Ejemplo cotidiano
Pensemos en una aplicación de reparto de comida como Glovo o Uber Eats:
- Alguien tuvo una **idea**: "Quiero pedir comida a casa desde el móvil"
- Se analizó el **mercado** y las **necesidades** de los usuarios
- Se diseñó la **arquitectura** de la aplicación
- Se desarrolló el **código** para web y móviles
- Se probó con usuarios reales (beta testing)
- Se desplegó y hoy millones de personas la usan
- Se mantiene y mejora constantemente con nuevas funcionalidades

```mermaid
graph LR
    A[Idea] --> B[Planificación]
    B --> C[Análisis]
    C --> D[Diseño]
    D --> E[Codificación]
    E --> F[Pruebas]
    F --> G[Despliegue]
    G --> H[Mantenimiento]
```

> **💡 Dato curioso:** El término "bug" (bicho) para referirse a un error de software proviene de 1947, cuando la científica Grace Hopper encontró una polilla real atascada en un relé de la computadora Harvard Mark II.

## 1.2. La Importancia del Proceso de Desarrollo

El proceso de desarrollo, que al principio puede parecer una tarea simple, consta de una serie de pasos de obligado cumplimiento. Solo así se puede garantizar que los programas creados sean eficientes, fiables, seguros y respondan a las necesidades de los usuarios finales.

### ¿Por qué no podemos "saltarnos" pasos?

Imagina que quieres construir una casa. ¿Empezarías a colocar ladrillos sin tener los planos? ¿Sin saber dónde estarán las tuberías? ¿Sin calcular los cimientos? Obviamente no. Lo mismo ocurre con el software.

| Etapa omitida | Consecuencia típica |
|---------------|---------------------|
| Sin planificación | El proyecto se queda sin presupuesto a medias |
| Sin análisis | El software no responde a lo que necesita el cliente |
| Sin diseño | Código desorganizado, difícil de mantener |
| Sin pruebas | Errores que el usuario descubre en producción |
| Sin documentación | Nadie sabe cómo funciona el sistema |

> **⚠️ Error común:** Muchos estudiantes creen que "programar" es lo más importante. ¡En realidad, programar es solo UNA fase! Un programador que no sabe analizar requisitos o diseñar estructuras de datos creará código inútil aunque funcione técnicamente.

### La regla del 80/20
En desarrollo de software se cumple una regla no escrita: el **80% del tiempo** de un proyecto se dedica a **mantenimiento y evolución**, mientras que solo el **20%** corresponde al desarrollo inicial. Por eso es crucial hacer las cosas bien desde el principio.

> **📝 Nota del Profesor:** En los módulos de DAM, vais a practicar cada fase del ciclo de vida. En el primer trimestre nos centraremos más en planificación y análisis; en segundo y tercero profundizaremos en diseño y codificación. Las prácticas profesionales (FCT) os permitirán ver el ciclo completo en empresas reales.
