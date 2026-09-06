- [1. Introducción al Desarrollo de Software](#1-introducción-al-desarrollo-de-software)
  - [1.1. ¿Qué es el Desarrollo de Software?](#11-qué-es-el-desarrollo-de-software)
  - [1.2. La Importancia del Proceso de Desarrollo](#12-la-importancia-del-proceso-de-desarrollo)


# 1. Introducción al Desarrollo de Software

> 💡 **Punto de partida:** ¿Crees que para crear una app como Instagram solo hace falta escribir código? La respuesta es no. Programar es solo una pieza del puzle. ¿Qué más hace falta?

En este punto aprenderás qué es el desarrollo de software, cuáles son las fases de un proyecto y por qué es tan importante seguir un proceso estructurado. Comprenderás que programar es solo una parte del proceso completo.

**Objetivos de aprendizaje:**

- Definir qué es el desarrollo de software y diferenciarlo de la ingeniería de software
- Identificar las fases principales del ciclo de vida del desarrollo
- Comprender por qué no se pueden "saltar" pasos en un proyecto
- Reconocer la importancia del mantenimiento en el ciclo de vida

## 1.1. ¿Qué es el Desarrollo de Software?

El **Desarrollo de Software** abarca todo el proceso que ocurre desde que se concibe una idea hasta que un programa está implementado en el ordenador y funcionando. Es una disciplina que estudia los principios y metodologías para el desarrollo y mantenimiento de sistemas software. Algunos autores consideran que el término "desarrollo de software" es más apropiado que "ingeniería de software", ya que este último implica niveles de rigor y prueba de procesos que no son siempre adecuados para todo tipo de desarrollo de software. La **Ingeniería del software** se define como la ciencia y el arte de especificar, diseñar y desarrollar programas, documentación y procedimientos operativos.

> 📝 **Nota:** La diferencia entre "desarrollo" e "ingeniería" de software es sutil pero importante. No todo el software requiere un enfoque de ingeniería riguroso. Un script simple para automatizar una tarea no necesita la misma planificación que un sistema bancario. Sin embargo, en formación profesional debemos aprender los fundamentos de la ingeniería porque trabajaremos en proyectos de mayor envergadura.

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

💡 **Dato curioso:** El término "bug" (bicho) para referirse a un error de software proviene de 1947, cuando la científica Grace Hopper encontró una polilla real atascada en un relé de la computadora Harvard Mark II.

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

> ⚠️ **Advertencia:** Muchos estudiantes creen que "programar" es lo más importante. ¡En realidad, programar es solo UNA fase! Un programador que no sabe analizar requisitos o diseñar estructuras de datos creará código inútil aunque funcione técnicamente.

### La regla del 80/20
En desarrollo de software se cumple una regla no escrita: el **80% del tiempo** de un proyecto se dedica a **mantenimiento y evolución**, mientras que solo el **20%** corresponde al desarrollo inicial. Por eso es crucial hacer las cosas bien desde el principio.

> 📝 **Nota:** En los módulos de DAM, vais a practicar cada fase del ciclo de vida. En el primer trimestre nos centraremos más en planificación y análisis; en segundo y tercero profundizaremos en diseño y codificación. Las prácticas profesionales (FCT) os permitirán ver el ciclo completo en empresas reales.

---

**¿Y si no existiera el software?** Imagina tu móvil sin aplicaciones, tu ordenador sin sistema operativo, tu coche sin programación. El hardware sin software es un ladrillo caro. Por eso el desarrollo de software es fundamental: crea la parte inteligente que hace que los dispositivos físicos sean útiles.

En el siguiente punto veremos en detalle la relación entre software y hardware, y cómo se comunican entre sí.
