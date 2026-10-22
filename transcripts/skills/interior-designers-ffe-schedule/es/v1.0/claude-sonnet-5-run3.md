# Transcript — skill interior-designers-ffe-schedule [es] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:15:46+00:00
- duration_s: 125.7
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

FF&E — Salón-comedor, Madrid (España)
Cliente: pareja (ficticia) — datos identificativos no incluidos.

═══════════════════════════════════════════
1. INTENCIÓN DE DISEÑO
═══════════════════════════════════════════

Estancia y uso:
  Salón-comedor, 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho.
  Madrid, España.

Usuarios / mascotas:
  Pareja adulta. Un gato que araña (sin menores en el briefing).

Gustos del cliente:
  Roble claro, lino.

Excluido por indicación del cliente:
  Blanco puro.
  Terciopelo.
  (Eliminados de cualquier material, acabado o alternativa propuesta para todas las piezas.)

Datos pendientes o conflictos de diseño:
  - No se han aportado medidas objetivo para sofá, mesa de centro, mesa de comedor, sillas, lámparas de pie ni aparador existente.
  - No se ha confirmado si las sillas son tapizadas (afecta a requisitos del gato y a materiales lino/roble).
  - No se ha confirmado la altura útil de ventana/techo-suelo ni la posición de barra para calcular las cortinas.
  - No se han indicado pasos o accesos estrechos relevantes para piezas voluminosas (sofá con chaise longue, mesa de comedor para 6).

═══════════════════════════════════════════
2. LISTADO FF&E
═══════════════════════════════════════════

MOB-01 — Sofá de 3 plazas con chaise longue
  Cantidad: 1
  Medida objetivo: FALTA (no se han aportado dimensiones)
  Requisitos por verificar: resistencia al rasguño y facilidad de limpieza del tapizado (gato); si se usa lino, verificar durabilidad y mantenimiento; color/acabado excluyendo blanco puro y terciopelo
  Asignación estimada: por asignar — IVA: con IVA (según presupuesto global)
  Plazo / pedir antes de: ver Control de plazos (plazo de tapicería 10–12 semanas aportado)
  Estado: nueva

TEX-01 — Alfombra (dejando 40 cm de suelo visto en cada lado)
  Cantidad: 1
  Medida objetivo y cálculo:
    Fórmula: (largo − 2 × margen) × (ancho − 2 × margen)
    Datos: largo estancia 6,4 m; ancho estancia 5,0 m; margen 0,4 m por lado (dato aportado)
    Cálculo: (6,4 − 2×0,4) × (5,0 − 2×0,4) = (6,4 − 0,8) × (5,0 − 0,8) = 5,6 m × 4,2 m
    Nota: cálculo realizado sobre las dimensiones totales de la estancia, a falta de otra referencia (p. ej. zona de estar delimitada). A confirmar con el cliente si el margen debía aplicarse a un área menor.
  Requisitos por verificar: resistencia al rasguño (gato), código de limpieza, abrasión (método y ciclos), resistencia al deslizamiento
  Asignación estimada: por asignar — IVA: con IVA
  Plazo / pedir antes de: viabilidad de plazo no comprobada — falta plazo de proveedor
  Estado: nueva

MOB-02 — Mesa de centro
  Cantidad: 1
  Medida objetivo: FALTA
  Requisitos por verificar: estabilidad; acabado en roble claro (gusto del cliente, pendiente de confirmar disponibilidad)
  Asignación estimada: por asignar — IVA: con IVA
  Plazo / pedir antes de: viabilidad de plazo no comprobada — falta plazo de proveedor
  Estado: nueva

MOB-03 — Mesa de comedor para 6
  Cantidad: 1
  Medida objetivo: FALTA (solo se indica capacidad "para 6", sin dimensiones)
  Requisitos por verificar: estabilidad; acabado en roble claro; holgura de circulación alrededor (a verificar en obra)
  Asignación estimada: por asignar — IVA: con IVA
  Plazo / pedir antes de: viabilidad de plazo no comprobada — falta plazo de proveedor
  Estado: nueva

MOB-04 — Sillas de comedor
  Cantidad: 6
  Medida objetivo: FALTA
  Requisitos por verificar: si son tapizadas — abrasión, código de limpieza, resistencia al rasguño (gato); si son de madera — acabado en roble claro, estabilidad
  Asignación estimada: por asignar — IVA: con IVA
  Plazo / pedir antes de: viabilidad de plazo no comprobada — pendiente confirmar si aplica el mismo plazo de tapicería (10–12 semanas) que el sofá
  Estado: nueva

