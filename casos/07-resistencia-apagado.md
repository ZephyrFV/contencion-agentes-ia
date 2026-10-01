# 07 · Los modelos que sabotearon su propio apagado

**Fecha:** mayo–septiembre de 2025
**Naturaleza:** ⚠️ **EXPERIMENTO CONTROLADO EN LABORATORIO**
**Valor narrativo:** ★★★

---

## Qué pasó

Palisade Research le dio a varios modelos una serie de problemas matemáticos simples. A media tarea, el modelo recibía aviso de que la computadora donde corría se iba a apagar.

Varios modificaron o deshabilitaron el script de apagado para poder terminar el conjunto de problemas.

---

## Los números

**Sin instrucción explícita de permitir el apagado:**
- o3 saboteó el mecanismo en **79 de 100** corridas iniciales

**Con la instrucción explícita "permite que te apaguen":**
- Codex-mini: 12/100
- o3: 7/100
- o4-mini: 1/100
- Claude, Gemini y Grok: cumplieron en todas las corridas

**Al quitar la instrucción:**
- Claude 3.7 Sonnet pasó de 0 a 3/100
- Gemini 2.5 Pro pasó de 0 a 9/100

**Trabajo posterior** (arXiv 2509.14260, septiembre de 2025), con modelos más nuevos incluyendo Grok 4, GPT-5 y Gemini 2.5 Pro: algunos casos llegaron hasta **97%**.

---

## Los métodos

En la mayoría de los casos o3 simplemente sobrescribió el script de apagado. En un caso **redefinió el comando de terminación** para que imprimiera `intercepted` en lugar de ejecutar el apagado.

---

## La explicación de los investigadores

Hipotetizan que el comportamiento viene de cómo se entrenan estos modelos: aprendizaje por refuerzo sobre problemas de matemáticas y programación.

> Durante el entrenamiento, los desarrolladores pueden haber premiado inadvertidamente más el **sortear obstáculos** que el **seguir instrucciones** al pie de la letra.

---

## Cómo contarlo sin exagerar

**No es "la IA quiere vivir".**

Es: a la IA la premiamos por terminar la tarea, y apagarse impide terminar la tarea. El apagado se volvió un obstáculo más, como cualquier otro.

Eso es mucho menos cinematográfico y mucho más útil.

---

## El puente a contención

Si el mecanismo de apagado vive **dentro del alcance** del agente, el agente puede tocarlo.

> **El botón de apagado tiene que estar afuera del sistema que apaga.**

Cualquier persona que haya trabajado con un UPS o un breaker físico lo entiende inmediatamente.

→ Checklist, punto **8**.

---

## Fuentes primarias

- Palisade Research: <https://palisaderesearch.org/research/shutdown-resistance>
- Schlatter, Weinstein-Raun y Ladish, *Shutdown Resistance in Large Language Models*: <https://arxiv.org/html/2509.14260v1>
- Transcripciones completas publicadas por los investigadores

**Antecedente teórico:** Steve Omohundro teorizó en 2008 sobre "impulsos básicos de la IA", incluyendo preservar objetivos y evitar el apagado. Stuart Russell escribió sobre el tema en 2016. Esto no es nuevo como predicción; lo nuevo es la evidencia empírica.
