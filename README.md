# Ecuador Growth ML

Nowcast del crecimiento interanual del PIB de Ecuador con Random Forest y despliegue MLOps en Streamlit.
Proyecto académico — Diplomado en BI e Inteligencia Artificial, Módulo 5 (MLOps). **Datos simulados.**

Autor: Victor Oña

**🚀 App en línea:** https://appmlopsreentrenamientopy-aah9dtpk6lpswpjr3vp3vj.streamlit.app/

## Contenido

| Archivo | Descripción |
|---|---|
| `Modelo_Nowcast_Dinamico_Ejecutado.ipynb` | Notebook ejecutado: justificación de variables, validación cruzada temporal, experiment tracker y exportación del modelo |
| `Modelo_Nowcast_Dinamico_Estudiantes.ipynb` | Notebook base del curso |
| `app_MLOps_reentrenamiento.py` | Aplicación Streamlit completa (predicción, CSV, tracker, monitoreo y reentrenamiento) |
| `app.py` | Versión de la aplicación sin la pestaña de reentrenamiento |
| `modelo_pib.joblib` | Pipeline entrenado (imputación + Random Forest, RUN-003) |
| `salidas_tracker/` | Experimentos, métricas por fold, mejor experimento, predicciones de prueba y configuración del modelo |
| `documentacion/` | Documentación en Word y PDF con capturas del código y de la aplicación |
| `*.csv` | Base histórica, diccionario de datos e indicadores nuevos (simulados) |

## Variables del Nowcast

`precio_petroleo`, `credito_privado`, `ventas_internas`, `consumo_electrico`: un indicador oportuno por cada canal
del ciclo ecuatoriano. Con ellas se obtiene el menor RMSE de validación cruzada (1,081) entre los conjuntos comparados
(20 variables: 1,253; top-4 por correlación: 1,337). Detalle en el notebook y en `documentacion/`.

## Ejecutar

```bash
pip install -r requirements.txt
streamlit run app_MLOps_reentrenamiento.py
```
