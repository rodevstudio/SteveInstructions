# Estructura de Datos para Registro de Leads

Este documento define la estructura exacta de datos que debe enviarse al sistema de registro de leads cuando se cierra una reunión.

## Campos Requeridos

### Información del Hotel
```
hotel_name: "Nombre completo del hotel"
city: "Ciudad donde está ubicado"
country: "País (CRÍTICO - determina closer asignado)"
hotel_type: "urbano | vacacional | resort | boutique | rural | cadena"
room_count: "Número aproximado de habitaciones"
primary_languages: ["Idioma1", "Idioma2", "Idioma3"]
current_channels: ["Booking", "WhatsApp", "Web", "Instagram", "Email"]
```

### Dolor Identificado
```
identified_pains: [
  "Dolor principal en 1 frase",
  "Dolor secundario si existe"
]
```

### Información de Contacto
```
contact_name: "Nombre completo del contacto"
contact_role: "Cargo en el hotel (Director, Propietario, etc.)"
contact_email: "email@hotel.com"
contact_phone: "+34XXXXXXXXX (siempre con prefijo internacional)"
preferred_language: "Idioma preferido para la reunión"
preferred_time: "mañanas | tardes | indiferente"
```

### Estado de la Reunión
```
meeting_status: "pending_confirmation"
```

### Temperatura del Lead
```
lead_temperature: "hot | warm | cold"
```

**Definiciones**:
- **hot**: Dolor claro + urgencia evidente + pidió reunión proactivamente
- **warm**: Dolor identificado + interés genuino + sin urgencia inmediata
- **cold**: Interés bajo + múltiples objeciones sin resolver + duda evidente

### Notas Internas para el Closer
```
internal_notes: "
CONTEXTO:
- Hotel: [nombre] | [ciudad, PAÍS]
- Tipo: [tipo] | Tamaño: [X hab] - [comentario relevante sobre tamaño]
- Perfil: [independiente | cadena con X propiedades]

DOLOR:
[Descripción del dolor en 1-2 frases usando las palabras exactas del lead cuando sea posible]

TEMPERATURA:
[Hot/Warm/Cold] - [justificación breve de por qué esta temperatura]

CONTEXTO ADICIONAL:
- Presupuesto: [mencionó limitaciones | no mencionó | presupuesto aprobado]
- Urgencia: [alta temporada próxima | sin urgencia | necesidad inmediata]
- Herramientas actuales: [qué usan ahora si mencionaron]
- Objeciones principales: [cuáles surgieron]
- Idiomas críticos: [idiomas que más necesitan]
- Particularidades: [cualquier detalle relevante]
- Si hotel pequeño: [¿interés real? ¿dudas sobre viabilidad?]
- Si cadena: [¿decisor final? ¿necesita aprobación?]

NOTAS PARA LA REUNIÓN:
- Enfocar presentación en: [beneficio específico que más resonó]
- Preparar casos de éxito de: [tipo de hotel similar]
- Revisar viabilidad comercial si: [contexto especial]
- Tener listos datos sobre: [funcionalidad específica que preguntaron]
- Otros: [cualquier recomendación adicional]
"
```

## Ejemplo Completo - Hotel Pequeño

```json
{
  "hotel_name": "Hotel Casa Luna",
  "city": "Granada",
  "country": "España",
  "hotel_type": "boutique",
  "room_count": "12",
  "primary_languages": ["Español", "Inglés", "Alemán", "Francés"],
  "current_channels": ["Booking", "Email", "Teléfono"],
  "identified_pains": [
    "Propietario no puede estar disponible 24/7, pierde mensajes de Booking nocturnos",
    "Barrera idiomática con 50% de huéspedes extranjeros"
  ],
  "contact_name": "María González",
  "contact_role": "Propietaria",
  "contact_email": "maria@casaluna.com",
  "contact_phone": "+34612345678",
  "preferred_language": "Español",
  "preferred_time": "tardes",
  "meeting_status": "pending_confirmation",
  "lead_temperature": "warm",
  "internal_notes": "
CONTEXTO:
- Hotel: Casa Luna | Granada, España
- Tipo: Boutique rural | Tamaño: 12 hab - Hotel pequeño pero con ocupación 80-90% en temporada
- Perfil: Independiente, gestionado directamente por propietaria

DOLOR:
Propietaria sola en gestión. No puede estar disponible 24/7 para consultas. Pierde mensajes de Booking por la noche y cree que ha perdido reservas directas por esto. 50% huéspedes extranjeros con dificultad idiomática.

TEMPERATURA:
Warm - Dolor real y urgencia moderada, pero sensible a precio por ser hotel pequeño.

CONTEXTO ADICIONAL:
- Presupuesto: Mencionó presupuesto ajustado, necesitará justificación ROI clara
- Urgencia: Sin urgencia inmediata, pero frustrada con situación actual
- Herramientas actuales: No usa ninguna herramienta digital, todo manual
- Objeciones principales: Duda si Roomie es 'para hoteles como el suyo' por tamaño
- Idiomas críticos: Alemán, francés, inglés (en ese orden de volumen)
- Particularidades: Alta temporada abril-octubre, fuera temporada cierra parcialmente
- Si hotel pequeño: Interés real, pero necesita ver viabilidad comercial clara

NOTAS PARA LA REUNIÓN:
- Enfocar en: Ahorro tiempo propietaria + no perder reservas nocturnas
- Preparar pricing específico para hoteles boutique
- Ser honesto sobre viabilidad comercial; si no encaja por tamaño, decirlo claramente
- Mencionar casos de hoteles boutique/rurales si existen
- Proponer implementación gradual (empezar con pocos idiomas/canales)
"
}
```

