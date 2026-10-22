# Transcript — skill interior-designers-ffe-schedule [es] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:57:52+00:00
- duration_s: 147.8
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

Estancia: salón-comedor, 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho. Madrid, España.
Usuarios: pareja (sin datos identificativos) y un gato que araña.
Gustos: roble claro, lino.
Excluido por indicación del cliente: blanco puro, terciopelo. Estos materiales/colores se retiran de cualquier propuesta de acabado para todas las piezas.
Datos pendientes o conflictos de diseño: no se han aportado dimensiones objetivo para sofá, mesa de centro, mesa de comedor, sillas, lámparas de pie ni cortinas; no se ha confirmado si las sillas son tapizadas; no se ha aclarado si el margen de la alfombra (40 cm por lado) se aplica al perímetro de toda la sala o a una zona concreta (estar/comedor); no se han facilitado las medidas del aparador existente.

LISTADO FF&E

Código: MOB-01 — Sofá de 3 plazas con chaise longue
 Cantidad: 1
 Medida objetivo: FALTA (sin dimensiones aportadas por el cliente; no se pueden derivar sin un criterio dimensional)
 Material/uso — requisitos por verificar: tejido resistente al arañado por gato y de fácil limpieza (verificar en ficha técnica, método y ciclos de abrasión); preferencia declarada por lino (confirmar disponibilidad); excluido terciopelo y blanco puro
 Asignación estimada: por asignar — confirmar con presupuesto; IVA incluido (según presupuesto total)
 Plazo / pedir antes de: plazo de tapicería aportado por proveedores: 10–12 semanas; margen acordado: FALTA; viabilidad de plazo no comprobada
 Estado: nueva

Código: MOB-02 — Mesa de centro
 Cantidad: 1
 Medida objetivo: FALTA (sin dimensiones ni criterio de proporción con el sofá aportados)
 Material/uso — requisitos por verificar: acabado y resistencia al uso si es roble claro (preferencia del cliente, no confirma disponibilidad); excluido terciopelo y blanco puro (no aplica a tablero pero se mantiene por coherencia de acabados)
 Asignación estimada: por asignar; IVA incluido
 Plazo / pedir antes de: sin plazo aportado — viabilidad de plazo no comprobada
 Estado: nueva

Código: MOB-03 — Mesa de comedor para 6
 Cantidad: 1
 Medida objetivo: FALTA (solo se indica capacidad "para 6", sin dimensiones ni espacio disponible confirmado)
 Material/uso — requisitos por verificar: acabado roble claro (preferencia); excluido terciopelo y blanco puro
 Asignación estimada: por asignar; IVA incluido
 Plazo / pedir antes de: sin plazo aportado — viabilidad de plazo no comprobada
 Estado: nueva

Código: MOB-04 — Sillas
 Cantidad: 6
 Medida objetivo: FALTA
 Material/uso — requisitos por verificar: confirmar si son tapizadas; si lo son, aplican los mismos requisitos que MOB-01 (abrasión, limpieza, resistencia al gato); si no, verificar estabilidad y acabado; excluido terciopelo y blanco puro
 Asignación estimada: por asignar; IVA incluido
 Plazo / pedir antes de: sin plazo confirmado para esta pieza — viabilidad de plazo no comprobada; si llevan tapicería, confirmar si entra en el mismo plazo de proveedor (10–12 semanas) indicado para el sofá
 Estado: nueva

Código: MOB-05 — Lámparas de pie
 Cantidad: 2
 Medida objetivo: FALTA (altura y dimensiones de base no aportadas)
 Material/uso — requisitos por verificar: seguridad eléctrica (certificación), estabilidad mecánica frente a vuelco (relevante con gato en la vivienda), reacción al fuego del material de pantalla si aplica
 Asignación estimada: por asignar; IVA incluido
 Plazo / pedir antes de: sin plazo aportado — viabilidad de plazo no comprobada
 Estado: nueva

Código: TEX-01 — Alfombra
 Cantidad: 1 (a confirmar si se necesita más de una pieza según zonas)
 Medida objetivo y cálculo: fórmula aplicada sobre las medidas de la sala completa, a falta de otra indicación:
  (largo − 2 × margen) × (ancho − 2 × margen) = (5,0 − 2×0,40) × (6,4 − 2×0,40) = 4,2 m × 5,6 m
  Nota: este cálculo asume que el margen de 40 cm se aplica al perímetro de toda la estancia (5,0 × 6,4 m). Si el cliente se refería a una zona concreta (p. ej. solo la zona de estar, bajo el sofá y mesa de centro) o a dos alfombras independientes, el resultado cambia — pendiente de confirmación.
 Material/uso — requisitos por verificar: resistencia al arañado por gato, código de limpieza, método y ciclos de abrasión si aplica, resistencia al deslizamiento (sí aplica, es revestimiento de suelo), reacción al fuego; excluido terciopelo; preferencia lino (confirmar si aplica a fibra de alfombra o solo a textiles de tapicería)
 Asignación estimada: por asignar; IVA incluido
 Plazo / pedir antes de: sin plazo aportado — viabilidad de plazo no comprobada
 Estado: nueva

