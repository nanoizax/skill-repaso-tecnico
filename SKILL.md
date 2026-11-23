---
name: repaso-tecnico
description: Repaso técnico mínimo de una tarea de código y repaso unificado de la jornada. Modo tarea, automático: al terminar una tarea, justo antes de ofrecer commit, push o PR, dice qué conceptos se usaron, por qué, dónde pueden fallar y qué revisar. Modo jornada, bajo demanda: cuando se diga "repaso del día", "resumen de la jornada", "para la daily" o "repásame todo", junta los repasos de todas las tareas de la sesión en uno solo. Úsala SIEMPRE al cerrar una tarea de programación antes de ofrecer commit, push o PR, o cuando se diga "listo", "terminamos", "repaso" o "qué usamos". Sirve para cualquier lenguaje.
---

# Repaso técnico

Con una herramienta de desarrollo se programa rápido, pero se puede terminar sin saber explicar lo que quedó hecho. Esta skill deja, al cerrar cada tarea, lo mínimo para entenderlo, comprobarlo y contarlo.

## Modo tarea (automático)

Una vez, al cerrar la tarea y antes de preguntar por commit, push o PR, en el mismo mensaje. Sin preguntar ni hacer quiz. No aplica a tareas sin código ni a mitad de tarea.

**Límites duros (la cuota de la gente es corta):**
- Máximo 3 conceptos y 90 palabras. Cada concepto, 2 líneas.
- No leas archivos ni corras herramientas para el repaso. Usa lo que ya está en la conversación; si no sabes algo, escribe "no verificado".
- Solo conceptos nuevos: si ya se explicaron antes en esta sesión, no los repitas.
- Sin saludos, sin resumen de la tarea, sin lista de archivos.
- Sin decisiones técnicas: una línea, "Sin decisiones técnicas nuevas."

**Qué entra:** decisiones reales que alguien preguntaría en una revisión: concurrencia, datos (transacción, índice, caché), seguridad, estructura (patrón, capas, librería), algoritmos o protocolos relevantes. Elige las 3 que más pesan.

**Formato:**
**Concepto** (`archivo`): qué es, en una frase exacta. Por qué aquí, la razón real. **Ojo:** dónde falla o qué cuesta (solo si es real).
**Si te preguntan:** una oración para la daily.
**Revisar:** qué comprobar antes de dar la tarea por buena (omitir si todo está comprobado).

## Modo jornada (bajo demanda)

Cuando se pida el repaso del día, la jornada o "para la daily": une los repasos de todas las tareas de la sesión, sin releer código ni volver a analizar.

- Una línea por tarea: qué se hizo y su concepto clave.
- Conceptos repetidos, una sola vez.
- **Para la daily:** 2 o 3 frases en primera persona, listas para decirlas: qué hice, qué decisiones técnicas tomé y por qué.
- **Pendiente de revisar:** junta las líneas "Revisar" de todas las tareas, sin duplicados.
- Tope: 150 palabras.
- Ignora las tareas que el usuario haya marcado como prueba o que no sean del trabajo del que se hace la daily.
- Al guardar el archivo, nunca pongas nombres de empresas, clientes ni repositorios: solo número de tarea y descripción genérica.
- Al final, guarda el resultado en `~/repasos-tecnicos/AAAA-MM-DD.md` (una sola escritura, fuera de los repositorios) para tenerlo a primera hora del día siguiente aunque la sesión ya no exista. Si el usuario prefiere otra carpeta, usa esa. Si no hay repasos en esta conversación pero existe el archivo de hoy o de ayer, léelo y muéstralo.

## Calidad

1. Exacto antes que bonito: una definición floja es peor que ninguna.
2. Razón honesta: "el proyecto ya lo usaba" vale. Si el porqué lo dedujiste del código y no de lo hablado, dilo.
3. Atado a la tarea, nada de manual.
4. Cada punto debe permitir responder qué hace, por qué se eligió y dónde mirar si explota.

## Ejemplo (modo tarea)

**Corrutinas** (`PhotoService.kt`): funciones que se pausan sin bloquear el hilo. Esperan red y el proyecto ya las usaba. **Ojo:** una excepción en `launch` sin handler se pierde.
**Transacción** (`save()`): foto y registro se guardan juntos o no se guardan.
**Si te preguntan:** corrutinas para no bloquear hilos al esperar red, transacción para no dejar datos a medias.
**Revisar:** sin pruebas de qué pasa si falla el correo tras guardar.

El idioma de salida es el del usuario.
