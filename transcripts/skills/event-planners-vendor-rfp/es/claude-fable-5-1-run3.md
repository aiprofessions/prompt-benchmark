# Transcript — skill event-planners-vendor-rfp [es] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:38:32+00:00
- duration_s: 71.0
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: f8484832ec8b99d2b8c1e83a23a5e10d3c77bc11ebb4e159ee01dab1dfc58df0
- skill_sha256: 3a4c08583cf16645cf8a45cfcf90f60600dd4eba87e7e284751fbfb3fe93c986

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: event-planners-vendor-rfp
description: "Úsala cuando pegues el briefing de un evento para obtener una RFP con requisitos, precios desglosados y pendientes por confirmar."
---

# Generador de RFP para proveedores de eventos

## Qué hace

Convierte el briefing en una solicitud de propuesta (RFP) para proveedores de eventos en México o España. Conserva literalmente los datos operativos y exige que el proveedor planifique conforme a las restricciones del espacio. Entrega un documento para revisión y envío, con precios desglosados y datos faltantes marcados como POR CONFIRMAR.

## Qué necesita

- Cliente, organizador, contacto profesional autorizado y nombre o tipo de evento.
- País (MX o ES), espacio y dirección, si constan.
- Fechas y horarios de acceso, carga y descarga, montaje (load-in), evento y desmontaje (load-out).
- Asistentes y cantidades por dieta o alergia, sin nombres ni datos que identifiquen a las personas.
- Servicios, equipos y requisitos técnicos.
- Restricciones de cocina, rigging o puntos de suspensión del espacio, accesos y carga y descarga.
- Presupuesto y moneda, con el formato original.
- Fecha límite de respuesta, fecha de decisión y criterios de evaluación.

Si faltan datos, continúa y escribe POR CONFIRMAR en el apartado correspondiente y en Pendientes. Si el usuario pide aclararlos antes de redactar, reúne las preguntas en un único mensaje. No adivines: los criterios propuestos del procedimiento son la única excepción a dejar los datos ausentes por confirmar; no son decisiones del cliente.

## Procedimiento

