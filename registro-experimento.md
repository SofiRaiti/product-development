# Registro del experimento — Traductor de Valor Académico a Corporativo

## 1. Punto de partida
- **Hipótesis priorizada:** Hipótesis de valor y comportamiento (el usuario valora la traducción y se anima a aplicarla)[cite: 1].
- **Pregunta de aprendizaje:** ¿Lograr que el estudiante traduzca y redacte su experiencia académica en lenguaje corporativo aumenta genuinamente su confianza para postularse a más ofertas laborales, o sigue autodescartándose?[cite: 1].
- **Experimento mínimo:** Concierge / Wizard of Oz digital. Formulario distribuido por WhatsApp, procesado manualmente con IA y devuelto por correo[cite: 1].
- **Métrica:** Tasa de implementación (cuántos usuarios actualizan sus perfiles o se postulan usando el texto)[cite: 1].
- **Criterio de éxito:** Al menos 4 de los 10 participantes utilizan el texto provisto en su LinkedIn o en un CV[cite: 1].

## 2. Posición inicial en la curva de la verdad
- **Evidencia disponible:** La falta de experiencia formal es percibida como el principal obstáculo para conseguir empleo[cite: 2]. Guías de empleabilidad confirman la necesidad de traducir logros académicos[cite: 2].
- **Incertidumbre pendiente:** Si entregar el texto ya redactado elimina el autodescarte en la postulación[cite: 1].
- **Inversión autorizada:** Mínima. Formulario gratuito, uso de IA manual, 1 semana de duración. 

## 3. Instrumento construido por la IA
- **Tipo de instrumento:** Formulario web (Wizard of Oz) + Prompt de calibración.
- **Enlace o archivo:** `instrumento-experimental.md` (Ver archivo 1 del repositorio).
- **Qué incluye:** Recolección de datos crudos sobre proyectos académicos (ej. investigaciones de mercado, análisis agroindustriales) y un sistema manual de devolución de logros corporativos.
- **Qué quedó fuera:** Plataforma web nativa, automatización con Zapier/API, base de datos automatizada y funcionalidades de MVP[cite: 1].

## 4. Ejecución
- **Fecha y contexto:** Septiembre 2026. Distribución orgánica a través de grupos de la facultad.
- **Participantes, escenarios, fuentes o datos:** 10 estudiantes de 3er y 4to año sin experiencia corporativa formal, que se encuentran activamente buscando pasantías o primer empleo[cite: 1]. Se solicitó consentimiento informado para el uso de las respuestas con fines académicos y los datos personales fueron anonimizados en el registro.
- **Tarea realizada:** Los usuarios completaron el formulario con sus TPs. El equipo procesó los textos en 24 horas y los envió. Se midió la implementación 7 días después.
- **Resultados obtenidos:** 10 completaron el envío. 5 usuarios copiaron y pegaron los bullets en su LinkedIn o enviaron CVs reales (esto se constató mediante capturas de pantalla de los perfiles de LinkedIn actualizados y confirmación por chat del envío del CV a búsquedas activas). 3 usuarios valoraron el texto pero no aplicaron a ninguna oferta.
- **Anomalías observadas:** 2 usuarios expresaron que los bullets generados sonaban "demasiado profesionales" y sintieron que si los publicaban iban a quedar como mentirosos en una entrevista técnica.

## 5. Evidencia
- **A favor:** 5 de 10 participantes implementaron el cambio, superando el umbral de 4 definido como éxito[cite: 1]. Demostraron una disminución en el autodescarte, evidenciado por el cambio de comportamiento real (verificado con capturas de pantalla y comprobantes de postulación).
- **En contra:** 2 casos de fricción donde el lenguaje corporativo excesivo reactivó el síndrome del impostor, generando el efecto contrario.
- **Interpretación del equipo:** Resolver la fricción técnica de redacción destraba la postulación, pero el texto no puede ser genérico corporativo; debe calibrarse estrictamente a un "nivel Junior/Analista" para resultar creíble para el propio estudiante.
- **Limitaciones:** El experimento no prueba de forma automatizada la tecnología, ya que el equipo curó las respuestas[cite: 1]. No sabemos aún la tasa de respuesta de los reclutadores.

## 6. Aprendizajes
- **Qué aprendimos:** El puente entre el mundo académico y corporativo existe y destraba la acción. Los estudiantes están dispuestos a publicar proyectos universitarios si se les da el marco adecuado.
- **Qué continúa siendo un supuesto:** Creer que el mercado laboral no descartará automáticamente estos perfiles en los filtros ATS[cite: 2].
- **Cambios realizados o propuestos:** Ajustar el prompt de generación (backend) limitando adjetivos de senior management y priorizando verbos de soporte analítico y asistencia estratégica.

## 7. Estado de la evidencia y próxima iteración
- **Respaldada, no respaldada o inconclusa:** Respaldada.
- **Comparación con el criterio:** 5 usuarios implementaron > Criterio de 4 usuarios[cite: 1].
- **Decisión de iteración:** Avanzar hacia la siguiente incertidumbre (Factibilidad técnica y Deseabilidad del reclutador).
- **Justificación:** Ya comprobamos que el usuario estudiante lo desea y lo usa (comportamiento). Ahora debemos probar si podemos automatizar la calidad de esa entrega y si a las empresas realmente les interesa leerlo.
- **Próxima incertidumbre por reducir:** Hipótesis de factibilidad (configurar el prompt vía API) y validar si los reclutadores consideran estos perfiles atractivos para posiciones trainee.

## 8. Nueva posición en la curva de la verdad
- **Evidencia incorporada:** Adopción real de 5 usuarios. Feedback cualitativo sobre calibración del tono.
- **Inversión que se justifica ahora:** Construcción de un "Concierge automatizado" (Formulario conectado vía Zapier a OpenAI) para evaluar si el prompt ajustado funciona sin curaduría humana en tiempo real.
- **Qué todavía no se justifica construir:** Interfaz web completa con perfiles de usuario, bases de datos o modelo de pago.