ILU-01 — Lámparas de pie
  Cantidad: 2
  Medida objetivo: FALTA
  Requisitos por verificar: estabilidad de la base; normativa eléctrica aplicable (a confirmar por el interiorista responsable); gestión de cableado considerando la presencia del gato
  Asignación estimada: por asignar — IVA: con IVA
  Plazo / pedir antes de: viabilidad de plazo no comprobada — falta plazo de proveedor
  Estado: nueva

TEX-02 — Cortinas (2 ventanas de 1,8 m de ancho)
  Cantidad: 2
  Medida objetivo: FALTA — falta altura de ventana/techo-suelo, posición de barra y fullness deseado para calcular ancho y caída de tela
  Requisitos por verificar: reacción al fuego/inflamabilidad según uso; si la tela llega al suelo, resistencia al desgarro/rasguño (gato); color/tejido en lino excluyendo blanco puro
  Asignación estimada: por asignar — IVA: con IVA
  Plazo / pedir antes de: viabilidad de plazo no comprobada — falta plazo de proveedor
  Estado: nueva

MOB-05 — Aparador de roble (existente, se conserva)
  Cantidad: 1
  Medida objetivo: FALTA (no se han aportado dimensiones; necesarias para verificar encaje con las piezas nuevas)
  Requisitos por verificar: estabilidad; estado de conservación; posible protección durante la obra (no se ha declarado intervención)
  Asignación estimada: adquisición 0 € (pieza ya propiedad del cliente); intervención/transporte no declarados — pendientes de confirmar
  Plazo / pedir antes de: disponibilidad por verificar (pieza ya en posesión del cliente, sin plazo de compra aplicable)
  Estado: existente-reutilizar (reutilización confirmada por el cliente: "se conserva")

═══════════════════════════════════════════
3. CONTROL DE PRESUPUESTO
═══════════════════════════════════════════

Presupuesto del cliente: 18.000 € — con IVA incluido (indicado literalmente por el cliente).
Incluye: transporte y montaje (según indicación del cliente).

Origen del reparto: no aportado por el cliente. No se ha recibido autorización para proponer un reparto, por lo que no se ha calculado ninguna propuesta.

Asignaciones estimadas: todas las partidas figuran como "por asignar"; una vez definidas, deberán confirmarse con presupuesto (ES) antes de aprobar compra.

Suma de asignaciones numéricas: 0 € (ninguna partida tiene importe asignado todavía).
Operación: 18.000 € − 0 € = 18.000 €.
Resultado: saldo aún no asignado = 18.000 €. (No se trata de ahorro ni de reserva disponible; es presupuesto total pendiente de distribuir entre las 8 piezas del listado.)

Transporte, montaje e intervenciones:
  - Transporte: incluido (según cliente).
  - Montaje: incluido (según cliente).
  - Intervención sobre el aparador existente (limpieza/protección/restauración): no declarada — pendiente de confirmar.

═══════════════════════════════════════════
4. CONTROL DE PLAZOS
═══════════════════════════════════════════

Fecha de montaje / instalación: 1 de marzo de 2027.

MOB-01 (sofá) — único código con plazo aportado:
  Plazo de proveedor (tapicería): 10–12 semanas. No se ha confirmado si son semanas naturales o laborables, ni si el plazo incluye transporte e instalación.
  Margen de seguridad acordado: FALTA.

  Cálculo (fórmula sin resolver completamente por falta de margen):
    Pedir antes de = fecha de montaje − plazo total − margen acordado

    Con plazo máximo (12 semanas = 84 días):
      1 de marzo de 2027 − 84 días = 7 de diciembre de 2026

    Con plazo mínimo (10 semanas = 70 días):
      1 de marzo de 2027 − 70 días = 21 de diciembre de 2026

    Sin margen de seguridad aplicado, "pedir antes de" cae entre el 7 y el 21 de diciembre de 2026. El margen acordado reduciría aún más estas fechas.

  Nota de contexto: la fecha de hoy (19 de octubre de 2026) queda antes de ambas fechas calculadas, por lo que el plazo no está vencido; sin embargo, quedan aproximadamente 7 a 9 semanas para definir dimensiones, materiales y confirmar pedido.

MOB-04 (sillas) — pendiente confirmar si aplica el mismo plazo de tapicería que el sofá (depende de si son tapizadas). Viabilidad no comprobada mientras no se aclare.

TEX-01, MOB-02, MOB-03, ILU-01, TEX-02 — viabilidad de plazo no comprobada: no se ha aportado plazo de proveedor para alfombra, mesa de centro, mesa de comedor, lámparas ni cortinas. Riesgo especialmente relevante si alguna de estas piezas es a medida o de importación.

