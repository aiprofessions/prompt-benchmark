# Transcript — skill event-planners-vendor-rfp [es] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:51:46+00:00
- duration_s: 49.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: f8484832ec8b99d2b8c1e83a23a5e10d3c77bc11ebb4e159ee01dab1dfc58df0
- skill_sha256: bd17f104a6a0defa7b3a9cf98aa01ddb6f768a169f51d03aba4f06f21edb91fa

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: event-planners-vendor-rfp
description: "Úsala cuando pegues el briefing de un evento y necesites una RFP para proveedores con requisitos, precios desglosados y pendientes por confirmar."
---

# Generador de RFP para proveedores de eventos

## Qué hace

Convierte el briefing en una solicitud de propuesta (RFP) para proveedores de eventos en México o España. Conserva literalmente los datos operativos y presenta las restricciones del espacio como condiciones de planificación. Prepara el documento para revisión y envío, con precios desglosados y los datos faltantes marcados como POR CONFIRMAR.

## Qué necesita

- Cliente, organizador, contacto autorizado y nombre o tipo de evento.
- País (MX o ES), espacio y dirección, si constan.
- Fechas y horarios de acceso, montaje (load-in), evento y desmontaje (load-out).
- Asistentes y cantidades por dieta o alergia, sin identificar a las personas.
- Servicios, equipos y requisitos técnicos.
- Restricciones de cocina, rigging del espacio, accesos y carga y descarga.
- Presupuesto y moneda, conservando el formato facilitado.
- Fecha límite de respuesta, fecha de decisión y criterios de evaluación.

Si faltan datos, continúa y escribe POR CONFIRMAR en el apartado correspondiente y en Pendientes. Si el usuario pide aclararlos antes de redactar, reúne las preguntas en un único mensaje. Nunca completes huecos por suposición.

## Procedimiento

1. Identifica el país sin inferirlo por la moneda. Adapta solo el texto de enlace: recinto, banquete, meseros y anticipo (MX); espacio, catering, camareros y señal o depósito (ES). Conserva el vocabulario original dentro de los requisitos literales.
2. Extrae una lista de todas las cantidades, fechas, horas y especificaciones técnicas. Incluye dietas, alergias, accesos, montaje y desmontaje. Copia cada dato exactamente, incluidos rangos, unidades, “aprox.”, “máx.” y expresiones como “antes de”. No conviertas monedas ni formatos.
3. Detecta contradicciones sin corregirlas. No sumes dietas y alergias como categorías excluyentes salvo que el briefing lo indique. Si hay una discrepancia aritmética comprobable, muestra la operación en Pendientes; si puede haber solapamiento, pide aclararlo.
4. Traslada cada limitación de cocina, rigging y acceso a Restricciones del espacio. Usa “El proveedor debe planificar conforme a esta restricción: [texto literal]” y pide que explique su solución. No atribuyas capacidades no documentadas.
5. Para servicios alimentarios o cuando consten alergias, solicita por escrito el procedimiento de manejo de alérgenos y prevención del contacto cruzado. Pide que cubra almacenamiento, preparación, servicio, identificación de platos y formación del personal. Si faltan datos de alergias, márcalos POR CONFIRMAR; no escribas “sin alergias”.
6. Prepara un desglose con una línea por servicio o equipo y líneas independientes para mano de obra, entrega, retiro, cargo por servicio, cada impuesto y propina. Pide cantidad, unidad, precio unitario y total. No inventes importes ni tipos impositivos; el proveedor completará su oferta e indicará expresamente qué conceptos no aplican.
7. Solicita certificado de seguro, condiciones de cancelación y condiciones del anticipo (MX) o señal/depósito (ES), con importe o porcentaje, vencimientos y devolución. No presentes estas solicitudes comerciales como obligaciones legales verificadas.
8. Copia literalmente el plazo de respuesta, la fecha de decisión y los criterios de evaluación. Si faltan criterios o ponderaciones, no los propongas como acordados: escribe POR CONFIRMAR.
9. Marca cualquier dato ausente como POR CONFIRMAR, incluidos presupuesto, contactos, teléfonos, fecha de emisión, moneda y capacidades del espacio. Distingue esos datos de los importes y documentos solicitados al proveedor, que deben figurar como “A completar por el proveedor”.
10. Omite identificadores y datos individuales de asistentes. Usa cantidades agregadas y revisa que las combinaciones de datos no permitan identificar a una persona. Si hay ese riesgo, solicita una versión desidentificada sin alterar por tu cuenta las cifras.
11. Redacta los ocho apartados del formato, en su orden. Reúne en Pendientes todos los datos faltantes, ambigüedades y contradicciones; no resuelvas ninguno por inferencia.
12. Antes de entregar, coteja la RFP con la lista del paso 2: comprueba que no falte ninguna cifra, plazo o especificación y que cada restricción esté incluida. Comprueba también el desglose, los documentos, el calendario y la privacidad. Corrige cualquier desviación respecto del briefing, sin modificar el briefing.

