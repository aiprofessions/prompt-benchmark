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
