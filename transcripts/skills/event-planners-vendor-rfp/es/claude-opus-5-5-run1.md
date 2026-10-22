# Transcript — skill event-planners-vendor-rfp [es] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:01:51+00:00
- duration_s: 48.8
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

SOLICITUD DE PROPUESTA (RFP): CATERING / BANQUETE

ENCABEZADO DE LA RFP
Solicitud de propuesta: servicio de banquete (cóctel, cena de tres tiempos y taquiza) para la boda de la familia Ejemplo (ficticia)
Cliente: POR CONFIRMAR
Organizador y contacto profesional autorizado: POR CONFIRMAR
Fecha de emisión: POR CONFIRMAR
País: México

RESUMEN DEL EVENTO
- Fecha: Sábado 20 de marzo de 2027
- Recinto: Hacienda Muestra, Tequisquiapan, Querétaro, México (ficticia)
- Dirección completa: POR CONFIRMAR
- Invitados: 180
- Acceso, carga y descarga: POR CONFIRMAR
- Montaje: POR CONFIRMAR
- Evento: cóctel 18:00–19:00, cena de tres tiempos 20:00, taquiza 00:30
- Desmontaje: POR CONFIRMAR
- Presupuesto y moneda: POR CONFIRMAR

ALCANCE Y REQUISITOS
- Cóctel: 18:00–19:00. Menú y cantidad de piezas por invitado: a proponer por el proveedor.
- Cena de tres tiempos: 20:00. Hora de término: POR CONFIRMAR.
- Taquiza: 00:30. Número de invitados que se considera: POR CONFIRMAR.
- Exclusión: "La barra libre la contrata el cliente aparte: no incluir bebidas alcohólicas."
- Bebidas sin alcohol, café, hielo, cristalería y coordinación con el proveedor de la barra: POR CONFIRMAR si forman parte del alcance.
- Mobiliario, vajilla, cubertería y mantelería: POR CONFIRMAR si forman parte del alcance.
- Equipo de cocina, calentamiento y refrigeración: el proveedor debe detallar todo lo necesario para operar sin cocina (ver Restricciones del recinto).
- Dietas y alergias (cantidades literales del briefing; no se asume que las categorías sean excluyentes):
    - 12 vegetarianos
    - 4 veganos
    - 2 celíacos
    - 1 persona con alergia grave a mariscos
- El proveedor debe ofrecer opciones adaptadas para cada tiempo del servicio: cóctel, cena y taquiza.

RESTRICCIONES DEL RECINTO
- El proveedor debe planificar conforme a esta restricción: "La hacienda NO tiene cocina: solo un área de servicio con toma de agua y corriente de 110 V."
- Explique su solución operativa para esta restricción en cada servicio (cóctel, cena de tres tiempos y taquiza): producción fuera del recinto o en sitio, transporte y conservación de temperaturas, equipo de calentamiento y refrigeración, fuente de energía y consumo eléctrico previsto, y uso del área de servicio.
- POR CONFIRMAR con el recinto: capacidad eléctrica disponible (amperaje y número de contactos), si se permite gas, fuego abierto o planta de luz, dimensiones del área de servicio, accesos y horarios de carga y descarga, montaje y desmontaje.

FORMATO DE PRECIO
Moneda: POR CONFIRMAR. Importes: a completar por el proveedor.

Concepto | Cantidad | Unidad | Precio unitario | Total
Alimentos/servicio: cóctel | | | |
Alimentos/servicio: cena de tres tiempos | | | |
Alimentos/servicio: taquiza | | | |
Alimentos/servicio: bebidas sin alcohol (si aplica) | | | |
Equipo: cocina móvil / calentamiento (una línea por equipo) | | | |
Equipo: refrigeración (una línea por equipo) | | | |
Equipo: generación o suministro eléctrico (si aplica) | | | |
Equipo: mobiliario, vajilla, cristalería, mantelería (una línea por concepto, si aplica) | | | |
Personal: meseros | | | |
Personal: cocina | | | |
Personal: otras funciones (una línea por función) | | | |
Traslado | | | |
Montaje | | | |
Desmontaje | | | |
Cargo por servicio (si aplica) | | | |
Propina (si aplica) | | | |
Subtotal antes de impuestos | | | |
IVA (MX): tasa e importe, a indicar por el proveedor | | | |
Otros impuestos, si corresponden (uno por línea) | | | |
Total | | | |

