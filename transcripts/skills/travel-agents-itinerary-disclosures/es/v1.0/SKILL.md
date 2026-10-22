---
name: travel-agents-itinerary-disclosures
description: "Úsala cuando pegues viajeros, fechas, destinos, restricciones y condiciones de la agencia para obtener un itinerario diario con condiciones de reserva y pendientes."
---
# Itinerario + condiciones de reserva

## Qué hace
Prepara un itinerario para revisión del agente, con un bloque por fecha y el reparto de noches solicitado.
Muestra cómo se aplican las restricciones y señala los datos pendientes de confirmación.
Reproduce literalmente las condiciones de la agencia, sin completar sus términos ni redactar obligaciones legales.

## Qué necesita
- Perfil desidentificado: número de viajeros, edades de menores y necesidades relevantes.
- País del pasaporte, solo si hace falta para orientar la consulta documental; nunca su número ni una copia.
- Fechas completas de llegada y salida, con año, destinos y orden de visita.
- Número de noches por destino, incluidas las noches en tránsito si las hay.
- Llegada, salida y traslados previstos; indicar qué está reservado y qué no.
- Movilidad, dieta, alergias, edades de niños, ritmo y otras peticiones.
- Indicar si se excluye el auto de renta (MX) / coche de alquiler (ES).
- Condiciones originales: anticipo (MX) / depósito o señal (ES), liquidación (MX) / pago final (ES) y aceptación del seguro.
- Otras condiciones que la agencia quiera incluir, copiadas tal como deben entregarse; conservar moneda y formato.
- Si falta información o hay contradicciones, pregunta una sola vez, agrupando las dudas.
- Si se solicita continuar, identifica los faltantes sin suponer respuestas.
- Sin fechas o reparto de noches coherentes, entrega solo un borrador incompleto; no construyas un calendario supuesto.

## Procedimiento
1. Extrae los datos aportados y separa hechos del encargo, peticiones, reservas existentes y términos originales.
   No interpretes una propuesta como reserva confirmada ni una cláusula de seguro como aceptación del cliente.
2. Calcula las noches entre llegada y salida y muestra la suma por destino.
   Comprueba que ambas cantidades coinciden; cuenta las noches en tránsito por separado si se han indicado.
   Si hay discrepancias, aplica la consulta única y no ajustes fechas ni noches por tu cuenta.
3. Crea exactamente un bloque por fecha, desde la llegada hasta la salida, ambas incluidas.
   Asigna a cada pernocta su destino y número; en la salida escribe «Sin pernocta» si no corresponde otra noche.
   Comprueba que el total por destino reproduce el reparto recibido.
4. Marca «Día de traslado» en llegada, salida y cualquier cambio de destino.
   Indica origen, destino y medio propuesto o pendiente; no inventes conexiones ni duraciones.
   Deja esos días ligeros, sin actividades que dependan de una conexión aún no confirmada.
5. Haz una lista de todas las restricciones y vincula cada una a decisiones concretas del plan.
   Movilidad: evita recorridos incompatibles y deja pendiente verificar accesibilidad con los proveedores.
   Sin auto/coche: no propongas conducir ni alquilar; señala alternativas y su disponibilidad pendiente.
   Ritmo: limita actividades y añade descansos según lo solicitado.
   Menores: usa las edades aportadas para orientar propuestas, sin garantizar admisión.
6. Aplica dieta y alergias a cada comida propuesta y actividad que incluya alimentos.
   Para cada alergia escribe «Confirmar con el proveedor por escrito» y crea una tarea específica.
   No garantices ausencia de alérgenos, contaminación cruzada ni seguridad alimentaria.
7. Marca cada precio, horario de apertura, tiempo de transporte, límite de edad o estatura y requisito de entrada con [confirm].
   Hazlo aunque el dato se haya aportado o parezca verificado; no lo presentes como hecho confirmado.
   No inventes cifras para acompañar la marca: si no hay dato, escribe qué debe confirmarse u omítelo.
   Las fechas, edades y noches del encargo no requieren esa marca por ser cifras.
8. Copia íntegramente las condiciones recibidas en un bloque literal, sin corregir ni traducir.
   Conserva palabras, cifras, porcentajes, plazos, moneda y puntuación; no añadas condiciones dentro del bloque.
   Comprueba por separado que constan anticipo/depósito, liquidación/pago final y aceptación del seguro.
   Para cada término ausente, añade fuera del bloque «No proporcionado por la agencia: [término]».
   Si el bloque contiene datos sujetos a [confirm], señálalos fuera, citando el fragmento y añadiendo [confirm].
9. En «Sobre sus peticiones», relaciona cada restricción con los días o decisiones que la atienden.
   Distingue aplicación propuesta de validación pendiente por un proveedor.
10. Incluye en los pendientes la consulta de pasaporte, visa (MX) / visado (ES) y entrada.
    Remite a fuentes oficiales del gobierno del país del pasaporte, del destino y, cuando proceda, del tránsito.
    Remite al cliente a su aseguradora para verificar cobertura; no garantices que el seguro cubre el viaje.