1. Comprueba la privacidad antes de extraer datos. No reproduzcas identificadores ni datos de salud vinculados a asistentes. Trabaja solo con un briefing desidentificado y herramientas aprobadas; si las cantidades o combinaciones permiten identificar a alguien, detén la redacción y pide una versión segura. No alteres cifras para anonimizar por tu cuenta.
2. Identifica el país solo si consta; no lo deduzcas de la moneda. Adapta el texto de enlace: recinto, banquete, meseros y anticipo (MX); espacio, catering, camareros y señal o depósito (ES). Mantén literal el vocabulario de los requisitos. Si falta el país, márcalo POR CONFIRMAR.
3. Extrae una lista de todas las cantidades, fechas, horas y especificaciones técnicas, incluidas dietas, alergias, accesos, carga y descarga, montaje y desmontaje. Copia cada dato exactamente, incluidos rangos, unidades, “aprox.”, “máx.” y “antes de”. No conviertas monedas ni formatos.
4. Detecta contradicciones sin corregirlas. No sumes dietas y alergias como categorías excluyentes salvo indicación expresa. Si hay una discrepancia aritmética comprobable, muestra la operación en Pendientes; si puede haber solapamiento, pide aclararlo.
5. Traslada cada limitación de cocina, rigging y acceso a Restricciones del espacio. Escribe “El proveedor debe planificar conforme a esta restricción: [texto literal]” y pide una solución operativa para cada una. No atribuyas capacidades no documentadas.
6. Para servicios alimentarios o alergias declaradas, solicita por escrito el procedimiento de manejo de alérgenos y prevención del contacto cruzado. Enumera cada alergia y dieta médica con su cantidad literal y exige que el protocolo responda a cada una: almacenamiento, preparación, servicio, identificación de platos y formación del personal. No uses “alergias varias”. Si una dieta no está clasificada, inclúyela y pide aclaración; si faltan datos, escribe POR CONFIRMAR, nunca “sin alergias”.
7. Enumera siempre líneas separadas para: alimentos/servicio y cada equipo; personal; traslado; montaje; desmontaje; cargo por servicio; propina; subtotal antes de impuestos; IVA (MX/ES) desglosado; otros impuestos, si corresponden, uno por línea; total. Pide cantidad, unidad, precio unitario y total por concepto, y tasa o tipo e importe para cada impuesto. El proveedor debe indicar “No aplica” donde corresponda. No inventes importes ni tasas, ni permitas agrupar traslado, montaje, desmontaje o impuestos con otros conceptos.
8. Solicita certificado de seguro y condiciones de cancelación y anticipo (MX) o señal/depósito (ES), con importe o porcentaje, vencimientos y devolución. Pide documentos e importes al proveedor sin presentarlos como obligaciones legales verificadas.
9. Copia literalmente el plazo de respuesta y la fecha de decisión, o escribe POR CONFIRMAR. Copia los criterios del briefing si existen. Si no existen, incluye el título “Criterios de evaluación propuestos — confirmar con el cliente antes de enviar” y esta lista: cumplimiento de requisitos; claridad del precio desglosado; experiencia/referencias; plan operativo ante las restricciones del lugar; protocolo de alérgenos/seguridad, si aplica; seguro y condiciones. Incluye alérgenos cuando haya alimentación o alergias; no limites la seguridad a esos servicios. No inventes ponderaciones. Añade a Pendientes la aprobación de los criterios antes del envío.
10. Marca los datos ausentes como POR CONFIRMAR, incluidos presupuesto, contactos, teléfonos, fecha de emisión, moneda y capacidades del espacio. Marca precios y documentos solicitados como “A completar por el proveedor”. No presentes los criterios propuestos como datos aportados por el cliente.
11. Redacta los ocho apartados del formato en su orden. Reúne en Pendientes todos los datos faltantes, ambigüedades, contradicciones y confirmaciones necesarias. No resuelvas ninguno por inferencia.
12. Coteja la RFP con la lista del paso 3: ninguna cifra, plazo o especificación debe faltar o cambiar. Verifica cada restricción, cada alergia y dieta médica en la solicitud del protocolo, todas las líneas de precio, seguro, condiciones y calendario. Comprueba que los criterios sean literales o estén marcados como propuestos y que se cumpla la privacidad. Corrige cualquier desviación sin modificar los datos del briefing.

## Formato de salida