## Ejemplo Completo - Cadena Grande

```json
{
  "hotel_name": "Grupo Hotelero Costa Azul",
  "city": "Múltiples (Málaga, Cádiz, Almería)",
  "country": "España",
  "hotel_type": "cadena",
  "room_count": "150-300 por propiedad (5 hoteles)",
  "primary_languages": ["Español", "Inglés", "Alemán", "Francés", "Holandés"],
  "current_channels": ["Booking", "Expedia", "WhatsApp", "Web", "Instagram"],
  "identified_pains": [
    "Recepción colapsada en temporada alta con consultas básicas en múltiples idiomas",
    "Staff temporal sin formación completa genera inconsistencias en información",
    "Reseñas negativas recurrentes sobre 'falta de información' y 'recepción saturada'"
  ],
  "contact_name": "Carlos Martínez",
  "contact_role": "Director de Operaciones de la Cadena",
  "contact_email": "carlos.martinez@costaazul.com",
  "contact_phone": "+34655123456",
  "preferred_language": "Español",
  "preferred_time": "mañanas",
  "meeting_status": "pending_confirmation",
  "lead_temperature": "hot",
  "internal_notes": "
CONTEXTO:
- Hotel: Grupo Costa Azul | Múltiples ubicaciones costa andaluza, España
- Tipo: Cadena hoteles vacacionales | Tamaño: 5 propiedades, 150-300 hab/hotel
- Perfil: Director Operaciones cadena, decisor real con presupuesto aprobado

DOLOR:
Recepción colapsada julio-agosto respondiendo consultas básicas en múltiples idiomas. Staff temporal sin formación completa causa inconsistencias. Reseñas negativas recurrentes sobre 'falta información' o 'recepción saturada'. Afecta a las 5 propiedades.

TEMPERATURA:
Hot - Problema urgente, presupuesto ya aprobado para soluciones digitales, decisor en llamada, necesita solución antes de próxima temporada alta.

CONTEXTO ADICIONAL:
- Presupuesto: Ya aprobado para herramientas digitales, presupuesto NO es objeción
- Urgencia: Alta - Quiere implementar antes de temporada alta (mayo-junio)
- Herramientas actuales: Ya usan PMS (Opera) y channel manager, buscan integración
- Objeciones principales: Ya probaron chatbot genérico y no funcionó, busca solución específica hotelera
- Idiomas críticos: Español, inglés, alemán, francés, holandés (en orden de volumen)
- Particularidades: Temporada alta muy concentrada (junio-septiembre), necesita escalabilidad rápida
- Si cadena: Decisor real, puede decidir implementación en las 5 propiedades si funciona bien

NOTAS PARA LA REUNIÓN:
- Lead MUY caliente, preparar propuesta implementación multi-propiedad
- Enfocar en: Escalabilidad cadena + consistencia entre hoteles + reducción carga temporada alta
- Preparar casos éxito de cadenas similares (vacacionales/costa)
- Hablar integración con Opera PMS y su channel manager actual
- Proponer piloto en 1 hotel antes de escalar a las 5 propiedades
- Mencionar personalización por propiedad manteniendo estándares grupo
- Timeline agresivo: necesita estar operativo en 3-4 meses
"
}
```

---

**Importante**: Todos los campos deben completarse. Si falta información crítica, obtenerla antes de cerrar la reunión.