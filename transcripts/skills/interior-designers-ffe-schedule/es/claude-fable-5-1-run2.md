# Transcript — skill interior-designers-ffe-schedule [es] — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:35:40+00:00
- duration_s: 105.2
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

- Estancia: salón-comedor, Madrid (ES); 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho. Uso: estar y comedor para 6. Piezas existentes: aparador de roble (se conserva). Preferencias: roble claro, lino.
- Usuarios / mascotas: pareja y un gato que araña. Requisito vinculado a sofá, sillas (si van tapizadas), alfombra y cortinas: resistencia a arañazos/abrasión y limpieza del tejido — por verificar en ficha técnica. El lino es preferencia del cliente; su comportamiento frente a un gato que araña queda por verificar, no se descarta.
- Excluido por indicación del cliente: blanco puro; terciopelo. Eliminados de todas las propuestas y alternativas.
- Supuestos de reparto pendientes de aprobación: no hay pesos del cliente; se propone peso 1 por fila (criterio provisional) para 7 filas nuevas + 1 partida auxiliar de transporte y montaje. Plazo de tapicería tomado en su valor máximo (12 semanas), base natural/laborable y alcance por confirmar.

LISTADO FF&E
(Partidas: importe — partida estimada — confirmar con presupuestos; todas con IVA. Fecha de pedido: 07/12/2026 provisional, ver Control de plazos.)

MOB-01 | Sofá 3 plazas con chaise longue | Cant. 1
  Medida objetivo: FALTA (no hay criterio de largo ni lado de la chaise).
  Material / requisitos: tejido limpiable y resistente a arañazos de gato: por verificar; lino propuesto si cumple; terciopelo excluido.
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA.
  Plazo: 10–12 semanas (tapicería, proveedor del estudio); fecha límite de pedido 07/12/2026 (provisional). Pendiente: base natural/laborable; si incluye transporte y montaje.
  Estado: nueva.

TEX-01 | Alfombra | Cant. 1
  Medida objetivo: margen 40 cm = 0,4 m (conversión para el cálculo). (6,4 − 2 × 0,4) × (5,0 − 2 × 0,4) = 5,6 m × 4,2 m, tomando la estancia completa. Si la alfombra solo cubre la zona de estar, FALTA la medida de esa zona.
  Material / requisitos: limpieza y resistencia al uso con gato: por verificar; deslizamiento: por verificar.
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA.
  Plazo: no indicado — podría adelantar la fecha de pedido; fecha de referencia 07/12/2026 (provisional).
  Estado: nueva.

MOB-02 | Mesa de centro | Cant. 1
  Medida objetivo: FALTA (depende de la medida del sofá y del paso previsto).
  Material / requisitos: roble claro propuesto (preferencia del cliente, coherente con MOB-05); estabilidad y acabado: por verificar.
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA.
  Plazo: no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 (provisional).
  Estado: nueva.

MOB-03 | Mesa de comedor para 6 | Cant. 1
  Medida objetivo: FALTA (no se aportó criterio de ancho por comensal ni paso alrededor).
  Material / requisitos: roble claro propuesto; estabilidad y acabado: por verificar. Blanco puro excluido.
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA.
  Plazo: no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 (provisional).
  Estado: nueva.

MOB-04 | Sillas de comedor | Cant. 6
  Medida objetivo: FALTA (altura de asiento vinculada a MOB-03).
  Material / requisitos: si llevan tapizado, mismo requisito que MOB-01 (arañazos, abrasión, limpieza) y aplica el plazo de tapicería; terciopelo excluido.
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA (para las 6).
  Plazo: no indicado (10–12 semanas solo si van tapizadas); referencia 07/12/2026 (provisional).
  Estado: nueva.

ILU-01 | Lámparas de pie | Cant. 2
  Medida objetivo: FALTA (altura y diámetro no indicados; techo 2,70 m como límite).
  Material / requisitos: documentación de seguridad eléctrica del fabricante: por verificar; estabilidad de la base con gato: por verificar.
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA (para las 2).
  Plazo: no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 (provisional).
  Estado: nueva.

TEX-02 | Cortinas | Cant. 2 (una por ventana)
  Medida objetivo: ancho de ventana 1,8 m cada una; alto de techo 2,70 m. FALTA: altura de instalación, solape lateral y factor de fruncido para calcular ancho y caída de tela.
  Material / requisitos: lino propuesto; reacción al fuego y limpieza: por verificar; resistencia a arañazos: por verificar. Blanco puro excluido.
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA.
  Plazo: no indicado — podría adelantar la fecha de pedido; referencia 07/12/2026 (provisional).
  Estado: nueva.

MOB-05 | Aparador de roble (existente) | Cant. 1
  Medida objetivo: FALTA (no aportada; necesaria para planta y paso).
  Material / requisitos: sin intervención declarada; estabilidad/anclaje: por verificar.
  Partida: 0 € adquisición — partida estimada — confirmar con presupuestos — con IVA; sin adquisición; otros costes (traslado dentro de la vivienda, anclaje) por confirmar.
  Plazo: sin pedido.
  Estado: existente-reutilizar (conservación indicada en el briefing).

AUX-01 | Transporte y montaje | partida auxiliar
  Partida: 2.250 € — partida estimada — confirmar con presupuestos — con IVA. Alcance por pieza pendiente.

