# alert_human – Notificaciones a humanos

Este documento define **cómo debe estructurarse una alerta** cuando Steve detecta  
que un humano debería intervenir o revisar el caso.

---

## 1. Objetivo de la alerta

La alerta debe permitir que un miembro del equipo:

- Entienda rápidamente qué pasa.
- Sepa si debe:
  - Llamar.
  - Responder él mismo por WhatsApp.
  - Revisar algo (queja, tema legal, etc.).

---

## 2. Situaciones típicas que generan alerta

- Lead de alto valor:
  - Cadena grande.
  - Grupo con varios hoteles interesantes.
- Conversación delicada:
  - Quejas serias.
  - Comentarios que puedan escalar.
- Temas fuera de alcance:
  - Cuestiones legales.
  - Propuestas de partnership.
  - Integraciones muy técnicas.

---

## 3. Contenido mínimo de la alerta

La tool debe producir algo que incluya:

- `lead_id`
- Datos básicos:
  - `name`
  - `role`
  - `hotel_name`
  - `chain_name` (si aplica)
  - `country`, `city`
- Motivo de la alerta:
  - Texto corto: “cadena grande interesada”, “queja seria”, “tema legal”, etc.
- Estado actual de la conversación:
  - Fase aproximada (exploración, propuesta, objeciones, cierre).
- Recomendación sugerida:
  - “Revisar conversación y llamar ASAP.”
  - “Entrar a contestar directamente por WhatsApp.”
  - “Revisar por tema legal.”

---

## 4. Estilo para el equipo

El resumen para humano debe ser:

- Muy directo.
- Sin adornos.
- Enfocado en:
  - Qué ha pasado.
  - Qué riesgo/oportunidad hay.
  - Qué siguiente paso se recomienda.

Ejemplo de plantilla conceptual:

- “Lead: [Nombre], [Rol], [Hotel], [Ciudad, País].”
- “Motivo alerta: [cadena grande + muestra interés en ver demo].”
- “Resumen: ha comentado X, Y, Z. Ha pedido A / ha mencionado B.”
- “Recomendación: revisar conversación y llamarle cuanto antes.”

---

## 5. Relación con otras tools

- Si se dispara `alert_human`, normalmente también:
  - El CRM debería tener el lead bien rellenado.
  - `conversation_logger` puede registrar este evento como algo a analizar después (por ejemplo: “big_chain_alert”).
