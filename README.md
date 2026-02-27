# analisis-riesgo-pozos-petroleros
“Modelo de decisión de inversión bajo restricción de riesgo utilizando regresión lineal y simulación bootstrap.”
---
#### 📊 Selección Óptima de Pozos Petroleros Bajo Incertidumbre
#### 🎯 Objetivo del Proyecto

Determinar en qué región desarrollar 200 pozos petroleros maximizando beneficio esperado, respetando una restricción de riesgo:

Probabilidad de pérdida < 2.5%

El proyecto combina regresión lineal, selección estratégica basada en predicciones y simulación bootstrap para modelar incertidumbre.

#### 🧠 Enfoque Metodológico
#### 1️⃣ Modelado Predictivo

Se entrenó un modelo de regresión lineal para estimar el volumen de reservas por pozo.

División entrenamiento / validación

Evaluación mediante RMSE

Eliminación de variables irrelevantes (ej. id)

Proceso reproducible y consistente entre regiones

#### 2️⃣ Estrategia de Selección

Para cada región:

Seleccionar los 200 pozos con mayor volumen predicho

Calcular ingresos usando volumen real

Fórmula financiera:

Ganancia = (Volumen total × 4500 USD) − 100,000,000 USD

Punto clave:
Se decide con predicción, pero se gana o pierde con valores reales.

#### 3️⃣ Análisis de Riesgo

Dado que el modelo tiene error (RMSE ≠ 0), se aplicó:

Bootstrapping con 1000 simulaciones

Intervalo de confianza 95%

Cálculo de probabilidad de pérdida

Esto permitió pasar de un número puntual a una distribución de beneficios.

#### 📈 Resultados
Región	Beneficio Promedio	Intervalo 95%	Prob. Pérdida
0	~4.02M	Incluye pérdidas	7%
1	~4.34M	Completamente positivo	1.1%
2	~3.84M	Incluye pérdidas	6.9%
🏆 Decisión Final

Aunque la Región 0 mostraba mayor ganancia en el cálculo determinístico, no cumple la política de riesgo.

La Región 1 es la única que:

Cumple la restricción (< 2.5%)

Presenta intervalo completamente positivo

Mantiene beneficio promedio sólido bajo incertidumbre

📌 Se priorizó política de riesgo sobre beneficio máximo puntual.

#### 💡 Aprendizajes Clave

No se decide con promedios regionales.

No se decide con el mayor número.

Se decide con distribución de escenarios.

El riesgo cambia la decisión óptima.

#### Este proyecto demuestra cómo integrar machine learning con criterios financieros reales y gestión de riesgo.

#### 🛠️ Tecnologías Utilizadas

Python

Pandas

NumPy

Scikit-learn

Simulación Bootstrap
