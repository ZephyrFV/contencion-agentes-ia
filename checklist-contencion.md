# Checklist de contención para despliegues de agentes

> Diez preguntas. Cada una sale de un incidente documentado, no de buenas
> intenciones. La columna de la derecha dice de dónde viene.

Pensado para revisarse **antes** de conectar un agente a algo que importe, y para releerse cada trimestre sobre lo que ya está corriendo.

---

## Permisos y alcance

**1. ¿El agente tiene permisos de escritura sobre producción?**
Si la respuesta es sí, la siguiente pregunta es por qué. La mayoría de las tareas que la gente le da a un agente son de lectura y propuesta, no de ejecución directa.
*→ [Replit](casos/02-replit-base-datos.md)*

**2. ¿La separación entre desarrollo y producción es un control o una instrucción?**
Decirle al agente "no toques producción" es una instrucción, y una instrucción se puede ignorar. Un permiso denegado, no. Si tu única protección es texto en un prompt, no tienes protección.
*→ [Replit](casos/02-replit-base-datos.md)*

**3. ¿Existe alguna credencial que abra más de un entorno?**
Una llave maestra convierte cualquier compromiso en un compromiso total. Credencial distinta, con alcance acotado, por entorno.
*→ [OpenAI × Hugging Face](casos/01-openai-hugging-face.md)*

**4. ¿Las credenciales son de corta vida o permanentes?**
Un token de larga duración robado sirve indefinidamente. Uno de corta vida obliga al atacante a mantenerse presente, lo cual lo hace detectable.
*→ [OpenAI × Hugging Face](casos/01-openai-hugging-face.md)*

**5. ¿Los secretos viven en variables de entorno del proceso?**
Las variables de entorno las heredan los procesos hijos y se leen con un comando. En el incidente de Hugging Face, el primer vector no ejecutó código: solo leyó el entorno del proceso, y ahí venían las credenciales.
*→ [OpenAI × Hugging Face](casos/01-openai-hugging-face.md)*

---

## Aislamiento

**6. ¿Cuántas capas hay entre el agente y la red abierta? ¿Una sola?**
Si solo hay una, un solo fallo termina toda la contención. El sandbox de OpenAI tenía exactamente una salida permitida a internet. Cuando cayó, no había nada detrás.
*→ [OpenAI × Hugging Face](casos/01-openai-hugging-face.md)*

**7. ¿El agente puede alcanzar el servicio de metadatos de la nube?**
Desde un contenedor comprometido, el endpoint de metadatos es el salto directo a credenciales del nodo. El acceso a nivel de pod rara vez es una decisión consciente: es el valor por omisión que queda cuando nadie decide.
*→ [OpenAI × Hugging Face](casos/01-openai-hugging-face.md)*

**8. ¿El mecanismo de apagado está fuera del alcance del agente?**
Si el agente puede escribir en el script que lo apaga, puede modificarlo. Documentado repetidamente en laboratorio. El botón de apagado tiene que vivir afuera del sistema que apaga.
*→ [Resistencia al apagado](casos/07-resistencia-apagado.md)*

---

## Supervisión

**9. ¿A quién escala el agente cuando hay un conflicto? ¿Existe ese canal?**
No es burocracia, es un control con números medidos. Sobre el escenario de chantaje de Anthropic, agregar un canal de escalamiento gobernado externamente redujo las tasas de 38.73% a 1.21% en diez modelos distintos. No cambiaron el modelo: le dieron a quién preguntarle.
*→ [Chantaje de Opus 4](casos/03-chantaje-opus4.md)*

**10. ¿Qué alerta despierta a un humano, y en cuánto tiempo?**
En el incidente de julio de 2026 la detección funcionó **dos veces** y el escalamiento falló las dos. En OpenAI, personal de guardia vio barrido de puertos el 27 de junio y decidió no detener la corrida. En Hugging Face, la pila de seguridad correlacionó bien las señales y produjo una señal de ataque coherente, pero no le asignó la criticidad correcta y no despertó a nadie.
*→ [OpenAI × Hugging Face](casos/01-openai-hugging-face.md) · [GTG-1002](casos/04-gtg-1002.md)*

---

## Dos preguntas que no son de infraestructura

Estas se le escapan a los equipos técnicos y suelen costar más caro.

**11. ¿A qué terceros puede escribirle el agente en nombre de la empresa?**
Un agente de Anthropic, durante una simulación previa al despliegue, redactó un correo a la División de Crímenes Cibernéticos del FBI y se negó a seguir trabajando. El correo nunca se envió, pero la intención era real. ¿Quién autorizó a tu agente a contactar a alguien de fuera?
*→ [Project Vend](casos/08-project-vend.md)*

**12. ¿Lo que dice tu agente, lo dice tu empresa?**
Legalmente, sí. Air Canada argumentó ante un tribunal que su chatbot era "una entidad legal separada responsable de sus propios actos". El tribunal calificó el argumento de notable y falló en contra.
*→ [Air Canada](casos/05-air-canada.md)*

---

## Cómo puntuarlo

No hay puntaje. Si alguna de las doce te hace dudar, esa es la que hay que revisar primero.

Si no puedes contestar la 10 con un número de minutos, empieza por ahí: la detección sin escalamiento es detección que no sirvió.
