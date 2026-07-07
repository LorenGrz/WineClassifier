# Repository Context

## Purpose

- Trabajo práctico de Matemática III sobre clasificación de vinos.
- Objetivo actual: predecir si un vino es blanco o tinto usando características físico-químicas.
- El objetivo original de predecir `quality` fue descartado por baja correlación lineal observada en el análisis exploratorio.

## Stack

- Python notebook.
- Jupyter.
- pandas, numpy, matplotlib, scikit-learn, tqdm.

## Project Structure

- `README.md`: documentación principal del proyecto.
- `TP_LORENZO_v2.ipynb`: notebook principal con análisis, red neuronal manual y comparación con scikit-learn.
- `WineQuality.csv`: dataset local usado por el notebook.
- `ConsignasTP.pdf`: consigna original del trabajo práctico.
- `Img/Realidad.jpg`: imagen usada originalmente en el README.
- `requirements.txt`: dependencias necesarias para ejecutar el notebook.

## Package Manager And Scripts

- No hay package manager de aplicación ni scripts automatizados.
- Entorno recomendado:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

## Architecture Rules

- Mantener el proyecto simple y orientado a notebook educativo.
- No convertirlo en una app salvo pedido explícito.
- Preferir explicaciones claras en español.
- Mantener `WineQuality.csv` como fuente local para que el repo clonado sea reproducible.
- Si se mejora el modelo, evitar borrar la implementación manual porque es parte del valor pedagógico del trabajo.

## Testing And Verification

- No hay tests automatizados.
- Verificación mínima:
  - validar que `TP_LORENZO_v2.ipynb` sea JSON válido;
  - abrir el notebook en Jupyter/VS Code;
  - ejecutar todas las celdas después de instalar dependencias.
- Este entorno no tenía pandas instalado al revisar el repo, por lo que no se ejecutó el notebook completo.

## Local Development Services

- Ninguno.
- Jupyter puede levantarse localmente cuando se necesite.

## Agent Notes

- El usuario pidió mejorar README y ordenar/explicar mejor el contenido del proyecto y notebooks.
- No hay que cambiar el objetivo del trabajo sin consultar.
- La documentación debe quedar clara, formal y presentable para un trabajo práctico.

## Last Reviewed

- 2026-07-07: se inspeccionaron archivos del repo, README, notebook, dataset y estructura general. Se confirmó que el proyecto es un notebook de clasificación binaria de tipo de vino.
