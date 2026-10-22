# Transcript — skill interior-designers-ffe-schedule [es] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:03:06+00:00
- duration_s: 90.8
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

INTENCIÓN DE DISEÑO

  Estancia, uso, ubicación y criterios del briefing:
    Salón-comedor, Madrid (España). 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho.
    Uso residencial: estar y comedor para 6.
    Gustos: roble claro, lino.
    Pieza existente: aparador de roble, se conserva.

  Usuarios / mascotas y requisitos asociados:
    Pareja (2 adultos) y un gato que araña. Esto afecta a:
      Tapicerías (MOB-01, MOB-04 si son tapizadas): resistencia a arañazos y enganches, por verificar.
      Alfombra (TEX-01): resistencia al uso con gato y limpieza, por verificar.
      Cortinas (TEX-02): resistencia a enganches y limpieza, por verificar.
      Lámparas de pie (ILU-01): estabilidad frente a vuelco, por verificar.

  Excluido por indicación del cliente:
    Blanco puro (en tejidos, acabados y pintura de todas las piezas).
    Terciopelo (en tapicerías, cortinas y alfombra).

  Conflictos y supuestos de reparto pendientes de aprobación:
    Lino frente a gato que araña. El lino es un gusto del cliente, no un rechazo. Su comportamiento ante arañazos en tapicería debe verificarse antes de proponerlo para el sofá o las sillas. Opciones a decidir: limitar el lino a las cortinas o confirmar un tejido concreto con ficha técnica. El terciopelo no se propone como alternativa.
    Alfombra. Se calcula sobre la estancia completa, pero en un salón-comedor podría corresponder solo a la zona de estar. Pendiente de confirmar.
    Reparto. Se usa peso 1 por fila como criterio provisional, no como estimación de mercado. Pendiente de aprobación.

LISTADO FF&E

  MOB-01 | Sofá 3 plazas con chaise longue | Cant. 1
    Medida objetivo: FALTA. También falta el lado de la chaise (izquierda o derecha).
    Material / uso: tapicería resistente a arañazos y limpiable, por verificar. Lino por confirmar (ver conflicto). Sin terciopelo ni blanco puro. Patas en roble claro, si procede.
    Partida: 2.000 € con IVA — partida estimada — confirmar con presupuestos.
    Plazo: tapicería 10–12 semanas (base de días no indicada). Fecha límite de pedido: 07/12/2026, provisional.
    Estado: nueva.

  TEX-01 | Alfombra | Cant. 1
    Medida objetivo, provisional si se refiere a la estancia completa:
      (6,4 m − 2 × 0,40 m) × (5,0 m − 2 × 0,40 m) = 5,6 m × 4,2 m.
      Los 40 cm del briefing se expresan como 0,40 m solo para operar.
      Si se limita a la zona de estar: FALTA medida de esa zona.
    Material / uso: limpieza y resistencia al uso con gato, por verificar. Sin terciopelo ni blanco puro.
    Partida: 2.000 € con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Referencia común: 07/12/2026.
    Estado: nueva.

  MOB-02 | Mesa de centro | Cant. 1
    Medida objetivo: FALTA.
    Material / uso: roble claro según gusto. Resistencia al rayado y limpieza del acabado, por verificar.
    Partida: 2.000 € con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Referencia: 07/12/2026.
    Estado: nueva.

  MOB-03 | Mesa de comedor para 6 | Cant. 1
    Medida objetivo: FALTA. No se ha indicado criterio de medida por comensal ni de paso perimetral.
    Material / uso: roble claro según gusto. Resistencia al rayado y limpieza del acabado, por verificar.
    Partida: 2.000 € con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Referencia: 07/12/2026.
    Estado: nueva.

  MOB-04 | Silla de comedor | Cant. 6
    Medida objetivo: FALTA.
    Material / uso: si son tapizadas, resistencia a arañazos y limpieza, por verificar. Estructura en roble claro, si procede.
    Partida: 2.000 € con IVA para las 6 — partida estimada — confirmar con presupuestos.
    Plazo: no indicado. Si son tapizadas, podría aplicarse el plazo de tapicería de 10–12 semanas. Referencia: 07/12/2026.
    Estado: nueva.

  ILU-01 | Lámpara de pie | Cant. 2
    Medida objetivo: FALTA.
    Material / uso: estabilidad frente a vuelco por el gato y documentación eléctrica del fabricante, por verificar. Sin blanco puro.
    Partida: 2.000 € con IVA para las 2 — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Referencia: 07/12/2026.
    Estado: nueva.

  TEX-02 | Cortinas para 2 ventanas | Cant. 2 ventanas (número de paños: FALTA)
    Medida objetivo: FALTA. Dato aportado: 1,8 m de ancho por ventana. Faltan altura de colocación, sistema (riel o barra), sobreancho y frunce. No se suponen.
    Material / uso: lino posible según gusto. Resistencia a enganches del gato y limpieza, por verificar. Sin terciopelo ni blanco puro.
    Partida: 2.000 € con IVA — partida estimada — confirmar con presupuestos. Falta aclarar si incluye rieles o barras.
    Plazo: no indicado. Si es confección tapizada o a medida, confirmar plazo. Referencia: 07/12/2026.
    Estado: nueva.

  AUX-01 | Transporte | Cant. 1 partida
    Medida objetivo: no aplicable.
    Material / uso: comprobar accesos de la vivienda (puerta, pasillos, escalera o ascensor) para el sofá con chaise y la mesa. FALTA.
    Partida: 2.000 € con IVA — partida estimada — confirmar con presupuestos.
    Plazo: coordinar con el montaje del 01/03/2027. Plazo de reserva no indicado.
    Estado: nueva (servicio).

  AUX-02 | Montaje | Cant. 1 partida
    Medida objetivo: no aplicable.
    Material / uso: falta concretar el alcance (montaje de muebles, cortinas, anclajes).
    Partida: 2.000 € con IVA — partida estimada — confirmar con presupuestos.
    Plazo: montaje 01/03/2027.
    Estado: nueva (servicio).

  MOB-05 | Aparador de roble | Cant. 1
    Medida objetivo: FALTA. Hace falta para planificar la distribución.
    Material / uso: limpieza y estabilidad, por verificar.
    Partida: adquisición 0 € con IVA, provisional. No consta expresamente que sea propiedad del cliente. No hay intervención declarada; otros costes, por confirmar. Partida estimada — confirmar con presupuestos.
    Plazo: sin pedido. Falta saber si requiere traslado o recolocación en el montaje.
    Estado: existente-reutilizar. La conservación está confirmada en el briefing.

