# Transcript — skill interior-designers-ffe-schedule [es] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:41:23+00:00
- duration_s: 89.9
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 97ac72d08175cf5ad204a1273025ff85553bbb55a79fbac8d5aba375b13dd779
- skill_sha256: e3d41b0872712d66b53d1bc3c09d5899a1167547200f4e8eee8a27c75ea71419

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: interior-designers-ffe-schedule
description: "Úsala cuando pegues el briefing de una estancia para obtener un listado FF&E con medidas, partidas estimadas, fecha de pedido y requisitos por verificar."
---
# Del briefing al listado de mobiliario (FF&E)

## Qué hace

Convierte el briefing de una estancia en un listado de mobiliario, accesorios y equipamiento para revisión profesional. Recoge las piezas solicitadas y existentes, calcula medidas cuando hay datos suficientes y distribuye el presupuesto en partidas estimadas. Contrasta los plazos aportados con la fecha de montaje y separa los requisitos por verificar de las prestaciones documentadas.

## Qué necesita

- País, localidad, tipo de estancia y uso previsto.
- Medidas de la estancia, pasos, accesos y piezas existentes, con unidades.
- Piezas solicitadas, cantidades y piezas existentes que se conservarán.
- Usuarios, necesidades de movilidad, menores y mascotas, sin identificadores personales.
- Gustos y rechazos de materiales, acabados, colores o estilos.
- Presupuesto total, moneda, IVA y alcance: adquisición, transporte, montaje e intervenciones.
- Asignaciones, prioridades o pesos de reparto, si existen.
- Fecha de montaje y plazos aportados por pieza; indicar días naturales o laborables y qué incluyen.
- Márgenes o criterios dimensionales necesarios para calcular medidas objetivo.

Pregunta por los datos ausentes en una sola ronda. Si el usuario pide avanzar, señala «FALTA» y reúne las ausencias en Preguntas para el cliente; no inventes datos. Las estimaciones de reparto son propuestas explícitas, no precios de mercado.

## Procedimiento

1. Comprueba que el material esté desidentificado y que las herramientas estén aprobadas por el estudio. Si contiene identificadores, pide una versión anonimizada antes de procesarlo con herramientas externas.
2. Copia exactamente cifras, unidades, fechas y formato monetario del briefing. Separa datos aportados, cálculos y pendientes. No conviertas divisas ni unidades sin autorización, salvo la conversión de plazos necesaria y explicada.
3. Crea un inventario con un código único por pieza o grupo idéntico. Comprueba que cada elemento solicitado y existente tenga fila; si una pieza existente cubre una solicitud, vincúlalas sin duplicar la cantidad.
4. Marca cada fila como «nueva» o «existente-reutilizar». Si la conservación no está confirmada, añade «reutilización por confirmar»; no la presentes como aprobada.
5. Copia los rechazos bajo «Excluido por indicación del cliente» y elimínalos de todas las propuestas de materiales, acabados y alternativas. Si chocan con una pieza solicitada o existente, conserva la necesidad en la tabla, señala el conflicto y pregunta; no recomiendes lo rechazado.
6. Incluye cantidad y medida objetivo en cada fila, o «FALTA». Para medidas derivadas, muestra fórmula, datos y resultado con unidades: alfombra (ES) / tapete (MX) = (largo − 2 × margen) × (ancho − 2 × margen). No supongas márgenes ni tamaños.
7. Vincula usuarios y mascotas con requisitos en las filas afectadas: limpieza del tejido, resistencia al uso previsto o cantos redondeados, según proceda. Escribe «por verificar», nunca una promesa de prestaciones.
8. Repite el presupuesto total exactamente como lo dio el cliente. Indica siempre «con IVA», «sin IVA» o «IVA: no indicado», también para las partidas; permite una nota común explícita. Pregunta si falta el dato y no calcules impuestos.
9. Define las filas que consumen presupuesto: adquisiciones nuevas e intervenciones declaradas en piezas existentes. Incluye transporte y montaje como partidas auxiliares si forman parte del total; si su alcance no está claro, señala que el reparto es provisional y que deberán incorporarse antes de aprobarlo.
10. Rellena siempre las partidas mediante un reparto proporcional del total indicado:
    - Usa los pesos numéricos del cliente. Si aporta importes por pieza, úsalos como pesos y muestra si normalizarlos al total altera su distribución; no lo ocultes.
    - Sin pesos numéricos, usa las cantidades conocidas de todas las filas presupuestables, incluidas las intervenciones. Si faltan cantidades o hay partidas auxiliares no comparables, propón peso 1 por fila, explícitamente como criterio provisional de reparto, no como cantidad.
    - No conviertas prioridades cualitativas en pesos numéricos sin confirmación.
    - Calcula cada partida = total × peso de la fila ÷ suma de pesos; muestra la operación por código.
