# Transcript — skill interior-designers-ffe-schedule [es] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:53:14+00:00
- duration_s: 64.1
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

Nota previa: he retirado el nombre del cliente; uso «la pareja». En esta terminal el formato markdown no se muestra, así que el listado aparece en bloques por código y no como tabla.

INTENCIÓN DE DISEÑO

  Estancia, uso y ubicación: salón-comedor de vivienda en Madrid (España). Mide 5,0 m × 6,4 m, con techo de 2,70 m y dos ventanas de 1,8 m de ancho.
  Usuarios / mascotas y criterios del briefing: pareja adulta y un gato que araña. Preferencias: roble claro y lino.
  Excluido por indicación del cliente: blanco puro, terciopelo.
  Datos pendientes o conflictos de diseño:
    - Lino frente a un gato que araña. El lino es una preferencia del cliente. Su resistencia a enganches y abrasión no está verificada, por lo que el interiorista debe decidir con la ficha técnica en la mano.
    - Alfombra. Con 40 cm de margen respecto a la estancia completa, la alfombra cubriría también la zona de comedor y quedaría bajo el aparador. Hay que confirmar si el margen se refiere a toda la estancia o solo a la zona de estar.
    - Faltan los accesos (portal, ascensor, escalera, puertas), relevantes sobre todo para el sofá con chaise longue.

LISTADO FF&E

  MOB-01 | Sofá 3 plazas con chaise longue | Cant. 1 | Estado: nueva
    Medida: FALTA. También falta la orientación de la chaise (izquierda o derecha).
    Requisitos por verificar: resistencia del tejido a arañazos y enganches, abrasión (método y ciclos), código de limpieza. Excluidos el terciopelo y el blanco puro. La compatibilidad del lino con el gato está por verificar.
    Asignación: por asignar (IVA incluido, según el total).
    Plazo: tapicería de 10–12 semanas, aportado por el cliente. Margen acordado: FALTA. Ver Control de plazos.

  MOB-02 | Mesa de centro | Cant. 1 | Estado: nueva
    Medida: FALTA (relación con el sofá y la circulación por definir).
    Requisitos por verificar: resistencia del acabado al rayado (gato), estabilidad. Roble claro como preferencia.
    Asignación: por asignar.
    Plazo: no aportado. Viabilidad de plazo no comprobada.

  MOB-03 | Mesa de comedor para 6 | Cant. 1 | Estado: nueva
    Medida: sin resolver. La fórmula de referencia es: largo = comensales por lado × ancho por comensal (+ cabeceras si las hay). Falta el criterio de ancho por comensal y la holgura perimetral para sillas y paso.
    Requisitos por verificar: resistencia del acabado al rayado y a las manchas. Roble claro como preferencia.
    Asignación: por asignar.
    Plazo: no aportado. Viabilidad de plazo no comprobada.

  MOB-04 | Sillas de comedor | Cant. 6 | Estado: nueva
    Medida: FALTA (altura de asiento según la mesa MOB-03).
    Requisitos por verificar: si van tapizadas, resistencia a arañazos, abrasión y código de limpieza. Excluidos el terciopelo y el blanco puro.
    Asignación: por asignar.
    Plazo: si van tapizadas, ¿aplica también el plazo de tapicería de 10–12 semanas? Por confirmar. Viabilidad no comprobada.

  MOB-05 | Aparador de roble (existente) | Cant. 1 | Estado: existente-reutilizar
    Medida: FALTA.
    Requisitos por verificar: estabilidad y posible anclaje al muro (el gato puede trepar).
    Asignación: adquisición 0 € (pieza del cliente). Traslado, restauración o adaptación: pendientes, no valorados.
    Plazo: disponibilidad para el montaje por confirmar.

  ILU-01 | Lámparas de pie | Cant. 2 | Estado: nueva
    Medida: altura FALTA.
    Requisitos por verificar: estabilidad frente a vuelco (gato), documentación de seguridad eléctrica, posición respecto a los enchufes.
    Asignación: por asignar.
    Plazo: no aportado. Viabilidad no comprobada.

  TEX-01 | Alfombra | Cant. 1 | Estado: nueva
    Medida: fórmula (largo − 2 × margen) × (ancho − 2 × margen), con margen = 40 cm = 0,40 m.
      (6,4 − 2 × 0,40) × (5,0 − 2 × 0,40) = 5,6 × 4,2 m.
      Válido solo si el margen se aplica a la estancia completa (ver conflicto).
    Requisitos por verificar: resistencia a arañazos y enganches (evitar bucles a confirmar con ficha), limpieza, resistencia al deslizamiento o base antideslizante. Excluido el blanco puro.
    Asignación: por asignar.
    Plazo: no aportado. Viabilidad no comprobada (posible pieza a medida por el tamaño).

  TEX-02 | Cortinas para 2 ventanas | Cant. 2 ventanas; nº de paños FALTA | Estado: nueva
    Medida: sin resolver. Ancho = (1,8 m + 2 × sobrepaso lateral) × factor de fruncido. Alto = altura de barra o riel al suelo − holgura (techo de 2,70 m como límite). Faltan el sobrepaso, el fruncido, la altura de la ventana, el tipo y la posición de la barra o riel, y la holgura.
    Requisitos por verificar: resistencia a enganches (gato), limpieza, solidez a la luz. Lino como preferencia. Excluidos el blanco puro y el terciopelo.
    Asignación: por asignar. ¿Barra o riel e instalación incluidos?
    Plazo: no aportado (¿confección a medida?). Viabilidad no comprobada.

  Cobertura: 7 piezas solicitadas y 1 existente, 8 filas, sin duplicados.

