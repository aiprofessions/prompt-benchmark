# Transcript — skill interior-designers-ffe-schedule [es] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:02:27+00:00
- duration_s: 66.3
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

  Estancia, uso y ubicación: salón-comedor de vivienda en Madrid (España). 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho.
  Usuarios / mascotas: pareja adulta y un gato que araña. No se indican menores ni necesidades de movilidad.
  Preferencias: roble claro y lino.
  Excluido por indicación del cliente: blanco puro y terciopelo. Quedan fuera de materiales, acabados y alternativas.
  Datos pendientes o conflictos de diseño:
    - El gato que araña afecta a todas las piezas tapizadas y textiles, también a las de lino. Hay que verificar la resistencia a enganches y arañazos en la ficha técnica. No se presupone que el lino la cumpla o la incumpla.
    - El margen de 40 cm de la alfombra, aplicado a toda la estancia, da una alfombra de 5,6 × 4,2 m que quedaría bajo la zona de sofá y la de comedor. Hay que confirmar si esa es la intención o si el margen se refiere solo a la zona de salón.
    - Faltan accesos: portal, ascensor, escalera y puertas. Son relevantes para el sofá con chaise longue, la alfombra y la mesa de comedor.
    - No se indica la ubicación del aparador ni la distribución entre las zonas de salón y comedor.

LISTADO FF&E

  Nota común de IVA: todas las asignaciones están "por asignar". El presupuesto total es con IVA.

  MOB-01  Sofá de 3 plazas con chaise longue
    Cant.: 1
    Medida objetivo: FALTA. También falta el lado de la chaise (izquierda o derecha).
    Requisitos por verificar:
      - Tapicería (lino u otro tejido, nunca terciopelo): resistencia a arañazos y enganches por el gato, facilidad de limpieza, abrasión, código de limpieza y reacción al fuego.
      - Color: no blanco puro.
    Asignación: por asignar (con IVA).
    Plazo: 10–12 semanas de tapicería (dato de proveedores). Pedir antes del 7-12-2026 menos el margen acordado (ver Control de plazos).
    Estado: nueva.

  MOB-02  Mesa de centro
    Cant.: 1
    Medida objetivo: FALTA.
    Requisitos por verificar: acabado (preferencia roble claro, no blanco puro), resistencia del acabado a arañazos y estabilidad.
    Asignación: por asignar (con IVA).
    Plazo: viabilidad de plazo no comprobada.
    Estado: nueva.

  MOB-03  Mesa de comedor para 6
    Cant.: 1
    Medida objetivo: FALTA. No hay criterio dimensional aportado para 6 comensales.
    Requisitos por verificar: acabado (preferencia roble claro), resistencia del acabado al uso y a arañazos, estabilidad y circulación alrededor.
    Asignación: por asignar (con IVA).
    Plazo: viabilidad de plazo no comprobada.
    Estado: nueva.

  MOB-04  Sillas de comedor
    Cant.: 6
    Medida objetivo: FALTA.
    Requisitos por verificar:
      - Estructura: preferencia roble claro, estabilidad.
      - Si llevan tapizado: tejido sin terciopelo, resistencia a arañazos y enganches, limpieza, abrasión y reacción al fuego.
    Asignación: por asignar (con IVA).
    Plazo: si son tapizadas, se aplican las 10–12 semanas de tapicería. Si no, viabilidad no comprobada.
    Estado: nueva.

  MOB-05  Aparador de roble (propiedad del cliente)
    Cant.: 1
    Medida: FALTA.
    Requisitos por verificar: estabilidad y necesidad de anclaje a pared (el gato puede trepar).
    Asignación: adquisición 0 € (pertenece al cliente). Transporte, recolocación o restauración pendientes de confirmar.
    Plazo: sin intervención declarada. Disponibilidad por confirmar.
    Estado: existente-reutilizar (conservación confirmada por el cliente).

  ILU-01  Lámparas de pie
    Cant.: 2
    Medida objetivo: FALTA (altura y base).
    Requisitos por verificar:
      - Estabilidad frente a vuelco por el gato y protección del cable.
      - Pantalla: no blanco puro.
      - Documentación de seguridad eléctrica aplicable.
    Asignación: por asignar (con IVA).
    Plazo: viabilidad de plazo no comprobada.
    Estado: nueva.

  TEX-01  Alfombra
    Cant.: 1
    Medida objetivo, con margen de 40 cm = 0,40 m por lado:
      (6,4 − 2 × 0,40) × (5,0 − 2 × 0,40) = 5,6 × 4,2 m
      El cálculo es provisional hasta confirmar si el margen se aplica a toda la estancia.
    Requisitos por verificar: material sin terciopelo, resistencia a arañazos y enganches (tejidos de bucle), facilidad de limpieza, abrasión, resistencia al deslizamiento o base antideslizante y reacción al fuego. Color: no blanco puro.
    Asignación: por asignar (con IVA).
    Plazo: viabilidad no comprobada. Con ese tamaño probablemente sería a medida, sin plazo confirmado.
    Estado: nueva.

  TEX-02  Cortinas
    Cant.: 2 (una por ventana). Número de paños: FALTA.
    Medida objetivo:
      - Ancho de ventana: 1,8 m (dato).
      - Ancho de cortina = (1,8 + 2 × desborde lateral) × factor de fruncido. Desborde y factor: FALTA.
      - Alto: depende de la altura de fijación (techo 2,70 m como dato) y de la caída deseada. FALTA.
    Requisitos por verificar: tejido (preferencia lino, no terciopelo, no blanco puro), resistencia a enganches por el gato, limpieza o lavado, comportamiento dimensional al lavar y reacción al fuego.
    Asignación: por asignar (con IVA). La instalación de rieles o barras queda pendiente.
    Plazo: confección a medida sin plazo confirmado. Viabilidad no comprobada.
    Estado: nueva.

  Cobertura: 7 piezas solicitadas y 1 existente dan 8 códigos, sin duplicados.