Indique "No aplica" donde corresponda. No sustituya el desglose por un precio global.
Mantenga impuestos, traslado, montaje y desmontaje separados; evite duplicar costos.

DOCUMENTOS REQUERIDOS AL PROVEEDOR
A completar por el proveedor:
- Certificado de seguro.
- Condiciones de cancelación.
- Condiciones de anticipo: importe o porcentaje, vencimientos y devolución.
- Procedimiento escrito de manejo de alérgenos y prevención del contacto cruzado para cada caso:
    - 2 celíacos
    - 1 persona con alergia grave a mariscos
    - 12 vegetarianos y 4 veganos (separación e identificación de preparaciones)
- El procedimiento debe explicar, para cada caso, el almacenamiento, la preparación, el servicio, la identificación de platos y la formación del personal. También debe indicar cómo se controla el contacto cruzado en traslado y emplatado, dado que el recinto no tiene cocina.
- Menú propuesto por tiempo, con la lista de alérgenos de cada platillo.

CALENDARIO Y EVALUACIÓN
- Fecha límite de respuesta: antes del 15 de diciembre de 2026
- Fecha de decisión: el 8 de enero de 2027
- Criterios de evaluación: el briefing no los incluye.

Criterios de evaluación propuestos — confirmar con el cliente antes de enviar
1. Cumplimiento de requisitos.
2. Claridad del precio desglosado.
3. Experiencia/referencias.
4. Plan operativo ante las restricciones del lugar.
5. Protocolo de alérgenos/seguridad, si aplica.
6. Seguro y condiciones.
- Ponderaciones: POR CONFIRMAR

PENDIENTES (POR CONFIRMAR)
- Cliente, organizador, contacto profesional autorizado y teléfonos.
- Fecha de emisión de la RFP.
- Dirección completa del recinto.
- Presupuesto y moneda.
- Horarios de acceso, carga y descarga, montaje y desmontaje.
- Hora de término de la cena de tres tiempos.
- Taquiza 00:30: confirmar que corresponde a la madrugada del domingo 21 de marzo de 2027.
- Taquiza: número de invitados que se considera (¿180?).
- Intervalo 19:00–20:00 entre el cóctel y la cena: ¿se requiere algún servicio?
- Solapamiento de dietas: confirmar si los 4 veganos están incluidos o no en los 12 vegetarianos. Confirmar también si los 2 celíacos o la persona con alergia a mariscos pertenecen además a alguna de esas categorías. No se han sumado.
- Alergia grave a mariscos: precisar el alcance (crustáceos, moluscos, pescado) y si debe excluirse cualquier marisco de todo el evento o solo del platillo de esa persona.
- Alcance de bebidas sin alcohol, café, hielo y cristalería, y coordinación con el proveedor de la barra libre.
- Alcance de mobiliario, vajilla, cubertería y mantelería.
- Capacidades del recinto: capacidad eléctrica a 110 V, uso de gas, fuego o planta de luz, y dimensiones y ubicación del área de servicio.
- Privacidad: los datos de dieta se comparten en forma agregada y sin nombres. Aun así, "1 persona con alergia grave a mariscos" es un caso individual. El responsable debe confirmar que compartirlo es necesario y que los destinatarios están autorizados (LFPDPPP, DOF 20.03.2025: https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm).
- Aprobación por el cliente de los criterios propuestos y sus ponderaciones antes del envío.

Notas: el profesional responsable debe revisar y aprobar esta RFP antes de enviarla. También debe verificar la vigencia y el alcance del seguro, el tratamiento fiscal, la viabilidad técnica sin cocina y los requisitos locales de higiene alimentaria con el recinto y la autoridad competente. Consulte references/checklist.md antes de enviar o firmar.

