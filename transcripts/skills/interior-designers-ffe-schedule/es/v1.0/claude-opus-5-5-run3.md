# Transcript — skill interior-designers-ffe-schedule [es] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:11:16+00:00
- duration_s: 59.8
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 97ac72d08175cf5ad204a1273025ff85553bbb55a79fbac8d5aba375b13dd779
- skill_sha256: b681b56b673159271f0369c3a40739d57fc86e503b94544859222ae41d262a82

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: interior-designers-ffe-schedule
description: "Úsala cuando pegues el briefing de una estancia y necesites un listado FF&E con medidas, asignaciones de presupuesto, plazos y requisitos por verificar."
---

# Del briefing al listado de mobiliario (FF&E)

## Qué hace

Convierte el briefing de una estancia en un listado FF&E de mobiliario, accesorios y equipamiento para revisión profesional. Incluye todas las piezas solicitadas y existentes, con medidas objetivo, requisitos de uso, asignaciones presupuestarias y control de plazos. Distingue los datos aportados, los cálculos y lo pendiente de confirmar; no selecciona productos ni certifica prestaciones.

## Qué necesita

- País y localidad del proyecto, tipo de estancia y uso previsto.
- Medidas de la estancia y de las piezas existentes, con unidades; pasos y accesos si se conocen.
- Piezas solicitadas, cantidades y piezas existentes que se conservarán.
- Usuarios, necesidades de movilidad, presencia de menores y mascotas, sin datos identificativos.
- Gustos y rechazos de materiales, acabados, colores o estilos.
- Presupuesto total, moneda, tratamiento del IVA y alcance: transporte, montaje e intervenciones incluidos o no.
- Asignaciones por pieza, o autorización para proponer un reparto del presupuesto.
- Fecha de montaje o instalación; plazos facilitados por proveedores y margen de seguridad acordado.
- Para medidas derivadas, márgenes o criterios dimensionales facilitados por el cliente o el interiorista.

Si faltan datos, reúne las preguntas en una sola ronda. Si se solicita avanzar, continúa con «FALTA» en los campos afectados y recoge cada ausencia en Preguntas para el cliente; no adivines cifras, unidades, cantidades ni fechas.

## Procedimiento

