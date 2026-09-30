# aprendizaje-y-mvp.md

## Lo que entiendo de sus experimentos (Recuperar)

- **Querían comprobar:** En la iteración con usuarios, si entregar la experiencia académica ya traducida elimina el autodescarte[cite: 8]. En la Iteración 2 (Prueba de Banco), si es factible configurar un prompt de IA que estandarice un tono Junior/Analista automáticamente sin edición del equipo[cite: 10].
- **El criterio de éxito era:** Al menos 4 de 10 usuarios utilizando el texto en su CV/LinkedIn (Iteración 1)[cite: 8]. Al menos 8 de 10 textos cumpliendo el estándar de tono sin corrección humana (Iteración 2)[cite: 10].
- **Construyeron o probaron:** Un Formulario "Wizard of Oz" operado manualmente por el equipo[cite: 8], seguido de una ejecución de un prompt de IA a ciegas sobre las 10 respuestas históricas para evaluar su precisión técnica limitando términos "senior"[cite: 10, 12].
- **El resultado registrado fue:** 5 usuarios implementaron los textos en la primera prueba[cite: 8]. En la iteración técnica, 9 de los 10 textos mantuvieron el tono correcto sin requerir edición humana[cite: 8]. 

### Chequeo rápido
- Hipótesis definida antes de probar: Sí[cite: 8, 10]
- Criterio definido antes de probar: Sí[cite: 8, 10]
- Hay resultados u observaciones: Sí[cite: 8, 11]
- Estado de la iteración: Lista para analizar.

---

## 2. Resultado

| Qué pasó | Cómo lo sabemos |
|---|---|
| 5 de los 10 estudiantes copiaron y pegaron los logros generados en su perfil público o enviaron CVs a búsquedas activas. | Capturas de pantalla de perfiles de LinkedIn actualizados y confirmaciones por chat del envío de CVs[cite: 8]. |
| 2 estudiantes rechazaron los textos porque palabras como "Lideré una estrategia de expansión" les generaron inseguridad para una entrevista técnica. | Feedback cualitativo a los 7 días (les dio miedo hacer *overselling* de un trabajo grupal)[cite: 11]. |
| La corrección técnica del prompt (restringiendo palabras como "Director" o "Impacto global") funcionó en 9 de 10 casos históricos. | Evaluación técnica a ciegas realizada por el equipo sobre las respuestas previas (Prueba de Banco)[cite: 8, 12]. |

- **Resultado frente al criterio:** Se alcanzó en ambas pruebas (5/10 usuarios > 4/10 esperados; 9/10 de precisión técnica > 8/10 esperados)[cite: 8, 10].
- **Algo que salió distinto de lo esperado:** El lenguaje corporativo demasiado ambicioso puede ser contraproducente en perfiles sin experiencia, reactivando el síndrome del impostor que se intentaba eliminar[cite: 8, 11].

---

## 3. Aprendizaje

- **Aprendimos que:** Resolver la fricción técnica de redacción efectivamente destraba la parálisis y lleva a la acción[cite: 8], siempre y cuando la traducción esté estrictamente limitada a verbos de soporte o asistencia (tono Junior) para que el estudiante no sienta que está mintiendo[cite: 11, 12].
- **Todavía no sabemos si:** Los reclutadores de las empresas realmente se sentirán atraídos por estos perfiles "traducidos" y si los usuarios confiarán en un flujo que sea 100% automatizado, sin el toque humano inicial[cite: 8].

---

## 4. Decisión

- **Elegimos:** Avanzar.
- **Porque:** Ya validamos que los estudiantes valoran la herramienta y la usan (riesgo de comportamiento resuelto)[cite: 8], y que la IA puede mantener el tono adecuado de forma autónoma (riesgo técnico resuelto)[cite: 8].
- **Próximo paso:** Construir el Concierge Automatizado (Formulario > Zapier > IA > Mail)[cite: 8].

---

## 5. Punto de partida del MVP

- **Usuario:** Estudiante universitario avanzado (3er o 4to año) sin experiencia corporativa formal[cite: 8].
- **Situación:** Está frente a la pantalla en blanco armando su perfil para su primera pasantía y no sabe cómo traducir sus investigaciones o TP complejos[cite: 9, 12].
- **Valor que queremos entregar:** Traducción instantánea y calibrada de su capital académico a lenguaje de mercado para eliminar la fricción de escritura y darle seguridad[cite: 7].
- **Una sola cosa que el MVP debe permitir hacer:** El estudiante completa un formulario sencillo y recibe instantáneamente (vía automatización) logros profesionales formateados en su correo[cite: 8].
- **Qué vamos a medir cuando lo use una persona:** Tasa de implementación automatizada (qué porcentaje de usuarios pega esos resultados en su LinkedIn o CV público durante la primera semana)[cite: 8].
