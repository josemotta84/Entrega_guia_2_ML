### Entrega_guia_2_ML
## Explicacion 
Este repositorio contiene los archivos de la entrega de la guia 2
En este proyecto se trabajó con dos archivos distintos para analizar el impacto de la calidad de los datos en el rendimiento de los modelos de Machine Learning:

- **`segunda_entrega_ml_ipynb.ipynb`**: Utiliza la base de datos `heart_disease_uci`, la cual contiene **valores faltantes** y **outliers**.
- **`Entrega_guia_2_ML.ipynb`**: Utiliza la base de datos `heart`, que es **más limpia y organizada**.

El objetivo fue comparar el desempeño de los modelos en entrenamiento y prueba para **evaluar cómo los datos desordenados pueden interferir con el rendimiento** del modelo. Se observó que:

- Cuando los datos están **limpios**, el modelo puede alcanzar un buen rendimiento en entrenamiento y prueba **sin necesidad de optimizar hiperparámetros**.
- En cambio, cuando los datos están **sucios o contienen ruido**, es necesario realizar una **optimización de hiperparámetros** (como mediante `GridSearchCV`) para **reducir el overfitting** y mejorar la capacidad de generalización del modelo.

---

## Conclusiones del Proyecto - Heart Disease UCI

A partir del análisis y modelado con la base de datos **Heart Disease UCI**, se concluye lo siguiente:

1. **Importancia del EDA**  
   La realización de un análisis exploratorio de datos (EDA) exhaustivo y robusto es crucial al entrenar un árbol de decisión en Machine Learning. Un buen EDA permite una mejor selección de características, lo que a su vez mejora el rendimiento del modelo. En este caso, la base de datos contenía varios valores nulos en distintas características, lo que hizo necesario un preprocesamiento cuidadoso.

2. **Características Seleccionadas**  
   Las variables seleccionadas tras el análisis fueron:  
   `cp_atypical angina`, `oldpeak`, `age`, `exang_True`, `sex_Male`, `thalach`, `chol`.

3. **Impacto de la Selección de Características**  
   La elección de estas 7 características derivó en mejores resultados en métricas clave como **Accuracy**, **F1-Score** y la **matriz de confusión**.

4. **Desempeño del Modelo Final**  
   El modelo final, optimizado con `GridSearchCV`, logró un **F1-score de aproximadamente 0.79**, con un buen equilibrio entre precisión y exhaustividad.

5. **Importancia de la Regularización**  
   La regularización utilizando hiperparámetros óptimos (`max_depth=None`, `min_samples_split=20`, `min_samples_leaf=8`) fue esencial para controlar el **overfitting** y mejorar la capacidad de generalización del modelo.

6. **Reducción de Overfitting y Underfitting**  
   La aplicación de `GridSearchCV` junto con la correcta elección de hiperparámetros permitió reducir tanto el overfitting como el underfitting, posicionando al modelo en una "zona saludable" para predecir correctamente enfermedades cardíacas.
