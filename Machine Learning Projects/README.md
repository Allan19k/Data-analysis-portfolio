# Predicción de Tasas de Cambio EUR/USD usando RNN y LSTM

Este proyecto analiza y predice las tasas de cambio diarias entre el Euro y el Dólar Estadounidense (EUR/USD) utilizando modelos de redes neuronales recurrentes: **RNN** y **LSTM**.

El objetivo es comparar el rendimiento de un modelo RNN simple con un modelo LSTM, más avanzado para capturar dependencias a largo plazo en series temporales.

Este trabajo forma parte de mi portafolio de proyectos, diseñado para demostrar mis habilidades en **Machine Learning** y **análisis de datos**, alineadas con oportunidades como prácticas profesionales en análisis de datos.

---

## 🎯 Objetivo

Predecir valores futuros de la tasa de cambio EUR/USD y evaluar la efectividad de dos modelos de redes neuronales recurrentes:

- **RNN (Red Neuronal Recurrente Simple):** Captura patrones básicos en series temporales.
- **LSTM (Memoria a Largo Plazo):** Maneja dependencias a largo plazo en los datos.

---

## 📊 Datos

- **Fuente:** Datos históricos de precios de cierre diarios obtenidos vía `yfinance`.
- **Rango de fechas:** 1 de enero de 2020 al 1 de enero de 2023.
- **División:** 80% para entrenamiento, 20% para prueba.
- **Ventaneo:** Se utilizó un tamaño de ventana de 10 días para crear secuencias (cada muestra usa los últimos 10 días para predecir el siguiente).

---

## ⚙️ Metodología

### 🔧 Preprocesamiento

- **Normalización:** `MinMaxScaler` para escalar los datos entre [0, 1].
- **Ventaneo:** Creación de secuencias temporales con ventana de 10 días.

### 🧠 Modelos

- **RNN:** Una capa `SimpleRNN` con 50 unidades.
- **LSTM:** Una capa `LSTM` con 50 unidades.
- Ambos modelos incluyen una **capa densa de salida** para predicción.

### ⚙️ Optimizador

- Se utilizó **Adam** por su adaptabilidad, eficiencia y estabilidad.

### 📏 Evaluación

- Métricas utilizadas: **MSE**, **RMSE** y **MAE** para comparar modelos.

---

## 📈 Resultados

| Modelo | MSE     | RMSE    | MAE     |
|--------|---------|---------|---------|
| RNN    | 0.0000  | 0.0069  | 0.0054  |
| LSTM   | 0.0002  | 0.0149  | 0.0115  |

> Ambos modelos mostraron buen rendimiento, con el RNN ligeramente superior en este caso, posiblemente debido a la simplicidad de los patrones en los datos.

---

## 🚀 Instrucciones de Uso

### 🛠️ Entorno

Este código está diseñado para ejecutarse en **Google Colab**.

### 📦 Dependencias

Instala las siguientes bibliotecas si es necesario:

```bash
!pip install yfinance
!pip install pydot
!apt-get install graphviz

