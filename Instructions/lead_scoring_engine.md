# lead_scoring_engine – Criterios de scoring de leads

Este documento define **cómo valorar un lead** a partir de sus características  
y devolver un nivel de prioridad + recomendación de acción.

---

## 1. Variables principales

La tool debe tener en cuenta (cuando haya datos):

- `rooms_band`: pequeño / medio / grande / muy grande.
- `is_chain`: true/false.
- `role` del contacto:
  - Director / GM.
  - Responsable de operaciones / recepción.
  - Comercial / revenue.
  - Otro.
- `main_pain_point`:
  - Si hay dolor claro en recepción / atención.
- `interest_signals`:
  - Responde rápido.
  - Hace preguntas.
  - Expresa explícitamente interés.

---

## 2. Reglas generales de scoring

### 2.1. Por tamaño de hotel

- Pequeño:
  - Puntos bajos.
- Medio:
  - Puntos medios.
- Grande o muy grande:
  - Puntos altos.

### 2.2. Por cadena

- `is_chain = true`:
  - Sumar puntos.
  - Más aún si cadena tiene varios hoteles relevantes.

### 2.3. Por rol

- Director / GM / Propietario:
  - Máximos puntos (decisor).
- Operaciones / recepción:
  - Buenos puntos (influyente, a veces decisor).
- Comercial / revenue:
  - Puntos medios (puede ser buen sponsor interno).
- Otros:
  - Puntos bajos.

### 2.4. Por dolor

- Si hay un dolor muy claro:
  - “Recepción saturada”, “muchas preguntas repetidas”, etc.:
  - Sumar puntos altos.
- Si no hay dolor claro:
  - Quitar puntos.

### 2.5. Por señales de interés

- Si el lead:
  - Responde rápido.
  - Hace preguntas.
  - Muestra curiosidad real.
- Sumar puntos.

---

## 3. Resultado del scoring

La tool debe devolver:

- `score`: numérico (0–100) o similar.
- `priority`:
  - `high`
  - `medium`
  - `low`
- `recommended_action`:
  - `"push_for_meeting"` → Steve debe insistir (con respeto) en cerrar reunión.
  - `"nurture"` → Mantener relación suave, sin presión, para más adelante.
  - `"deprioritize"` → No dedicarle demasiados esfuerzos.
  - `"escalate_to_human"` → Puede ser interesante que un humano entre antes (ej. cadena grande).

---

## 4. Interpretación para Steve

Esta tool no habla con el lead, solo devuelve datos para que Steve actúe.

- `priority = high` + `push_for_meeting`:
  - Steve debe centrarse en cerrar reunión con decisión.
- `priority = high` + `escalate_to_human`:
  - Steve debe informar al sistema para que avise a un humano.
- `priority = medium`:
  - Steve actúa normal, sin forzar demasiado.
- `priority = low`:
  - Steve puede ser más ligero en insistencia.
  - Si ve poco encaje, puede cerrar antes de perder tiempo.

---

## 5. Casos extremos

- Lead muy pequeño, sin dolor y sin interés:
  - Score bajo, `deprioritize`.
- Cadena grande, rol de director, dolor claro:
  - Score alto, `escalate_to_human` o `push_for_meeting`.

La tool debe apoyar este tipo de decisiones de forma consistente.
