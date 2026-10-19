# Clase 8 · Pruebas y mejoras del MVP

- **Equipo, fecha, usuario y problema:**
  - Equipo: Milagros Gil, Josefina Llorente, Sofia Raiti, Chen Wen Hua, Ibañez Ana Lucia, Cingolani Franco
  - Fecha de la primera ronda de pruebas: 18/10/2026
  - Usuario: estudiante universitario de 3er o 4to año, sin experiencia laboral corporativa formal, que está armando su CV o LinkedIn para una primera pasantía.
  - Problema: no sabe cómo traducir un trabajo práctico o una investigación de la facultad al lenguaje de un CV, y tiende a descartar esa experiencia por considerarla poco profesional.
- **MVP: acceso y versiones:**
  - Acceso: https://generador-de-logros-para-cv.vercel.app (enlace público, no requiere cuenta).
  - Versión probada en esta ronda: **v1 (inicial)**. El estudiante elige el rol al que aspira y describe su proyecto; la página llama a un servicio de IA (Gemini) desde el servidor y devuelve 3 logros en tono Junior/Analista, o una pregunta de seguimiento si falta detalle.
  - Versión nueva (v2): cambios de manejo de errores subidos a la rama `v0/cv-achievement-translator`. Confirmado el 18/10/2026: el enlace público ya muestra la interfaz de error nueva (captura de pantalla de una prueba del equipo, no de un participante).
- **Tarea, inicio, finalización y condición de cierre:**
  - Tarea (consigna dada a los participantes): "Estás por postularte a tu primera pasantía y querés poner un proyecto de la facultad en tu CV para que suene profesional." Se les pidió probar sin instrucciones sobre cómo usar la herramienta.
  - Inicio: el participante abre el enlace.
  - Finalización: el participante ve en pantalla los 3 logros redactados.
  - Condición de cierre o abandono: *no se definió antes de la primera ronda*. Propuesta para la segunda ronda, a confirmar por el equipo: abandono si la persona deja de intentar sin obtener los 3 logros.
- **Qué cuenta como ayuda:** cualquier explicación del equipo, antes o durante el uso, sobre qué es la herramienta o cómo se usa. La consigna de la tarea no cuenta como ayuda.
- **Funcional / manual / simulado:**
  - Funcional: formulario con selección de rol y descripción del proyecto con contador de palabras; llamada a la IA desde el servidor; detección de descripciones sin detalle suficiente y pregunta de seguimiento; botones para copiar los logros.
  - Manual: el registro de las pruebas (lo hace el equipo a mano).
  - Simulado: nada. Los logros los genera la IA en el momento, sin revisión humana.
  - No existe registro automático de uso: el equipo no puede ver qué escribió cada persona ni qué recibió, salvo que lo cuente.

## Reconstrucción del recorrido

1. **Nuestro usuario tiene el problema de** no saber cómo traducir sus trabajos prácticos o investigaciones al lenguaje de un CV, y de descartarlos por parecerle poco profesionales, **cuando** arma su CV o LinkedIn para una primera pasantía.
2. **La hipótesis más riesgosa era**, en la primera iteración, que entregar la experiencia ya traducida reduce el autodescarte. Después pasó a ser técnica (si un prompt mantiene el tono Junior sin edición). Lo que sigue abierto desde la Clase 6 es si los estudiantes usan y confían en un flujo automático, y si los reclutadores valoran estos perfiles.
3. **Para probarla hicimos** un experimento manual con formulario y 10 estudiantes (Clase 4), una prueba de banco con 10 casos históricos (Clase 5) y un MVP web público que llama a la IA en el momento (Clase 7). En la Clase 8 lo probamos con 4 estudiantes.
4. **Observamos que** 5 de 10 estudiantes implementaron el texto en el experimento manual, que 9 de 10 textos mantuvieron el tono Junior en la prueba de banco, y que en la ronda 1 con el MVP público 3 de 4 obtuvieron los logros en su primer intento. Un participante tuvo fallas del servicio de IA durante horas.
5. **Por eso decidimos** avanzar hacia un MVP automático (Clase 6) y, ahora, priorizar la falla del servicio de IA antes de seguir probando el valor.
6. **Nuestro MVP permite** que un estudiante convierta la descripción de un proyecto en 3 logros de tono Junior, **y todavía necesitamos comprobar** que funciona de forma confiable, que los estudiantes realmente usan los logros en un CV, y qué opinan los reclutadores.

## Plan de medición

