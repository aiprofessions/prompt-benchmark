# Transcript — skill interior-designers-ffe-schedule [es] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:10:10+00:00
- duration_s: 88.3
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

LISTADO FF&E: SALÓN-COMEDOR, PROYECTO "PAREJA EJEMPLO" (FICTICIO)
Borrador para revisión profesional. Avanzo con los datos aportados; lo que falta se marca como FALTA y se reúne en el apartado 6.

1. INTENCIÓN DE DISEÑO

  Estancia, uso y ubicación
  - Salón-comedor de vivienda en Madrid, España.
  - Dimensiones: 5,0 m × 6,4 m; techo de 2,70 m.
  - Dos ventanas de 1,8 m de ancho cada una.
  - Uso de estar y comedor para 6 comensales.

  Preferencias del cliente
  - Le gustan el roble claro y el lino.
  - Se conserva el aparador de roble existente. Hay que coordinar el tono con el roble claro (acabado del aparador por confirmar).

  Usuarios y requisitos asociados
  - Pareja adulta y un gato que araña.
  - Requisitos por verificar en la ficha técnica y con muestras:
      resistencia a arañazos y enganches en sofá, sillas tapizadas, cortinas y alfombra;
      limpieza de textiles;
      estabilidad frente a vuelco en lámparas de pie y aparador.
  - No se indican necesidades de movilidad ni menores.

  Excluido por indicación del cliente
  - Blanco puro.
  - Terciopelo.
  Ambos quedan fuera de todas las propuestas de tejidos, acabados y alternativas.

  Conflictos y supuestos pendientes de aprobación
  - Lino con gato que araña: no es un rechazo. Su comportamiento frente a arañazos debe verificarse en la ficha técnica y con muestras antes de especificarlo en asientos o cortinas.
  - Alfombra: el margen de 40 cm se ha aplicado a toda la estancia, porque es lo que indica el briefing. Esa alfombra cubriría también la zona de comedor; hay que confirmar si se refiere a la estancia completa o solo a la zona de estar.
  - Reparto del presupuesto: el criterio de peso 1 por fila es provisional y requiere aprobación (ver apartado 3).
  - Plazos: no consta si son días naturales o laborables. El cálculo es provisional (ver apartado 4).

