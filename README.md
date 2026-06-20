# 🚢 Predicción de Supervivencia en el Titanic con Machine Learning

¡Bienvenido/a a mi primer proyecto de Ciencia de Datos! En este repositorio desarrollo un modelo predictivo para resolver el clásico desafío de Kaggle: **Titanic - Machine Learning from Disaster**. El objetivo es predecir qué pasajeros sobrevivieron al naufragio utilizando algoritmos de Inteligencia Artificial.

---

## 📊 El Dataset
Los datos contienen información real sobre los pasajeros del Titanic, incluyendo características como:
*   `Pclass`: Clase del pasajero (1ª, 2ª o 3ª).
*   `Sex`: Género (convertido a valores numéricos para el modelo).
*   `Age`: Edad (las edades faltantes se completaron con la mediana).
*   `SibSp` / `Parch`: Información sobre familiares a bordo.

---

## 🛠️ Tecnologías Utilizadas
*   **Lenguaje:** Python 🐍
*   **Entorno:** Jupyter Notebooks en VS Code 📝
*   **Librerías Clave:** 
    *   `Pandas` (Manipulación y limpieza de datos)
    *   `Scikit-Learn` (Creación y evaluación del modelo de ML)

---

## 🤖 El Modelo y Resultados
Para este proyecto implementé un **Árbol de Decisión (`DecisionTreeClassifier`)**. 

A través de este algoritmo, la Inteligencia Artificial aprendió a identificar patrones (por ejemplo, el impacto del género y la clase en la tasa de supervivencia) dividiendo los datos en un 80% para entrenamiento y 20% para evaluación.

*   **Precisión del Modelo:** Obtuve un **[78.77%]** de precisión en los datos de prueba.

---

## 📁 Estructura del Proyecto
*   `data/`: Carpeta local que contiene los datos de Kaggle (protegida por `.gitignore`).
*   `exploracion.ipynb`: Notebook principal con la limpieza de datos y el entrenamiento de la IA.
*   `README.md`: Descripción del proyecto.