```markdown
## Encabezado de la RFP
Solicitud de propuesta: [servicios] para [evento]
Cliente: [literal o POR CONFIRMAR]
Organizador y contacto profesional autorizado: [literal o POR CONFIRMAR]
Fecha de emisión y país: [datos del briefing o POR CONFIRMAR]

## Resumen del evento
- Fecha, espacio y dirección: [literales o POR CONFIRMAR]
- Asistentes: [literal o POR CONFIRMAR]
- Acceso, carga y descarga, montaje: [literales o POR CONFIRMAR]
- Evento y desmontaje: [literales o POR CONFIRMAR]
- Presupuesto y moneda: [formato original o POR CONFIRMAR]

## Alcance y requisitos
- [Cada servicio y equipo con sus requisitos técnicos literales]
- Dietas y alergias: [cada una con su cantidad literal o POR CONFIRMAR]

## Restricciones del espacio
- El proveedor debe planificar conforme a esta restricción: [texto literal].
- Explique su solución operativa para cada restricción.
- [Condiciones necesarias no documentadas: POR CONFIRMAR]

## Formato de precio
Moneda: [formato original o POR CONFIRMAR]. Importes: A completar por el proveedor.
| Concepto | Cantidad | Unidad | Precio unitario | Total |
|---|---|---|---|---|
| Alimentos/servicio: [una línea por cada servicio] | | | | |
| Equipo: [una línea por cada equipo] | | | | |
| Personal: [desglosar por función solicitada] | | | | |
| Traslado | | | | |
| Montaje | | | | |
| Desmontaje | | | | |
| Cargo por servicio (si aplica) | | | | |
| Propina (si aplica) | | | | |
| Subtotal antes de impuestos | | | | |
| IVA (MX/ES): [tasa o tipo e importe, por proveedor] | | | | |
| Otros impuestos, si corresponden: [uno por línea] | | | | |
| Total | | | | |
Indique “No aplica” donde corresponda. No sustituya el desglose por un precio global.
Mantenga impuestos, traslado, montaje y desmontaje separados; evite duplicar costes.

## Documentos requeridos al proveedor
A completar por el proveedor:
- Certificado de seguro.
- Condiciones de cancelación.
- Condiciones de anticipo (MX) o señal/depósito (ES): importe o porcentaje, vencimientos y devolución.
- Si hay alimentación o alergias: procedimiento escrito de manejo de alérgenos y prevención del contacto cruzado para [cada alergia y dieta médica con su cantidad literal].
- El procedimiento debe explicar almacenamiento, preparación, servicio, identificación de platos y formación del personal para cada caso.

## Calendario y evaluación
- Fecha límite de respuesta: [literal o POR CONFIRMAR]
- Fecha de decisión: [literal o POR CONFIRMAR]
- Criterios de evaluación: [literales del briefing; si faltan, usar el siguiente bloque]
Criterios de evaluación propuestos — confirmar con el cliente antes de enviar
1. Cumplimiento de requisitos.
2. Claridad del precio desglosado.
3. Experiencia/referencias.
4. Plan operativo ante las restricciones del lugar.
5. Protocolo de alérgenos/seguridad, si aplica.
6. Seguro y condiciones.
- Ponderaciones: [literales o POR CONFIRMAR]

## Pendientes (por confirmar)
- [Cada dato faltante, ambigüedad o contradicción; operación solo si procede]
- [Si se proponen criterios: obtener confirmación del cliente antes de enviar]
```

## Límites

- No inventes datos operativos, contactos, capacidades, estadísticas, leyes, artículos, autoridades, fechas, tasas de impuestos ni fuentes. No añadas citas distintas de la indicada abajo.
- No cambies cantidades ni horarios para hacerlos coherentes. No supongas que una dieta equivale a una alergia o que las categorías no se solapan.
- No presentes criterios propuestos como acordados ni inventes ponderaciones. El cliente debe confirmar los criterios propuestos antes de enviar.
- No certifiques cumplimiento normativo, seguridad alimentaria ni cobertura del seguro. El profesional responsable debe verificar vigencia, alcance y adecuación del seguro, condiciones económicas, tratamiento fiscal y viabilidad técnica con el proveedor y el espacio.
- Licencias, alcohol, alérgenos e higiene alimentaria dependen de la normativa local o autonómica: el profesional responsable, habilitado cuando corresponda, debe confirmar los requisitos con el espacio y la autoridad competente antes de contratar.
- No se ha verificado ninguna fuente oficial específica sobre IA para organizadores de eventos en ES/MX. Consulta al organismo profesional o a la autoridad competente sobre los requisitos aplicables.
- Privacidad: pide al usuario desidentificar el briefing antes de compartirlo y utilizar únicamente herramientas aprobadas por su organización para datos personales. No incluyas listas nominales ni datos de salud individuales; las cantidades agregadas tampoco deben permitir reidentificar.
- Si se envían datos de asistentes, el responsable debe verificar la protección de datos aplicable, la necesidad de compartirlos y los destinatarios autorizados; en México, LFPDPPP 2025. En España, confirma los requisitos con el responsable de protección de datos.
- Fuente permitida: Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- El profesional responsable debe aprobar la RFP y resolver los pendientes que impidan enviarla o contratar; el documento no sustituye esa revisión.
- Consulta references/checklist.md antes de enviar o firmar.

## Ejemplo

