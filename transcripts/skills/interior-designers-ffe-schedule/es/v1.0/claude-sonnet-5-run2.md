# Transcript — skill interior-designers-ffe-schedule [es] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:06:53+00:00
- duration_s: 136.3
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

Estancia: salón-comedor, Madrid (España). Dimensiones: 5,0 m × 6,4 m; techo 2,70 m; dos ventanas de 1,8 m de ancho cada una.
Uso: estar + comedor para la pareja (sin datos identificativos).
Usuarios: pareja y un gato que araña.
Preferencias del cliente: roble claro, lino.
Excluido por indicación del cliente: blanco puro, terciopelo. Estos materiales/acabados se eliminan de cualquier propuesta y, si afectan a una pieza solicitada, se señala como conflicto pendiente sin recomendar la opción rechazada (en este briefing no hay pieza cuya única opción sea blanco puro o terciopelo, así que no se registra conflicto).
Datos pendientes o conflictos de diseño: no se han aportado medidas objetivo para la mayoría de piezas nuevas (solo se dan datos de la estancia, ventanas y el margen de la alfombra); la mesa de comedor solo tiene capacidad (6 personas) sin medidas; faltan accesos/pasos para verificar viabilidad de entrada de piezas grandes.

LISTADO FF&E
(Código | Pieza | Cant. | Medida objetivo y cálculo | Requisitos por verificar | Asignación estimada / IVA | Plazo / pedir antes de | Estado)

SOF-01 | Sofá 3 plazas con chaise longue | 1 | FALTA (sin medidas objetivo aportadas; solo se indica tipología) | Tapizado: reacción al fuego/inflamabilidad, abrasión (método y ciclos, incluidos double rubs si aplica), código de limpieza, resistencia al arañazo por presencia de gato (sin estándar oficial confirmado, pendiente de ficha técnica) | por asignar — asignación estimada por confirmar con presupuesto (ES) | Plazo tapicería proveedores: 10–12 semanas; viabilidad de plazo no comprobada (falta margen acordado y confirmación de si incluye transporte/instalación y si son semanas naturales o laborables) | nueva

TEX-01 | Alfombra | 1 | Fórmula aplicada sobre dimensiones de la estancia: (6,4 − 2×0,4) × (5,0 − 2×0,4) = 5,6 m × 4,2 m — calculado sobre toda la estancia a falta de indicación de zona específica (ver pregunta 2) | Reacción al fuego, abrasión, código de limpieza, resistencia al deslizamiento, resistencia al arañazo por gato | por asignar | Sin plazo de proveedor aportado; viabilidad de plazo no comprobada | nueva

MES-01 | Mesa de centro | 1 | FALTA (sin medidas aportadas) | Estabilidad, acabado/resistencia a manchas si roble claro o lino en algún componente; cantos redondeados: no aplica, no se reportan menores en el hogar | por asignar | Sin plazo de proveedor aportado; viabilidad de plazo no comprobada | nueva

MES-02 | Mesa de comedor para 6 | 1 | FALTA (solo se indica capacidad para 6 personas, sin medidas objetivo) | Estabilidad, resistencia de acabado; cantos redondeados: no aplica (sin menores reportados) | por asignar | Sin plazo de proveedor aportado; viabilidad de plazo no comprobada | nueva

SIL-01 | Sillas | 6 | FALTA (sin medidas aportadas) | Material no especificado (¿tapizadas o sólidas?): si tapizadas, verificar fuego, abrasión y limpieza en ficha; si madera, verificar acabado y estabilidad | por asignar | Sin plazo de proveedor aportado; viabilidad de plazo no comprobada | nueva

LAM-01 | Lámparas de pie | 2 | FALTA (sin altura ni medidas aportadas) | Seguridad eléctrica/certificación, estabilidad de base, cableado — normativa eléctrica local a confirmar por profesional habilitado | por asignar | Sin plazo de proveedor aportado; viabilidad de plazo no comprobada | nueva

COR-01 | Cortinas para las dos ventanas | 2 (un conjunto por ventana; confirmar si cada conjunto incluye uno o dos paños) | Ancho de ventana reportado: 1,8 m por unidad; ancho de tela y caída: FALTA (depende de holgura/fruncido deseado y de altura de instalación de barra/riel, no indicados; el techo de 2,70 m no determina por sí solo la caída) | Reacción al fuego/inflamabilidad (especialmente en salón-comedor), código de limpieza; evaluar si queda al alcance del gato (resistencia al arañazo si aplica) | por asignar | Sin plazo de proveedor aportado; viabilidad de plazo no comprobada | nueva

MOB-01 | Aparador de roble (existente) | 1 | FALTA (sin medidas aportadas; verificar en obra contra el espacio disponible) | Estabilidad y anclaje si aplica; material roble claro coincide con preferencia del cliente | 0 € (ya pertenece al cliente); sin intervención indicada — si se requiere restauración o ajuste, coste pendiente | No requiere plazo de compra; si hubiera intervención, su plazo queda pendiente de confirmar | existente-reutilizar

CONTROL DE PRESUPUESTO