2. LISTADO FF&E

  MOB-01 · Sofá de 3 plazas con chaise longue
    Cantidad: 1
    Medida objetivo: FALTA (medidas y lado de la chaise no indicados)
    Material y uso, por verificar:
      tapicería resistente a arañazos;
      tejido limpiable;
      lino según preferencia, condicionado a esa verificación;
      sin terciopelo ni blanco puro.
    Partida: 2.000 € con IVA. Partida estimada, confirmar con presupuestos.
    Plazo: tapicería 10–12 semanas (aportado). Fecha límite de pedido: 07/12/2026 (provisional).
    Estado: nueva

  MOB-02 · Mesa de centro
    Cantidad: 1
    Medida objetivo: FALTA
    Material y uso, por verificar:
      roble claro según preferencia;
      cantos y acabado frente a arañazos, por verificar.
    Partida: 2.000 € con IVA. Partida estimada, confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha de referencia: 07/12/2026.
    Estado: nueva

  MOB-03 · Mesa de comedor para 6
    Cantidad: 1
    Medida objetivo: FALTA (no hay medidas ni criterio dimensional por comensal)
    Material y uso, por verificar:
      roble claro;
      acabado resistente al uso de comedor, por verificar.
    Partida: 2.000 € con IVA. Partida estimada, confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha de referencia: 07/12/2026.
    Estado: nueva

  MOB-04 · Sillas de comedor
    Cantidad: 6
    Medida objetivo: FALTA
    Material y uso, por verificar:
      si van tapizadas, resistencia a arañazos y limpieza;
      sin terciopelo ni blanco puro.
    Partida: 2.000 € con IVA para el grupo completo de 6 unidades. Partida estimada, confirmar con presupuestos.
    Plazo: si van tapizadas, 10–12 semanas (aportado); si no, plazo no indicado. Fecha de referencia: 07/12/2026.
    Estado: nueva

  MOB-05 · Aparador de roble
    Cantidad: 1
    Medida objetivo: FALTA (medidas del existente)
    Material y uso, por verificar:
      estabilidad y anclaje con gato;
      estado del acabado.
    Partida: fuera del reparto.
      No se declaran adquisición ni intervención.
      No consta expresamente la titularidad, así que no se asigna 0 € de adquisición hasta confirmarla.
      Otros costes (traslado, reparación) por confirmar.
    Plazo: sin pedido; intervención no declarada.
    Estado: existente-reutilizar (conservación confirmada por el cliente)

  ILU-01 · Lámparas de pie
    Cantidad: 2
    Medida objetivo: FALTA
    Material y uso, por verificar:
      estabilidad frente a vuelco (gato);
      documentación eléctrica del fabricante.
    Partida: 2.000 € con IVA para el grupo de 2. Partida estimada, confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha de referencia: 07/12/2026.
    Estado: nueva

  TEX-01 · Alfombra
    Cantidad: 1
    Medida objetivo (40 cm = 0,40 m, conversión solo para el cálculo):
      (6,4 − 2 × 0,40) × (5,0 − 2 × 0,40) = 5,6 m × 4,2 m
      Supone que el margen se aplica a toda la estancia (ver pregunta 2).
    Material y uso, por verificar:
      resistencia a arañazos y enganches (evitar fibras que el gato pueda enganchar, por verificar);
      limpieza;
      resistencia al deslizamiento;
      sin blanco puro.
    Partida: 2.000 € con IVA. Partida estimada, confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha de referencia: 07/12/2026.
    Estado: nueva

  TEX-02 · Cortinas
    Cantidad: 2 (una por ventana; número de paños por confirmar)
    Medida objetivo: FALTA
      Ancho de ventana aportado: 1,8 m cada una.
      Faltan el sobreancho, el fruncido, la caída y la altura de colocación (techo 2,70 m).
      No supongo márgenes.
    Material y uso, por verificar:
      lino según preferencia, condicionado a su resistencia a arañazos;
      limpieza;
      reacción al fuego;
      sin terciopelo ni blanco puro.
    Partida: 2.000 € con IVA para ambas. Partida estimada, confirmar con presupuestos.
    Plazo: no indicado (no consta si la confección se incluye en "tapicería"). Fecha de referencia: 07/12/2026.
    Estado: nueva

  AUX-01 · Transporte
    Cantidad: partida auxiliar
    Medida objetivo: no aplicable
    Material y uso: no aplicable
    Partida: 2.000 € con IVA. Partida estimada, confirmar con presupuestos.
    Plazo: no consta si está incluido en los plazos.
    Estado: auxiliar

  AUX-02 · Montaje
    Cantidad: partida auxiliar
    Medida objetivo: no aplicable
    Material y uso: no aplicable
    Partida: 2.000 € con IVA. Partida estimada, confirmar con presupuestos.
    Plazo: montaje el 01/03/2027.
    Estado: auxiliar

3. CONTROL DE PRESUPUESTO

  Total y alcance
  - Total del cliente: 18.000 €, IVA incluido.
  - Incluye transporte y montaje.

  Criterio de reparto
  - El cliente no ha dado pesos numéricos.
  - Hay partidas auxiliares no comparables por cantidad, y la cantidad de cortinas es incierta.
  - Criterio provisional, pendiente de aprobación: peso 1 por fila presupuestable.
  - Filas presupuestables: 9.
      MOB-01, MOB-02, MOB-03, MOB-04, ILU-01, TEX-01, TEX-02, AUX-01 y AUX-02.
      MOB-05 queda fuera porque no se declaran adquisición ni intervención.

  Cálculo por código (las 9 filas dan el mismo resultado)
  - 18.000 × 1 ÷ 9 = 2.000 € con IVA.
  - Cada importe es una partida estimada, a confirmar con presupuestos.

  Advertencia sobre el criterio
  - El peso 1 por fila asigna lo mismo a 6 sillas que a una mesa de centro.
  - Es un criterio de reparto, no una estimación de mercado. Conviene que el cliente fije prioridades o pesos.

  Cuadre
  - Ajuste de redondeo: 0 € (la división es exacta).
  - Suma mostrada: 9 × 2.000 = 18.000 €.
  - Total menos suma: 0 €.

  Alcance
  - Transporte y montaje: incluidos.
  - Intervenciones en el aparador: pendientes (no declaradas).
  - Confección e instalación de cortinas (rieles o barras): pendiente de confirmar si están incluidas.

