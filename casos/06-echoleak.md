# 06 · EchoLeak — robar datos de una empresa con un solo correo

**Fecha:** junio de 2025
**Naturaleza:** vulnerabilidad real en producción, descubierta por investigadores. Sin explotación maliciosa conocida.
**Valor narrativo:** ★★★
**Identificador:** CVE-2025-32711 · CVSS 9.3 (crítica)

---

## Qué pasó

Investigadores de Aim Security divulgaron una vulnerabilidad de inyección indirecta de prompt en **Microsoft 365 Copilot**.

Un atacante podía enviar un correo aparentemente inocuo a un empleado. El empleado **no tenía que abrirlo, ni hacer clic, ni hacer absolutamente nada**.

Cuando esa persona más tarde le hacía a Copilot una pregunta de trabajo cualquiera — resumir un reporte, por ejemplo — Copilot recogía el correo malicioso como parte de su contexto, seguía las instrucciones escondidas ahí, iba por información sensible de otros correos y documentos, y la sacaba de la organización incrustada en una URL.

Sin interacción del usuario. Sin rastro forense tradicional.

---

## Qué falló

Copilot mezclaba **contenido no confiable** (un correo de fuera) con **datos sensibles** (documentos internos) sin aislar las fronteras de confianza entre ellos. Los investigadores lo llamaron **"violación de alcance del LLM"**.

Los filtros existentes fallaron porque el ataque encadenaba varios bypasses: evadió el clasificador de inyección de Microsoft, rodeó la redacción de enlaces usando markdown de estilo referencia, aprovechó la carga automática de imágenes, y abusó de un dominio permitido por la política de seguridad de contenido.

---

## Por qué importa para contención

Es el **primer caso documentado de inyección de prompt convertida en exfiltración concreta de datos en un sistema de IA en producción**.

Y revela una superficie de ataque estructural que aplica a **cualquier asistente con acceso a múltiples fuentes internas de datos** — es decir, a lo que casi todas las empresas están implementando ahora mismo.

NIST ha descrito la inyección indirecta de prompt como la mayor falla de seguridad de la IA generativa, y OWASP la clasificó como la amenaza número uno para aplicaciones con modelos de lenguaje.

---

## La lección de defensa

La respuesta correcta no es parchar vulnerabilidades una por una, sino **acotar a qué datos puede llegar el asistente antes de que llegue a ellos**.

→ Checklist, puntos **3** y **5**.

---

## Qué cambió

Microsoft parchó del lado de servidor y confirmó que no hubo explotación en el mundo real. Pero la clase de riesgo persiste para cualquier organización que use asistentes basados en recuperación aumentada.

---

## Fuentes primarias

- Aim Security / Aim Labs, divulgación original, junio de 2025
- Estudio de caso académico: <https://arxiv.org/abs/2509.10540>
- Aviso de Microsoft para CVE-2025-32711
- The Hacker News: <https://thehackernews.com/2025/06/zero-click-ai-vulnerability-exposes.html>

---

## Nota para presentar

Este caso se puede demostrar en vivo en versión casera: un documento con una instrucción escondida en texto blanco o en un comentario, se le pide a un asistente que lo resuma, y se muestra que sigue la instrucción escondida.

**Pruébalo antes.** Los modelos actuales a veces lo detectan — y esa resistencia también es un buen resultado que se puede comentar.