CONTROL DE PRESUPUESTO

- Total del cliente: 18.000 € IVA incluido, con transporte y montaje. Todas las partidas: con IVA.
- Base proporcional: peso 1 por fila presupuestable, criterio provisional (hay partida auxiliar no comparable con cantidades). Filas: MOB-01, TEX-01, MOB-02, MOB-03, MOB-04, ILU-01, TEX-02, AUX-01. Suma de pesos = 8.
- Por código: 18.000 × 1 ÷ 8 = 2.250 € — partida estimada — confirmar con presupuestos (igual para los 8 códigos). MOB-05: 0 € adquisición.
- Ajuste de redondeo: ninguno necesario (2.250 × 8 = 18.000 exacto).
- Suma mostrada: 2.250 × 8 + 0 = 18.000 €; total menos suma = 0 €.
- Transporte y montaje: incluidos (AUX-01). Intervenciones en MOB-05: ninguna declarada; costes de traslado/anclaje pendientes, no incluidos en ninguna partida.
- Nota: el peso 1 por fila asigna lo mismo a 6 sillas que a 1 mesa de centro; si el cliente prefiere pesos por cantidad o asignaciones concretas, el reparto se recalcula.

CONTROL DE PLAZOS

- Montaje: 01/03/2027 (lunes). Plazo más largo indicado: 12 semanas (tapicería), código MOB-01; aplicable también a MOB-04 si van tapizadas.
- Conversión: 12 × 7 = 84 días naturales, PROVISIONAL (el briefing no indica si son semanas naturales o laborables).
- Fecha límite de pedido = 01/03/2027 − 84 días = 07/12/2026 (provisional, referencia común; no es garantía del proveedor). A día de hoy (20/10/2026) quedan 48 días; no vencida.
- Pendiente: si las 10–12 semanas incluyen transporte y montaje; plazos de TEX-01, MOB-02, MOB-03, MOB-04, ILU-01 y TEX-02 (cualquiera de ellos podría adelantar la fecha); calendario de festivos si la base fuese laborable.

ESPECIFICACIONES POR VERIFICAR
(Documento necesario en todos los casos: ficha técnica del fabricante o del proveedor del tejido; validación por el profesional responsable.)

- MOB-01 Sofá: reacción al fuego — pendiente; abrasión con método y ciclos (Martindale / double rubs) — pendiente; código de limpieza — pendiente; deslizamiento — no aplicable (no es revestimiento de suelo).
- TEX-01 Alfombra: reacción al fuego — pendiente; abrasión/uso — pendiente; limpieza — pendiente; deslizamiento (base antideslizante) — pendiente.
- MOB-02 y MOB-03 Mesas: reacción al fuego — a confirmar por el interiorista si aplica en uso residencial; abrasión y limpieza — no aplicable (sin textil); deslizamiento — no aplicable. Acabado y estabilidad — pendiente.
- MOB-04 Sillas: si tapizadas, igual que MOB-01; si no, igual que mesas.
- ILU-01 Lámparas: documentación de seguridad eléctrica y estabilidad — pendiente; fuego/abrasión/limpieza/deslizamiento — no aplicable (no textil ni suelo), salvo pantalla textil.
- TEX-02 Cortinas: reacción al fuego — pendiente; limpieza — pendiente; abrasión — pendiente por el gato; deslizamiento — no aplicable.
- MOB-05 Aparador: estabilidad/anclaje — pendiente; resto no aplicable (pieza existente sin intervención).
- Las exigencias locales de uso y seguridad las confirma el interiorista responsable.

PREGUNTAS PARA EL CLIENTE

1. Plazo tapicería (MOB-01, MOB-04): ¿10–12 semanas en días naturales o laborables? ¿Incluye transporte y montaje? Si solo entrega, hay que sumar el tiempo de montaje.
2. Plazos ausentes: TEX-01, MOB-02, MOB-03, ILU-01, TEX-02 — ¿plazos de proveedor? Pueden adelantar la fecha del 07/12/2026.
3. MOB-04: ¿sillas tapizadas o sin tapizar? Afecta a plazo y a requisitos por el gato.
4. TEX-01: ¿la alfombra cubre toda la estancia (5,6 × 4,2 m) o solo la zona de estar? En ese caso, medidas de la zona.
5. Medidas: sofá (largo y lado de la chaise), mesa de centro, mesa de comedor y sillas (criterio de ancho por comensal y paso), lámparas (altura máxima), aparador existente. También pasos, puertas y accesos para comprobar entrega.
6. TEX-02: altura de instalación de la barra, solape lateral y factor de fruncido para calcular tela.
7. Reparto: ¿se aprueba peso 1 por fila (2.250 € cada una, transporte y montaje incluidos como partida propia) o se prefieren pesos por cantidad o importes por pieza?
8. MOB-05: ¿se confirma que no requiere intervención ni traslado con coste? ¿Posición final en planta?
9. Lino con gato que araña: ¿se mantiene como preferencia en sofá y cortinas aunque la ficha técnica indique menor resistencia, o se admite otro tejido no terciopelo?
10. ¿Quién coordina recepción, almacenaje y fecha única de montaje con los distintos proveedores?

Antes de enviar al cliente: revisar references/checklist.md y confirmar que el briefing está desidentificado (aquí solo figura «pareja Ejemplo», ficticia).

