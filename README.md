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

## 🛠️ Detalles de las Herramientas Utilizadas

Para resolver este problema de predicción, utilicé el ecosistema científico de Python, seleccionando cada herramienta por sus fortalezas específicas:

* **Python 🐍:** El lenguaje base, elegido por su sintaxis limpia y su dominio absoluto en el campo del Machine Learning.
* **Visual Studio Code (VS Code) 📝:** El entorno de desarrollo (IDE) desde el cual gestioné los archivos, la terminal de Git y la ejecución del código.
* **Jupyter Notebooks (`.ipynb`):** Utilizado dentro de VS Code para experimentar de forma interactiva. Permite ejecutar el código en bloques o celdas individuales, facilitando la visualización inmediata de los datos sin tener que reiniciar todo el programa.
* **Pandas 🐼:** La librería fundamental para la manipulación de datos. La utilicé para cargar el archivo CSV, explorar las filas y columnas, y realizar la limpieza de la estructura.
* **Scikit-Learn (Sklearn) 🤖:** La librería líder para Machine Learning tradicional en Python. De aquí utilicé el módulo `train_test_split` para separar los datos y el algoritmo `DecisionTreeClassifier` para construir el modelo matemático.

---

## 🧼 Proceso de Limpieza y Preparación de Datos (Paso a Paso)

Los datos crudos de Kaggle no se pueden introducir directamente en un modelo de Inteligencia Artificial. Los algoritmos matemáticos requieren datos puramente numéricos y completos. El proceso de curación siguió estos tres pasos esenciales:

### Paso 1: Tratamiento de Valores Faltantes (Imputación)
Al inspeccionar el dataset, descubrí que a la columna de la edad (`Age`) le faltaban muchos registros. Dejar estos vacíos (valores nulos) haría que el modelo fallara.
* **Solución:** Utilicé la **mediana** de todas las edades del barco para rellenar los huecos vacíos (`.fillna()`). Elegí la mediana en lugar del promedio porque es más resistente a los valores extremos (por ejemplo, si había pasajeros ancianos aislados de 80 años, no alteraban tanto el resultado).

### Paso 2: Conversión de Variables Categóricas a Numéricas (Encoding)
La columna de género (`Sex`) contenía texto: `"male"` (hombre) y `"female"` (mujer). Las computadoras no entienden el concepto de género, solo entienden bits y números.
* **Solución:** Realicé un mapeo binario (`.map()`) para transformar el texto en datos cuantitativos:
    * `female` ➔ `0`
    * `male` ➔ `1`

### Paso 3: Selección de Características (Feature Selection)
El dataset original incluye información que no aporta valor predictivo directo para la supervivencia o que requería un procesamiento de lenguaje natural avanzado (como el nombre del pasajero `Name`, el número de ticket `Ticket` o el código de cabina `Cabin`).
* **Solución:** Filtré el dataset para conservar únicamente las variables numéricas clave que impactaban directamente las probabilidades de supervivencia: la clase del boleto (`Pclass`), el género transformado (`Sex`), la edad corregida (`Age`), y la cantidad de familiares a bordo (`SibSp` y `Parch`).