11. Etiqueta cada partida «partida estimada — confirmar con presupuestos»; en México aclara «presupuestos: cotizaciones». Nunca dejes celdas vacías ni escribas «ninguna». Si falta el total, escribe «FALTA total — partida estimada pendiente de cálculo» y pregunta; no inventes importes.
12. En reutilización, indica adquisición 0 solo si consta que la pieza pertenece al cliente. Separa las intervenciones y otros costes; no supongas que reutilizar es gratuito. El cero también lleva la etiqueta de partida estimada, con la explicación «sin adquisición; otros costes por confirmar» cuando corresponda.
13. Si no hay filas presupuestables, no dividas entre cero: registra el total como «reserva sin destino confirmado — partida estimada — confirmar con presupuestos» en Control de presupuesto y pregunta por su destino. No inventes compras.
14. Redondea al formato monetario del usuario y ajusta la última partida presupuestable para que la suma coincida con el total; muestra el ajuste. Suma todas las partidas y reservas, calcula total menos suma y declara el alcance incluido, excluido o pendiente. No llames «ahorro» al saldo.
15. Identifica el plazo más largo aportado y sus códigos. Convierte semanas a días naturales solo si esa base está confirmada: semanas × 7. Para días laborables, exige el calendario aplicable; si no se aporta, muestra un cálculo provisional de lunes a viernes, sin festivos, y advierte que debe revisarse.
16. Calcula y muestra una fecha concreta: «Fecha límite de pedido = fecha de montaje − plazo más largo indicado». Escribe la operación con sus datos y resultado en Control de plazos y la fecha en cada fila nueva o con intervención.
    - Esa fecha es una referencia común calculada con los plazos disponibles, no una garantía del proveedor.
    - Para filas sin plazo, añade «plazo no indicado — podría adelantar la fecha de pedido» y pregunta.
    - Si falta la fecha de montaje o no existe ningún plazo utilizable, escribe la fórmula con «FALTA»; no inventes una fecha para completar la tabla.
17. Comprueba si los plazos incluyen transporte y montaje; si no consta, pregunta y marca el cálculo como provisional. Declara una fecha vencida solo si tienes una fecha de referencia fiable y la muestras.
18. Por código, registra los datos que deben contrastarse en fichas técnicas del fabricante: reacción al fuego o inflamabilidad; abrasión, método y ciclos, incluidos double rubs cuando corresponda; códigos de limpieza; resistencia al deslizamiento.
19. Marca cada comprobación como pendiente o «no aplicable» con motivo. Si el usuario aporta documentación, identifica su procedencia y deja la validación al profesional; no presentes una clasificación como hecho certificado ni equipares métodos de ensayo.
20. Antes de emitir, coteja inventario y tabla; rechazos y propuestas; usuarios y requisitos; total y suma; IVA; y fecha de pedido con su cálculo. Comprueba que no haya partidas vacías. Emite las seis secciones siguientes en orden y reúne todas las ausencias y decisiones pendientes en la última.

## Formato de salida

```markdown
## Intención de diseño
- Estancia, uso, ubicación y criterios del briefing: …
- Usuarios / mascotas y requisitos asociados: …
- Excluido por indicación del cliente: …
- Conflictos y supuestos de reparto pendientes de aprobación: …

## Listado FF&E
| Código | Pieza | Cant. | Medida objetivo y cálculo | Material / uso: requisitos por verificar | Partida estimada e IVA | Plazo / fecha límite de pedido | Estado |
|---|---|---|---|---|---|---|---|
| … | … | … | … | … | importe — partida estimada — confirmar con presupuestos | plazo aportado; fecha calculada; pendientes | nueva / existente-reutilizar |

## Control de presupuesto
- Total del cliente: …; con IVA / sin IVA / IVA: no indicado.
- Base proporcional y pesos: …; criterio provisional o aportado por el cliente: …
- Por código: total × peso ÷ suma de pesos = partida estimada — confirmar con presupuestos.
- En MX, presupuestos significa cotizaciones.
- Ajuste de redondeo: …; partidas auxiliares o reserva, si proceden: …
- Suma mostrada: …; total menos suma: …
- Transporte, montaje e intervenciones: incluidos / excluidos / pendientes.

## Control de plazos
- Montaje: …; plazo más largo indicado y códigos: …
- Conversión y calendario utilizado: …
- Fecha límite de pedido = [montaje] − [plazo más largo] = [fecha concreta].
- Plazos ausentes, alcance y calendario por confirmar: …

## Especificaciones por verificar
- [Código]: reacción al fuego, abrasión y método, códigos de limpieza, deslizamiento.
- Para cada comprobación: documento necesario; pendiente / no aplicable con motivo.
- El interiorista responsable confirma las exigencias locales de uso y seguridad.

## Preguntas para el cliente
1. [Código o asunto]: dato ausente, alcance, conflicto o decisión pendiente.
```