Presupuesto del cliente: 18.000 €, con IVA incluido. Incluye transporte y montaje (declarado explícitamente).
Origen del reparto: no aportado por el cliente y sin autorización explícita para proponer un reparto → todas las partidas quedan "por asignar".
Asignaciones estimadas: pendientes; cuando se definan, se etiquetarán como "asignación estimada — confirmar con presupuesto (ES)".
Suma de asignaciones numéricas: 0 € (todas las partidas están "por asignar"; MOB-01 aporta 0 € de adquisición por ser ya del cliente).
Diferencia: 18.000 € − 0 € = 18.000 € → saldo aún no asignado (no es ahorro ni reserva disponible).
Transporte y montaje: incluidos según lo indicado por el cliente. Intervenciones sobre MOB-01 (si las hubiera): pendientes de valorar.

CONTROL DE PLAZOS

Fecha de montaje: 1 de marzo de 2027.

SOF-01: plazo aportado por proveedores de tapicería: 10–12 semanas. No se confirma si ese plazo incluye transporte e instalación, ni si se expresa en semanas naturales o laborables, ni el margen de seguridad acordado con el cliente. Cálculo de "pedir antes de" = fecha de montaje − plazo total hasta disponibilidad − margen acordado: no se puede completar por falta de margen y de confirmación de alcance → viabilidad de plazo no comprobada.

TEX-01, MES-01, MES-02, SIL-01, LAM-01, COR-01: sin plazo de proveedor aportado → viabilidad de plazo no comprobada para todas. Se recomienda especial atención si alguna de estas piezas (p. ej. mesa de comedor o cortinas a medida) resulta ser fabricación a medida o importación, dado que el margen hasta el 1 de marzo de 2027 es limitado si los plazos resultan largos.

MOB-01: no requiere plazo de adquisición (ya en posesión del cliente); si se precisa intervención, su plazo queda pendiente.

ESPECIFICACIONES POR VERIFICAR

SOF-01: reacción al fuego/inflamabilidad del tapizado — pendiente de ficha técnica; abrasión (método y ciclos, incluidos double rubs si aplica) — pendiente; código de limpieza — pendiente; resistencia al arañazo (gato) — pendiente, sin estándar oficial confirmado en este briefing.

TEX-01: reacción al fuego — pendiente; resistencia al deslizamiento — pendiente; abrasión y código de limpieza — pendiente; resistencia al arañazo (gato) — pendiente.

MES-01 / MES-02: estabilidad — pendiente de verificación en obra; cantos redondeados — no aplica (no se reportan menores en el hogar); acabado/resistencia a manchas — pendiente si se usa roble claro o lino en algún componente.

SIL-01: pendiente definir material (tapizado o sólido) para saber qué ficha técnica aplica (fuego/abrasión/limpieza si tapizadas; acabado/estabilidad si madera).

LAM-01: seguridad eléctrica y certificación — pendiente; estabilidad de base — pendiente de verificación en obra.

COR-01: reacción al fuego/inflamabilidad — pendiente; código de limpieza — pendiente; alcance al gato — pendiente de valorar según altura final de instalación.

MOB-01: estabilidad y, si aplica, anclaje — pendiente de verificación en obra.

Reacción al fuego y seguridad: el interiorista responsable confirma las exigencias aplicables según el uso de la estancia y la normativa local vigente, así como la documentación necesaria para acreditarlas.

PREGUNTAS PARA EL CLIENTE

1. SOF-01, MES-01, MES-02, SIL-01, LAM-01, MOB-01: no se han aportado medidas objetivo (solo tipología o, en el caso de la mesa de comedor, capacidad para 6). ¿Puede indicar medidas deseadas o tolerancias para cada pieza?

2. TEX-01: el cálculo se ha hecho sobre las dimensiones totales de la estancia (5,0 × 6,4 m menos 0,4 m de margen por lado = 4,2 × 5,6 m). ¿Es correcto que la alfombra cubra todo el salón-comedor, o debe limitarse a la zona de estar (sofá + mesa de centro)? El resultado cambiaría sustancialmente.

3. COR-01: ¿a qué altura se instalará la barra/riel y qué caída desea (hasta el suelo, alféizar, etc.)? ¿Qué factor de holgura/fruncido debe aplicarse sobre los 1,8 m de ancho de cada ventana? ¿Cada ventana lleva uno o dos paños?

4. Presupuesto: ¿autoriza al estudio a proponer un reparto de los 18.000 € entre las piezas, o aportará usted las asignaciones por partida?

5. SOF-01: ¿el plazo de 10–12 semanas de tapicería incluye transporte e instalación? ¿se expresa en semanas naturales o laborables? ¿qué margen de seguridad desea aplicar antes del montaje del 1 de marzo de 2027?

6. TEX-01, MES-01, MES-02, SIL-01, LAM-01, COR-01: ¿puede facilitar los plazos de entrega de los proveedores para estas piezas? Es especialmente relevante si alguna es fabricación a medida o importada, dado el margen hasta marzo de 2027.

7. SIL-01: ¿las sillas son tapizadas o de material sólido (madera u otro)? Esto determina las especificaciones de ficha técnica que aplican.

8. Gato que araña: ¿desea que el criterio de resistencia al arañazo se aplique también a las cortinas y/o a las sillas, o solo al sofá y la alfombra?

9. MOB-01: ¿el aparador existente requiere alguna intervención (limpieza, ajuste, pequeña reparación) antes del montaje, o se instala tal cual sin coste adicional?

10. (Opcional, recomendable) ¿Existen pasos estrechos, escaleras o ascensor que condicionen las dimensiones máximas de piezas como el sofá o la mesa de comedor?

