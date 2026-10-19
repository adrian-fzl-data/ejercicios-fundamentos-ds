# Proyecto: Práctica Estimación de Precios

## Contexto
- Soy estudiante de 2º de Ingeniería de Datos (Universidad de Oviedo).
- Práctica de regresión: se estiman precios de mercado de ordenadores tomando como punto de partida del dataset "data/laptops_Dataset.csv".
- Entorno: Python en `venv/`, dependencias en `requirements.txt`.
- Pautas del enunciado: Imagina que una empresa de re-commerce (reventa de tecnología) quiere expandirse al mercado de Oriente Medio, concretamente a Egipto. Te han entregado un archivo "bruto" extraído mediante web scraping en noviembre de 2025. Su objetivo es claro: necesitan un tasador automático. Quieren saber si, basándose en las especificaciones técnicas, podemos predecir el precio de mercado con un margen de error menor al 5%.
- Objetivo del ejercicio: 
Tu misión final no es entregar un archivo .ipynb con una regresión lineal y ya está. Tu objetivo es construir un Banco de Pruebas (Benchmark) donde sometas a competición a todos los "contendientes" que hemos visto en el curso:
- Regresión Lineal: Tu línea base (Baseline). Es sencilla e interpretable, pero ¿es suficiente para capturar la complejidad del mercado?
- Random Forest / XGBoost: Los reyes del dato tabular. ¿Son capaces de manejar las relaciones no lineales entre la RAM, el procesador y el precio sin sobreajustar (overfitting)?

Para decidir cuál es el ganador, no te fijarás solo en un número. Deberás realizar un testeo cruzado basado en tres pilares:
1. **Precisión Métrica**: Deberás presentar una tabla comparativa final con los resultados de cada modelo sobre el set de Test (datos que el modelo nunca ha visto):

    - MAE (Mean Absolute Error): ¿Cuántos euros se desvía el modelo en promedio?

    - R² (R-Cuadrado): ¿Qué porcentaje de la variabilidad del precio estamos explicando realmente?
2. **Análisis de Residuos**: Un modelo puede tener un MAE bajo pero fallar estrepitosamente en los portátiles de gama alta. ¿El modelo infravalora sistemáticamente los ordenadores de lujo? ¿Hay algún sesgo en marcas específicas?
3. **Interpretabilidad vs. Performance**: A veces, un modelo que falla por 5€ más que otro es mejor porque nos permite explicarle al departamento de compras por qué el precio es ese (usando los coeficientes o valores SHAP). Deberás justificar tu elección final basándote en este equilibrio.

Instrucciones para la Entrega Final
Tu notebook debe concluir con una Sección de Juicio Crítico:
- Tabla de Benchmark: Comparativa visual de las métricas de todos los modelos testeados.
- Justificación de Selección: Un texto breve donde digas: "Elijo el modelo [X] porque, aunque su R² es similar al de [Y], presenta una mayor estabilidad en los residuos y una menor complejidad computacional".
- Predicción en Producción: Ejecuta tu modelo ganador con unos datos de test para demostrar que está listo para su uso real.


## Tu rol: tutor, no autor
- `Práctica Estimación Precios.ipynb` es mi trabajo. Lo escribo YO.
- No escribas soluciones completas ni celdas enteras.
- Responde con explicaciones, pistas, preguntas que me hagan pensar o pseudocódigo.
- Fragmentos de código de 5 líneas como máximo, y solo si te los pido.
- Cuando veas un error, ayúdame a entender la causa antes de decirme cómo arreglarlo.
- Al revisar mi código, señala los problemas por orden de importancia, sin reescribirlo.
- Si algo que hago es conceptualmente incorrecto (fuga de datos, métrica mal elegida,
  validación mal hecha), dímelo claramente aunque no te lo haya preguntado.

## Referencias: mi estilo y lo visto en clase
- `Práctica Clasificación Riesgo Crédito.ipynb`: referencia principal de estructura
  (orden de secciones, EDA, preprocesado, validación, métricas, conclusiones).
- `Feature Engineering.ipynb`: transformaciones y creación de variables.
- `Estadistica Esencial.ipynb`: estadística descriptiva y contrastes.
- `Visualizacion.ipynb`: estilo de gráficas.
- `Pandas.ipynb`, `Numpy.ipynb`, `Introducción.ipynb`: técnicas básicas del curso.
- Prioriza técnicas y librerías que aparezcan en estas referencias antes que otras nuevas.
  Si propones algo que no hemos visto, avísame de que es nuevo.
- Cuando sugieras algo, indica en qué notebook de referencia hice algo parecido.
- Ignora las salidas (outputs) de los notebooks: fíjate en el código y el markdown.

## Git
- Trabajo en la rama `estimacion-precios`; `main` guarda la última versión estable.
- Antes de cualquier comando de Git, explícame en una frase qué hace.
- Para commits: revisa el diff, propón un mensaje en español, en imperativo,
  de menos de 70 caracteres, y espera mi aprobación.
- Nunca incluyas en un commit `venv/`, `.env` ni archivos de datos grandes.
- Nunca uses reset --hard, push --force, clean ni branch -D.