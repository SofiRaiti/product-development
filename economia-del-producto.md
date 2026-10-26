# Economía del producto — Traductor de Valor Académico a Corporativo

- **Fecha, moneda y período:** 26/10/2026, USD, por mes.
- **Usuario, valor y evidencia disponible:** estudiantes de 3er y 4to año sin experiencia corporativa formal reciben 3 logros en tono Junior para su CV. Evidencia de uso: en el experimento manual, 5 de 10 usaron el texto; en la primera ronda con la versión pública, 3 de 4 obtuvieron los logros en su primer intento. **No hay evidencia de disposición a pagar.**
- **Quién pagaría y por qué:** un centro de carreras universitario (B2B2C), para que sus egresados accedan con más facilidad a pasantías. **Hipótesis**: todavía no se habló con ningún centro de carreras. El estudiante usa la herramienta sin pagar.
- **Unidad económica:** un estudiante activo por mes. Supuesto de volumen: 2 usos por estudiante por mes y 500 usos por mes por cuenta institucional (unos 250 estudiantes activos).

## Números iniciales

| Concepto | Importe y unidad | Tipo | Fuente o motivo |
| --- | --- | --- | --- |
| Ingreso por unidad | USD 9 por estudiante activo por mes | Estimación | Decisión del equipo, sin fuente externa |
| Costo variable: IA (Gemini) | USD 0,0093 por estudiante por mes (2 usos × 2 llamadas × USD 0,002325) | Estimación | Por llamada: ~1.100 tokens de entrada y ~400 de salida (estimados) a USD 0,75 y 3,75 por millón (referencia: eesel.ai, oct. 2026; verificar en ai.google.dev; los precios se duplican desde 01/2027) |
| Costos fijos por mes | Hosting Vercel Pro: USD 20 | Referencia | vercel.com/pricing, consultado el 19/10/2026 (el plan Hobby no permite uso comercial) |
| Otros costos fijos | Dominio; tiempo del equipo para mantenimiento y atención | Pendiente | Falta investigar el precio del dominio y estimar horas y valor horario |
| Inversión inicial | MVP construido con planes gratuitos; sin desembolso conocido | Pendiente | Falta valorar el tiempo del equipo |

## Resultado y escenario

- **Contribución por unidad = ingreso − costo variable.** Base: 9 − 0,0093 ≈ **USD 8,99** por estudiante por mes.
- **Escenario exigente** (cambia solo el precio, a USD 1): 1 − 0,0093 ≈ **USD 0,99**.
- Con 250 estudiantes activos, la contribución por cuenta sería de unos USD 2.248 (base) y USD 248 (exigente) por mes. Para cubrir solo los USD 20 de hosting harían falta unos 3 estudiantes (base) o 21 (exigente).
- **Qué significa:** el costo de IA es muy bajo, por lo que el resultado depende casi por completo del precio y de que alguien pague. **Qué no demuestra:** no es ganancia (faltan costos fijos pendientes), ni prueba demanda o disposición a pagar. Hoy el plan gratuito de Gemini permite solo 20 pedidos por día; con cobro habría que pasar a un plan pago.

## Primeros clientes

- **Canal:** contactos de docentes y de la facultad para llegar al centro de carreras de la Universidad Austral. Costo monetario: pendiente (no hay gasto publicitario). Esfuerzo: tiempo del equipo para escribir, reunirse y hacer demostraciones.
- **CAC y repago:** no calculables, porque todavía no hay clientes.

## Supuesto por comprobar

- **Supuesto elegido:** un centro de carreras pagaría USD 9 por estudiante activo por mes.
- **Prueba:** enviar una propuesta de una página (prueba de 1 mes y luego USD 9 por estudiante activo por mes) al centro de carreras de la Universidad Austral y a hasta 2 más. **Acción observable:** que agenden una reunión con quien decide o expresen por escrito su interés en la prueba. **Registro:** tabla con fecha, cargo del contacto (sin nombre), canal, respuesta y acción.
- **Criterio previo:** al menos 1 de los 3 centros contactados agenda reunión o confirma por escrito en dos semanas (criterio exploratorio). **Decisión:** si se cumple, definir condiciones de la prueba y el precio; si no, revisar precio, pagador o propuesta de valor antes de descartar el problema. Un interés escrito no prueba pago efectivo.
- **Responsable y fecha:** todo el equipo. Propuesta enviada antes del 30/10/2026; resultados revisados el 13/11/2026.
