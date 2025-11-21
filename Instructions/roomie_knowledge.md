# roomie_knowledge – Conocimiento de producto para Steve

Este documento contiene información que puedes usar para explicar Roomie  
de forma clara, honesta y orientada a valor.

No es un guion literal, son piezas que puedes combinar según el contexto.

---

## 1. Qué es Roomie (definiciones por nivel de detalle)

### 1.1. Versión muy corta (1 frase)

- Roomie es un **recepcionista virtual por WhatsApp 24/7** para hoteles.

### 1.2. Versión corta

- Roomie es un **asistente virtual para hoteles** que atiende a los huéspedes por WhatsApp las 24 horas, respondiendo sus dudas frecuentes y liberando tiempo al equipo de recepción.

### 1.3. Versión media

- Roomie es un **recepcionista virtual especializado en hoteles** que funciona sobre WhatsApp (y otros canales que se definan).  
  Responde automáticamente las preguntas más frecuentes de los huéspedes (wifi, horarios, servicios, normas, ubicación, etc.), en distintos idiomas y a cualquier hora, para que el personal de recepción pueda centrarse en lo realmente importante: check-ins, upselling, incidencias reales y atención de más valor.

### 1.4. Versión un poco más desarrollada (para contexto antes de la demo)

- Roomie es un **SaaS para hoteles** que actúa como un recepcionista virtual conectado al canal de mensajería del hotel (por ejemplo, WhatsApp).  
  A través de una base de conocimiento configurable, Roomie:
  - Responde preguntas frecuentes de huéspedes.
  - Les ayuda a entender servicios, horarios y normas del hotel.
  - Puede dirigirles a reservar, llamar o contactar con el hotel cuando algo requiere atención humana.  
  El objetivo no es sustituir a la recepción, sino **quitarle de encima el volumen de preguntas repetidas** que consumen horas cada día.

---

## 2. Problemas que resuelve Roomie (dolores)

Puedes usar estos puntos para conectar con la realidad del hotel:

- Recepción saturada respondiendo lo mismo todo el día.
- Llamadas por detalles que están en la web o en una hoja de bienvenida.
- WhatsApps de huéspedes que se quedan sin responder o se responden tarde.
- Personal de recepción haciendo malabares entre llamadas, check-ins y mensajes.
- Huéspedes frustrados porque tardan en recibir una respuesta.
- Tiempo de personal invertido en tareas de bajo valor repetitivo.

---

## 3. Beneficios clave para el hotel

### 3.1. Operacionales

- **Libera horas** de trabajo de recepción al día.
- Reduce interrupciones constantes mientras el personal hace check-in, cobra, etc.
- Disminuye el riesgo de mensajes sin responder.
- Ayuda a mantener un estándar de respuesta homogéneo.

### 3.2. Experiencia del huésped

- Respuestas **rápidas** (en segundos) a preguntas recurrentes.
- Atención disponible **24/7**, incluso cuando la recepción no tiene personal.
- Menos frustración por esperas.
- Información clara, en el idioma del huésped (según capacidades actuales).

### 3.3. Para la dirección / propiedad

- Equipo más enfocado en tareas de valor (upselling, experiencia, reputación).
- Percepción de servicio moderno y ágil.
- Escalabilidad: más huéspedes atendidos sin tener que crecer tanto en plantilla.

---

## 4. Cómo se adapta Roomie al hotel

Puntos que puedes usar para tranquilizar dudas:

- Roomie se configura con:
  - Información personalizada del hotel: horarios, servicios, normas, etc.
  - Tono y estilo del hotel (más formal, más cercano).
- Se pueden definir:
  - Qué temas responde Roomie.
  - Qué temas se deben derivar siempre a humanos.
- No requiere grandes integraciones técnicas en la versión inicial (ajusta a la realidad actual de tu producto).

---

## 5. Alcance actual (lo que sí hace)

Adáptalo a la realidad actual de tu implementación, pero como base:

- Responde preguntas frecuentes sobre:
  - Horario de check-in/check-out.
  - Wifi (contraseña, funcionamiento).
  - Desayuno / comidas (horarios, ubicación).
  - Aparcamiento.
  - Servicios (spa, piscina, gimnasio, etc.).
  - Normas básicas (mascotas, fumar, ruidos, etc.).
  - Ubicación y cómo llegar.
- Puede:
  - Responder de forma inmediata sin intervención humana.
  - Derivar al hotel cuando la consulta supera su alcance (por ejemplo, incidencias graves, quejas, temas sensibles).

---

## 6. Lo que NO hace (límites, para no prometer de más)

No afirmes cosas que no sean ciertas en tu versión actual. Como marco general:

- Roomie **no sustituye al 100% al personal de recepción**.
- Roomie **no decide precios ni modifica reservas** por sí solo (a menos que lo implementéis a futuro).
- Roomie **no gestiona pagos** directamente (si esto es cierto en tu caso).
- Roomie **no se inventa políticas** del hotel:
  - Solo responde en base a lo que se haya configurado en su base de conocimiento.

Puedes usar esta idea:

> “Roomie no viene a decidir por vosotros, viene a encargarse de las preguntas que os hacen 20 veces al día.”

---

## 7. Puntos clave que puedes usar según el tipo de hotel

### 7.1. Hotel urbano / de negocios

- Muchos huéspedes de paso, con:
  - Preguntas sobre horarios, wifi, facturas, salidas tempranas.
- Beneficios a enfatizar:
  - Respuesta rápida.
  - Menos llamadas a recepción por cosas sencillas.
  - Mejor gestión de picos de check-in.

### 7.2. Hotel vacacional / de costa

- Huéspedes con muchas dudas sobre:
  - Actividades.
  - Servicios del hotel.
  - Normas de piscina, toallas, animación, etc.
- Beneficios a enfatizar:
  - Menos saturación en recepción por preguntas repetidas.
  - Mejor experiencia del huésped en vacaciones (no quieren esperar).

### 7.3. Cadenas / grupos hoteleros

- Mucha complejidad operativa.
- Varios hoteles, distintos equipos.
- Beneficios a enfatizar:
  - Estandarización de respuesta.
  - Escalabilidad: una forma de atención replicable entre hoteles.
  - Posibilidad de tener una base de conocimiento general + ajustes por hotel (según vuestras capacidades futuras).

---

## 8. Cómo explicar el proceso de implantación (visión simplificada)

Adapta a tu realidad, pero como patrón:

1. **Recogida de información**:
   - Se recopilan horarios, servicios, normas, etc.
2. **Configuración de Roomie**:
   - Se carga esta información en la base de conocimiento.
   - Se ajusta el tono y estilo.
3. **Pruebas internas**:
   - Se testea con el equipo del hotel.
4. **Lanzamiento con huéspedes**:
   - Se comunica el número / canal.
   - Se monitoriza el rendimiento y se ajusta.

Objetivo del discurso:

> “No es un proyecto eterno, es algo que se puede dejar funcionando en poco tiempo y luego se va refinando.”

---

## 9. Frases–marco que puedes reutilizar y adaptar

No las copies tal cual si no quieres, pero son buenas estructuras:

- “Roomie es como tener un recepcionista extra que solo se dedica a responder preguntas repetidas, y nunca se cansa.”
- “La idea no es sustituir a nadie, es quitar de en medio todo lo que os roba tiempo y no aporta mucho valor.”
- “Mientras vuestro equipo hace check-ins, cobra, atiende incidencias… Roomie puede ir contestando Whatsapp con las típicas dudas.”
- “Hoy Roomie es un plus, pero muy pronto este tipo de atención será lo mínimo que los huéspedes esperen.”

---
