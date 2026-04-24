## Prompt malo:

--- 

Utilizando el texto de drácula, genera un modelo generativo de lenguaje.

--- 

## Prompt básico:

--- 

Buscamos generar en Python un modelo sencillo para generar texto, entrenado sobre el texto de drácula que se encuentra en https://www.gutenberg.org/cache/epub/345/pg345.txt

Realiza un preprocesamiento del texto para quedarnos con solo letras minúsculas (no números), y ocupemos como corpus reducido solo de la palabra 9,720 a 10,000 después de procesar.

El modelo debe basarse en n-gramas, es decir: tomar un n-grama al azar del corpus, y luego elegir aleatoriamente, pero según las frecuencias en el texto, un n-grama que le siga al anterior. Para después de k n-gramas.

--- 

## Prompt aumentado con principios de prompt engineering:

--- 

Actúa como un **científico de datos experto en NLP (Procesamiento de Lenguaje Natural)**. Tu objetivo es construir un modelo de generación de texto basado en n-gramas utilizando Python.

### Contexto y Requisitos Técnicos
Debes desarrollar un script que cumpla con las siguientes especificaciones:
- **Fuente de datos:** Utiliza el texto de *Drácula* disponible en `https://www.gutenberg.org/cache/epub/345/pg345.txt` (reliza la descarga con `requests`).
- **Stack:** Python 3.x, utilizando únicamente la librería estándar o `re` para limpieza. No utilices frameworks pesados como TensorFlow o PyTorch.

### Tarea Paso a Paso (Chain-of-Thought)
Sigue esta secuencia lógica para implementar la solución:
1.  **Preprocesamiento:** - Convierte todo el texto a minúsculas.
    - Elimina números, signos de puntuación y caracteres especiales (solo mantén letras y espacios).
    - Tokeniza el texto por palabras.
2.  **Segmentación del Corpus:** - Extrae el subconjunto del corpus que va desde la palabra **9,720 hasta la 10,000** (inclusive).
3.  **Construcción del Modelo de N-gramas:**
    - Crea una estructura de datos (ej. diccionario) donde cada clave sea un n-grama de tamaño $n$ y el valor sea una lista de palabras que le siguen con sus frecuencias respectivas.
4.  **Lógica de Generación:**
    - Selecciona un n-grama inicial de forma aleatoria del corpus procesado.
    - Genera una secuencia de longitud $k$, eligiendo la siguiente palabra basándote en la distribución de probabilidad (frecuencia) del n-grama actual.

### Ejemplo de Salida Esperada (Few-Shot)
Si el corpus fuera "el gato come pan, el gato bebe leche" y $n=2$:
- Entrada: `('el', 'gato')`
- Posibles salidas: `come` (50%), `bebe` (50%).

### Restricciones de Salida
- El código debe estar documentado.
- El valor de $n$ (tamaño del n-grama) y $k$ (longitud de generación) deben ser variables fácilmente modificables al inicio del script.

---

## Checklist de Principios Aplicados

| Principio | Aplicación en el Prompt |
| :--- | :--- |
| **Aprovecha roles y personas** | "Actúa como un Ingeniero de Software experto en NLP". |
| **Proporciona contexto** | Se incluye la URL de la fuente y las especificaciones de limpieza del texto. |
| **Sé específico sobre tu objetivo** | Se define claramente que se busca un modelo de n-gramas con lógica probabilística. |
| **Divide tareas complejas** | El proceso se desglosó en Preprocesamiento, Segmentación, Construcción y Generación. |
| **Guía paso a paso (CoT)** | La sección "Tarea Paso a Paso" fuerza un razonamiento secuencial. |
| **Incluye ejemplos (Few-Shot)** | Se añadió el ejemplo del "gato" para ilustrar la lógica de probabilidad. |
| **Basado en restricciones** | Se limitó el uso de librerías y se definieron los índices exactos del corpus (9,720-10,000). |