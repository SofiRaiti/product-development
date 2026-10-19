# Clase 7 — Del aprendizaje al primer MVP

## 1. Recuperar el punto de partida

* **Usuario y situación:** Estudiante universitario avanzado (3er o 4to año de Cs. Económicas/Marketing) sin experiencia laboral corporativa previa, situado en el momento exacto en que se sienta frente a la pantalla en blanco para armar su primer CV o actualizar su LinkedIn para aplicar a pasantías.
* **Valor que queremos entregar:** Transformar descripciones coloquiales de proyectos o investigaciones académicas en viñetas (*bullets*) de competencias profesionales con lenguaje de negocios de nivel Junior/Analista, eliminando la sensación de "CV vacío" y el autodescarte sin generar un "overselling" que provoque síndrome del impostor.
* **Única acción central del MVP:** El usuario ingresa el rol al que aspira y la descripción informal de un trabajo práctico o investigación de la facultad, y obtiene inmediatamente 3 viñetas redactadas en tono Junior/Analista listas para copiar y pegar en su CV o perfil.
* **Decisión tomada:** Priorizar el riesgo técnico calibrando el tono antes de desarrollar integraciones complejas. Se definieron reglas estrictas de prompt engineering que prohíben términos de alta jerarquía (como "líder" o "gerente") y priorizan verbos de soporte y análisis.
* **Duda técnica pendiente:** ¿Puede la IA calibrar este tono junior de forma consistente (meta: al menos 8 de 10 casos) sin requerir supervisión o edición humana manual?
* **Duda de valor pendiente:** ¿Tener estos logros redactados en lenguaje de negocios realmente evita el descarte por parte de los reclutadores frente a filtros de "años de experiencia"?

---

## 2. Diseñar un recorrido mínimo

* **Inicio:** El usuario accede a la herramienta y visualiza la consigna: *"Transformá tu trabajo práctico en logros profesionales para tu CV"*.
* **Acción:**
  1. Ingresa el rol deseado (ej. *Pasantía en Finanzas*, *Analista de Marketing*).
  2. Ingresa la descripción en sus propias palabras de su proyecto académico (qué hizo, qué herramientas usó y qué resultado obtuvo).
  3. Presiona el botón *"Traducir a logros profesionales"*.
* **Resultado:** La interfaz devuelve en pantalla exactamente 3 viñetas (*bullets*) de nivel Junior/Analista estructuradas por competencias profesionales, junto a un botón directo de *"Copiar al portapapeles"*.
* **Control de errores:** Si algún campo está vacío o la descripción no tiene detalle suficiente, el sistema no genera logros: muestra un aviso o hace una pregunta de seguimiento. Si el servicio de IA no responde, muestra un mensaje con botón "Reintentar" que conserva el texto.

---

## 3. Recortar el alcance y resolver los datos

| Componente | Estado en este MVP | Detalle |
| :--- | :--- | :--- |
| **Formulario y validación** | Funciona ahora | Captura rol y descripción; bloquea entradas vacías o insuficientes. |
| **Entrega de viñetas** | Funciona ahora | Muestra en pantalla los 3 logros calibrados y listos para copiar. |
| **Lógica de calibración** | Funciona ahora (versión actual) | La versión actual llama a un servicio de IA (Gemini) desde el servidor, con las reglas del prompt calibrado. *(La primera versión `index.html` usaba una heurística local simulada.)* |
| **Cuentas y Login** | Fuera de alcance | No requiere usuario ni contraseñas para minimizar fricción de prueba. |
| **Exportación / Integraciones** | Fuera de alcance | No genera PDFs ni conecta por Zapier/Make en esta etapa. |

* **Datos de entrada:** Reales, provistos directamente por el estudiante que prueba la herramienta.
* **Datos de salida:** Formateados según las pautas de estilo junior validadas en el instrumento experimental.

---

## 4. Construir y mejorar conversando con la IA

* **Herramienta elegida (versión actual):** Aplicación web hecha con v0 y desplegada en Vercel; el servidor llama a Gemini y la clave no queda expuesta en el navegador. *(Primera versión: aplicación autocontenida en un único archivo `index.html`.)*
* **Acceso a la versión:** https://generador-de-logros-para-cv.vercel.app (página pública, sin cuenta). Versión probada con personas en la Clase 8: **v1**. La **v2** (manejo de errores mejorado) está en la rama `v0/cv-achievement-translator` y el enlace público ya la sirve (confirmado el 18/10/2026 con captura de la interfaz de error nueva). La versión anterior `index.html` queda como historial.
* **Verificación técnica realizada:**
  * Se comprobó la respuesta ante campos vacíos o descripciones insuficientes (no genera logros).
  * Se verificó la generación de 3 viñetas con verbos de soporte analítico (*Asistencia en...*, *Recopilación de...*, *Colaboración en...*), excluyendo términos de jerarquía senior (*Líder*, *Director*).
  * Se probó la acción del botón de copiado rápido al portapapeles.
  * v2: v0 verificó con respuestas simuladas un fallo temporal (reintento exitoso) y un fallo definitivo (mensaje con "Reintentar").