1. Retira identificadores personales antes de trabajar y utiliza únicamente herramientas aprobadas por el estudio. Si no puedes tratar el material con esas condiciones, solicita una versión anonimizada.
2. Extrae medidas, cantidades, presupuesto y fechas conservando cifras, unidades y formato monetario del usuario. Separa datos aportados de cálculos; no conviertas unidades o divisas sin autorización.
3. Crea un inventario de todas las piezas solicitadas y existentes. Asigna códigos únicos y estables, como MOB-01 o TEX-01, y comprueba al final que cada entrada tenga una fila, sin duplicar una existente que cubra una pieza solicitada.
4. Usa únicamente los estados «nueva» y «existente-reutilizar». Si no está confirmado que una existente se conserve, mantén esa fila como «existente-reutilizar» con la nota «reutilización por confirmar»; no autorices su uso. Registra otros conflictos en notas y preguntas, no como estados nuevos.
5. Copia los rechazos en «Excluido por indicación del cliente». Elimínalos de materiales, acabados y alternativas propuestos. Si afectan a una pieza solicitada o existente, conserva su fila como necesidad pendiente, señala el conflicto y pide una decisión sin recomendar la opción rechazada.
6. Escribe una cantidad y una medida objetivo por fila, o «FALTA». Para dimensiones derivadas, muestra fórmula, datos y resultado con unidades: alfombra (ES) / tapete (MX) = (largo − 2 × margen) × (ancho − 2 × margen). Sin margen aportado, deja la fórmula sin resolver y pregunta.
7. Relaciona cada necesidad de usuarios o mascotas con requisitos por verificar en las piezas afectadas. Por ejemplo: facilidad de limpieza y resistencia del tejido para mascotas; cantos redondeados para menores. No afirmes que una pieza ofrece esas prestaciones.
8. Repite literalmente el presupuesto total y su moneda. Indica «con IVA», «sin IVA» o «IVA: no indicado» tanto para el total como para las asignaciones, mediante una nota común cuando compartan tratamiento. Si falta ese dato, pregúntalo; no calcules impuestos.
9. Usa las asignaciones aportadas o, con autorización, propone un reparto claramente identificado como tal. Etiqueta cada importe como «asignación estimada — confirmar con presupuesto (ES) / cotización (MX)». Sin reparto ni autorización, escribe «por asignar». No inventes precios, nombres de productos ni modelos.
10. En piezas reutilizadas, separa adquisición de posibles costes de transporte, restauración, retapizado o montaje. Indica adquisición 0 solo si ya pertenecen al cliente; no supongas que reutilizarlas carece de costes. Deja las intervenciones no valoradas como pendientes.
11. Suma las asignaciones numéricas mostrando la operación y calcula presupuesto menos suma solo si son comparables en moneda e IVA. Con partidas pendientes, llama al resultado «saldo aún no asignado», no ahorro ni reserva disponible. Declara qué gastos están incluidos, excluidos o pendientes y señala cualquier exceso.
12. En cada fila nueva o con intervención, comprueba el plazo frente al montaje. Con datos suficientes, calcula «Pedir antes de = fecha de montaje − plazo total hasta disponibilidad para instalar − margen acordado» y muestra la operación. Confirma si los plazos incluyen transporte e instalación y si se expresan en días naturales o laborables.
13. Si falta fecha, plazo o margen, escribe «viabilidad de plazo no comprobada» y pregunta por el dato. Señala especialmente piezas a medida o importadas sin plazo confirmado. Solo declara una fecha vencida si dispones de una fecha de referencia fiable y la indicas; no inventes urgencias.
14. Por código, enumera los datos que deben verificarse en ficha técnica del fabricante según material y uso: reacción al fuego o inflamabilidad, abrasión —método y ciclos, incluidos double rubs si corresponde—, códigos de limpieza y resistencia al deslizamiento. No equipares métodos ni presentes valores o clasificaciones como hechos comprobados.
15. Marca las especificaciones sin documentación como pendientes y justifica las que no sean aplicables. Indica que el interiorista responsable confirma las exigencias de reacción al fuego y seguridad según el uso y la normativa local.
16. Revisa cobertura de piezas, rechazos, operaciones, IVA y plazos. Emite las seis secciones en el orden indicado y reúne en Preguntas para el cliente todos los datos ausentes, decisiones y conflictos sin resolver.

## Formato de salida

```markdown
## Intención de diseño
- Estancia, uso y ubicación: …
- Usuarios / mascotas y criterios del briefing: …
- Excluido por indicación del cliente: …
- Datos pendientes o conflictos de diseño: …

## Listado FF&E
| Código | Pieza | Cant. | Medida objetivo y cálculo | Material / uso: requisitos por verificar | Asignación estimada e IVA | Plazo / pedir antes de | Estado |
|---|---|---|---|---|---|---|---|
| … | … | … | … | … | … | … | nueva / existente-reutilizar |

## Control de presupuesto
- Presupuesto del cliente: …; con IVA / sin IVA / IVA no indicado.
- Origen del reparto: aportado / propuesta autorizada / pendiente.
- Asignaciones estimadas: confirmar con presupuestos (ES) / cotizaciones (MX).
- Suma y operación: …; partidas pendientes: …
- Diferencia y operación: …; saldo aún no asignado / reserva si todo está incluido / exceso.
- Transporte, montaje e intervenciones: incluidos / excluidos / pendientes.

## Control de plazos
- Fecha de montaje o instalación: …
- Por código: plazo aportado, alcance, margen acordado y cálculo de pedir antes de: …
- Viabilidad no comprobada, riesgos y confirmaciones necesarias: …

## Especificaciones por verificar
- [Código]: requisito, dato y ficha técnica necesaria; pendiente / no aplicable con motivo.
- Reacción al fuego y seguridad: el interiorista confirma exigencias según uso y normativa local.

## Preguntas para el cliente
1. [Código o asunto]: dato ausente, decisión o conflicto por resolver.
```

## Límites