Entrada ficticia:
```text
Cliente: Muestra; evento: cena; espacio: Salón Example (ES).
Asistentes: 40; 5 vegetarianos; 2 alergia a frutos secos; 1 celiaquía.
Servicio: catering; montaje 17:00–18:30; cena 20:00–22:30; desmontaje 22:30–00:00.
Cocina: sin fuegos; rigging: no permitido; acceso: montacargas hasta 19:00.
Fecha, presupuesto, moneda, contacto, respuesta, decisión y criterios: POR CONFIRMAR.
```

Salida abreviada (la versión completa desarrolla las líneas de precio y todos los pendientes):
```markdown
## Encabezado de la RFP
Solicitud de propuesta de catering para Muestra; cena en Salón Example (ES).
## Resumen del evento
Asistentes: 40; montaje 17:00–18:30; cena 20:00–22:30; desmontaje 22:30–00:00.
## Alcance y requisitos
Catering; 5 vegetarianos; 2 alergia a frutos secos; 1 celiaquía.
## Restricciones del espacio
Planifique conforme a: cocina: sin fuegos; rigging: no permitido; acceso: montacargas hasta 19:00. Explique su solución.
## Formato de precio
Separe catering, equipos, personal, traslado, montaje, desmontaje, cargo por servicio, propina, subtotal, IVA (ES), otros impuestos si corresponden y total; indique “No aplica” donde corresponda.
## Documentos requeridos al proveedor
Certificado de seguro; condiciones de cancelación y señal/depósito; protocolo escrito de alérgenos y contacto cruzado para “2 alergia a frutos secos” y “1 celiaquía”.
## Calendario y evaluación
Respuesta y decisión: POR CONFIRMAR. Criterios de evaluación propuestos — confirmar con el cliente antes de enviar: cumplimiento de requisitos; claridad del precio desglosado; experiencia/referencias; plan operativo ante las restricciones del lugar; protocolo de alérgenos/seguridad; seguro y condiciones.
## Pendientes (por confirmar)
Fecha, emisión, dirección, organizador, contacto, presupuesto, moneda, respuesta, decisión y ponderaciones; confirmar criterios antes de enviar; aclarar dieta vegetariana y acceso para desmontaje 22:30–00:00 con montacargas hasta 19:00.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Arma la solicitud de propuesta (RFP) para el catering con este briefing.
Evento: boda de la familia Ejemplo (ficticia). Sábado 20 de marzo de 2027. Lugar: Hacienda Muestra, Tequisquiapan, Querétaro, México (ficticia). La hacienda NO tiene cocina: solo un área de servicio con toma de agua y corriente de 110 V.
Invitados: 180. Horario: cóctel 18:00–19:00, cena de tres tiempos 20:00, taquiza 00:30.
La barra libre la contrata el cliente aparte: no incluir bebidas alcohólicas.
Dietas: 12 vegetarianos, 4 veganos, 2 celíacos, 1 persona con alergia grave a mariscos.
Propuestas antes del 15 de diciembre de 2026. Decisión el 8 de enero de 2027.
````

## Output (verbatim stdout, session metadata stripped)

SOLICITUD DE PROPUESTA (RFP) — BANQUETE / CATERING

ENCABEZADO DE LA RFP
Solicitud de propuesta: catering (cóctel, cena de tres tiempos y taquiza) para la boda de la familia Ejemplo (ficticia).
Cliente: familia Ejemplo (ficticia)
Organizador y contacto profesional autorizado: POR CONFIRMAR
Fecha de emisión: POR CONFIRMAR
País: México (MX)

RESUMEN DEL EVENTO
- Fecha: Sábado 20 de marzo de 2027
- Recinto: Hacienda Muestra, Tequisquiapan, Querétaro, México (ficticia). Dirección exacta: POR CONFIRMAR
- Asistentes: Invitados: 180
- Acceso, carga y descarga, montaje: POR CONFIRMAR
- Horario del evento (literal): cóctel 18:00–19:00, cena de tres tiempos 20:00, taquiza 00:30
- Desmontaje: POR CONFIRMAR
- Presupuesto y moneda: POR CONFIRMAR

ALCANCE Y REQUISITOS
- Servicio de catering para 180 invitados en tres momentos:
    1. Cóctel 18:00–19:00
    2. Cena de tres tiempos 20:00 (hora de fin: POR CONFIRMAR)
    3. Taquiza 00:30 (hora de fin: POR CONFIRMAR)
- Bebidas alcohólicas: NO incluir. Literal del briefing: "La barra libre la contrata el cliente aparte: no incluir bebidas alcohólicas."
- Bebidas no alcohólicas, hielo, cristalería, mantelería, mobiliario, equipo de cocina móvil, generación eléctrica adicional: POR CONFIRMAR si forman parte del alcance; el proveedor debe indicar qué incluye y qué excluye.
- Personal: meseros, capitanes, cocina y limpieza: cantidad propuesta por el proveedor, desglosada por función.
- Dietas y alergias (cantidades literales, no sumar entre categorías, puede haber solapamiento):
    - 12 vegetarianos
    - 4 veganos
    - 2 celíacos
    - 1 persona con alergia grave a mariscos

RESTRICCIONES DEL RECINTO
- El proveedor debe planificar conforme a esta restricción: "La hacienda NO tiene cocina: solo un área de servicio con toma de agua y corriente de 110 V."
  Explique su solución operativa: cómo producirá, conservará en frío/caliente, regenerará y servirá tres servicios (cóctel 18:00–19:00, cena 20:00, taquiza 00:30) para 180 invitados sin cocina en sitio; qué equipo traerá (cocina móvil, refrigeración, generador u otro), qué carga eléctrica requiere frente a la corriente de 110 V disponible y qué necesita del recinto.
- Rigging o puntos de suspensión: POR CONFIRMAR (no documentado).
- Accesos, carga y descarga, horario de montaje y desmontaje, estacionamiento de vehículos del proveedor: POR CONFIRMAR (no documentado).
- Capacidad eléctrica (amperaje) de la corriente de 110 V, caudal de la toma de agua, dimensiones del área de servicio, permiso para instalar fuego/gas/generador: POR CONFIRMAR (no documentado). No se atribuye al recinto ninguna capacidad no indicada en el briefing.

FORMATO DE PRECIO
Moneda: POR CONFIRMAR. Importes: A completar por el proveedor.
Indique cantidad, unidad, precio unitario y total por concepto. Para cada impuesto, tasa e importe. Escriba "No aplica" donde corresponda. No sustituya el desglose por un precio global. Mantenga impuestos, traslado, montaje y desmontaje en líneas separadas; no duplique costes.

  Concepto                                                   Cant.  Unidad  P. unitario  Total
  ---------------------------------------------------------  -----  ------  -----------  -----
  Alimentos/servicio: cóctel 18:00–19:00 (180)
  Alimentos/servicio: cena de tres tiempos 20:00 (180)
  Alimentos/servicio: taquiza 00:30 (180)
  Alimentos/servicio: menús especiales (12 vegetarianos,
    4 veganos, 2 celíacos, 1 alergia grave a mariscos)
  Bebidas no alcohólicas (si aplica / POR CONFIRMAR alcance)
  Equipo: cocina móvil / producción sin cocina en sitio
  Equipo: refrigeración y conservación
  Equipo: generador o solución eléctrica (si aplica)
  Equipo: mobiliario, mantelería, cristalería, loza (si aplica)
  Equipo: [cada otro equipo, una línea por equipo]
  Personal: meseros
  Personal: capitanes / coordinación
  Personal: cocina
  Personal: limpieza / lavaloza
  Personal: [cada otra función]
  Traslado
  Montaje
  Desmontaje
  Cargo por servicio (si aplica)
  Propina (si aplica)
  Subtotal antes de impuestos
  IVA (MX): tasa e importe, por proveedor
  Otros impuestos, si corresponden: [uno por línea]
  Total

DOCUMENTOS REQUERIDOS AL PROVEEDOR
A completar por el proveedor:
- Certificado de seguro (responsabilidad civil y el que el proveedor considere aplicable), con vigencia y cobertura.
- Condiciones de cancelación.
- Condiciones de anticipo (MX): importe o porcentaje, vencimientos y devolución.
- Procedimiento escrito de manejo de alérgenos y prevención del contacto cruzado, que responda por separado a cada caso:
    - 1 persona con alergia grave a mariscos
    - 2 celíacos
    - 4 veganos
    - 12 vegetarianos
  El procedimiento debe explicar, para cada caso: almacenamiento, preparación, servicio, identificación de platos y formación del personal. Debe cubrir los tres servicios (cóctel, cena, taquiza) y considerar que la producción ocurre sin cocina en el recinto.
- Referencias de eventos comparables (bodas de ~180 invitados sin cocina en sitio).
- Propuesta de menú para cada servicio y para cada dieta/alergia listada.

CALENDARIO Y EVALUACIÓN
- Fecha límite de respuesta: Propuestas antes del 15 de diciembre de 2026
- Fecha de decisión: Decisión el 8 de enero de 2027
- Criterios de evaluación: no constan en el briefing.

Criterios de evaluación propuestos — confirmar con el cliente antes de enviar
  1. Cumplimiento de requisitos.
  2. Claridad del precio desglosado.
  3. Experiencia/referencias.
  4. Plan operativo ante las restricciones del lugar (sin cocina; área de servicio con toma de agua y corriente de 110 V).
  5. Protocolo de alérgenos/seguridad.
  6. Seguro y condiciones.
- Ponderaciones: POR CONFIRMAR

PENDIENTES (POR CONFIRMAR)
- Organizador y contacto profesional autorizado (nombre, teléfono, correo).
- Fecha de emisión de la RFP.
- Dirección exacta de Hacienda Muestra.
- Presupuesto y moneda.
- Horarios de acceso, carga y descarga, montaje y desmontaje del proveedor.
- Hora de fin de la cena de tres tiempos y de la taquiza; confirmar si la taquiza 00:30 y el desmontaje caen ya en el domingo 21 de marzo de 2027 y si el recinto permite operar a esa hora.
- Capacidades del recinto: amperaje disponible en la corriente de 110 V, caudal de la toma de agua, dimensiones del área de servicio, permiso para generador, gas o fuego, rigging, estacionamiento.
- Alcance exacto del catering: bebidas no alcohólicas, hielo y mezcladores para la barra libre (contratada aparte), mobiliario, mantelería, cristalería, loza, pastel.
- Coordinación con el proveedor de barra libre (quién aporta hielo, cristalería y personal de barra).
- Dietas: aclarar si las categorías se solapan (p. ej., si los 4 veganos están contados también entre los 12 vegetarianos; si los 2 celíacos o la persona con alergia a mariscos están dentro de alguna otra categoría). No se han sumado.
- Confirmar si "celíacos" implica dieta sin gluten estricta por diagnóstico médico (tratar como médica hasta aclarar).
- Confirmar con el responsable que la cantidad "1 persona con alergia grave a mariscos" no permite reidentificar al asistente antes de compartir la RFP con terceros; el briefing no contiene nombres.
- Criterios de evaluación: obtener confirmación del cliente de los criterios propuestos y de sus ponderaciones antes de enviar.
- Verificación por el profesional responsable de seguro, condiciones económicas, tratamiento fiscal (IVA MX) y viabilidad técnica con proveedor y recinto; esta RFP no certifica cumplimiento normativo, seguridad alimentaria ni cobertura.

Nota de cotejo: todas las cifras, horas y fechas del briefing aparecen literales (180; 18:00–19:00; 20:00; 00:30; 12/4/2/1; 110 V; 20 de marzo de 2027; 15 de diciembre de 2026; 8 de enero de 2027). No se añadieron tasas, importes ni capacidades del recinto. Revisar references/checklist.md antes de enviar.

