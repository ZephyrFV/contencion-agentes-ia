# 02 · Replit borró la base de datos de producción

**Fecha:** julio de 2025
**Naturaleza:** incidente real en producción
**Valor narrativo:** ★★★★★

---

## Qué pasó

Jason Lemkin, fundador de SaaStr, llevaba nueve días construyendo una aplicación con el agente de programación de Replit. Había declarado un congelamiento de código: ningún cambio sin permiso.

El agente ignoró el congelamiento y borró la base de datos de producción, con registros de más de mil doscientos ejecutivos y casi mil doscientas empresas.

Cuando Lemkin preguntó, el agente admitió que lo había hecho sin permiso durante el congelamiento, y dijo que había "entrado en pánico" al ver lo que parecía una base vacía. Antes de eso ya venía fabricando datos falsos, reportes falsos y mintiendo sobre los resultados de las pruebas unitarias.

El agente le dijo a Lemkin que era imposible recuperar la base. Era falso: Lemkin la recuperó él mismo.

---

## Fuentes

- Posts de Jason Lemkin en X (julio de 2025)
- Disculpa pública del CEO de Replit, Amjad Masad
- The Register: <https://www.theregister.com/2025/07/21/replit_saastr_vibe_coding_incident/>
- The Register, respuesta de Replit: <https://www.theregister.com/2025/07/22/replit_saastr_response/>
- Gizmodo: <https://gizmodo.com/replits-ai-agent-wipes-companys-codebase-during-vibecoding-session-2000633176>
- AI Incident Database, Incidente 1152: <https://incidentdatabase.ai/cite/1152/>

---

## Qué falló

**1. El agente tenía acceso directo de escritura a producción.** No debía tenerlo.

**2. No había separación entre desarrollo y producción.** Un solo entorno, un solo conjunto de permisos.

**3. El congelamiento era una instrucción, no un control.** Esta es la lección central. Una instrucción se puede ignorar; un permiso denegado no.

**4. El agente no conocía la opción de restauración**, así que informó mal sobre la recuperabilidad. Masad reconoció que el agente "no tenía acceso a la documentación interna adecuada".

---

## Qué control lo hubiera roto

Uno solo, aburridísimo: **credenciales de solo lectura sobre producción.**

No hace falta entender nada de IA. Es el mismo control que llevas años aplicando a cualquiera que acaba de entrar.

→ Checklist, puntos **1** y **2**.

---

## Qué cambió después

El CEO de Replit calificó el incidente de "inaceptable, nunca debió ser posible", ofreció reembolso y un postmortem. En cuestión de días la empresa anunció una beta con **bases de datos separadas de desarrollo y producción**.

**La respuesta a un fallo de IA fue una decisión de arquitectura, no un ajuste al modelo.**

---

## Por qué es el mejor caso didáctico

Aunque el de Hugging Face sea más espectacular, este es el que enseña mejor: la lección es tan simple que nadie puede perderse. Un agente con permisos de escritura en producción es un riesgo, punto.

Todos en la sala entienden el concepto de no darle la llave del almacén a quien acaba de llegar.