| Métrica | Fórmula/unidad | Fuente y momento | Criterio exploratorio | Decisión |
| --- | --- | --- | --- | --- |
| Éxito | Participantes que ven los 3 logros en su primer intento / participantes que intentan | Relato del participante, justo después de usar la herramienta | Ronda 1: no se fijó. Ronda 2 (propuesto): al menos 4 de 5 | Si no se alcanza, corregir primero lo que impide completar el recorrido principal |
| Autonomía | Participantes que completan sin ayuda / participantes que intentan | Relato del participante y observación del equipo, justo después de usar la herramienta | Ronda 1: no se fijó. Ronda 2 (propuesto): al menos 4 de 5 | Si no se alcanza, mejorar las explicaciones o interacciones donde se pidió ayuda |
| Valor | Participantes que usan los logros generados en un CV o perfil real, con captura de pantalla / participantes que intentan | Declaración del participante y captura, en un seguimiento a los 7 días | Ronda 1: no se fijó. Ronda 2 (propuesto): al menos 2 de 5 | Si se alcanza, avanzar a probar el valor con reclutadores. Si no, revisar qué impide usar el texto |

Nota: los criterios no estaban definidos antes de la ronda 1, por lo que los resultados de esa ronda son un análisis retrospectivo. Los criterios de la ronda 2 son una propuesta inicial y deben confirmarse antes de probar. El valor medido es un indicador aproximado: la declaración de uso con captura no prueba por sí sola que el CV haya mejorado el resultado de una postulación.

## Registro de pruebas

Todos los participantes se declararon estudiantes de 3er año o 3er/4to año sin experiencia corporativa formal (autodeclarado). La muestra es de 4 personas y fue convocada por el equipo.

| ID | Perfil/segmento | Versión | Intentó | Completó | Sin ayuda | Valor/unidad o no medido | Dificultad y ayuda |
| --- | --- | --- | --- | --- | --- | --- | --- |
| U1 | Sí (autodeclarado) | v1 | Sí | No en el primer intento. Completó tras varios reintentos | Sí | No medido. Dice que los usaría como base, sin usarlos todavía | La IA no respondía. Apareció en rojo "No pudimos conectar con el servicio de IA. Proba de nuevo en unos segundos." Unos 10 intentos en computadora y menos de 5 en celular, todos fallidos. Unas 2 horas después, en computadora, funcionó. Sin ayuda del equipo |
| U2 | Sí (autodeclarado) | v1 | Sí | Sí | Sí | No medido. Dice que los usaría, adaptándolos con detalles propios | Ninguna. Resultado instantáneo |
| U3 | Sí (autodeclarado) | v1 | Sí | Sí | No | No medido. Dice que le sirvieron para incluir proyectos que no creía poder poner en su CV | Necesitó que el equipo le explicara de qué se trataba la herramienta. Después fue fácil. Menos de 5 minutos |
| U4 | Sí (autodeclarado) | v1 | Sí | Sí | Sí | Declara haber usado el resultado en su CV (proyecto de finanzas). Evidencia (captura): pendiente | Ninguna. Menos de 3 minutos |

Observaciones adicionales (no son métricas principales):
- Expectativa previa: U1 esperaba recibir un análisis o feedback del proyecto, no logros para el CV. U2, U3 y U4 dijeron que el resultado coincidió con lo esperado.
- Confianza en un resultado generado por IA sin revisión previa: ninguno de los 4 dijo tener menos confianza. U1 y U2 aclararon que revisarían el contenido antes de usarlo. U3 y U4 expresaron confianza plena.

## Aprendizaje e iteración

- **Hechos observados y posibles causas:**
  - Hecho: 3 de 4 participantes obtuvieron los 3 logros en su primer intento. U1 tuvo errores repetidos de conexión con la IA durante varias horas, en dos dispositivos distintos.
  - Hecho: 2 de 4 completaron sin ayuda del equipo (U2, U4). U3 necesitó una explicación sobre qué es la herramienta.
  - Hecho: U4 declara haber usado los logros en su CV.
  - Posible causa del error de U1: sobrecarga del servicio de IA. Indicio, no confirmación: al probar el cambio, v0 vio que Gemini respondió durante toda su sesión con errores 503 de "high demand" o se quedó sin responder. Eso fue en otro momento que la prueba de U1, así que es coherente con lo que ocurrió pero no lo demuestra. Otras causas (cuota o problema del servidor) no se descartaron.
  - Posible causa (sin verificar) de la ayuda a U3: la página no deja claro de inmediato qué hace la herramienta. U1, U2 y U4 dijeron que estaba claro.
- **Prioridad elegida y justificación:** la falla del servicio de IA (U1).
  - Gravedad: alta. Bloquea por completo la tarea, durante horas y en dos dispositivos, y el mensaje de error no indicó qué hacer.
  - Frecuencia observada: 1 de 4 participantes, con unos 15 intentos fallidos.
  - Esfuerzo: bajo. Son cambios pequeños en la ruta del servidor y en el mensaje.
  - Descartada por ahora: aclarar el propósito de la página (U3). Frecuencia 1 de 4, gravedad baja (completó después de una explicación) y no apareció en los otros tres.
  - Esta prioridad fue propuesta por la IA y debe ser confirmada por el equipo antes de entregar.
