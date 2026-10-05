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
* **Control de errores:** Si algún campo está vacío o la descripción contiene menos de 20 caracteres, el sistema bloquea el envío y muestra un aviso indicando qué información falta completar.

---

## 3. Recortar el alcance y resolver los datos

| Componente | Estado en este MVP | Detalle |
| :--- | :--- | :--- |
| **Formulario y validación** | Funciona ahora | Captura rol y descripción; bloquea entradas vacías o insuficientes. |
| **Entrega de viñetas** | Funciona ahora | Muestra en pantalla los 3 logros calibrados y listos para copiar. |
| **Lógica de calibración** | Simulado / Local | Heurística basada en el banco de verbos y reglas estrictas del prompt calibrado. |
| **Cuentas y Login** | Fuera de alcance | No requiere usuario ni contraseñas para minimizar fricción de prueba. |
| **Exportación / Integraciones** | Fuera de alcance | No genera PDFs ni conecta por Zapier/Make en esta etapa. |

* **Datos de entrada:** Reales, provistos directamente por el estudiante que prueba la herramienta.
* **Datos de salida:** Formateados según las pautas de estilo junior validadas en el instrumento experimental.

---

## 4. Construir y mejorar conversando con la IA

* **Herramienta elegida:** Aplicación web autocontenida en un único archivo (`index.html`), accesible desde cualquier navegador sin requerir servidores ni instalaciones locales.
* **Acceso a la versión:** Archivo `index.html` disponible en la raíz del repositorio (abrir directamente con doble clic en el navegador).
* **Verificación técnica realizada:**
  * Se comprobó la respuesta ante campos vacíos o descripciones de menos de 20 caracteres (muestra alerta y detiene el proceso).
  * Se verificó la generación estricta de 3 viñetas utilizando verbos de soporte analítico (*Asistencia en...*, *Recopilación de...*, *Colaboración en...*), excluyendo términos de jerarquía senior (*Líder*, *Director*).
  * Se probó la acción del botón de copiado rápido al portapapeles.
* **Pendiente de probar:** Probar la herramienta con estudiantes fuera del equipo para evaluar si el vocabulario generado se percibe natural y preciso frente a proyectos cuantitativos específicos.

---

## 5. Probar con otra persona y registrar (mvp.md)

### Nuestro primer MVP

* **Usuario y situación:** Estudiante universitario avanzado de Cs. Económicas/Marketing buscando pasantía, armando su CV frente a la pantalla en blanco.
* **Valor y acción central:** Ingresar un trabajo práctico complejo en lenguaje coloquial y recibir 3 viñetas profesionales calibradas en tono junior para copiar en su perfil.
* **Forma de ejecución:** Archivo local `index.html` ejecutable en cualquier navegador web.
* **Métrica observada:** Estudiantes que completan la acción y evalúan los textos como "listos para pegar en su CV sin editar".

### Prueba e iteración

* **Quién probó (rol) y tarea:** Estudiante de 4to año de Comercialización. Tarea: ingresar el trabajo práctico más difícil de la carrera y evaluar si usaría los textos resultantes en una postulación real.
* **Qué ocurrió y cómo lo sabemos:** Completó la acción en menos de 2 minutos. Declaró que los verbos reflejaban su aporte real sin sonar exagerados, sintiéndose seguro de defender ese contenido en una entrevista.
* **Devolución concreta dada a la IA:** *"El formulario funciona rápido y el tono es creíble, pero si menciono herramientas técnicas específicas (como SPSS o Excel avanzado) en la descripción, el resultado no las nombra explícitamente."*
* **Ajuste realizado:** Se actualizó la lógica de extracción de texto para identificar herramientas técnicas ingresadas y mencionarlas dentro del bloque de recopilación y análisis de datos.
* **Próximo ajuste:** Integrar el formulario directamente a la API de lenguaje manteniendo el sistema de prompts limitadores para ofrecer mayor variedad de redacción sin perder el estándar junior.