4. CONTROL DE PLAZOS

  Datos aportados
  - Montaje: 01/03/2027.
  - Plazo más largo indicado: 12 semanas, extremo superior del rango de tapicería 10–12.
  - Códigos afectados: MOB-01 y MOB-04 si las sillas van tapizadas. TEX-02 está por confirmar.

  Conversión (provisional: no consta si los plazos son días naturales o laborables)
  - En días naturales: 12 × 7 = 84 días.
  - En días laborables (lunes a viernes, sin festivos): 60 días.
      Con montaje en lunes, el resultado es la misma fecha.
      Los festivos no están considerados y adelantarían la fecha. Hace falta el calendario aplicable.

  Resultado
  - Fecha límite de pedido = 01/03/2027 − 84 días = 07/12/2026.
  - Es una referencia común calculada con el plazo disponible, no una garantía del proveedor.
  - Con la fecha de la sesión (19/10/2026) como referencia, no está vencida.

  Pendientes
  - Plazos no indicados: MOB-02, MOB-03, ILU-01, TEX-01, TEX-02 y MOB-04 si no va tapizada. Podrían adelantar la fecha.
  - No consta si las 10–12 semanas cuentan hasta la entrega e incluyen transporte y montaje.

5. ESPECIFICACIONES POR VERIFICAR

  Documento necesario en todos los casos: ficha técnica del fabricante. Todas las comprobaciones están pendientes, salvo las marcadas como no aplicables.

  MOB-01 (sofá)
  - Reacción al fuego del tapizado y del relleno.
  - Abrasión: método y ciclos (Martindale o double rubs, sin equipararlos).
  - Código de limpieza.
  - Resistencia a arañazos y enganches.
  - Deslizamiento: no aplicable, no es revestimiento de suelo.

  MOB-02 y MOB-03 (mesas)
  - Reacción al fuego: según el uso, a confirmar por el interiorista.
  - Abrasión y resistencia del acabado de la superficie.
  - Limpieza del acabado.
  - Deslizamiento: no aplicable.

  MOB-04 (sillas)
  - Si van tapizadas: reacción al fuego, abrasión con su método y ciclos, y código de limpieza.
  - Si no: la abrasión del tapizado no aplica.
  - Deslizamiento: no aplicable.

  MOB-05 (aparador)
  - Estabilidad y anclaje: a verificar en obra.
  - Fuego, abrasión y deslizamiento: no aplicables a una pieza existente sin intervención.

  ILU-01 (lámparas)
  - Estabilidad.
  - Documentación eléctrica del fabricante.
  - Abrasión, limpieza textil y deslizamiento: no aplicables, salvo pantallas textiles (limpieza y fuego por verificar).

  TEX-01 (alfombra)
  - Reacción al fuego.
  - Resistencia al desgaste: método indicado por el fabricante.
  - Código de limpieza.
  - Resistencia al deslizamiento de la pieza y su base.

  TEX-02 (cortinas)
  - Reacción al fuego.
  - Código de limpieza.
  - Abrasión: no aplicable como superficie de asiento.
  - Deslizamiento: no aplicable.

  El interiorista responsable confirma las exigencias locales de uso y seguridad y su acreditación.

6. PREGUNTAS PARA EL CLIENTE

  1. MOB-01: medidas máximas del sofá y lado de la chaise longue.
  2. TEX-01: ¿los 40 cm se aplican a toda la estancia (alfombra de 5,6 × 4,2 m) o solo a la zona de estar? Si es solo la zona de estar, indicad sus medidas.
  3. MOB-02, MOB-03 y MOB-04: medidas o criterios dimensionales (espacio por comensal, circulación). ¿Las sillas van tapizadas?
  4. TEX-02: tipo de cortina, número de paños, sobreancho, fruncido, caída y altura de colocación. ¿Se incluyen confección y rieles?
  5. MOB-05: medidas del aparador, acabado del roble, titularidad confirmada y si necesita alguna intervención o traslado.
  6. Lino y gato: ¿aceptáis que el lino quede condicionado a las pruebas de resistencia a arañazos o preferís otra fibra? Blanco puro y terciopelo quedan excluidos.
  7. Presupuesto: ¿se aprueba el peso 1 por fila? ¿Hay prioridades o pesos numéricos por pieza?
  8. Plazos: ¿las 10–12 semanas son naturales o laborables? ¿Cuentan hasta la entrega o incluyen montaje? Si son laborables, ¿qué calendario aplica?
  9. Plazos ausentes: alfombra, mesas, lámparas y cortinas.
  10. Accesos: medidas de puertas, pasillos, escalera o ascensor para la entrega del sofá y la mesa.
  11. Montaje: ¿quién coordina entrega y montaje el 01/03/2027?

Nota: el profesional responsable debe verificar en obra las medidas, la circulación, los accesos, la estabilidad, los anclajes, las fichas técnicas, los presupuestos, el IVA y los plazos antes de aprobar compras o instalación. Antes de enviar, revisad references/checklist.md.