- **Pedido a la IA y decisión del equipo:**
  - Primer pedido (análisis, sin modificar nada):
    > Nuestro usuario es un estudiante de 3er o 4to año sin experiencia corporativa que quiere traducir un proyecto de la facultad a 3 logros para su CV. Probamos la versión v1 con 4 estudiantes de ese perfil. Observamos que 3 de 4 obtuvieron los logros en su primer intento. Un participante vio durante varias horas, en computadora y en celular, el mensaje "No pudimos conectar con el servicio de IA. Proba de nuevo en unos segundos." unas 15 veces, y recién funcionó unas 2 horas después. Elegimos trabajar sobre esta falla porque bloquea por completo la tarea y el mensaje no le indicó cómo resolverla. Ayudanos a analizar posibles causas y proponé hasta tres cambios pequeños. Antes de modificar, discutamos las alternativas.
  - Cambio propuesto para pedir después de elegir (un solo cambio, tres partes):
    1. Registrar en los logs del servidor el error real que devuelve el servicio de IA (código y mensaje), sin incluir la clave ni el texto del usuario.
    2. Reintentar automáticamente hasta 2 veces, con una espera breve, antes de mostrar el error.
    3. Reemplazar el mensaje de error por uno que diga que el servicio puede estar ocupado y que conviene esperar unos minutos, y asegurar que el texto escrito por el usuario no se borre.
  - Segundo pedido (implementación):
    > Implementá estos tres cambios en el manejo de errores de la ruta del servidor y de la página: registrar el error real, reintentar hasta 2 veces con una espera breve, y mostrar un mensaje claro sin borrar lo que escribió el usuario. Conservá el formulario, el contador de palabras, la pregunta de seguimiento y el resto del recorrido. El criterio de aceptación es: si el servicio de IA falla de forma temporal, la página reintenta y muestra los logros; si sigue fallando, muestra el nuevo mensaje, conserva el texto del usuario y el error real queda en los logs. Probá el recorrido principal y un caso de error. Indicá qué verificaste y qué sigue pendiente de prueba con personas.
  - Decisión del equipo sobre las alternativas: se aplicaron los tres cambios propuestos.
- **Cambio realizado y verificación técnica** (según el informe de v0, versión v2, rama `v0/cv-achievement-translator`):
  - Registro del error real: en los logs del servidor queda cada intento (1/3, 2/3, 3/3) con el tipo de fallo, el código HTTP y el mensaje que devuelve Gemini. Si no se recupera, queda una línea final con el fallo definitivo.
  - Reintentos: hasta 2 más, con esperas de 0,6 s y 1,2 s. Solo se reintentan fallos temporales (429, 5xx, red, tiempo agotado, respuesta vacía o mal formada). En el peor caso la respuesta tarda unos 26 s antes de mostrar el error.
  - Mensaje en la página: si fallan todos los intentos aparece "El servicio de IA no está respondiendo en este momento. Tu texto sigue guardado acá: esperá un minuto y tocá «Reintentar»", con un botón "Reintentar". El texto, el rol y el contador de palabras no se borran. El formulario, la pregunta de seguimiento y el resto del recorrido no cambiaron.
  - Verificado en el navegador (a 623×718): con 2 fallos forzados y una respuesta válida en el tercer intento, la página mostró los 3 logros y los logs registraron los dos fallos y el éxito. Esa respuesta válida era fija, no generada por Gemini. Con los 3 intentos fallando apareció el mensaje nuevo con "Reintentar", y el texto (33 palabras) y el rol "Marketing estratégico" se conservaron. El error real de Gemini (503 "high demand" y tiempos agotados) quedó registrado en los logs. El código TypeScript compila sin errores.
  - No se pudo comprobar: el recorrido completo con Gemini respondiendo de verdad (logros generados y pregunta de seguimiento con la lógica nueva), porque Gemini estuvo saturado durante toda la sesión de v0.
  - Limitación: los reintentos cortos ayudan con fallos pasajeros, pero no resolverían una saturación que dure horas como la que vio U1. Lo que sí cambia es que el usuario recibe una instrucción útil y el equipo ve la causa real en los logs.
  - Las pruebas de v0 son técnicas, con una respuesta simulada. No cuentan como participantes humanos ni como mejora de uso.
  - **Causa encontrada (18/10/2026, 22:00–22:12, logs de Vercel y Rate Limit de Google AI Studio):** en el plan gratuito, el modelo Gemini 3.8 Flash permite 5 pedidos por minuto y **20 por día**. El pico de los últimos 28 días fue **31 de 20** pedidos diarios (límite superado) y 4 de 5 por minuto. Los tokens no son el problema (4,45K de 250K). En los logs, de 6 llamadas a `/api/traducir` entre 22:01 y 22:05, 2 respondieron 200 (las dos preguntas de seguimiento), 2 dieron 504 por tiempo agotado y 2 dieron 502 por un 429 de Gemini. Esto corrige nuestra hipótesis anterior de sobrecarga (503): no apareció ningún 503 en estos logs. Queda sin confirmar si los 429 vienen del límite diario o del por minuto, y si los reintentos automáticos (hasta 3 pedidos por clic) gastan cuota.
  - Consecuencia para el producto: con 20 pedidos por día, el servicio no alcanza para una segunda ronda con 5 personas (cada persona puede usar 2 o 3 pedidos, más los reintentos). El mensaje "esperá un minuto" tampoco es correcto cuando el límite es diario.

