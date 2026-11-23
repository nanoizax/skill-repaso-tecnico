# skill-repaso-tecnico

**Al terminar cada tarea de código, un repaso de 90 palabras: qué usaste, por qué, dónde puede fallar y qué comprobar. Y al final del día, el resumen listo para la daily.**

Una skill para tu herramienta de desarrollo. Sin quiz, sin leer archivos de más y con un tope de texto para no gastar tu cuota.

---

## Para qué fue creada

Esta skill fue creada **para la comunidad**. Cuando una herramienta escribe el código por ti, es fácil cerrar la tarea sin saber explicar qué se hizo ni por qué. El día que te pregunten en una daily, en una revisión de código o en una entrevista, la respuesta no sale. Aquí se cierra ese hueco con lo mínimo necesario, en el momento justo: antes de hacer commit.

## ¿Qué es esto?

Dos modos en un solo `SKILL.md`:

1. **Modo tarea (automático):** al cerrar una tarea y antes de ofrecer commit, push o PR, resume los conceptos técnicos que se usaron.
2. **Modo jornada (cuando lo pides):** junta los repasos de todas las tareas de la sesión en un resumen del día, con la frase lista para la daily.

## El problema que resuelve

- Entregas código que funciona pero **no sabes explicar** por qué se hizo así.
- En la daily tienes que acordarte de lo de ayer y no te acuerdas.
- Si algo se rompe, **no sabes en qué parte mirar**, porque no hay rastro de las decisiones.
- Das por buena una tarea que **nadie comprobó** (por ejemplo, un proyecto sin pruebas automáticas).
- Con el tiempo, lo que sabías de buenas prácticas se oxida porque ya no lo practicas.

## Para qué sirve

- Entender qué se hizo y por qué, **sin leer 50 páginas de documentación**.
- Ver **dónde puede fallar** cada decisión y qué conviene revisar antes de dar la tarea por buena.
- Llegar a la daily con **2 o 3 frases en primera persona**, listas para decirlas.
- Tener un archivo con el resumen del día anterior a primera hora de la mañana.
- Si algo explota, saber en qué parte mirar.

## Cuándo usarla

- Al terminar cualquier tarea de programación, en cualquier lenguaje.
- Cuando trabajas con una herramienta que escribe mucho código por ti.
- Cuando tienes daily, revisión de código o entrevista y quieres explicar lo que hiciste.

## Cuándo **no** usarla

- En tareas sin código (preguntas, lectura, charla). No se activa.
- Si ya tienes un proceso de documentación de decisiones que cubre lo mismo.
- Si buscas estudiar con preguntas y respuestas: esta skill explica, no te examina.

## Cómo instalarla

1. Descarga este repositorio y copia `SKILL.md` en una carpeta llamada `repaso-tecnico` dentro del directorio de skills de tu herramienta de desarrollo.
2. Listo. El modo tarea se activa solo al cerrar una tarea de código. Para el modo jornada, escribe "repaso del día" o "para la daily".
3. **(Opcional)** El resumen del día se guarda en `~/repasos-tecnicos/AAAA-MM-DD.md`. Si prefieres otra carpeta, dilo en tu primer mensaje del día.

Cada herramienta guarda sus skills en un sitio distinto; consulta la documentación de la tuya.

## Ejemplo

Tarea: un script que consulta 5 URLs a la vez. Al cerrarla, antes de preguntar por el commit, sale esto:

```
Corrutinas (descargas.py): funciones que se pausan sin bloquear el hilo; esperan red.
  Ojo: si el límite de tiempo cancela una tarea y el código atrapa mal la cancelación, sigue ejecutándose.
gather (descargas.py): lanza varias corrutinas a la vez. Por eso el total fue 1.50 s y no la suma.
Si te preguntan: usé corrutinas porque el trabajo es esperar red, y un límite de tiempo por consulta
  para que una lenta no frene a las demás.
Revisar: el script se corrió una sola vez y con tiempos aleatorios.
```

Y al final del día, con "repaso del día":

```
Migración de componentes: componentes por niveles para quitar duplicados y
estado levantado en la página (ya unos 10 useState).
Para la daily: Migré la interfaz a una estructura por niveles para eliminar componentes
duplicados y concentré el estado en la página. El lint pasó de 16 errores a 0.
Pendiente de revisar: el repo no tiene script de pruebas; recorrer las pantallas a mano.
```

## Qué incluye

- **Modo tarea:** máximo 3 conceptos y 90 palabras, 2 líneas por concepto, solo conceptos nuevos de esa sesión.
- **Modo jornada:** una línea por tarea, conceptos sin repetir, frase para la daily y pendientes juntos. Tope de 150 palabras.
- **Archivo diario** fuera de tus repositorios, sin nombres de empresas ni de clientes.
- **Ahorro de cuota:** no lee archivos ni corre herramientas para armar el repaso. Usa solo lo que ya está en la conversación.

## Límites honestos

- **Leer un repaso no es memorizarlo.** Ayuda a entender y a explicar, pero para retener de verdad hace falta practicar sacando las respuestas de tu cabeza. La skill no te examina a propósito, para no gastar cuota.
- **El "por qué" puede ser una racionalización.** Si la herramienta lo dedujo del código y no de lo que hablaron, la skill lo avisa. Contrástalo tú.
- **No sustituye entender la arquitectura** de tu proyecto, solo explica lo que se hizo en cada tarea.
- **Solo sabe lo que hay en la conversación.** Si abres una sesión nueva, el modo jornada usa el archivo guardado del día anterior.
- Si la tarea no tuvo decisiones técnicas, el repaso es una sola línea.

## Skills relacionadas

[`skill-commits-limpios`](https://github.com/nanoizax/skill-commits-limpios) para que el commit que sigue al repaso salga bien hecho y firmado por una persona.

## Licencia y autoría

[MIT](LICENSE) · Hecha por Leandro Manuel Perez Montañana.
Más skills y herramientas gratis en **[soytegno.sonholab.com](https://soytegno.sonholab.com)** · TikTok [@soytegno](https://www.tiktok.com/@soytegno)
