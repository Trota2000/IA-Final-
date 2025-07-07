# IA-Final-
# Análisis de Texto con Google Colab

## Versiones

- **Versión 1.0**: Implementación básica del análisis de texto y consultas interactivas (Fecha: 2025-07-07).

## Librerías Necesarias

Este proyecto utiliza las siguientes librerías:

- **Python 3**: El lenguaje principal utilizado para escribir el código.
- **spaCy**: Usado para el procesamiento de lenguaje natural (tokenización, extracción de palabras significativas, etc.). 
- **nltk**: Para manejo de stopwords (palabras vacías) en el análisis de texto.
- **sklearn**: Usado para la vectorización **TF-IDF** y el algoritmo de **KMeans** para el clustering temático.
- **matplotlib**: Utilizado para generar los gráficos (distribución de temas, palabras más frecuentes).
- **collections**: Para contar las palabras más frecuentes en el texto procesado.
- **fpdf**: Si deseas generar un PDF del análisis de texto o resultados.
  
Puedes instalar las librerías necesarias utilizando el siguiente comando en **Google Colab**:

```bash
!pip install spacy nltk scikit-learn matplotlib fpdf

Descripción del Programa
Este programa permite realizar un análisis de texto utilizando Google Colab. El cuaderno permite cargar un archivo de texto, procesarlo, realizar un análisis de frecuencia de palabras, aplicar clustering temático y realizar consultas interactivas sobre el contenido. El flujo general sigue los siguientes pasos:

Carga y Preprocesamiento del Texto: El archivo de texto es cargado y procesado, limpiando caracteres no deseados y normalizando el texto.

Tokenización y Frecuencia de Palabras: Se tokeniza el texto y se analiza la frecuencia de las palabras, mostrando estadísticas relacionadas con el texto.

Clustering Temático: Se aplica el algoritmo KMeans de sklearn para identificar los temas principales en el texto y obtener las palabras clave que representan cada tema.

Consultas Interactivas: Permite a los usuarios realizar consultas interactivas sobre el contenido procesado, como la cantidad de palabras, las palabras clave por tema, y más.

Documentación del Script Usado
Este script fue escrito en Python y se ejecuta en Google Colab, utilizando varias bibliotecas populares de análisis de texto, como spaCy, sklearn y matplotlib.

Pasos del Script:
Carga y Preprocesamiento:

El texto se carga y se limpia utilizando la librería re para eliminar puntuación, números y espacios innecesarios.

spaCy se usa para procesar el texto y extraer las palabras más significativas (sustantivos, verbos, adjetivos).

Tokenización y Conteo de Palabras:

Se utiliza spaCy para tokenizar el texto y extraer las palabras significativas. Luego, se usa Counter para contar las palabras más frecuentes.

Clustering Temático con KMeans:

Se utiliza KMeans de sklearn para identificar los temas principales en el texto.

El modelo TF-IDF es utilizado para generar una representación numérica del texto, lo cual ayuda a identificar las palabras clave de cada tema.

Generación de Gráficos:

Distribución de los Temas (Clusters): Un gráfico de barras muestra la distribución de los temas encontrados por KMeans.

Top 10 Palabras Más Frecuentes: Un gráfico de barras muestra las palabras más frecuentes en el texto procesado.

Palabras Clave por Tema: Se visualizan las palabras clave más importantes de cada tema.

Gráficos Generados
Distribución de los Temas (Clusters):
Este gráfico muestra cómo se distribuyen los fragmentos de texto en los diferentes temas generados por KMeans.

plt.hist(kmeans.labels_, bins=num_clusters, color='skyblue', rwidth=0.8)
plt.title("Distribución de temas en el libro")
plt.xlabel("Tema (Cluster)")
plt.ylabel("Cantidad de fragmentos")
plt.grid(True)
plt.show()

![Captura de pantalla 2025-07-07 105611](https://github.com/user-attachments/assets/713354b9-0b5a-4717-bc46-b3e1ade29d30)

plt.bar(df_top["Palabra"], df_top["Frecuencia"], color='orange')
plt.title("Top 10 palabras más frecuentes con significado propio")
plt.xlabel("Palabra")
plt.ylabel("Frecuencia")
plt.grid(True)
plt.show()

![Captura de pantalla 2025-07-07 105630](https://github.com/user-attachments/assets/c229d1e6-f51a-4aeb-b694-9e2293e10bc6)