## Formato de salida

```markdown
## Encabezado de la RFP
Solicitud de propuesta: [servicios] para [evento]
Cliente: [literal o POR CONFIRMAR]
Organizador y contacto autorizado: [literal o POR CONFIRMAR]
Fecha de emisión y país: [datos del briefing o POR CONFIRMAR]

## Resumen del evento
- Fecha y espacio: [literales o POR CONFIRMAR]
- Asistentes: [literal o POR CONFIRMAR]
- Acceso y montaje: [literales o POR CONFIRMAR]
- Evento y desmontaje: [literales o POR CONFIRMAR]
- Presupuesto y moneda: [formato original o POR CONFIRMAR]

## Alcance y requisitos
- [Cada servicio/equipo y sus requisitos técnicos literales]
- Dietas y alergias: [cantidades literales o POR CONFIRMAR]

## Restricciones del espacio
- El proveedor debe planificar conforme a esta restricción: [texto literal].
- Explique cómo cumplirá cada restricción.
- [Capacidades o condiciones necesarias no documentadas: POR CONFIRMAR]

## Formato de precio
Moneda: [formato original o POR CONFIRMAR]. Precios: A completar por el proveedor.
| Concepto | Cantidad | Unidad | Precio unitario | Total |
|---|---|---|---|---|
| [Una línea por cada servicio o equipo] | | | | |
| Mano de obra | | | | |
| Entrega | | | | |
| Retiro | | | | |
| Cargo por servicio | | | | |
| [Cada impuesto, separado y con tipo indicado por el proveedor] | | | | |
| Propina | | | | |
No sustituya el desglose por un precio global. Indique los conceptos que no aplican y evite duplicar costes.

## Documentos requeridos al proveedor
- Certificado de seguro.
- Condiciones de cancelación.
- Condiciones de anticipo (MX) o señal/depósito (ES): importe o porcentaje, vencimientos y devolución.
- Procedimiento escrito de manejo de alérgenos y prevención del contacto cruzado cuando haya servicios alimentarios o consten alergias.

## Calendario y evaluación
- Fecha límite de respuesta: [literal o POR CONFIRMAR]
- Fecha de decisión: [literal o POR CONFIRMAR]
- Criterios y ponderaciones: [literales o POR CONFIRMAR]

## Pendientes (por confirmar)
1. [Dato faltante, ambigüedad o contradicción; operación solo si procede]
```

## Límites

- No inventes datos operativos, contactos, capacidades, estadísticas, leyes, artículos, autoridades, fechas ni fuentes. No añadas citas distintas de la fuente indicada abajo.
- No cambies cantidades ni horarios para hacerlos coherentes. No supongas que una dieta equivale a una alergia ni que las categorías no se solapan.
- No certifiques cumplimiento normativo ni cobertura del seguro. El profesional responsable debe verificar el alcance, la vigencia y la adecuación del seguro, las condiciones económicas y la viabilidad técnica con el proveedor y el espacio.
- Licencias, alcohol, alérgenos e higiene alimentaria dependen de la normativa local o autonómica: el profesional responsable, habilitado cuando corresponda, debe confirmar los requisitos con el espacio y la autoridad competente antes de contratar.
- No se ha verificado ninguna fuente oficial específica sobre IA para organizadores de eventos en ES/MX. Consulta al organismo profesional o a la autoridad competente para verificar los requisitos aplicables.
- Privacidad: desidentifica el briefing antes de procesarlo y utiliza únicamente herramientas aprobadas por tu organización para datos personales. No reproduzcas listas nominales ni datos de salud individuales en la RFP; utiliza datos agregados que no permitan reidentificar.
- Si se envían datos de asistentes, el responsable debe verificar la protección de datos aplicable, la necesidad de compartirlos y los destinatarios autorizados; en México, LFPDPPP 2025. En España, confirma los requisitos con el responsable de protección de datos.
- Fuente permitida: Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- El profesional responsable debe revisar y aprobar la RFP y decidir qué pendientes impiden enviarla o contratar.
- Consulta references/checklist.md antes de enviar o firmar.

## Ejemplo