## Comparación

| Métrica | Antes (n y resultado) | Después (n y resultado) | Interpretación y límites |
| --- | --- | --- | --- |
| Éxito | 3 de 4 (v1, primer intento) | Pendiente | n muy pequeño. Convocatoria hecha por el equipo. Resultado retrospectivo, sin criterio fijado de antemano |
| Autonomía | 2 de 4 (v1) | Pendiente | Idem. Falta confirmar en qué momento se le explicó la herramienta a U3 |
| Valor | No medido. 1 de 4 declara haber usado los logros en su CV, sin evidencia todavía | Pendiente | La mayoría son declaraciones de intención, no uso real |

## Próximo paso

- **Incertidumbre pendiente:**
  - Si el límite diario del plan gratuito de Gemini (20 pedidos por día en Gemini 3.8 Flash, superado el 18/10/2026) alcanza para la ronda 2. Si no, hay que activar la facturación o cambiar a otro modelo con más cuota, y dejar de reintentar ante un 429.
  - Si los estudiantes realmente usan los logros en un CV o perfil (hoy solo U4 lo declara).
  - Si los reclutadores valoran estos perfiles (aprendizaje abierto de iteraciones anteriores).
- **Acción más barata, responsable y momento:**
  1. Confirmar los criterios de la ronda 2 y la prioridad elegida (todo el equipo, antes de implementar el cambio).
  2. Pedir a U4 la captura del CV y los datos pendientes de U1, U2 y U3 (quienes coordinaron las pruebas; Chen Wen Hua, Ibañez Ana Lucia y Cingolani Franco, esta semana).
  3. Resolver la cuota de Gemini (facturación o modelo con más cuota), pedir a v0 que no reintente ante un 429 y que el mensaje diga que se alcanzó el límite del día, verificar el recorrido principal y un caso de error, y repetir la prueba con 3 a 5 personas nuevas del mismo perfil (momento a definir por el equipo).

## Plan de la ronda 2 (pendiente, no realizada)

- Versión: v2, con el cambio de manejo de errores.
- Participantes: 5 personas nuevas, estudiantes de 3er o 4to año sin experiencia corporativa. Si participa alguien de la ronda 1, aclararlo en el registro porque ya conoce el recorrido.
- Tarea y definiciones: las mismas que en la ronda 1 (ver arriba), con los criterios propuestos confirmados antes de probar.
- Antes de empezar: repetir el recorrido principal con Gemini respondiendo de verdad (con una descripción completa y con una vaga). En una prueba del equipo con la v2 pública, el texto "nunca tuve la experiencia de trabajo… soy una persona muy organizada y comprometida" (30 palabras, sin proyecto) mostró el mensaje de error nuevo con el botón "Reintentar", y el texto y el rol se conservaron. Se esperaba una pregunta de seguimiento. Todavía no se sabe si fue saturación de Gemini o una respuesta mal formada ante esa entrada: hay que revisar los logs del servidor.
- Registrar además: dispositivo, hora de la prueba, si apareció el mensaje de error, cuánto esperó la persona y si entendió el mensaje y el botón "Reintentar".
- Resultados: pendiente. No se completan hasta que haya participantes reales.
- **Qué observar y qué decisión tomar según el resultado:**
  - Si el error de la IA vuelve a aparecer en la ronda 2: priorizar su corrección antes de seguir probando valor.
  - Si no vuelve a aparecer: mantener la versión y probar el valor en un contexto más real (uso del texto en una postulación).

## Datos pendientes de confirmar

- U1: en qué horario probó y qué ocurrió exactamente en el servidor en ese momento.
- U2: si los términos "Go-to-Market", "Buyer Persona" y "ROI" estaban en su descripción original.
- U3: en qué momento pidió la explicación (antes de abrir la página o ya usándola).
- U4: captura de pantalla del CV con el contenido usado.
