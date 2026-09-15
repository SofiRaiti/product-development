# Diseño del Experimento — Iteración 2 (Prueba de Banco)

## 1. Evidencia de partida
En el experimento anterior (Wizard of Oz), comprobamos que entregar la experiencia académica traducida a lenguaje de negocios elimina el autodescarte (5 de 10 usuarios la implementaron). Sin embargo, descubrimos que si el tono es excesivamente corporativo, reactiva el síndrome del impostor en perfiles junior. La nueva incertidumbre es de factibilidad técnica: probar si la IA puede calibrar el tono automáticamente sin que el equipo lo edite manualmente.

## 2. Experimento elegido
- **Tipo:** Prueba de Banco (Evaluación técnica con datos históricos).
- **Justificación:** Es la forma más rápida y barata de probar el nuevo prompt limitador de tono antes de conectar automatizaciones complejas (Zapier) con usuarios reales.

## 3. Partes reales y simuladas
- **Real:** La generación del texto a través del modelo de IA y los datos de entrada (las 10 respuestas históricas reales de los estudiantes).
- **Simulado:** La interacción con el usuario (no participan usuarios nuevos; el equipo asume el rol de evaluador técnico).

## 4. Contrato experimental
- **Hipótesis:** Factibilidad técnica (podemos configurar un prompt que estandarice el tono junior automáticamente).
- **Pregunta de aprendizaje:** ¿El sistema automatizado genera textos que mantienen el tono Junior/Analista sin requerir ninguna corrección manual por parte del equipo?
- **Participantes / Escenarios:** 10 casos históricos (respuestas del formulario de la Iteración 1).
- **Acción observable:** Ejecución del prompt a ciegas y evaluación del texto resultante.
- **Métrica:** Tasa de éxito del prompt (cantidad de textos aprobados como "listos para enviar").
- **Criterio de éxito:** Al menos 8 de 10 textos cumplen el estándar sin requerir edición.
- **Limitación:** Esta prueba produce evidencia técnica, no evidencia de comportamiento o adopción de usuarios.

## 5. Alcance mínimo
- **Imprescindible:** Los 10 textos originales de los estudiantes y el prompt ajustado con límites de términos senior.
- **Fuera de alcance:** Automatización con Zapier/Make, envío de correos, landing page o interfaz web. 

## 6. Decisiones humanas del equipo
- Se decidió priorizar la resolución del Riesgo Técnico (calibración del prompt) antes de volver a exponer el experimento al Riesgo de Mercado.
- El equipo definió el criterio estricto de 8 sobre 10 casos.
- El equipo aprobó reducir el alcance para no construir la automatización (Zapier) hasta no comprobar que la IA no entregaría textos incongruentes.