Entrada ficticia:
```text
Cliente: Muestra; evento: comida; espacio: Sala Example (MX).
Asistentes: 30; 4 vegetarianos; alergias: POR CONFIRMAR.
Servicio: banquete; montaje 11:00–12:00; comida 13:00–15:00; desmontaje 15:00–16:00.
Cocina: solo regeneración; rigging: sin puntos de colgado; acceso: por puerta lateral.
Fecha del evento, presupuesto, moneda, contacto, respuesta, decisión y criterios: POR CONFIRMAR.
```

Salida abreviada (el documento completo desarrolla el desglose y todos los pendientes):
```markdown
## Encabezado de la RFP
## Resumen del evento
Muestra · comida · Sala Example (MX) · 30; montaje 11:00–12:00; comida 13:00–15:00; desmontaje 15:00–16:00.
## Alcance y requisitos
banquete; 4 vegetarianos; alergias: POR CONFIRMAR.
## Restricciones del espacio
Planifique conforme a: cocina: solo regeneración; rigging: sin puntos de colgado; acceso: por puerta lateral. Explique cómo.
## Formato de precio
Líneas independientes: banquete, mano de obra, entrega, retiro, cargo por servicio, cada impuesto y propina; a completar por el proveedor.
## Documentos requeridos al proveedor
Certificado de seguro; cancelación; anticipo con importe, vencimientos y devolución; procedimiento escrito de alérgenos y contacto cruzado.
## Calendario y evaluación
Respuesta, decisión, criterios y ponderaciones: POR CONFIRMAR.
## Pendientes (por confirmar)
Fecha del evento y de emisión, organizador, contacto, presupuesto, moneda, alergias, respuesta, decisión, criterios y ponderaciones.
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

SOLICITUD DE PROPUESTA (RFP) - BANQUETE

1. ENCABEZADO DE LA RFP

  Solicitud de propuesta: servicio de banquete (cóctel, cena de tres tiempos y taquiza) para la boda de la familia Ejemplo (ficticia)
  Cliente: POR CONFIRMAR (el briefing menciona "el cliente" sin identificarlo)
  Organizador y contacto autorizado: POR CONFIRMAR
  Fecha de emisión: POR CONFIRMAR
  País: México

2. RESUMEN DEL EVENTO

  - Fecha: Sábado 20 de marzo de 2027
  - Recinto: Hacienda Muestra, Tequisquiapan, Querétaro, México (ficticia). Dirección exacta: POR CONFIRMAR
  - Invitados: 180
  - Horario:
      cóctel 18:00–19:00
      cena de tres tiempos 20:00 (hora de término: POR CONFIRMAR)
      taquiza 00:30 (hora de término: POR CONFIRMAR)
  - Acceso y montaje: POR CONFIRMAR
  - Desmontaje: POR CONFIRMAR
  - Presupuesto y moneda: POR CONFIRMAR

3. ALCANCE Y REQUISITOS

  - Cóctel: 18:00–19:00. Contenido y formato: POR CONFIRMAR.
  - Cena de tres tiempos: 20:00. Formato de servicio: POR CONFIRMAR.
  - Taquiza: 00:30. Formato y cantidades: POR CONFIRMAR.
  - Bebidas: "La barra libre la contrata el cliente aparte: no incluir bebidas alcohólicas." No se ha confirmado si el banquete debe incluir bebidas sin alcohol, café o agua.
  - Meseros, mobiliario, mantelería, loza, cristalería y cubertería: POR CONFIRMAR si forman parte del alcance.
  - Dietas y alergias, según el briefing:
      12 vegetarianos
      4 veganos
      2 celíacos
      1 persona con alergia grave a mariscos
    No se sabe si estas categorías se solapan, por lo que no deben sumarse. Tampoco consta a qué servicios aplican (cóctel, cena o taquiza).

4. RESTRICCIONES DEL ESPACIO

  - El proveedor debe planificar conforme a esta restricción: "La hacienda NO tiene cocina: solo un área de servicio con toma de agua y corriente de 110 V."
  - Explique cómo cumplirá esta restricción en los tres servicios. Indique dónde se producirán los alimentos, cómo se transportarán y mantendrán a temperatura, y qué equipo aportará. Señale también qué requerimientos tendrá de energía, agua y espacio.
  - Datos no documentados (POR CONFIRMAR):
      capacidad eléctrica disponible (amperaje y número de contactos)
      si se permiten gas, fuego abierto o una planta de luz
      dimensiones del área de servicio
      accesos, carga y descarga, y horarios de entrada al recinto
      restricciones de rigging

5. FORMATO DE PRECIO

  Moneda: POR CONFIRMAR. Precios: A completar por el proveedor.

  Concepto                                       | Cantidad | Unidad | Precio unitario | Total
  Cóctel                                         |          |        |                 |
  Cena de tres tiempos                           |          |        |                 |
  Taquiza                                        |          |        |                 |
  Menús especiales (vegetariano, vegano,         |          |        |                 |
    sin gluten, sin mariscos), si tienen costo   |          |        |                 |
  Equipo de cocina o regeneración que aporte     |          |        |                 |
    el proveedor, si aplica                      |          |        |                 |
  Mano de obra (meseros, cocina, coordinación)   |          |        |                 |
  Entrega                                        |          |        |                 |
  Retiro                                         |          |        |                 |
  Cargo por servicio                             |          |        |                 |
  Impuesto (una línea por cada impuesto, con el  |          |        |                 |
    tipo indicado por el proveedor)              |          |        |                 |
  Propina                                        |          |        |                 |

  No sustituya el desglose por un precio global. Indique qué conceptos no aplican y evite duplicar costos.

6. DOCUMENTOS REQUERIDOS AL PROVEEDOR

  - Certificado de seguro.
  - Condiciones de cancelación.
  - Condiciones del anticipo: importe o porcentaje, vencimientos y devolución.
  - Procedimiento escrito de manejo de alérgenos y prevención del contacto cruzado. Debe cubrir almacenamiento, preparación, servicio, identificación de platos y formación del personal. Incluya:
      el manejo de la alergia grave a mariscos
      el manejo de los menús sin gluten para celíacos
      las medidas para producir fuera del recinto, dado que la hacienda no tiene cocina

7. CALENDARIO Y EVALUACIÓN

  - Fecha límite de respuesta: "Propuestas antes del 15 de diciembre de 2026."
  - Fecha de decisión: "Decisión el 8 de enero de 2027."
  - Criterios y ponderaciones: POR CONFIRMAR

8. PENDIENTES (POR CONFIRMAR)

  1. Cliente, organizador, contacto autorizado y teléfono.
  2. Fecha de emisión de la RFP.
  3. Dirección exacta de la Hacienda Muestra.
  4. Presupuesto y moneda. No se infiere MXN solo porque el evento sea en México.
  5. Horarios de acceso, montaje y desmontaje.
  6. Horas de término de la cena y de la taquiza.
  7. Taquiza a las 00:30: confirmar que corresponde a la madrugada del domingo 21 de marzo de 2027. Esto afecta los horarios de desmontaje y retiro.
  8. Servicios entre 19:00 y 20:00: confirmar si hay alguno entre el fin del cóctel y el inicio de la cena.
  9. Formato de cada servicio (canapés o estaciones; servicio emplatado o bufé) y contenido de la taquiza.
  10. Bebidas sin alcohol, café y agua: ¿se incluyen en el banquete? Si la barra la contrata el cliente aparte, confirmar quién suministra hielo y cristalería.
  11. Meseros, mobiliario, mantelería y loza: ¿forman parte del alcance?
  12. Dietas: ¿se solapan las categorías? Por ejemplo, si algún celíaco también es vegano o vegetariano.
  13. Dietas: ¿aplican a los tres servicios?
  14. Alergia grave a mariscos: confirmar si abarca crustáceos y moluscos. Confirmar también si debe excluirse el marisco de todo el menú o solo del plato de esa persona.
  15. Alergias: confirmar si hay otras alergias. No consta que no las haya.
  16. Capacidad eléctrica del área de servicio y si se permiten gas, fuego abierto o una planta de luz.
  17. Accesos, carga y descarga, y rigging del recinto.
  18. Criterios de evaluación y sus ponderaciones.
  19. Privacidad: la RFP no incluye nombres. Aun así, la cifra "1 persona con alergia grave a mariscos" es un dato de salud de una sola persona. El responsable debe confirmar si puede compartirse así o si requiere una versión desidentificada. La cifra no se ha alterado.

Notas para el responsable (no forman parte del envío al proveedor):

  - Revise y apruebe la RFP antes de enviarla. Decida también qué pendientes impiden enviarla o contratar.
  - Antes de contratar, confirme con el recinto y la autoridad competente los requisitos sobre alérgenos, higiene alimentaria y uso de gas o fuego. Verifique además el alcance y la vigencia del seguro del proveedor.
  - Si se comparten datos de invitados, verifique que se cumpla la LFPDPPP (DOF 20.03.2025). Puede consultarla en https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (consultada el 2026-10-19).
  - Consulte references/checklist.md antes de enviar o firmar.

