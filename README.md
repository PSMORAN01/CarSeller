# Predicción del precio de autos usados 🚗💸

Este proyecto tiene como objetivo predecir el precio de autos usados a partir de sus características técnicas y de registro. Se probaron distintos enfoques de regresión como Random Forest y CatBoost, evaluando el rendimiento con la métrica RMSE.

---

## 📊 Descripción general

Trabajé con un dataset llamado `car_data.csv` que contenía información sobre vehículos listados para venta, incluyendo marca, tipo de vehículo, combustible, potencia, año de registro, kilometraje y si el vehículo fue o no reparado.

Se limpiaron los datos, se codificaron las variables categóricas y se probaron dos enfoques distintos:

- Árboles de regresión tradicionales (`RandomForestRegressor`)
- Modelo optimizado para variables categóricas (`CatBoostRegressor`)

---

## ⚙️ Tecnologías utilizadas

- Python 3
- Pandas, NumPy
- Scikit-learn
- CatBoost
- OrdinalEncoder
- Métricas: `mean_squared_error`, `RMSE`
- Medición de tiempos de entrenamiento y predicción

---

## 🧼 Preprocesamiento

1. Eliminación de columnas irrelevantes:
   - `DateCrawled`, `DateCreated`, `LastSeen`, `NumberOfPictures`, `PostalCode`

2. Imputación de valores nulos en columnas categóricas con `"unknown"`

3. Conversión de la variable `NotRepaired` a formato binario (`yes` → 1, `no` → 0, `unknown` → -1)

4. Codificación:
   - `OrdinalEncoder` para `RandomForest`
   - Codificación automática interna para `CatBoost`

5. División en conjuntos de entrenamiento y validación con `train_test_split`

---

## 🤖 Modelos entrenados

### 🌳 Random Forest Regressor
- `n_estimators=100`
- `max_depth=10`
- Entrenamiento rápido
- RMSE validación: **bajo**, buen desempeño general

### 🐈 CatBoost Regressor
- Maneja automáticamente variables categóricas sin codificarlas manualmente
- Mejora en la precisión final
- Mayor tiempo de entrenamiento, pero mejor generalización

---

## 📈 Resultados

- **Random Forest** fue eficiente y preciso, especialmente en tiempos cortos.
- **CatBoost** ofreció mejor desempeño en términos de RMSE con menos trabajo de preprocesamiento.
- Ambos modelos lograron predecir precios con buena aproximación, útil para portales de autos usados o concesionarios.

---

## 🧠 Lecciones aprendidas

- El preprocesamiento de variables categóricas es clave para modelos tradicionales como Random Forest.
- CatBoost es ideal cuando se trabaja con muchos datos categóricos y se quiere mantener un pipeline simple.
- Medir tiempos de ejecución puede ser tan importante como la métrica de error cuando pensamos en aplicaciones reales.

---

## 👨‍💻 Autor

**Pablo Sebastián Morán**  
📧 psmoran01@gmail.com  
🔗 [GitHub](https://github.com/PSMORAN01)  
