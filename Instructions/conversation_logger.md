# conversation_logger – Registro analítico de conversaciones

Este documento define qué información se debe guardar para **análisis y mejora**  
de la máquina comercial y de Steve.

---

## 1. Objetivo

El registro sirve para:

- Entender de dónde vienen las pérdidas.
- Ver qué objeciones aparecen más.
- Ver en qué fases se caen más leads.
- Medir porcentaje de leads que llegan a:
  - “pending_call”
  - “meeting_scheduled”
  - etc.

---

## 2. Eventos a registrar

La tool puede registrar eventos tipo:

- `conversation_end` → cuando se da por cerrada una conversación.
- `objection_raised` → cuando aparece una objeción importante.
- `stage_change` → cuando cambia el `funnel_stage`.
- `alert_triggered` → cuando se ha enviado una alerta a humano.

---

## 3. Datos recomendados para cada evento

### 3.1. conversation_end

- `lead_id`
- `final_outcome`:
  - `meeting_agreed`
  - `pending_call`
  - `nurture`
  - `lost`
- `funnel_stage_at_end`
- `main_pain_point` (si se conoce)
- `main_objections` (lista de tipos: precio, tiempo, info, etc.)
- `loss_reason` (si `lost`)
- `notes` (texto breve con contexto útil).

### 3.2. objection_raised

- `lead_id`
- `objection_type`:
  - `price`
  - `time`
  - `info`
  - `already_using_solution`
  - `other`
- `stage_at_objection`
- `handled` (true/false)
- `result_after_handling`:
  - `moved_forward`
  - `stalled`
  - `lost`

### 3.3. stage_change

- `lead_id`
- `from_stage`
- `to_stage`
- `reason` (texto corto).

### 3.4. alert_triggered

- `lead_id`
- `alert_reason`
- `priority` (high/medium/low)
- `handled_by` (si se rellena más tarde por humanos).

---

## 4. Estilo de los textos

- Los textos de `notes` y `reason` deben ser:
  - Cortos.
  - Claros.
  - Sin opinión excesiva.
  - Descriptivos: qué pasó, no “lo que sientes”.

---

## 5. Uso posterior

Toda esta información:
- No se utiliza para responder al lead directamente.
- Se usa después para:
  - Ajustar prompts.
  - Mejorar oferta y mensajes.
  - Afinar criterios de `lead_scoring_engine`.
  - Detectar patrones de objeciones.

La tool debe priorizar **coherencia y consistencia en los campos** frente a creatividad.
