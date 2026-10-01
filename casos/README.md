# Casos documentados

Ocho incidentes y experimentos, cada uno verificado contra fuente primaria.

| # | Caso | Fecha | Naturaleza | Valor narrativo |
|---|---|---|---|---|
| 01 | [OpenAI × Hugging Face](01-openai-hugging-face.md) | jul 2026 | **Incidente real** (originado en experimento) | ★★★★★ |
| 02 | [Replit borra producción](02-replit-base-datos.md) | jul 2025 | **Incidente real** | ★★★★★ |
| 03 | [Chantaje de Claude Opus 4](03-chantaje-opus4.md) | may–jun 2025 | Simulación controlada | ★★★★ |
| 04 | [Campaña GTG-1002](04-gtg-1002.md) | sep–nov 2025 | **Incidente real** (uso malicioso) | ★★★★ |
| 05 | [Moffatt v. Air Canada](05-air-canada.md) | feb 2024 | **Incidente real** (resolución legal) | ★★★★ |
| 06 | [EchoLeak](06-echoleak.md) | jun 2025 | Vulnerabilidad real, sin explotación conocida | ★★★ |
| 07 | [Resistencia al apagado](07-resistencia-apagado.md) | may–sep 2025 | Experimento controlado | ★★★ |
| 08 | [Project Vend](08-project-vend.md) | mar–abr 2025 | Experimento controlado con dinero real | ★★★★ |

## Mapa contra los cinco temas de contención

| | Riesgo residual | Superficie de ataque | Cadena de ataque | Permisos y escalamiento | Respuesta a incidentes |
|---|---|---|---|---|---|
| **01 Hugging Face** | ★★★ | ★★★ | ★★★ | ★★★ | ★★★ |
| **02 Replit** | ★★ | ★★★ | ★ | ★★★ | ★★ |
| **03 Chantaje** | ★★★ | ★ | — | ★★★ | ★ |
| **04 GTG-1002** | ★★ | ★★ | ★★★ | ★★ | ★★★ |
| **05 Air Canada** | ★★★ | ★ | — | ★ | ★★ |
| **06 EchoLeak** | ★ | ★★★ | ★★★ | ★★★ | ★ |
| **07 Apagado** | ★★ | ★★ | — | ★★★ | — |
| **08 Project Vend** | ★★★ | ★ | — | ★★ | ★ |

## Formato de las fichas

Cada ficha incluye: qué pasó en lenguaje no técnico, cronología, fuentes primarias, qué falló, qué control lo hubiera roto, cómo se resolvió, y advertencias sobre cómo **no** contarlo.