Código: TEX-02 — Cortinas
 Cantidad: 2 ventanas de 1,8 m de ancho cada una (confirmar número de paños por ventana: 1 o 2 por lado)
 Medida objetivo: FALTA (no se ha aportado altura de ventana, caída deseada ni tipo de instalación —riel o barra— ni margen de vuelo lateral habitual; no se puede calcular el ancho de confección sin estos datos)
 Material/uso — requisitos por verificar: reacción al fuego/inflamabilidad de textil vertical (el interiorista confirma si aplica según uso residencial y normativa local), código de limpieza; abrasión y deslizamiento: no aplicable por tratarse de textil vertical sin roce de uso ni ser revestimiento de suelo (a confirmar por el interiorista si procede verificar igualmente); excluido terciopelo y blanco puro; preferencia lino
 Asignación estimada: por asignar; IVA incluido
 Plazo / pedir antes de: sin plazo aportado — viabilidad de plazo no comprobada
 Estado: nueva

Código: MOB-06 — Aparador de roble (existente, se conserva)
 Cantidad: 1
 Medida objetivo: FALTA (el cliente confirma que se conserva, pero no se han aportado sus dimensiones ni su ubicación definitiva en la sala)
 Material/uso — requisitos por verificar: estabilidad y anclaje si procede, estado de acabado del roble, verificar resistencia a arañado en la superficie si el gato tiene acceso a esa zona
 Asignación estimada: 0 € de adquisición (ya pertenece al cliente); transporte/reubicación/intervención: no indicado — pendiente de confirmar si requiere alguno de estos conceptos
 Plazo / pedir antes de: no aplica plazo de fabricación; disponibilidad por verificar si requiere intervención
 Estado: existente-reutilizar (confirmado por el cliente, "se conserva")

CONTROL DE PRESUPUESTO

Presupuesto del cliente: 18.000 €, IVA incluido. Incluye transporte y montaje, según indicación del cliente.
Origen del reparto: no aportado por el cliente; no se ha recibido autorización para proponer un reparto — pendiente de confirmar.
Asignaciones estimadas: todas las piezas nuevas constan como "por asignar"; cuando se definan, deberán etiquetarse como "asignación estimada — confirmar con presupuesto" antes de considerarse definitivas.
Suma de partidas numéricas: MOB-06 adquisición 0 € (resto de piezas sin importe asignado) → 0 € + 0 € (piezas nuevas pendientes) = 0 €.
Partidas pendientes de asignación: MOB-01, MOB-02, MOB-03, MOB-04, MOB-05, TEX-01, TEX-02.
Diferencia: 18.000 € − 0 € = 18.000 € → saldo aún no asignado (no es ahorro ni reserva disponible; refleja que el reparto del presupuesto está pendiente de definir).
Transporte y montaje: incluidos en el presupuesto según indicación del cliente, para las piezas nuevas. Para el aparador (MOB-06) no se ha indicado si necesita transporte o intervención — pendiente.

CONTROL DE PLAZOS

Fecha de montaje o instalación: 1 de marzo de 2027 (aportada por el cliente).

MOB-01 (sofá): plazo aportado por proveedores de tapicería: 10–12 semanas. Alcance del plazo (si incluye transporte e instalación) y tipo de días (naturales o laborables): no confirmado. Margen de seguridad acordado: FALTA.
 Cálculo de la fórmula: Pedir antes de = fecha de montaje − plazo total − margen acordado.
 Sin margen (orientativo, no es fecha de pedido confirmada):
  Con 12 semanas (84 días): 1 marzo 2027 − 84 días = 7 diciembre 2026.
  Con 10 semanas (70 días): 1 marzo 2027 − 70 días = 21 diciembre 2026.
 Al faltar el margen, la fecha real de pedido debe ser anterior a estas referencias. Con fecha de hoy, 19 de octubre de 2026, restan aproximadamente 7 a 10 semanas hasta esas fechas orientativas — dato para que el cliente valore la urgencia de confirmar el margen y el alcance del plazo, sin que esto implique un plazo vencido.
 Viabilidad de plazo no comprobada hasta disponer de margen acordado y confirmación de alcance (transporte/instalación) y tipo de días.

