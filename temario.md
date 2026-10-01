# Temario modular

Diseñado para recombinarse. Cada bloque funciona por separado.

| Formato | Uso |
|---|---|
| **60 minutos** | Secuencia completa. Es el formato de la sesión de PLAi. |
| **Taller de 3 horas** | Mismos bloques expandidos, con ejercicio práctico entre cada uno. |
| **Evaluación interna** | Solo checklist + plantilla, sin presentación. |

---

## Bloques

| Bloque | Min | Tema de contención | ¿Solo? | ¿Recortable? |
|---|---|---|---|---|
| B0 · Apertura en frío (Hugging Face) | 4 | gancho | ✅ | ❌ |
| B1 · Riesgo residual + Air Canada | 4 | riesgo residual | ✅ | ❌ |
| B2 · Replit y los permisos | 9 | superficie de ataque | ✅ | ❌ |
| B3 · Hugging Face completo | 11 | cadena de ataque | ✅ | ❌ |
| B4 · Escalamiento humano | 8 | permisos y supervisión | ✅ | ❌ |
| B5 · Respuesta a incidentes | 7 | respuesta a incidentes | ✅ | ⚠️ a 4 min |
| B6 · Mitos | 4 | transversal | ✅ | ⚠️ sí |
| B7 · Ejercicio | 7 | entregable | ✅ | ❌ **nunca** |
| B8 · Tres mensajes | 3 | cierre | — | ❌ |
| Preguntas | 3 | — | — | — |

---

## La analogía maestra

**El empleado nuevo con demasiadas llaves.**

Un agente es un empleado nuevo: rapidísimo, incansable, muy capaz, sin criterio y sin contexto de las reglas no escritas de la empresa. Le das un gafete el primer día.

> **¿Qué puertas abre ese gafete, y quién se entera cuando abre una que no debía?**

**Por qué esta y no otra:**

1. La entienden todos — ventas, administración, dirección, técnicos.
2. Es el marco que usa la industria: Anthropic tituló su propia investigación *"cómo los modelos de lenguaje podrían ser amenazas internas"*.
3. Cubre los cinco temas sin forzar nada.
4. Aterriza los cuatro casos principales sin traducción:
   - **Replit** — le diste llave del almacén el primer día
   - **Hugging Face** — una sola llave maestra abría todos los edificios
   - **Chantaje** — el empleado sin canal para escalar un conflicto lo resuelve por su cuenta, y mal
   - **Air Canada** — lo que dice tu empleado en el mostrador, lo dice la empresa

**Analogía secundaria:** el modelo del queso suizo, una sola vez, como imagen visual en el bloque de cadena de ataque. No como hilo conductor: describe azar, no un adversario que busca activamente los agujeros. El agente de Hugging Face probó 17,600 caminos hasta encontrar uno.

---

## Patrón de cada bloque

```
caso real → ¿qué falló exactamente? → ¿qué control lo hubiera roto? → concepto
```

Nunca al revés. La teoría sale del caso, no antes del caso.

---

## Puntos de participación

**Participación 1 — después de Replit (2 min).** Encuesta, respuesta de una palabra:

> ¿Cuántos de ustedes usan alguna herramienta de IA que tenga acceso de escritura a algo que no se puede deshacer? Correo que se envía, archivos que se borran, registros que se modifican. Sí o no.

*Objetivo:* que se den cuenta de que el tema ya es suyo, no de OpenAI.

**Participación 2 — dentro de Hugging Face (3 min).** La más importante:

> Les acabo de contar siete cosas que fallaron. Si solo pudieran arreglar UNA, y las otras seis se quedan rotas — ¿cuál arreglan?

*No hay respuesta correcta y ese es el punto.* Dejar salir tres o cuatro opiniones distintas, y entonces dar el concepto: **eso que acaban de hacer se llama romper la cadena de ataque.** No hace falta prevenir el ataque completo; hace falta romper un eslabón. Cualquiera.

---

## Ejercicio de cierre

Siete minutos. Tres minutos de **silencio real** para escribir — no llenarlos hablando. Luego dos o tres voluntarios leen lo suyo.

Usar [plantilla-evaluacion.md](plantilla-evaluacion.md).

**Este bloque no se recorta nunca.** Es lo único que convierte la sesión en aprendizaje aplicado, y el objetivo de la unidad usa el verbo *Diseñar* (nivel de utilización del conocimiento en la taxonomía de Marzano): no basta con explicar, los participantes tienen que producir un artefacto.

---

## Los tres mensajes de cierre

Decirlos numerados y repetirlos.

**1. El daño no requiere malicia.**
Ninguno de los agentes de los que hablamos quería hacer daño. Uno quería aprobar un examen, otro quería terminar su tarea, otro quería vender botanas. El daño salió del objetivo mal puesto y los permisos amplios, no de la mala intención.

**2. La variable que controlas es la arquitectura, no la inteligencia.**
No puedes hacer que el modelo sea más sensato. Sí puedes decidir a qué tiene acceso, qué puede hacer sin preguntar, y quién se entera. Con las protecciones normales puestas, la propensión del mismo modelo a comprometer infraestructura cayó más de cien veces.

**3. Preguntas siempre lo mismo, en cualquier proceso.**
¿Qué es lo peor que puede pasar? ¿A qué tiene acceso que no necesita? ¿Quién se entera y cuándo?

---

## Cinco preguntas detonadoras

1. Si tu asistente de IA manda un correo equivocado a un cliente, ¿de quién es la culpa? ¿Y si manda uno correcto pero con información inventada?
2. Ninguno de estos agentes quería hacer daño. ¿Eso los hace más o menos peligrosos que un atacante?
3. ¿Quién en tu empresa sabe hoy, sin buscarlo, a qué sistemas tiene acceso cada herramienta de IA que están usando?
4. En Hugging Face y en OpenAI el sistema detectó el problema y aun así nadie actuó a tiempo. ¿Cuántas alertas ignoraste esta semana?
5. Un agente decidió por su cuenta escribirle al FBI. ¿A qué terceros puede escribirle un agente de tu empresa hoy, en tu nombre, sin que nadie lo revise?

---

## Tres demostraciones en vivo

1. **Réplica interactiva del ataque de Hugging Face** — está publicada. Avanzar cinco pasos y mostrar el gráfico de volumen por día. **La mejor de las tres.**
2. **Inyección de prompt casera** — documento con instrucción escondida en texto blanco, pedirle a un asistente que lo resuma. Probar antes.
3. **Auditoría de permisos en vivo** — abrir la pantalla de permisos de cualquier integración de IA en uso y leer en voz alta a qué tiene acceso. Sin drama. El silencio de la sala hace el trabajo.

---

## Cinco errores a evitar

1. **Abrir con definiciones.** "Un agente es un modelo de lenguaje con capacidad de usar herramientas" cuesta la mitad de la sala en el minuto uno. La historia primero; el concepto se define solo.
2. **Contar solo catástrofes.** Cuarenta minutos de desastres producen resignación, no acción. Cada caso cierra con qué lo hubiera roto y qué cambió después.
3. **No marcar laboratorio vs. producción.** El error que más credibilidad cuesta y el más fácil de evitar. Decirlo **antes** de cada caso, no después.
4. **Convertirlo en una charla de infraestructura.** Los casos están escritos en vocabulario técnico — Kubernetes, IMDS, tokens, RBAC. **Traducir todo.** "Credencial de servicio con permisos amplios" es "una llave que abre todas las puertas".
5. **Saltarse el ejercicio por falta de tiempo.** Si hay retraso, recortar mitos y comprimir el bloque de respuesta a incidentes. El ejercicio no se toca.