## Límites

- No inventes productos, modelos, precios comerciales, plazos, fechas de proveedor, clasificaciones, estadísticas, leyes, artículos, organismos ni enlaces. Las fechas calculadas deben derivarse de datos aportados; las del ejemplo son ficticias.
- No presentes repartos como ofertas, requisitos como prestaciones garantizadas ni el listado como certificación de cumplimiento o autorización de instalación.
- El profesional responsable, habilitado cuando corresponda en la jurisdicción, debe verificar medidas en obra, circulación, accesos, estabilidad, anclajes, materiales, fichas técnicas, presupuestos o cotizaciones, IVA y plazos antes de aprobar compras o instalación.
- Las exigencias de reacción al fuego y seguridad dependen del uso y la normativa local: el interiorista responsable confirma las exigencias aplicables y su acreditación.
- No se ha verificado orientación oficial específica sobre IA para interioristas en España ni en México. Consulta con tu colegio profesional o autoridad competente las obligaciones aplicables; no añadas citas oficiales no verificadas.
- Privacidad: elimina nombres, domicilios, contactos e identificadores en imágenes y planos; utiliza solo los datos mínimos y herramientas aprobadas por el estudio. No envíes información identificable a servicios no autorizados.
- Antes de enviar o firmar, consulta references/checklist.md.

## Ejemplo

Entrada ficticia:
```text
Proyecto Muestra, ES: salón de 5 × 4 m; familia con gato; se pide avanzar con pendientes.
1 sofá y 1 alfombra nuevos; conservar 1 butaca propia, sin intervención; rechazo: lino.
Margen de alfombra: 0,5 m por lado; medidas del sofá y butaca pendientes.
Total: 4.000 € con IVA para adquisiciones; transporte y montaje excluidos.
Montaje: 15/03/2027; plazos hasta entrega: sofá 10 semanas, alfombra 4, de días naturales.
```

