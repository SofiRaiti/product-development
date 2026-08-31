# Lean Product Canvas — Traductor de Valor Académico a Corporativo

> Este canvas contiene hipótesis. La evidencia surgirá de observar y experimentar.

## 1. Problema de negocio
Estudiantes universitarios avanzados sin experiencia corporativa tienen dificultad para traducir sus proyectos académicos complejos al lenguaje de negocios al redactar su primer CV o LinkedIn, lo que provoca perfiles sub-optimizados que solo listan materias aprobadas. Lo sabemos por la existencia de guías especializadas (ej. Miss CV) y la observación de pares. Todavía necesitamos comprobar si lograr esta traducción evita realmente el rechazo del mercado.

## 2. Resultados de negocio
- Aumentar la tasa de perfiles completados (estudiantes que logran redactar y exportar la descripción de al menos un proyecto académico complejo, como análisis de cadenas de valor o logística) de [pendiente de medir] a [objetivo] durante su primera sesión de uso de la herramienta.
- Aumentar la cantidad de postulaciones enviadas por usuario (pasar de la parálisis a la acción) de [pendiente de medir] a [objetivo] en los primeros 15 días posteriores a la optimización de su perfil.

## 3. Usuarios y clientes
- **Usuario principal:** Estudiantes universitarios de 3er y 4to año sin experiencia corporativa formal, que se encuentran activamente buscando pasantías o primer empleo.
- **Cliente/Decisor:** El mismo estudiante (considerando un modelo inicial de adopción directa B2C, gratuito o freemium).
- **Influenciadores:** Pares universitarios, centros de estudiantes y creadores de contenido sobre empleabilidad juvenil.

## 4. Necesidades y resultados del usuario
Cuando me siento frente a la pantalla en blanco para armar mi CV o LinkedIn para mi primera pasantía, quiero poder explicar la complejidad técnica de mis trabajos prácticos universitarios usando lenguaje profesional corporativo, para sentir seguridad sobre el valor de mi perfil y evitar que los reclutadores me descarten automáticamente.

## 5. Ideas de solución

### Asistente Generativo de Habilidades (Solución Seleccionada)
- **Propuesta:** Una plataforma web enfocada en automatización e inteligencia donde el estudiante ingresa en lenguaje coloquial qué hizo en la universidad (ej: "hice encuestas para evaluar familias de tránsito" o "analicé la exportación del limón y la yerba mate") y el sistema le devuelve bullets de impacto (ej: "Diseño de instrumentos de investigación de campo", "Análisis estratégico de logística agroindustrial").
- **Valor para el usuario:** Elimina la fricción técnica de traducción, aportando el vocabulario y la estructura de resultados que el estudiante desconoce.
- **Tecnología central:** Aplicación web sencilla integrada con una API de IA generativa configurada con prompts específicos de reclutamiento.
- **Datos necesarios:** Inputs crudos del usuario sobre sus tareas y metodologías universitarias.
- **Riesgo principal:** Que el texto generado suene demasiado artificial y los reclutadores lo perciban como inauténtico.
- **Prototipo inicial:** Formulario online conectado mediante Zapier a una cuenta de IA, que devuelva la redacción formateada al correo del usuario.
- **Dependencias:** Ninguna infraestructura física ni aprobación de terceros.
- **Estado:** Idea no validada.

## 6. Hipótesis principales

### Hipótesis de problema
Creemos que los estudiantes universitarios sin experiencia subestiman sus proyectos académicos porque no conocen el vocabulario corporativo para describirlos. Lo sabremos si, al mostrarles proyectos universitarios estándar, más del 70% no sabe qué competencias transversales listar a partir de ellos.

### Hipótesis de valor
Creemos que un asistente guiado de redacción logrará que los estudiantes estructuren perfiles atractivos. Lo sabremos si al menos el 60% de los usuarios que prueban la herramienta califica el texto resultante como "listo para usar" y superior a su versión original.

### Hipótesis de comportamiento
Creemos que los estudiantes aplicarán esta herramienta directamente en su búsqueda laboral. Lo sabremos si más del 50% de los testeadores copian y pegan los bullets generados en sus perfiles reales de LinkedIn o CVs durante la primera semana.

### Hipótesis de factibilidad
Creemos que podemos configurar un prompt que transforme descripciones académicas en competencias corporativas precisas y naturales. Lo sabremos si reclutadores o profesores evalúan de forma anónima una muestra de textos generados y los validan como propios de un perfil junior sólido.

## 7. Lo más importante por aprender
¿Lograr que el estudiante traduzca y redacte su experiencia académica en lenguaje corporativo aumenta genuinamente su confianza para postularse a más ofertas laborales, o sigue autodescartándose al ver que el aviso pide "años de experiencia"?

## 8. Experimento mínimo

- **Hipótesis que prueba:** Hipótesis de valor y comportamiento (el usuario valora la traducción y se anima a aplicarla).
- **Objetivo:** Validar si entregar el trabajo académico ya traducido a lenguaje de negocios elimina el bloqueo de la hoja en blanco.
- **Tipo de experimento:** Concierge / Wizard of Oz digital.
- **Herramienta:** Formulario gratuito (Google Forms o Tally) distribuido por WhatsApp. El procesamiento se hace manualmente por el equipo usando ChatGPT en el backend, y el resultado se envía por correo al usuario.
- **Participantes:** 10 estudiantes de 3er o 4to año de la facultad que estén buscando empleo activamente.
- **Duración:** 1 semana.
- **Tarea:** El estudiante debe completar un formulario explicando con sus palabras un TP largo y complejo. Recibirá a las pocas horas 3 alternativas de "logros profesionales" para sumar a su CV.
- **Métrica:** Tasa de implementación (cuántos usuarios actualizan sus perfiles o se postulan a una búsqueda usando el texto).
- **Criterio de éxito:** Al menos 4 de los 10 participantes utilizan el texto provisto en su LinkedIn o en un CV enviado a una empresa real.
- **Criterio de fracaso:** Menos de 4 participantes lo utilizan, aduciendo que la redacción no les sirve, suena irreal o no los representa.
- **Aprendizaje esperado:** Descubrir si resolver la barrera técnica de redacción es suficiente para que el usuario avance en el embudo de contratación.
- **Limitaciones:** El experimento no prueba de forma automatizada la tecnología, ya que el equipo curará las respuestas manualmente para garantizar calidad en esta primera etapa.
