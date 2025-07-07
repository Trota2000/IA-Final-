# IA-Final-
 Estudiante: Diego Troche
 
 Docente: Ing. Richard Nuñez
 
 Asignatura: Inteligencia Artificial
 
 Obra: El imperio Final
 
 Autor: Brandon Sanderson
 
# Análisis de Texto con Google Colab

## Versiones

- **Versión 1.0: Implementación básica del análisis de texto y consultas interactivas (Fecha: 2025-07-07).

- **Versión 2.0: Soporte para análisis de documentos PDF (Fecha: 2025-07-07)

## Librerías Necesarias

Este proyecto utiliza las siguientes librerías:

| Name                           | Version | License                            |
| ------------------------------ | ------- | ---------------------------------- |
| **Google Colab**               | -       | -                                  |
| **re**                         | -       | Python Software Foundation License |
| **spaCy**                      | 3.0.0   | MIT License                        |
| **Counter** (from collections) | -       | Python Software Foundation License |
| **nltk**                       | 3.6.3   | Apache Software License 2.0        |
| **sklearn**                    | 0.24.2  | BSD License                        |
| **matplotlib**                 | 3.4.2   | Python Software Foundation License |
| **pandas**                     | 1.2.4   | BSD License                        |
| **numpy**                      | 1.20.1  | BSD License                        |
| **PyPDF2**                     | 1.26.0  | BSD License                        |
| **pdfplumber**                 | 0.6.2   | MIT License                        |
| **pymupdf**                    | 1.18.19 | MIT License                        |

  
Puedes instalar las librerías necesarias utilizando el siguiente comando en **Google Colab**:

```bash
!pip install spacy
!pip install nltk
!pip install scikit-learn
!pip install matplotlib
!pip install pandas
!pip install numpy
!pip install PyPDF2
!pip install pdfplumber
!pip install pymupdf
```
## Descripción del Programa
Este programa permite realizar un análisis de texto utilizando Google Colab. El cuaderno permite cargar un archivo de texto, procesarlo, realizar un análisis de frecuencia de palabras, aplicar clustering temático y realizar consultas interactivas sobre el contenido. El flujo general sigue los siguientes pasos:

- Carga y Preprocesamiento del Texto: El archivo PDF o texto es cargado y procesado, limpiando caracteres no deseados y normalizando el texto.

- Tokenización y Frecuencia de Palabras: Se tokeniza el texto y se analiza la frecuencia de las palabras, mostrando estadísticas relacionadas con el texto.

- Clustering Temático: Se aplica el algoritmo KMeans de sklearn para identificar los temas principales en el texto y obtener las palabras clave que representan cada tema.

- Consultas Interactivas: Permite a los usuarios realizar consultas interactivas sobre el contenido procesado, como la cantidad de palabras, las palabras clave por tema, y más.

## Documentación del Script Usado
Este script fue escrito en Python y se ejecuta en Google Colab, utilizando varias bibliotecas populares de análisis de texto, como spaCy, nltk, sklearn, matplotlib, pandas, y numpy.

Pasos del Script:
Carga y Preprocesamiento:

- El texto se carga desde un archivo PDF o TXT utilizando files.upload() en Google Colab.

- Se utiliza PyPDF2 o pdfplumber para extraer texto de archivos PDF.

- Se realiza un preprocesamiento donde el texto se convierte a minúsculas, se eliminan caracteres no alfanuméricos, números y espacios innecesarios.

Tokenización y Conteo de Palabras:

 - Se utiliza spaCy para tokenizar el texto y extraer las palabras significativas. Luego, se usa Counter de collections para contar las palabras más frecuentes.

Clustering Temático con KMeans:

 - Se utiliza KMeans de sklearn para identificar los temas principales en el texto.

 - El modelo TF-IDF es utilizado para generar una representación numérica del texto, lo cual ayuda a identificar las palabras clave de cada tema.

Generación de Gráficos:

 - Distribución de los Temas (Clusters): Un gráfico de barras muestra la distribución de los temas encontrados por KMeans.

 - Top 10 Palabras Más Frecuentes: Un gráfico de barras muestra las palabras más frecuentes en el texto procesado.

 - Palabras Clave por Tema: Se visualizan las palabras clave más importantes de cada tema.

## Gráficos Generados
Distribución de los Temas (Clusters):

- Este gráfico muestra cómo se distribuyen los fragmentos de texto en los diferentes temas generados por KMeans.
```bash
plt.hist(kmeans.labels_, bins=num_clusters, color='skyblue', rwidth=0.8)
plt.title("Distribución de temas en el libro")
plt.xlabel("Tema (Cluster)")
plt.ylabel("Cantidad de fragmentos")
plt.grid(True)
plt.show()
```
![Captura de pantalla 2025-07-07 105611](https://github.com/user-attachments/assets/87537bfa-2348-4e4a-853e-7e38a06081e3)

Listado de 10 Palabras Más Frecuentes:

- Un gráfico de barras visualiza las palabras más frecuentes en el texto, excluyendo las palabras vacías.
```bash
plt.bar(df_top["Palabra"], df_top["Frecuencia"], color='orange')
plt.title("Top 10 palabras más frecuentes con significado propio")
plt.xlabel("Palabra")
plt.ylabel("Frecuencia")
plt.grid(True)
plt.show()
```
![Captura de pantalla 2025-07-07 105630](https://github.com/user-attachments/assets/056ec790-4d09-45f5-94ca-2d552825d370)

Palabras Clave por Tema:

- Los temas generados por KMeans se visualizan mostrando las palabras clave más relevantes para cada tema.
Palabras clave por tema:

🔹 Tema 1:
[['transigido' 'dejándolo' 'dejándoles' ... 'camon' 'vin' 'kelsier']]

🔹 Tema 2:
[['maltrechos' 'malhumorada' 'maliciosa' ... 'venture' 'vin' 'elend']]

🔹 Tema 3:
[['ex' 'recorrido' 'recorriendo' ... 'dockson' 'brisa' 'kelsier']]

🔹 Tema 4:
[['mina' 'migajas' 'milagro' ... 'soldados' 'inquisidor' 'kelsier']]

🔹 Tema 5:
[['malditos' 'malignidad' 'maligna' ... 'lord' 'legislador' 'marsh']]


## Licencia

- Este proyecto está bajo las siguientes licencias:



| Name                           | Version | License                            |
| ------------------------------ | ------- | ---------------------------------- |
| **Google Colab**               | -       | -                                  |
| **re**                         | -       | Python Software Foundation License |
| **spaCy**                      | 3.0.0   | MIT License                        |
| **Counter** (from collections) | -       | Python Software Foundation License |
| **nltk**                       | 3.6.3   | Apache Software License 2.0        |
| **sklearn**                    | 0.24.2  | BSD License                        |
| **matplotlib**                 | 3.4.2   | Python Software Foundation License |
| **pandas**                     | 1.2.4   | BSD License                        |
| **numpy**                      | 1.20.1  | BSD License                        |
| **PyPDF2**                     | 1.26.0  | BSD License                        |
| **pdfplumber**                 | 0.6.2   | MIT License                        |
| **pymupdf**                    | 1.18.19 | MIT License                        |


Consulta la documentación oficial de cada paquete para más detalles sobre sus licencias.