CONTROL DE PRESUPUESTO

  Presupuesto del cliente: 18.000 € IVA incluido.
  Origen del reparto: pendiente. No hay asignaciones por pieza ni autorización para proponerlas.
  Asignaciones estimadas: ninguna. Cuando existan, se confirmarán con presupuestos de proveedor.
  Suma de asignaciones numéricas: 0 € (solo MOB-05, adquisición). Partidas pendientes: MOB-01 a MOB-04, ILU-01, TEX-01 y TEX-02, además de las intervenciones o el transporte de MOB-05 y los rieles de las cortinas.
  Diferencia: 18.000 − 0 = 18.000 €. Es saldo aún no asignado, no ahorro.
  Transporte y montaje: incluidos en los 18.000 € según el briefing. Falta saber si están dentro de cada pieza o en partida aparte. Las intervenciones sobre MOB-05 y la instalación de cortinas están pendientes.

CONTROL DE PLAZOS

  Fecha de montaje: 1 de marzo de 2027.
  Fecha de referencia: 19 de octubre de 2026.

  MOB-01 (y MOB-04 si va tapizada): plazo de tapicería de 10–12 semanas.
    - Con 12 semanas (peor caso): 1-3-2027 − 84 días = 7-12-2026, menos el margen acordado.
    - Con 10 semanas: 1-3-2027 − 70 días = 21-12-2026, menos el margen acordado.
    - Falta el margen acordado, así que no hay fecha definitiva para pedir.
    - El 7-12-2026 está a 7 semanas de la fecha de referencia. No está vencido, pero el margen es ajustado.
    - Por confirmar: si el plazo incluye transporte y montaje, y si son semanas naturales.

  MOB-02, MOB-03, ILU-01, TEX-01 y TEX-02: viabilidad de plazo no comprobada.
  Riesgo: TEX-01 (posible tamaño a medida) y TEX-02 (confección a medida) no tienen plazo confirmado.

  MOB-05: sin intervención declarada. Si se restaura o se traslada, hará falta su plazo.

ESPECIFICACIONES POR VERIFICAR (en ficha técnica del fabricante)

  MOB-01: abrasión (método y ciclos, incluidos double rubs si aplica), resistencia a enganches o arañazos, código de limpieza, reacción al fuego de tejido y relleno. Pendiente.
  MOB-02 / MOB-03: resistencia del acabado y estabilidad. Pendiente. Reacción al fuego: el interiorista confirma si aplica.
  MOB-04: estabilidad. Si es tapizada, abrasión, limpieza y reacción al fuego. Pendiente.
  MOB-05: estabilidad y anclaje. Pendiente. Las fichas de producto no aplican porque es pieza existente.
  ILU-01: estabilidad y documentación de seguridad eléctrica. Pendiente.
  TEX-01: abrasión, limpieza, resistencia al deslizamiento y reacción al fuego. Pendiente.
  TEX-02: reacción al fuego, limpieza o lavado y estabilidad dimensional. Pendiente.

  Reacción al fuego y seguridad: el interiorista responsable confirma las exigencias según el uso y la normativa local, así como la documentación que las acredite. No se presentan valores ni clasificaciones como comprobados.

PREGUNTAS PARA EL CLIENTE

  1. Presupuesto: ¿hay reparto por pieza o autorizan una propuesta de reparto? ¿El transporte y montaje van dentro de cada pieza o en partida aparte?
  2. Plazos: ¿qué margen de seguridad se acuerda antes del 1-3-2027? ¿El plazo de 10–12 semanas incluye transporte y montaje? ¿Son semanas naturales?
  3. MOB-01: ¿qué medidas máximas tiene el sofá y en qué lado va la chaise longue? ¿Cómo son los accesos (portal, ascensor, escalera, puertas)?
  4. MOB-02 / MOB-03: ¿qué medidas objetivo o criterios dimensionales usamos? ¿Mesa de comedor rectangular, redonda o extensible?
  5. MOB-04: ¿las sillas son tapizadas?
  6. MOB-05: ¿qué medidas tiene el aparador y dónde va? ¿Necesita traslado, restauración o anclaje?
  7. ILU-01: ¿qué altura y estilo buscan para las lámparas? ¿Dónde están los puntos de enchufe?
  8. TEX-01: ¿el margen de 40 cm es respecto a toda la estancia (5,6 × 4,2 m) o solo a la zona de salón? ¿Hay plazo de proveedor?
  9. TEX-02: ¿qué altura de fijación, caída, desborde lateral, fruncido y número de paños quieren? ¿Hay que instalar rieles o barras?
  10. Gato: ¿aceptan que la elección del lino en las tapicerías quede condicionada a verificar su resistencia a arañazos? Si la ficha no lo respalda, ¿qué prefieren?
  11. Plazos del resto de piezas: ¿hay plazos de proveedor para MOB-02, MOB-03, ILU-01, TEX-01 y TEX-02?

  Antes de enviar, el profesional responsable debe revisar references/checklist.md y verificar en obra medidas, accesos, circulación, estabilidad y anclajes.

