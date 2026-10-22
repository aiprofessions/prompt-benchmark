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