- No inventes productos, modelos, precios, plazos, fechas, clasificaciones, estadísticas ni referencias legales. No añadas citas, enlaces, organismos concretos o fuentes no facilitadas.
- No presentes asignaciones como ofertas ni conviertas requisitos en prestaciones garantizadas. Indica siempre el tratamiento del IVA o que falta confirmarlo.
- No afirmes cumplimiento normativo ni aptitud para uso o instalación a partir del briefing.
- El profesional responsable y, cuando corresponda, habilitado en la jurisdicción debe verificar medidas en obra, circulación, accesos, estabilidad, anclajes, fichas técnicas, costes y plazos antes de aprobar compras o instalación.
- Las exigencias de reacción al fuego y seguridad dependen del uso y la normativa local: el interiorista responsable las confirma, así como la documentación necesaria para acreditarlas.
- No se ha verificado ninguna orientación oficial específica sobre IA para interioristas en España o México. Consulta con tu colegio profesional o autoridad competente sobre las obligaciones aplicables.
- Privacidad: elimina nombres, domicilios, contactos y elementos identificables de imágenes y planos; usa solo herramientas aprobadas por el estudio y los datos mínimos necesarios.
- Antes de enviar o firmar, consulta references/checklist.md.

## Ejemplo

Entrada ficticia:

```text
Proyecto Muestra, vivienda en MX; estancia de 4 × 3 m, pareja con perro.
Piezas: 1 tapete nuevo; conservar 1 mesa propia de 1 × 0,5 m, sin intervención.
Margen del tapete: 0,5 m por lado. Rechazo: terciopelo.
Total: 6.000 MXN con IVA, asignados al tapete; recogida y colocación propias sin coste.
Fecha de instalación y plazo de entrega pendientes; reparto aportado por el cliente.
```

Salida abreviada:

