# hotel_info_search – Contexto de hoteles para Steve

Este documento sirve para **interpretar y resumir información de un hotel**  
a partir de datos externos (web, ficha pública, etc.) y devolver algo útil para Steve.

---

## 1. Objetivo del resumen

Dado un hotel/cadena, la tool debe devolver un contexto breve y usable:

- Nombre del hotel.
- Ubicación principal.
- Tipo de hotel.
- Tamaño aproximado.
- Pertenencia a cadena.
- Pistas útiles para el enfoque comercial.

---

## 2. Clasificación de tipo de hotel

Si la información lo permite, clasificar el hotel en una de estas categorías:

- **Urbano / Business**
  - Ubicado en ciudad.
  - Orientado a negocios, trabajo, estancias cortas.
- **Vacacional / Resort**
  - Ubicado en zona de costa, montaña o destino turístico.
  - Enfoque en ocio, familia, vacaciones.
- **Mixto**
  - Combina ocio y negocios de forma evidente.
- **Boutique / Pequeño**
  - Pocas habitaciones, experiencia más íntima/personalizada.
- **Otro / No claro**
  - Cuando no haya datos suficientes.

---

## 3. Estimación de tamaño

Si hay datos sobre nº de habitaciones, clasificar en rangos:

- **Pequeño**: hasta ~40 habitaciones.
- **Medio**: 41–120 habitaciones.
- **Grande**: 121–300 habitaciones.
- **Muy grande**: más de 300 habitaciones.

Si no hay datos claros:

- Devolver tamaño como “desconocido”.

---

## 4. Cadena vs. Independiente

- Si el hotel pertenece claramente a un grupo/cadena:
  - `is_chain = true`
  - `chain_name = nombre de la cadena`
- Si parece un hotel independiente:
  - `is_chain = false`
- Si el nombre es de cadena y hay varios hoteles:
  - Marcar `ambiguous = true` y listar candidatos:

Ejemplo conceptual de salida:

- `match_type`: `"hotel"` | `"chain"` | `"ambiguous"`
- `candidates`: lista de:
  - `name`
  - `city`
  - `country`
  - `rooms_estimate`
  - `chain_name` (si aplica)
  - `hotel_type` (urbano, vacacional, etc.)

---

## 5. Ángulos para Steve según el tipo de hotel

La tool debe ayudar a Steve dándole pistas sobre qué ángulos de dolor/beneficio son más relevantes:

### 5.1. Hotel urbano / business

- Dolor típico:
  - Alta rotación de huéspedes.
  - Muchas dudas sobre:
    - Check-in temprano.
    - Facturas.
    - Transporte / cómo llegar.
- Ángulo sugerido:
  - “Agilidad y rapidez de respuesta”.
  - “Menos llamadas por temas simples mientras recepción está atendiendo check-ins.”

### 5.2. Hotel vacacional / resort

- Dolor típico:
  - Muchos huéspedes preguntando por:
    - Horarios de comida.
    - Actividades.
    - Servicios (piscina, spa, kids club…).
- Ángulo sugerido:
  - “Reducir saturación de recepción por dudas repetidas.”
  - “Mejor experiencia para familias que no quieren esperar respuesta.”

### 5.3. Cadena / grupo

- Dolor típico:
  - Coordinación entre varios hoteles.
  - Diferentes equipos, políticas, etc.
- Ángulo sugerido:
  - “Estandarizar respuestas.”
  - “Escalar la atención sin escalar el número de personas al mismo ritmo.”

---

## 6. Salida esperada (a nivel conceptual)

La tool debe devolver un resumen estructurado (no en texto libre para el usuario) que contenga, como mínimo:

- `primary_name`: nombre principal.
- `primary_location`: ciudad + país (si se sabe).
- `hotel_type`: urbano / vacacional / mixto / boutique / otro.
- `rooms_band`: pequeño / medio / grande / muy grande / desconocido.
- `is_chain`: true/false.
- `chain_name`: si existe.
- `ambiguous`: true/false.
- `candidates`: si hay ambigüedad.
- `angle_notes`: texto breve con recomendaciones de enfoque para Steve.

Steve no debe enseñar esta estructura al lead, sino usarla para:

- Saber de qué tipo de hotel se trata.
- Elegir mejor qué dolores/beneficios enfatizar.
- Guardar datos útiles en el CRM.