MOB-05 (aparador existente) — no aplica plazo de compra; pendiente confirmar disponibilidad para la fecha de montaje si requiere intervención.

═══════════════════════════════════════════
5. ESPECIFICACIONES POR VERIFICAR
═══════════════════════════════════════════

MOB-01 (sofá): reacción al fuego/inflamabilidad del tapizado — pendiente de ficha técnica; abrasión (método y ciclos, incluidos double rubs si corresponde) — pendiente; código de limpieza — pendiente; resistencia al rasguño (relevante por el gato) — pendiente, sin clasificación comprobada.

TEX-01 (alfombra): reacción al fuego si aplica normativa local — pendiente; abrasión (método y ciclos) — pendiente; código de limpieza — pendiente; resistencia al deslizamiento — pendiente; resistencia al rasguño (gato) — pendiente.

MOB-02 (mesa de centro): estabilidad — pendiente de verificación en obra; acabado roble claro — a confirmar disponibilidad, sin ficha técnica aportada.

MOB-03 (mesa de comedor): estabilidad — pendiente; acabado roble claro — a confirmar; no aplica reacción al fuego (mobiliario rígido, no textil) — no aplicable por tipo de pieza.

MOB-04 (sillas): si tapizadas — abrasión, limpieza y rasguño pendientes (igual que MOB-01); si madera — estabilidad y acabado pendientes. No se puede completar hasta aclarar el tipo de construcción.

ILU-01 (lámparas de pie): estabilidad de base — pendiente; normativa eléctrica aplicable — pendiente, a confirmar por el interiorista responsable.

TEX-02 (cortinas): reacción al fuego/inflamabilidad — pendiente, especialmente relevante según normativa local de uso; resistencia al desgarro si la tela llega al suelo (por el gato) — pendiente.

MOB-05 (aparador existente): estabilidad y estado de conservación — pendiente de verificación en obra; no aplica reacción al fuego por tratarse de mobiliario de madera no textil.

Reacción al fuego y seguridad: el interiorista responsable confirma las exigencias aplicables según el uso del espacio y la normativa local vigente en Madrid, España, así como la documentación necesaria para acreditarlas. Ninguna clasificación mencionada aquí debe interpretarse como verificada.

═══════════════════════════════════════════
6. PREGUNTAS PARA EL CLIENTE
═══════════════════════════════════════════

1. Presupuesto: ¿cómo desean repartir los 18.000 € entre las piezas, o autorizan que se proponga un reparto estimado a confirmar con presupuesto?

2. MOB-01 (sofá): ¿qué dimensiones objetivo (largo, profundidad, profundidad de chaise longue) buscan?

3. TEX-01 (alfombra): el cálculo de 5,6 × 4,2 m se ha hecho sobre las dimensiones totales de la estancia. ¿Es correcto, o el margen de 40 cm debía aplicarse a una zona de estar más reducida?

4. MOB-02 (mesa de centro): ¿qué dimensiones objetivo tiene en mente?

5. MOB-03 (mesa de comedor): ¿qué dimensiones objetivo (largo × ancho) necesitan para sentar a 6 personas con holgura?

6. MOB-04 (sillas): ¿son tapizadas o de madera? Si son tapizadas, ¿qué material (lino u otro, excluyendo terciopelo)?

7. ILU-01 (lámparas de pie): ¿qué altura y tipo de base buscan?

8. TEX-02 (cortinas): ¿cuál es la altura de ventana a suelo o a techo, la posición prevista de la barra y el fullness (pliegue) deseado? Esto es necesario para calcular el ancho y la caída de la tela.

9. MOB-05 (aparador): ¿cuáles son sus dimensiones exactas? ¿Requiere alguna intervención (limpieza, protección, pequeña restauración) antes o durante la obra?

10. Plazos: ¿el plazo de 10–12 semanas de tapicería corresponde solo al sofá o también a las sillas (si son tapizadas)? ¿Está expresado en semanas naturales o laborables, e incluye transporte e instalación? ¿Qué margen de seguridad desean aplicar antes de la fecha de montaje del 1 de marzo de 2027?

11. Plazos de proveedor para mesa de centro, mesa de comedor, sillas (si no tapizadas), lámparas de pie, cortinas y alfombra: ¿disponen de esta información?

12. Accesos: ¿hay pasos, escaleras o puertas estrechas relevantes para la entrada de piezas voluminosas como el sofá con chaise longue o la mesa de comedor para 6?