Salida abreviada; etiquetas de partidas e IVA se muestran conjuntamente:
```text
Intención de diseño
Familia con gato; lino excluido de las propuestas.
Listado FF&E
MOB-01 | Sofá | 1 | FALTA medida | Tejido limpiable: verificar | 2.000 € | 10 semanas; pedir 04/01/2027 | nueva.
TEX-01 | Alfombra | 1 | (5 − 2 × 0,5) × (4 − 2 × 0,5) = 4 × 3 m | Limpieza y uso con gato: verificar | 2.000 € | 4 semanas; pedir 04/01/2027 | nueva.
MOB-02 | Butaca propia | 1 | FALTA medida | Limpieza y estabilidad: verificar | 0 € adquisición | Sin pedido; montaje por confirmar | existente-reutilizar.
Control de presupuesto
Total: 4.000 € con IVA; cada importe es «partida estimada — confirmar con presupuestos», con IVA. Nuevas: 4.000 × 1 ÷ 2 = 2.000 € cada una; suma 2.000 + 2.000 + 0 = 4.000 €; saldo 0 €; sin ajuste; transporte y montaje excluidos.
Control de plazos
MOB-01: 10 × 7 = 70 días naturales; fecha límite de pedido = 15/03/2027 − 70 días = 04/01/2027; coordinación del montaje pendiente.
Especificaciones por verificar
Todas: fuego, abrasión y método, limpieza; TEX-01: deslizamiento; en asientos, deslizamiento no aplicable como revestimiento de suelo. Fichas pendientes; exigencias locales a confirmar por el interiorista.
Preguntas para el cliente
¿Localidad, medidas de sofá y butaca y accesos? ¿Se aprueba el reparto? ¿Quién coordina entrega y montaje?
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

Material: cliente marcado como ficticio y sin identificadores; se procesa tal cual. Los datos ausentes se marcan FALTA y se reúnen al final en una sola ronda de preguntas.

INTENCIÓN DE DISEÑO
- Estancia: salón-comedor, Madrid (ES), 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho. Uso: estar y comedor para 6.
- Usuarios / mascotas: pareja y un gato que araña. Requisito ligado a todas las piezas tapizadas y textiles (MOB-01, MOB-04, TEX-01, TEX-02): resistencia al arañazo y limpieza del tejido, por verificar en ficha técnica.
- Preferencias: roble claro, lino.
- Excluido por indicación del cliente: blanco puro, terciopelo. Eliminados de todas las propuestas y alternativas.
- Conflictos y supuestos pendientes de aprobación:
  - Lino (gusto) frente a gato que araña: la idoneidad del lino en superficies tapizadas debe verificarse con fichas técnicas antes de proponerlo en MOB-01 y MOB-04; no se descarta, se señala.
  - Reparto presupuestario con peso 1 por fila (criterio provisional, no cantidad).
  - Alfombra: el margen de 40 cm se ha aplicado a la estancia completa por ser el único dato disponible; confirmar si se refiere a la zona de estar.

LISTADO FF&E
(Partidas: importe — partida estimada — confirmar con presupuestos — con IVA. Fecha límite de pedido común calculada: 07/12/2026, provisional.)

MOB-01 | Sofá 3 plazas con chaise longue | 1 | Medida: FALTA (sin criterio dimensional ni orientación del chaise) | Tejido: resistencia al arañazo, limpieza; excluidos blanco puro y terciopelo | 2.000 € | 10–12 semanas (tapicería, proveedores del estudio); pedir antes del 07/12/2026; base de días y alcance por confirmar | nueva

MOB-02 | Mesa de centro | 1 | Medida: FALTA (depende de MOB-01) | Roble claro posible; cantos y acabado limpiable por verificar | 2.000 € | plazo no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 | nueva

MOB-03 | Mesa de comedor para 6 | 1 | Medida: FALTA (sin criterio de plaza por comensal ni paso alrededor) | Roble claro posible; acabado por verificar | 2.000 € | plazo no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 | nueva

MOB-04 | Sillas de comedor | 6 | Medida: FALTA (coordinar con altura de MOB-03) | Si tapizadas: aplica plazo de tapicería y requisitos de arañazo/limpieza; excluidos blanco puro y terciopelo | 2.000 € (6 ud.) | 10–12 semanas si son tapizadas, por confirmar; referencia 07/12/2026 | nueva

ILU-01 | Lámparas de pie | 2 | Medida: FALTA (altura y diámetro) | Estabilidad frente a gato (base, cable) por verificar | 2.000 € (2 ud.) | plazo no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 | nueva

TEX-01 | Alfombra | 1 | (6,4 − 2 × 0,4) × (5,0 − 2 × 0,4) = 5,6 m × 4,2 m, si el margen se refiere a la estancia completa; FALTA confirmar zona | Fibra y densidad resistentes al arañazo, limpieza, antideslizante por verificar; excluido blanco puro | 2.000 € | plazo no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 | nueva

TEX-02 | Cortinas | 2 ventanas de 1,8 m | Medida: FALTA (altura de ventana, altura de colgado, fruncido, sistema de barra/riel) | Lino posible en cortina si se verifica frente a gato; excluido blanco puro; limpieza por verificar | 2.000 € (2 ud.) | plazo no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 | nueva

MOB-05 | Aparador de roble | 1 | Medida: FALTA (necesaria para distribución) | Sin intervención declarada; estabilidad y anclaje por verificar | 0 € adquisición — partida estimada — confirmar con presupuestos — con IVA; sin adquisición, propiedad del cliente por confirmar, otros costes por confirmar | sin pedido; reubicación en montaje por confirmar | existente-reutilizar

AUX-01 | Transporte | — | no aplica | — | 2.000 € | alcance por confirmar | partida auxiliar
AUX-02 | Montaje | — | no aplica | — | 2.000 € | 01/03/2027 | partida auxiliar

CONTROL DE PRESUPUESTO
- Total del cliente: 18.000 € IVA incluido (con IVA), transporte y montaje incluidos.
- Base proporcional: sin pesos numéricos del cliente. Hay partidas auxiliares (transporte, montaje) no comparables por cantidad, por lo que se propone peso 1 por fila presupuestable como criterio provisional de reparto, no como cantidad. Filas con peso: MOB-01, MOB-02, MOB-03, MOB-04, ILU-01, TEX-01, TEX-02, AUX-01, AUX-02 = 9 filas; suma de pesos 9. MOB-05 peso 0 (sin adquisición ni intervención declarada).
- Por código: 18.000 × 1 ÷ 9 = 2.000 € — partida estimada — confirmar con presupuestos — con IVA (igual para los nueve códigos).
- Ajuste de redondeo: ninguno necesario (9 × 2.000 = 18.000). Reserva: no procede.
- Suma mostrada: 2.000 × 9 + 0 (MOB-05) = 18.000 €; total menos suma: 0 €.
- Transporte y montaje: incluidos en el total, importe no desglosado por el cliente; el reparto es provisional hasta disponer de sus presupuestos. Intervenciones en MOB-05: no declaradas.
- Alternativa pendiente de aprobación: usar cantidades como pesos (6 sillas, 2 lámparas, 2 cortinas) alteraría la distribución; no se aplica sin confirmación.

CONTROL DE PLAZOS
- Montaje: 01/03/2027. Plazo más largo indicado: 12 semanas (tapicería), aplicable a MOB-01 y a MOB-04 si son tapizadas.
- Conversión: 12 semanas × 7 = 84 días naturales. El cliente no indica si la base es natural o laborable. Cálculo provisional lunes a viernes sin festivos: 60 días laborables = misma fecha; con festivos de diciembre–enero (Madrid) la fecha se adelantaría. Debe revisarse con el calendario del proveedor.
- Fecha límite de pedido = 01/03/2027 − 84 días naturales = 07/12/2026 (provisional). Con 10 semanas: 01/03/2027 − 70 días = 21/12/2026; se usa el plazo largo como referencia común.
- No consta si las 10–12 semanas incluyen transporte y montaje; de no incluirlos, la fecha se adelanta. Fecha de referencia actual 20/10/2026: la fecha límite no está vencida.
- Plazos ausentes: MOB-02, MOB-03, ILU-01, TEX-01, TEX-02 — podrían adelantar la fecha de pedido.

ESPECIFICACIONES POR VERIFICAR
- MOB-01, MOB-04 (tejido tapizado): reacción al fuego del tejido y relleno; abrasión con método y ciclos (Martindale o double rubs según origen); código de limpieza; deslizamiento no aplicable (no es revestimiento de suelo). Pendiente: fichas técnicas del fabricante.
- TEX-02: reacción al fuego, código de limpieza; abrasión y deslizamiento no aplicables (cortina). Pendiente.
- TEX-01: reacción al fuego, resistencia al deslizamiento (o base antideslizante), limpieza, abrasión de la fibra. Pendiente.
- MOB-02, MOB-03, MOB-05 (madera): limpieza y resistencia del acabado; abrasión textil y deslizamiento no aplicables; fuego pendiente según exigencia local. Pendiente.
- ILU-01: abrasión, limpieza y deslizamiento no aplicables; reacción al fuego de pantalla y estabilidad pendientes; conformidad eléctrica a verificar por el profesional.
- El interiorista responsable confirma las exigencias locales de uso y seguridad aplicables a vivienda en Madrid; nada de lo anterior es clasificación certificada.

PREGUNTAS PARA EL CLIENTE
1. MOB-01: medidas objetivo (largo, fondo, altura), lado del chaise y accesos (puerta, ascensor, escalera).
2. MOB-03/MOB-04: medidas objetivo, forma de la mesa y si las sillas son tapizadas (afecta al plazo y a los requisitos frente al gato).
3. MOB-02, ILU-01: criterios dimensionales.
4. TEX-01: ¿el margen de 40 cm se refiere a la estancia completa (5,6 × 4,2 m) o a la zona de estar? Si es la zona de estar, indicar sus medidas.
5. TEX-02: altura de ventana, altura de colgado, fruncido, sistema de sujeción y si ya existe barra o riel.
6. MOB-05: medidas del aparador, confirmación de propiedad y de que no requiere intervención; ubicación prevista.
7. Lino: ¿se mantiene como opción en tapicería pese al gato, condicionado a fichas técnicas, o se reserva solo para cortinas?
8. Presupuesto: ¿se aprueba el reparto con peso 1 por fila o se prefieren pesos/prioridades? ¿Hay importe estimado para transporte y montaje?
9. Plazos: ¿las 10–12 semanas son días naturales o laborables, e incluyen transporte y montaje? Plazos de alfombra, cortinas, mesas y lámparas.
10. Montaje: ¿quién coordina entrega y montaje el 01/03/2027 y hay restricciones de horario o acceso en la finca?

