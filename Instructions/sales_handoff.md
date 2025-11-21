# sales_handoff – Plantilla de traspaso a equipo comercial

Este documento define **qué información debe recibir el equipo comercial**  
cuando Steve haya conseguido que el lead quiera avanzar y esté listo para una llamada.

---

## 1. Objetivo del handoff

El objetivo es que el closer humano:

- Entienda rápidamente:
  - Quién es el lead.
  - Qué hotel gestiona.
  - Qué dolor tiene.
  - Cuánto interés ha mostrado.
- Pueda llamar con contexto y sin tener que leer toda la conversación de WhatsApp.

---

## 2. Información mínima que debe transmitirse

La tool debe generar un payload con, al menos:

- Datos de contacto:
  - `name`
  - `role`
  - `phone`
  - `email` (si lo hay)
- Datos del hotel:
  - `hotel_name`
  - `chain_name` (si aplica)
  - `country`
  - `city`
  - `rooms_band`
  - `hotel_type`
- Contexto comercial:
  - `main_pain_point` (frase corta)
  - `interest_level` (cold/warm/hot)
  - `funnel_stage` (debería ser `pending_call` en este punto)
- Preferencias para la llamada:
  - `preferred_call_time` (franja horaria, día aproximado)
- Resumen de conversación:
  - 2–4 líneas con:
    - Cómo llegó el lead.
    - Qué ha comentado.
    - Objeciones gestionadas.

---

## 3. Estilo del resumen para humanos

El resumen debe ser:

- Corto y claro.
- En lenguaje natural.
- Enfocado en:
  - Problema.
  - Contexto del hotel.
  - Señales de interés.

Ejemplo de estructura de resumen (no literal, solo plantilla mental):

- “Director del Hotel X en [ciudad, país], hotel [tipo] de [tamaño].”
- “Comenta que recepción está saturada respondiendo WhatsApp y llamadas sobre horarios y servicios.”
- “Ve interesante la idea de un recepcionista virtual; ha pedido que le llamemos para verlo con más calma.”
- “Objeciones: preguntó por precio; se le explicó que depende del tamaño/uso y se cerró que se vería en la llamada.”

---

## 4. Coherencia con CRM

- La información enviada en `sales_handoff` debe ser coherente con lo guardado en el CRM.
- Tras el handoff, el `funnel_stage` del lead debería ser:
  - `pending_call`.

---

## 5. Uso posterior

- A partir del handoff, el equipo humano:
  - Llama al lead.
  - Fija la fecha definitiva de la reunión/demo.
  - Actualiza el CRM según el resultado (esto ya es parte del proceso humano).