CONTROL DE PRESUPUESTO

  Total del cliente: 18.000 € IVA incluido, con transporte y montaje. Todas las partidas se expresan con IVA (nota común).

  Base proporcional y pesos:
    No hay pesos numéricos.
    Las partidas auxiliares no son comparables y faltan cantidades (paños de cortina).
    Criterio provisional: peso 1 por fila presupuestable, 9 filas.
    No refleja el coste relativo real: por ejemplo, el sofá y las 6 sillas reciben lo mismo que una lámpara. Hace falta que el cliente indique pesos.

  Cálculo por código:
    MOB-01, TEX-01, MOB-02, MOB-03, MOB-04, ILU-01, TEX-02, AUX-01, AUX-02:
    18.000 × 1 ÷ 9 = 2.000 € cada uno — partida estimada — confirmar con presupuestos.
    MOB-05: 0 € de adquisición (fuera del reparto, titularidad por confirmar).

  Ajuste de redondeo: no necesario.

  Suma: 9 × 2.000 + 0 = 18.000 €. Total menos suma: 0 €.

  Alcance:
    Incluidos: adquisiciones, transporte y montaje.
    Pendientes: rieles o barras de cortina, retirada de embalajes, recolocación del aparador y posibles intervenciones.

CONTROL DE PLAZOS

  Montaje: 01/03/2027.
  Plazo más largo indicado: tapicería, 12 semanas (extremo superior de 10–12). Aplica a MOB-01 y, si es tapizado, a MOB-04.

  Conversión y calendario:
    El briefing no indica si son días naturales o laborables.
    Si son naturales: 12 × 7 = 84 días.
    Si son laborables (cálculo provisional de lunes a viernes, sin festivos): 12 × 5 = 60 días laborables. Desde el lunes 01/03/2027 lleva a la misma fecha.
    Con los festivos de Navidad y del calendario de Madrid aplicable, la fecha laborable se adelantaría. Hace falta ese calendario.

  Fecha límite de pedido = 01/03/2027 − 84 días naturales = 07/12/2026 (lunes).
    Es una referencia común calculada, no una garantía del proveedor.
    Con 10 semanas sería el 21/12/2026. Se usa el plazo más largo.
    Respecto a la fecha del sistema (19/10/2026), quedan 49 días. No está vencida.

  Por confirmar:
    Si las 10–12 semanas incluyen transporte y montaje. El cálculo es provisional hasta saberlo.
    Plazos de TEX-01, MOB-02, MOB-03, MOB-04, ILU-01 y TEX-02. Cualquiera mayor de 12 semanas adelantaría la fecha.

