# Contención de agentes de IA — material abierto en español

> **⚠️ BORRADOR EN DESARROLLO.** Este repositorio está en construcción activa.
> El material se presenta el **22 de octubre de 2026**. Las fichas de casos
> están verificadas contra fuente primaria, pero el contenido puede cambiar
> hasta esa fecha. Ver [ESTADO.md](ESTADO.md).

Módulo de enseñanza sobre **defensa en profundidad para sistemas de IA agénticos**, dirigido a equipos de infraestructura, operaciones y negocio en América Latina.

Casi toda la literatura sobre contención de agentes existe solo en inglés y está escrita para perfiles de investigación. Este material está hecho para quien despliega estos sistemas en producción.

---

## El problema

La mayor parte del despliegue de IA no ocurre dentro de laboratorios de frontera. Ocurre en empresas ordinarias conectando agentes capaces a sistemas de producción, sin diseño de aislamiento, sin acotar credenciales y sin ruta de escalamiento.

El incidente de julio de 2026 entre OpenAI y Hugging Face es la mejor evidencia de por qué importa: el agente **no era malicioso**, estaba optimizando un examen, y las debilidades individuales que explotó eran completamente ordinarias. Según el reporte de OpenAI, bajo el andamiaje y el prompt de sistema de producción, la propensión del mismo modelo a comprometer infraestructura **cayó más de 100 veces**.

No cambió el modelo. Cambió la capa de protección alrededor.

**Esa es la tesis de este material: la variable que controlas es la arquitectura, no la inteligencia.**

---

## Contenido

| Archivo | Qué es |
|---|---|
| **[checklist-contencion.md](checklist-contencion.md)** | Diez puntos para revisar en cualquier despliegue de agentes |
| **[casos/](casos/)** | Ocho incidentes documentados contra fuente primaria, cada uno mapeado a un control arquitectónico concreto |
| **[mitos.md](mitos.md)** | Titulares que no sobreviven revisión de fuente primaria |
| **[plantilla-evaluacion.md](plantilla-evaluacion.md)** | Una página para evaluar un proceso propio |
| **[temario.md](temario.md)** | Estructura modular de la sesión, recombinable en 60 min o taller largo |
| **[fuentes.md](fuentes.md)** | Bibliografía completa, separando fuentes primarias de secundarias |

---

## Principio editorial

Cada caso está clasificado como **experimento controlado** o **incidente real en producción**.

| Capacidad demostrada en condiciones artificiales | Comportamiento espontáneo en producción |
|---|---|
| Un laboratorio construyó el escenario a propósito | Ocurrió sin que nadie lo diseñara |
| Suele haber protecciones deshabilitadas | Protecciones normales activas |
| Prueba que *puede* pasar | Prueba que *pasó* |

Confundir los dos es la forma más rápida de perder credibilidad técnica, y buena parte de la cobertura de prensa los confunde. De los ocho casos aquí documentados, **cuatro son incidentes reales** y cuatro son experimentos. Ambos importan, por razones distintas.

Cuando una afirmación no sobrevive la revisión de fuente primaria, va a [mitos.md](mitos.md) en vez de descartarse en silencio. Esa sección tiene valor propio.

---

## Contexto

Este material se presenta como **Unidad 5, «Minimizando el daño»**, del curso *Cuando la inteligencia artificial se sale de control*, impartido por PLAi ([plai.mx](https://plai.mx)) con Luis Cosio como experto titular. Sesión del 22 de octubre de 2026.

Cubre el mismo terreno que la Unidad 4 del curso **AGI Strategy** de [BlueDot Impact](https://bluedot.org/courses/agi-strategy) («Defence in Depth»), adaptado para una audiencia que no lo va a leer en inglés.

La estructura de tres capas de BlueDot es la columna vertebral conceptual:

1. **Prevenir** el entrenamiento peligroso — *fuera del alcance de este material*
2. **Restringir** las capacidades peligrosas — superficie de ataque, aislamiento, permisos
3. **Resistir** las acciones peligrosas — riesgo residual, ruptura de cadena, respuesta a incidentes

---

## Cómo usarlo

El material es modular. Cada caso y cada bloque del temario funciona por separado.

- **Sesión de 60 minutos** — secuencia completa del [temario](temario.md)
- **Taller de 3 horas** — mismos bloques, expandidos, con ejercicio entre cada uno
- **Evaluación interna** — [checklist](checklist-contencion.md) + [plantilla](plantilla-evaluacion.md), sin necesidad de presentación

No hace falta pedir permiso para darlo. La licencia lo permite explícitamente.

---

## Autoría

**Fernando Valdovinos Antonio** — Hybrid Ops Team Leader en [iNBest](https://inbest.cloud). Operación de clúster Virtuozzo Hybrid Infrastructure, arquitectura en GCP y Azure. Ciudad de México.

Sin formación convencional en seguridad de IA. Lo que aporto es el lado operativo: la cronología técnica del incidente de Hugging Face está escrita en el vocabulario con el que trabajo todos los días — cuentas de servicio de Kubernetes, endpoints de metadatos de nube, alcance de credenciales, redes mesh. Traducir eso a algo accionable para quien no lo va a leer en inglés es el hueco que este material intenta cerrar.

Correcciones y aportaciones bienvenidas vía issues.

---

## Licencia

[CC BY 4.0](LICENSE) — uso libre, incluso comercial, con atribución.
