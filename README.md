# Detección de Indicadores Lingüísticos de Sintomatología Depresiva en Redes Sociales Peruanas

**Autor:** Jhan Pierre Becerra Huaytalla  
**Universidad:** Universidad Tecnológica del Perú (UTP)  
**Año:** 2026

## Descripción

Pipeline completo de detección automática de indicadores lingüísticos 
asociados a sintomatología depresiva en español peruano, comparando dos 
arquitecturas basadas en BETO (Cañete et al., 2020):

- **M1 — Baseline:** BETO fine-tuneado directamente sobre el corpus peruano
- **M2 — DAPT:** BETO con Domain-Adaptive Pretraining (Gururangan et al., 2020)
  vía MLM sobre corpus temático + LATAM, seguido de fine-tuning supervisado

## Resultados principales

| Modelo | AUC-ROC | F1 |
|---|---|---|
| M1 Baseline | 0.774 ± 0.009 | 0.716 ± 0.008 |
| M2 DAPT | 0.808 ± 0.009 | 0.744 ± 0.016 |

Test DeLong: z = 2.573, p = 0.010 (IC 95%: [0.008, 0.061])

## Estructura del notebook

| Bloque | Contenido |
|---|---|
| 0 | Introducción y configuración |
| 1 | Setup e instalación |
| 2 | Recolección y preprocesamiento del corpus |
| 3 | Pre-entrenamiento MLM (DAPT) y fine-tuning multi-seed |
| 4 | Evaluación (AUC-ROC, F1, Precision, Recall) |
| 5 | Test estadístico DeLong |
| 6 | Visualizaciones para publicación |
| 7 | Análisis avanzado de errores |
| 8 | Demo de inferencia |

## Corpus

- **Clasificación (Parte B + C):** r/peru + r/PeruFinanzas
- **Pre-entrenamiento MLM (Parte A):** subreddits temáticos de salud mental + LATAM
- **Etiquetado:** supervisión distante vía léxico DSM-5/PHQ-9

## Referencias

- Cañete et al. (2020). Spanish Pre-trained BERT Model and Evaluation Data.
- Gururangan et al. (2020). Don't Stop Pretraining. ACL 2020.
- DeLong et al. (1988). Biometrics, 44(3), 837–845.
- Wei & Zou (2019). EDA: Easy Data Augmentation. EMNLP-IJCNLP 2019.