CONTROL DE PRESUPUESTO

  Presupuesto del cliente: 18.000 € IVA incluido, con transporte y montaje incluidos.
  Origen del reparto: pendiente. No hay asignaciones por pieza ni autorización para proponerlas.
  Asignaciones estimadas: ninguna. Cuando existan, se confirman con presupuestos de proveedor.
  Suma: 0 € (MOB-05, adquisición) = 0 €. Partidas pendientes: MOB-01 a MOB-04, ILU-01, TEX-01, TEX-02 y las intervenciones de MOB-05.
  Diferencia: 18.000 € − 0 € = 18.000 € de saldo aún no asignado. No es ahorro ni reserva.
  Transporte y montaje: incluidos en el total. Pendientes: traslado o restauración del aparador, e instalación de barras o rieles.

CONTROL DE PLAZOS

  Fecha de montaje: 1 de marzo de 2027. Fecha de referencia de hoy: 19 de octubre de 2026.
  MOB-01 (y MOB-04 si va tapizado):
    - Plazo de tapicería: 10–12 semanas. No consta si incluye transporte y montaje.
    - Margen acordado: FALTA.
    - Cálculo sin margen:
        1/03/2027 − 12 semanas (84 días) = 7/12/2026
        1/03/2027 − 10 semanas (70 días) = 21/12/2026
    - Pedir antes de = 7/12/2026 − margen acordado, tomando el escenario de 12 semanas. No está vencido a fecha de hoy.
    - La viabilidad queda no comprobada hasta conocer el margen y el alcance del plazo.
  Resto de piezas: viabilidad de plazo no comprobada (sin plazo aportado).
  Riesgos y confirmaciones:
    - Plazos de la alfombra (posible pieza a medida) y de las cortinas (confección).
    - Si los cierres por festividades de diciembre y enero afectan a los plazos (preguntar a los proveedores).

ESPECIFICACIONES POR VERIFICAR

  MOB-01: reacción al fuego, abrasión (método y ciclos; double rubs si la ficha usa ese método, sin equiparar métodos), código de limpieza, resistencia a enganches. Pendiente de ficha.
  MOB-02 y MOB-03: resistencia del acabado al rayado y a las manchas, estabilidad. Pendiente. Cantos redondeados: no se exigen por falta de menores; el interiorista decide.
  MOB-04: si van tapizadas, lo mismo que MOB-01. Si no, acabado y estabilidad. Pendiente.
  MOB-05: estabilidad y anclaje. Verificación en obra pendiente.
  ILU-01: documentación de seguridad eléctrica y estabilidad. Pendiente.
  TEX-01: reacción al fuego, limpieza, resistencia al deslizamiento o base antideslizante, comportamiento ante arañazos. Pendiente.
  TEX-02: reacción al fuego, limpieza, solidez a la luz. Pendiente.
  Reacción al fuego y seguridad: el interiorista confirma las exigencias según el uso y la normativa local, y la documentación que las acredita.

PREGUNTAS PARA EL CLIENTE

  1. Reparto: ¿hay asignaciones por pieza o autorizan que propongamos un reparto de los 18.000 €?
  2. TEX-01: ¿el margen de 40 cm se aplica a toda la estancia o solo a la zona de estar?
  3. MOB-01: ¿medidas máximas, orientación de la chaise, preferencia de tejido dado el gato (lino por confirmar)?
  4. MOB-02, MOB-03, ILU-01: ¿medidas o criterios dimensionales (ancho por comensal, holguras, alturas)?
  5. MOB-04: ¿sillas tapizadas o no?
  6. MOB-05: ¿medidas, ubicación, y si necesita traslado, restauración o anclaje? ¿Con qué coste?
  7. TEX-02: ¿altura de las ventanas, tipo y posición de la barra o riel, sobrepaso, fruncido, nº de paños? ¿Instalación incluida?
  8. Plazos: ¿margen de seguridad acordado? ¿Los 10–12 semanas incluyen transporte y montaje? ¿Plazos de las demás piezas?
  9. Accesos: ¿dimensiones de portal, ascensor, escalera y puertas?
  10. Interiorista: decidir sobre la compatibilidad del lino con el gato, sin recurrir al terciopelo.

Antes de enviar o firmar, revisar references/checklist.md. Las medidas en obra, la circulación, los anclajes, las fichas técnicas, los costes y los plazos debe verificarlos el profesional responsable.