11. Separa «Por reservar» de «Por confirmar», con una casilla por tarea.
    Incluye servicios sin reservar, cada dato marcado [confirm], alergias, traslados y datos ausentes.
    No vuelvas a presentar como pendiente de reserva un servicio que el usuario indica ya reservado.
12. Revisa: bloques = fechas inclusivas; noches = diferencia entre fechas = suma del reparto.
    Verifica cada restricción, cada traslado, cada marca obligatoria y la coincidencia literal de las condiciones.
    Si no puedes cumplir una comprobación, declara el borrador incompleto y el motivo.

## Formato de salida
```markdown
## El viaje en un vistazo
- Estado: [borrador para revisión / incompleto y motivo]
- Viajeros: [perfil desidentificado y edades relevantes]
- Fechas: [llegada–salida]; noches: [diferencia entre fechas] = [suma por destino]
## Día a día
- [Fecha] · [Destino] · [Noche y lugar / Sin pernocta] · [Día de traslado, si corresponde]
  [Plan, restricciones aplicadas y datos sujetos a [confirm]; repetir por cada fecha]
## Sobre sus peticiones
- [Petición]: [decisión y día; validación pendiente, si procede].
## Condiciones de reserva
> [Texto íntegro de la agencia, sin alteraciones]
Observaciones fuera del texto: [términos ausentes y datos sujetos a [confirm], si los hay].
## Por reservar / por confirmar
Por reservar:
- [ ] [Servicio no reservado].
Por confirmar:
- [ ] [Dato, proveedor o información faltante; una tarea por elemento].
- [ ] Consultar fuentes oficiales de los gobiernos pertinentes sobre pasaporte, visa/visado y entrada [confirm].
- [ ] Confirmar cobertura con su aseguradora.
```

## Límites
- No inventes reservas, disponibilidad, precios, horarios, requisitos, condiciones ni estadísticas.
- No añadas leyes, artículos, autoridades, enlaces ni referencias normativas distintos de la fuente indicada.
- El agente responsable debe verificar viabilidad, accesibilidad, traslados, restricciones de menores y respuesta de proveedores sobre alergias antes de presentar servicios como confirmados.
- Debe comprobar los términos vigentes y la situación real de aceptación del seguro; no presupongas consentimiento ni impongas una forma de aceptación no facilitada.
- (ES) Los viajes combinados tienen información precontractual obligatoria. (MX) Hay normas de protección al consumidor. La agencia confirma sus obligaciones con su asesor; esta skill no redacta esos textos.
- No se ha verificado orientación oficial específica sobre IA para agencias en ES/MX; consulta con el organismo profesional o regulador competente, sin atribuirle recomendaciones no verificadas.
- Privacidad: usa solo datos desidentificados y herramientas aprobadas por la agencia; excluye nombres reales, documentos, contactos y datos de salud identificables. Si aparecen, pide una versión desidentificada y no los reproduzcas.
- El profesional responsable debe verificar el tratamiento autorizado de datos y las obligaciones de protección de datos aplicables; en México, la LFPDPPP 2025.
- Fuente: Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- Antes de enviar, revisión del agente responsable: see references/checklist.md.

## Ejemplo
Entrada ficticia:
```text
Familia Muestra: dos adultos y un niño de 8 años; mercado MX.
Del 4 al 5 de mayo de 2027; Ciudad Muestra, 1 noche; nada reservado.
Sin auto de renta; ritmo tranquilo; alergia al cacahuate.
Condiciones: Anticipo: 20%. Liquidación antes de salir. Seguro: aceptación pendiente.
```
Salida abreviada:
```text
## El viaje en un vistazo
Borrador: Familia Muestra, dos adultos y niño de 8; 4–5 mayo 2027; 1 noche = Ciudad Muestra 1.
## Día a día
4 mayo · Ciudad Muestra · Noche 1 · Día de traslado: llegada; traslado con conductor por confirmar, sin auto de renta; paseo corto y descanso.
5 mayo · Ciudad Muestra · Sin pernocta · Día de traslado: salida; descanso y traslado con conductor por confirmar.
## Sobre sus peticiones
Ritmo tranquilo y paseo familiar por la edad indicada; sin comidas propuestas; alergia al cacahuate pendiente de validación.
## Condiciones de reserva
Anticipo: 20%. Liquidación antes de salir. Seguro: aceptación pendiente.
## Por reservar / por confirmar
Por reservar: [ ] Alojamiento. [ ] Traslado de llegada. [ ] Traslado de salida.
Por confirmar: [ ] Llegada con proveedor. [ ] Salida con proveedor. [ ] Alergia al cacahuate con proveedores de alimentos, por escrito.
[ ] Consultar gobiernos del país del pasaporte y destino sobre pasaporte, visa y entrada [confirm].
[ ] Confirmar cobertura con su aseguradora. [ ] Aclarar aceptación del seguro.
```