MOB-04 (sillas): si resultan tapizadas, aclarar si aplica el mismo plazo de proveedor (10–12 semanas) que el sofá o uno distinto.

Resto de piezas (MOB-02 mesa de centro, MOB-03 mesa de comedor, MOB-05 lámparas de pie, TEX-01 alfombra, TEX-02 cortinas): no se han aportado plazos de entrega — viabilidad de plazo no comprobada en todos los casos. Prestar especial atención si alguna de estas piezas termina siendo a medida o de importación, dado el margen ajustado hasta el montaje.

MOB-06 (aparador): no aplica plazo de fabricación; pendiente confirmar si necesita transporte o intervención y, en tal caso, su plazo.

ESPECIFICACIONES POR VERIFICAR

MOB-01 (sofá): reacción al fuego/inflamabilidad — pendiente; abrasión, método y ciclos (incluidos double rubs si corresponde) — pendiente; código de limpieza — pendiente; resistencia al deslizamiento — no aplicable (no es revestimiento de suelo).
MOB-02 (mesa de centro) y MOB-03 (mesa de comedor): reacción al fuego — no aplicable en mobiliario rígido sin tapicería salvo acabados lacados/barnizados específicos, a confirmar por el interiorista; resistencia al rayado del acabado — pendiente; abrasión y deslizamiento — no aplicable.
MOB-04 (sillas): pendiente definir si tapizadas; si lo son, mismas verificaciones que MOB-01; si no, verificar estabilidad y acabado — pendiente.
MOB-05 (lámparas de pie): seguridad eléctrica (certificación) — pendiente; estabilidad frente a vuelco — pendiente; reacción al fuego del material de pantalla si aplica — pendiente.
MOB-06 (aparador): estabilidad y anclaje si procede — pendiente; resistencia del acabado a arañado — pendiente.
TEX-01 (alfombra): reacción al fuego — pendiente; abrasión, método y ciclos — pendiente; código de limpieza — pendiente; resistencia al deslizamiento — pendiente (sí aplica, es revestimiento de suelo).
TEX-02 (cortinas): reacción al fuego/inflamabilidad de textil vertical — pendiente, a confirmar por el interiorista si la normativa local lo exige en uso residencial; código de limpieza — pendiente; abrasión — no aplicable por tratarse de textil vertical sin roce de uso continuo (a confirmar); deslizamiento — no aplicable (no es revestimiento de suelo).

El interiorista responsable confirma las exigencias de reacción al fuego y seguridad aplicables según el uso de la estancia y la normativa local vigente; este listado no certifica cumplimiento normativo alguno.

PREGUNTAS PARA EL CLIENTE

1. MOB-01 (sofá): dimensiones objetivo (largo total, profundidad, orientación de la chaise longue) y margen de seguridad acordado antes del montaje para calcular la fecha límite de pedido.
2. MOB-02 (mesa de centro): dimensiones objetivo o espacio disponible junto al sofá.
3. MOB-03 (mesa de comedor): dimensiones objetivo o espacio disponible, más allá de la capacidad para 6 personas.
4. MOB-04 (sillas): dimensiones y confirmación de si son tapizadas (afecta a especificaciones y plazo de proveedor).
5. MOB-05 (lámparas de pie): altura y dimensiones de base deseadas.
6. TEX-01 (alfombra): ¿el margen de 40 cm por lado se aplica al perímetro de toda la sala (5,0 × 6,4 m) o a una zona concreta (estar o comedor)? ¿Se necesita una sola alfombra o dos piezas independientes?
7. TEX-02 (cortinas): altura de ventana y caída deseada, número de paños por ventana, tipo de instalación (riel o barra) y margen de vuelo lateral deseado.
8. MOB-06 (aparador): dimensiones actuales, ubicación definitiva en la nueva distribución y si requiere transporte o alguna intervención.
9. Presupuesto: ¿desean aportar un reparto por pieza o autorizan que se proponga uno, claramente identificado como estimación a confirmar?
10. Plazos: confirmar si las 10–12 semanas de tapicería del sofá incluyen transporte e instalación, y si se expresan en semanas naturales o laborables; margen de seguridad acordado antes del 1 de marzo de 2027; plazos de entrega pendientes para mesa de centro, mesa de comedor, sillas, lámparas de pie, cortinas y alfombra.
11. MOB-04 (sillas): si son tapizadas, ¿comparten el mismo plazo de proveedor que el sofá (10–12 semanas) u otro distinto?