```markdown
## Intención de diseño
Pareja con perro; excluido por indicación del cliente: terciopelo.
## Listado FF&E
| Código | Pieza | Cant. | Medida / cálculo | Requisitos por verificar | Asignación estimada, con IVA | Plazo | Estado |
|---|---|---|---|---|---|---|---|
| TEX-01 | Tapete | 1 | (4 − 2 × 0,5) × (3 − 2 × 0,5) = 3 × 2 m | Fácil limpieza y resistencia al uso con perro: verificar | 6.000 MXN | Viabilidad no comprobada | nueva |
| MOB-01 | Mesa propia | 1 | 1 × 0,5 m | Verificar estabilidad | 0 MXN; sin intervención | Disponibilidad por verificar | existente-reutilizar |
## Control de presupuesto
Total: 6.000 MXN con IVA. Suma: 6.000 + 0 = 6.000 MXN; diferencia: 6.000 − 6.000 = 0 MXN. Asignaciones a confirmar con cotización; recogida y colocación propias sin coste declarado.
## Control de plazos
TEX-01: faltan fecha, plazo y margen acordado; no se puede calcular cuándo pedir.
## Especificaciones por verificar
TEX-01: fuego, abrasión y método, limpieza y deslizamiento en ficha; MOB-01: estabilidad. El interiorista confirma aplicabilidad y seguridad local.
## Preguntas para el cliente
¿Cuál es la localidad, la fecha de instalación, el plazo de entrega y el margen acordado? ¿Estará disponible la mesa?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prepara el listado FF&E de esta estancia.
Cliente: pareja Ejemplo (ficticia), Madrid, España. Estancia: salón-comedor de 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho.
Piezas: sofá de 3 plazas con chaise longue; alfombra dejando 40 cm de suelo visto en cada lado; mesa de centro; mesa de comedor para 6; 6 sillas; 2 lámparas de pie; cortinas para las dos ventanas.
Existente: aparador de roble — se conserva.
Usuarios: la pareja y un gato que araña.
Le gusta: roble claro, lino. No le gusta: el blanco puro, el terciopelo.
Presupuesto: 18.000 € IVA incluido, con transporte y montaje. Montaje: 1 de marzo de 2027. Plazo de tapicería según nuestros proveedores: 10–12 semanas.
````

## Output (verbatim stdout, session metadata stripped)

INTENCIÓN DE DISEÑO

  Estancia, uso y ubicación: salón-comedor, vivienda en Madrid (España). Estancia de 5,0 × 6,4 m, techo de 2,70 m y dos ventanas de 1,8 m de ancho; falta su altura.
  Usuarios / mascotas: pareja adulta y un gato que araña. No se indican necesidades de movilidad ni menores.
  Criterios del briefing: gustan el roble claro y el lino.
  Excluido por indicación del cliente: blanco puro, terciopelo.
  Datos pendientes o conflictos de diseño:
    - El lino gusta, pero hay un gato que araña. Debe verificarse la resistencia a arañazos y enganches de cualquier tejido, incluido el lino, antes de elegirlo.
    - Una alfombra con 40 cm libres por lado ocuparía también la zona de comedor. Falta confirmar si debe cubrir toda la estancia o solo la zona de estar.
    - Falta coordinar el tono del aparador de roble existente con el roble claro deseado.

LISTADO FF&E

  Nota común de IVA: el presupuesto total es con IVA. Las asignaciones aún no existen ("por asignar"). Cuando se asignen, se expresarán con IVA para que sean comparables.

  MOB-01  Sofá de 3 plazas con chaise longue
    Cant.: 1
    Medida objetivo: FALTA (ancho, fondo y lado de la chaise)
    Requisitos por verificar: resistencia del tapizado a arañazos y enganches de gato, abrasión, limpieza; excluido el terciopelo y el blanco puro
    Asignación: por asignar (con IVA)
    Plazo: tapicería de 10–12 semanas; pedir antes de: no calculable (falta margen)
    Estado: nueva

  TEX-01  Alfombra
    Cant.: 1
    Medida objetivo: (640 − 2 × 40) × (500 − 2 × 40) = 560 × 420 cm (5,6 × 4,2 m). Equivalencia: 6,4 m = 640 cm y 5,0 m = 500 cm.
    Requisitos por verificar: resistencia a arañazos y enganches, facilidad de limpieza, base o sistema antideslizante; sin terciopelo ni blanco puro
    Asignación: por asignar (con IVA)
    Plazo: FALTA; viabilidad de plazo no comprobada
    Estado: nueva

  MOB-02  Mesa de centro
    Cant.: 1
    Medida objetivo: FALTA
    Requisitos por verificar: acabado (roble claro preferido) resistente a arañazos, estabilidad
    Asignación: por asignar (con IVA)
    Plazo: FALTA; viabilidad de plazo no comprobada
    Estado: nueva

  MOB-03  Mesa de comedor para 6
    Cant.: 1
    Medida objetivo: FALTA (no hay criterio dimensional por comensal ni de circulación)
    Requisitos por verificar: acabado resistente a arañazos, estabilidad
    Asignación: por asignar (con IVA)
    Plazo: FALTA; viabilidad de plazo no comprobada
    Estado: nueva

  MOB-04  Sillas de comedor
    Cant.: 6
    Medida objetivo: FALTA
    Requisitos por verificar: si son tapizadas, resistencia a arañazos, abrasión y limpieza; estabilidad
    Asignación: por asignar (con IVA)
    Plazo: FALTA; si son tapizadas, falta confirmar si aplica el plazo de 10–12 semanas
    Estado: nueva

  ILU-01  Lámparas de pie
    Cant.: 2
    Medida objetivo: FALTA
    Requisitos por verificar: estabilidad frente a vuelcos (gato), seguridad eléctrica
    Asignación: por asignar (con IVA)
    Plazo: FALTA; viabilidad de plazo no comprobada
    Estado: nueva

  TEX-02  Cortinas
    Cant.: 2 (una por ventana; número de paños FALTA)
    Medida objetivo: ancho = 1,8 m + márgenes laterales (FALTA margen); alto FALTA (punto de colgado; techo de 2,70 m)
    Requisitos por verificar: resistencia a enganches de gato, reacción al fuego, limpieza; lino preferido, sin terciopelo ni blanco puro
    Asignación: por asignar (con IVA); el sistema de colgado no está definido
    Plazo: FALTA; falta confirmar si aplica el plazo de tapicería
    Estado: nueva

  MOB-05  Aparador de roble
    Cant.: 1
    Medida objetivo: FALTA (medidas del existente)
    Requisitos por verificar: estabilidad y posible anclaje a pared (gato)
    Asignación: adquisición 0 € si pertenece al cliente; intervenciones, traslado o anclaje pendientes de valorar
    Plazo: no aplica salvo que haya intervención
    Estado: existente-reutilizar

CONTROL DE PRESUPUESTO

  Presupuesto del cliente: 18.000 € con IVA. Incluye transporte y montaje.
  Origen del reparto: pendiente. No hay asignaciones aportadas ni autorización para proponer un reparto.
  Asignaciones estimadas: todas por asignar. Cuando existan, deberán confirmarse con presupuesto de proveedor.
  Suma: 0 € en asignaciones numéricas (solo MOB-05, adquisición 0 €). Partidas pendientes: MOB-01 a MOB-04, TEX-01, TEX-02, ILU-01 y las posibles intervenciones de MOB-05.
  Diferencia: 18.000 € − 0 € = 18.000 €. Es saldo aún no asignado, no ahorro ni reserva.
  Transporte y montaje: incluidos en el total según el cliente. Falta saber si incluyen la instalación de las cortinas (rieles o barras).
  Intervenciones en MOB-05: pendientes.

CONTROL DE PLAZOS

  Fecha de montaje: 1 de marzo de 2027. Fecha de referencia para los cálculos: 19 de octubre de 2026 (hoy).

  MOB-01: plazo aportado de tapicería de 10–12 semanas. No hay margen acordado, así que no puede calcularse la fecha de pedido. Como referencia sin margen (no es una fecha de pedido):
    1-mar-2027 − 12 semanas (84 días) = 7-dic-2026
    1-mar-2027 − 10 semanas (70 días) = 21-dic-2026
    El margen acordado adelantará estas fechas.
    Por confirmar: si el plazo incluye transporte y montaje o solo la fabricación, si son semanas naturales o laborables, y los cierres del proveedor en Navidad.

  TEX-01, MOB-02, MOB-03, ILU-01: viabilidad de plazo no comprobada (faltan plazo y margen).

  MOB-04, TEX-02: viabilidad no comprobada. Falta confirmar si llevan tapicería o confección a medida y si aplica el plazo de 10–12 semanas.

  Riesgo: las piezas a medida o importadas sin plazo confirmado son críticas para el 1 de marzo.

ESPECIFICACIONES POR VERIFICAR

  Estado de todas: pendientes de ficha técnica.

  MOB-01: reacción al fuego del tapizado y del relleno; abrasión con método y ciclos (sin equiparar métodos); código de limpieza; resistencia a enganches. Resistencia al deslizamiento: no aplica, no es superficie de paso.
  TEX-01: reacción al fuego; resistencia al deslizamiento de la base o del soporte antideslizante; código de limpieza; resistencia al uso y a enganches.
  MOB-02 y MOB-03: resistencia del acabado al rayado; estabilidad. Abrasión textil: no aplica, sin tapizado.
  MOB-04: estabilidad. Si son tapizadas, también reacción al fuego, abrasión (método y ciclos) y limpieza.
  ILU-01: estabilidad y documentación de seguridad eléctrica.
  TEX-02: reacción al fuego; limpieza y comportamiento al lavado; resistencia a enganches. Abrasión y deslizamiento: no aplican, no es tapizado ni pavimento.
  MOB-05: estabilidad y necesidad de anclaje en obra.

  Reacción al fuego y seguridad: el interiorista responsable confirma las exigencias según el uso y la normativa local, y la documentación que debe acreditarlas.

PREGUNTAS PARA EL CLIENTE

  1. Presupuesto: ¿autorizáis una propuesta de reparto por pieza o vais a aportar asignaciones?
  2. TEX-01: ¿la alfombra cubre toda la estancia (5,6 × 4,2 m) o solo la zona de estar? En ese caso, ¿con qué medidas y margen?
  3. MOB-01: ¿qué medidas máximas tiene el sofá y en qué lado va la chaise?
  4. MOB-02, MOB-03, MOB-04, ILU-01: ¿qué medidas objetivo o criterios dimensionales usamos (espacio por comensal, circulación)?
  5. TEX-02: ¿cuál es la altura de las ventanas, el punto de colgado, el número de paños y el margen lateral? ¿Hay que incluir rieles o barras?
  6. MOB-05: ¿qué medidas tiene el aparador? ¿Pertenece al cliente y sigue en la vivienda? ¿Necesita restauración, traslado o anclaje?
  7. Materiales: ante el gato que araña, ¿se mantiene el lino como preferencia, sujeto a verificar su resistencia? ¿El tono del aparador condiciona el roble claro de las piezas nuevas?
  8. Plazos: ¿qué margen de seguridad acordamos? ¿El plazo de 10–12 semanas incluye transporte y montaje, y se cuenta en semanas naturales? ¿Aplica también a las sillas y las cortinas?
  9. Plazos: ¿qué plazos tienen la alfombra, las mesas y las lámparas?
  10. Transporte y montaje: ¿incluyen la instalación de cortinas y lámparas?

Antes de enviar al cliente, revisad references/checklist.md. Las medidas en obra, la circulación, los accesos, los costes y los plazos debe verificarlos el profesional responsable.

