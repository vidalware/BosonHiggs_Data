
# 🧪 Descubriendo el Bosón de Higgs con Machine Learning

Este proyecto explora la aplicación de técnicas de clasificación supervisada para identificar eventos candidatos al bosón de Higgs en un entorno simulado del LHC. Utilizando un dataset provisto por ATLAS vía el portal Kaggle, se entrena un modelo de machine learning para distinguir entre colisiones de fondo y eventos potencialmente asociados a la producción del bosón de Higgs.

---

## 🧬 Contexto físico

En julio de 2012, los experimentos ATLAS y CMS en el LHC anunciaron el descubrimiento del bosón de Higgs, la última pieza faltante del Modelo Estándar. Dada la enorme cantidad de eventos de colisiones en los detectores y la baja probabilidad de producción del Higgs, se requiere un filtrado sofisticado de señales.

Este notebook replica ese desafío: identificar, entre millones de colisiones, aquellos pocos eventos que tienen una alta probabilidad de corresponder a la desintegración del Higgs.

---

## 📂 Estructura del proyecto

- `Encontrando_el_boson_de_higgs.ipynb`: notebook principal con el flujo completo de trabajo.

Flujo del análisis:

1. Carga del dataset ATLAS (Kaggle)
2. Limpieza y preprocesamiento
3. Exploración y visualización de variables físicas
4. Ingeniería de características
5. Entrenamiento de clasificadores (Random Forest)
6. Evaluación con métricas ROC-AUC y AMS
7. Predicción y visualización de resultados

---

## 📊 Dataset

- Fuente: [Kaggle - Higgs Boson Challenge (ATLAS)](https://www.kaggle.com/competitions/higgs-boson)
- 250.000 eventos simulados de colisiones p-p
- Variables físicas: energía, momento transversal, ángulo azimutal, masa invariante, entre otras
- Etiqueta objetivo: `Label` (signal `s` vs background `b`)
- Peso: `Weight`, utilizado para evaluar significancia estadística (AMS)

---

## 🧠 Modelos utilizados

- **Random Forest Classifier** con validación cruzada
- Métricas utilizadas:
  - ROC-AUC
  - AMS (Approximate Median Significance), métrica inspirada en física de partículas

Fórmula de la significancia AMS:

```math
AMS = \sqrt{2 \left[ (s + b + 10) \cdot \ln\left(1 + \frac{s}{b + 10}\right) - s \right]}
```

Donde:
- *s*: suma de pesos de eventos verdaderos positivos
- *b*: suma de pesos de eventos de fondo mal clasificados

---

## 📈 Resultados

- Se obtuvo un modelo con **ROC-AUC > 0.80**, indicando buena capacidad de discriminación.
- Variables más relevantes identificadas por el modelo:
  - Masa invariante (invariant mass)
  - Energía visible
  - Momento transversal del segundo leptón

---

## 🔬 Conclusión

Este proyecto demuestra cómo el aprendizaje automático puede aplicarse en contextos reales de física de partículas. El uso de modelos robustos como Random Forest, combinado con ingeniería de características basada en conocimiento físico, permite detectar eventos raros con alta significancia estadística. Esta metodología es una herramienta valiosa para experimentos de búsqueda de nueva física más allá del Modelo Estándar.

---

## 🚀 Posibles extensiones

- Implementar modelos como XGBoost y comparar su desempeño con AMS
- Usar técnicas de ensamblado (ensemble) para aumentar la robustez
- Aplicar interpretabilidad con SHAP para entender decisiones del modelo
- Visualizar resultados en un mapa topológico del detector

---

## 💻 Requisitos

```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
```


## 👨‍🔬 Autor

**Marcelo Vidal**  
Licenciado en Física Aplicada e Ingeniería Física  
[LinkedIn](https://www.linkedin.com/in/marcelo-vidal-bravo)  
[ORCID](https://orcid.org/0000-0002-0196-3533)
