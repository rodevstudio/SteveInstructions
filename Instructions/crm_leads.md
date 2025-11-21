# crm_leads – Convenciones de datos para el CRM

Este documento define las **categorías y etiquetas** que se deben usar  
al guardar información de leads en el CRM.

---

## 1. Campos clave

La tool de CRM debe trabajar con campos consistentes como:

- `lead_id`
- `name`
- `whatsapp_number` (u otro identificador de canal)
- `email` (si existe)
- `role`
- `hotel_name`
- `chain_name`
- `country`
- `city`
- `rooms_band` (pequeño / medio / grande / muy grande / desconocido)
- `hotel_type` (urbano / vacacional / mixto / boutique / otro)
- `main_pain_point`
- `funnel_stage`
- `interest_level`
- `loss_reason` (si se pierde)
- `notes`

---

## 2. funnel_stage (etapas del funnel)

Valores recomendados:

- `new` → lead nuevo, apenas contacto inicial.
- `problem_exploration` → ya se ha hablado de dolores.
- `qualified` → rol y hotel entendidos, hay encaje.
- `pending_call` → el lead ha aceptado avanzar y falta llamada para fijar fecha de reunión/demo.
- `meeting_scheduled` → reunión/demo ya agendada (en la versión futura del sistema).
- `nurture` → interesado, pero para más adelante.
- `lost` → no interesado / no encaja.

---

## 3. interest_level

Valores sugeridos:

- `cold` → contesta poco, sin interés claro.
- `warm` → responde, muestra curiosidad, pero sin compromiso aún.
- `hot` → dice explícitamente que le interesa, pide ver demo, etc.

---

## 4. loss_reason

Razones frecuentes cuando un lead se marca como `lost`:

- `no_pain` → no tiene el problema que resolvemos.
- `no_time` → no quiere/puede dedicar tiempo ahora, y es claro que no quiere ni más tarde.
- `no_fit` → no es el tipo de hotel que buscamos (muy pequeño, modelo raro, etc.).
- `happy_with_current_solution` → ya tiene una solución y no quiere mirar alternativas.
- `price_concern` → cree que no va a poder pagar o no quiere invertir.
- `other` → otra razón (describir en `notes`).

---

## 5. interest_signals (implícitos)

Aunque no se guarde como campo aislado, es recomendable anotar en `notes`:

- Si responde rápido.
- Si pregunta por detalles.
- Si menciona explícitamente problemas que encajan muy bien con Roomie.
- Si habla en plural (“estamos buscando”, “estamos mirando opciones…”).

---

## 6. Uso esperado

- Cada vez que Steve tenga información nueva relevante:
  - El sistema debe actualizar los campos correspondientes.
- Al finalizar la conversación:
  - Debe quedar:
    - `funnel_stage` coherente.
    - `interest_level` ajustado.
    - `loss_reason` (si aplica).
    - `notes` con cualquier detalle útil para el equipo comercial.