* **Pendiente de probar:** el recorrido completo con Gemini respondiendo de forma estable, y una segunda ronda con personas nuevas. El 18/10/2026 se superó el límite diario del plan gratuito de Gemini (31 de 20 pedidos), lo que explica errores 429.

---

## 5. Probar con otra persona y registrar (mvp.md)

### Nuestro primer MVP

* **Usuario y situación:** Estudiante universitario avanzado (3er o 4to año) sin experiencia corporativa formal, frente a la pantalla en blanco armando su CV o LinkedIn para su primera pasantía.
* **Valor y acción central:** El estudiante elige el rol al que aspira, describe su proyecto académico más complejo y recibe 3 logros profesionales redactados en tono Junior/Analista, listos para copiar en su CV o perfil.
* **Forma de ejecución:** https://generador-de-logros-para-cv.vercel.app (ver sección 4).
* **Funciona / manual o simulado / fuera de alcance:** Funciona de verdad: formulario, contador de palabras, llamada a la IA desde el servidor, pregunta de seguimiento, botones de copiar. Manual: el registro de las pruebas lo hace el equipo. Fuera de alcance: cuentas, base de datos, historial, pagos, panel de administración.
* **Evidencia disponible y duda pendiente:** En el experimento manual (Clase 4), 5 de 10 estudiantes usaron el texto en su perfil o CV. En la prueba de banco (Clase 5), 9 de 10 textos mantuvieron el tono Junior sin edición. En la primera ronda con la versión pública (Clase 8), 3 de 4 participantes obtuvieron los logros en su primer intento; ninguno dijo tener menos confianza por saber que los genera una IA (declaración propia). Duda pendiente: si el servicio de IA tendrá cuota suficiente, si los estudiantes usan los logros en un CV real (hoy 1 de 4 lo declara, sin captura) y si los reclutadores valoran estos perfiles.
* **Métrica observada:** Éxito (completan la acción), Autonomía (completan sin ayuda) y Valor (usan los logros en un CV o perfil real). Detalle en `pruebas-y-mejoras-mvp.md`.

### Prueba e iteración

**Primera prueba (versión `index.html`, registrada por el equipo)**

* **Quién probó (rol) y tarea:** Estudiante de 4to año de Comercialización. Tarea: ingresar el trabajo práctico más difícil de la carrera y evaluar si usaría los textos resultantes en una postulación real.
* **Qué ocurrió y cómo lo sabemos:** Completó la acción en menos de 2 minutos. Declaró que los verbos reflejaban su aporte real sin sonar exagerados, sintiéndose seguro de defender ese contenido en una entrevista.
* **Devolución concreta dada a la IA:** *"El formulario funciona rápido y el tono es creíble, pero si menciono herramientas técnicas específicas (como SPSS o Excel avanzado) en la descripción, el resultado no las nombra explícitamente."*
* **Ajuste realizado:** Se actualizó la lógica de extracción de texto para identificar herramientas técnicas ingresadas y mencionarlas dentro del bloque de recopilación y análisis de datos.

**Segunda prueba (versión pública v1, Clase 8, 18/10/2026)**

* **Quién probó (rol) y tarea:** 4 estudiantes de 3er año sin experiencia corporativa formal (autodeclarado), U1 a U4. Tarea: "Estás por postularte a tu primera pasantía y querés poner un proyecto de la facultad en tu CV para que suene profesional." Sin indicaciones.
* **Qué ocurrió y cómo lo sabemos (relato de cada participante):** U2, U3 y U4 obtuvieron los 3 logros en su primer intento (U3 necesitó que le explicaran de qué se trataba). U1 vio repetidamente el error "No pudimos conectar con el servicio de IA" y pudo ver los logros unas 2 horas después. U4 declara haberlos usado en su CV (falta la captura).
* **Devolución concreta que dimos a la IA:** el pedido de análisis y de implementación está en `pruebas-y-mejoras-mvp.md`.
* **Cambio realizado y resultado de la nueva prueba:** v2 con registro del error real en los logs, hasta 2 reintentos con espera breve y un mensaje claro con botón "Reintentar". Los logs del 18/10/2026 mostraron que la causa era el límite diario del plan gratuito de Gemini (429) y tiempos agotados. La segunda ronda con personas nuevas todavía no se realizó.
* **Próximo ajuste:** resolver la cuota (activar facturación o usar un modelo con más cuota), no reintentar ante un 429 y mostrar que se alcanzó el límite del día, y repetir la prueba con 3 a 5 personas nuevas.
