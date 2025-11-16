# **Resumen**

La hipoxemia es un fenómeno crítico y un riesgo significativo en pacientes sometidos a cirugía torácica que requieren ventilación unipulmonar (VUP). Aunque los avances en anestesia han reducido su incidencia, la identificación oportuna de pacientes en riesgo sigue siendo un desafío clínico, lo que justifica la necesidad de evolucionar hacia estrategias predictivas mediante herramientas de Inteligencia Artificial (IA).

El objetivo general de este proyecto fue implementar, entrenar y evaluar un modelo de Aprendizaje Automático (ML) capaz de predecir la hipoxemia en pacientes con VUP.

---

Se utilizó un enfoque de estudio piloto, realizando la curaduría y selección de datos de la base de datos **VitalDB**, de Physionet, que ofrece información multiparamétrica de alta resolución. Tras un filtrado riguroso, la cohorte final se compuso de **910 cirugías torácicas** con VUP.

La predicción se planteó como un problema de clasificación. Las series de tiempo fueron acondicionadas mediante **ventanas deslizantes de cinco minutos**, con el propósito de anticipar un evento de hipoxemia (SpO₂ < 90% durante al menos 60 segundos) en los siguientes cinco minutos. El conjunto de datos presentó un fuerte desbalance de clases (**3.2% de eventos positivos**).

Se implementaron y compararon cuatro arquitecturas clásicas de ML:

* Regresión Logística
* **Random Forest**
* **XGBoost**
* **Gradient Boosting**

Además de modelos ensamblados:

* **Stacking**
* **Soft Voting**
* **Weighted Voting**

La optimización de hiperparámetros utilizó como métrica principal el **Área bajo la Curva de Precisión-Recall (PR-AUC)**, la más adecuada en escenarios desbalanceados.

---

Tras la optimización y el análisis comparativo, los modelos **XGBoost** y **Gradient Boosting** optimizados demostraron la mayor capacidad discriminativa, alcanzando un **PR-AUC de 0.7780**. Aunque los modelos **extVoting Ensemble** lograron un F1-Score ligeramente superior, el modelo **XGBoost optimizado** fue seleccionado como el de mejor desempeño general.

Esta elección se basó en su excelente equilibrio de métricas (PR-AUC = 0.7780, Recall = 0.7247) y, especialmente, en su buena calibración, lo que garantiza que las probabilidades predichas funcionen como estimadores confiables del riesgo clínico.

Este estudio confirma la viabilidad del uso de ML para predecir hipoxemia en pacientes con VUP, ofreciendo una herramienta con alto potencial para el soporte de decisiones clínicas y la mitigación de eventos adversos críticos.

---

Si quieres, también te preparo una versión más breve, una versión estilo abstract académico, o una versión orientada a inversionistas / público técnico.