ESPECIFICACIONES POR VERIFICAR
(Documento necesario en todos los casos: ficha técnica del fabricante. Todas las comprobaciones están pendientes salvo que se indique.)

  MOB-01: reacción al fuego o inflamabilidad del tejido y del relleno, pendiente. Abrasión con método y ciclos (Martindale o double rubs; no son equiparables), pendiente. Código de limpieza, pendiente. Resistencia a enganches o arañazos, pendiente. Deslizamiento: no aplicable, no es revestimiento de suelo.
  TEX-01: reacción al fuego, abrasión o resistencia al uso, código de limpieza, pendientes. Deslizamiento de la alfombra y de la base o antideslizante, pendiente.
  MOB-02 y MOB-03: reacción al fuego, pendiente según exigencia aplicable. Resistencia del acabado al rayado y limpieza, pendiente. Abrasión textil: no aplicable, sin tapizado. Deslizamiento: no aplicable.
  MOB-04: si son tapizadas, fuego, abrasión con método y ciclos, y limpieza, pendientes. Si no lo son, abrasión textil no aplicable. Deslizamiento: no aplicable.
  ILU-01: documentación eléctrica y de estabilidad, pendiente. Fuego, pendiente según materiales de la pantalla. Abrasión y deslizamiento: no aplicables.
  TEX-02: reacción al fuego, pendiente. Código de limpieza y comportamiento al lavado (encogimiento del lino), pendiente. Abrasión: no aplicable, no hay rozamiento de uso como asiento. Deslizamiento: no aplicable.
  MOB-05: limpieza y estabilidad, pendientes. Fuego, abrasión y deslizamiento: no aplicables, es pieza existente sin intervención.

  El interiorista responsable confirma las exigencias locales de uso y seguridad y su acreditación.

PREGUNTAS PARA EL CLIENTE

  1. Accesos: medidas de la puerta de entrada, pasillos, escalera o ascensor. Posición de puertas, ventanas y huecos en planta.
  2. MOB-01: medidas objetivo o espacio disponible, y lado de la chaise.
  3. MOB-01 y MOB-04: con el gato que araña, ¿se mantiene el lino como opción de tapicería o se reserva para las cortinas? ¿Las sillas son tapizadas?
  4. TEX-01: ¿los 40 cm se miden respecto a toda la estancia (resultado 5,6 × 4,2 m) o solo a la zona de estar? Si es la zona de estar, ¿qué medidas tiene?
  5. MOB-02, MOB-03, ILU-01, MOB-05: medidas o criterios dimensionales (por ejemplo, ancho por comensal y paso alrededor de la mesa).
  6. TEX-02: altura de colocación, riel o barra (¿incluido en la partida?), número de paños, sobreancho y frunce, opacidad.
  7. Presupuesto: ¿pesos o prioridades numéricas por pieza? El reparto a partes iguales es solo provisional.
  8. Alcance de transporte y montaje: ¿incluye instalación de cortinas, anclajes, retirada de embalajes y recolocación del aparador?
  9. MOB-05: ¿confirmáis que el aparador es propiedad del cliente? ¿Requiere alguna intervención (restauración, ajuste)?
  10. Plazos: ¿las 10–12 semanas son días naturales o laborables? ¿Incluyen transporte y montaje? ¿Qué plazos tienen el resto de piezas? Si son laborables, ¿qué calendario de festivos aplica?

Antes de enviar o firmar, revisa el checklist del estudio (references/checklist.md). Las medidas, fichas técnicas, presupuestos y plazos deben verificarse en obra y con proveedores antes de aprobar compras.

