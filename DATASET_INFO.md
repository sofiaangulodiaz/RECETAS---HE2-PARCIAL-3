# 📊 Información del Dataset Utilizado

Este proyecto utiliza el dataset **`m3hrdadfi/recipe_nlg_lite`** disponible públicamente en Hugging Face.

🔗 **Link al dataset:**  
https://huggingface.co/datasets/m3hrdadfi/recipe_nlg_lite

---

## 📘 Descripción General

El dataset `recipe_nlg_lite` es una versión reducida y manejable del dataset original **RecipeNLG**, creada para experimentación con modelos de NLP, generación de texto y sistemas inteligentes.

Está compuesto por miles de recetas con texto estructurado y es ideal para tareas como:

- Recuperación semántica  
- Embedding & similarity search  
- Generación de instrucciones culinarias  
- Sistemas de recomendación  

---

## 🧾 Columnas Principales

Cada receta contiene los siguientes campos:

| Columna        | Descripción |
|----------------|-------------|
| **uid**        | Identificador único |
| **name**       | Nombre de la receta |
| **description**| Descripción breve |
| **ingredients**| Lista de ingredientes |
| **steps**      | Instrucciones paso a paso |
| **ner**        | Entidades nombradas (opcional) |

---

## 🧪 Subconjunto Usado en Este Proyecto

Para este proyecto se utiliza un subconjunto de **300 recetas**, permitiendo:

- Ejecución rápida en Google Colab  
- Bajo consumo de memoria  
- Desarrollo ágil del pipeline RAG  

---

## 💻 Ejemplo de Carga del Dataset

```python
from datasets import load_dataset

dataset = load_dataset("m3hrdadfi/recipe_nlg_lite", trust_remote_code=True)
train_ds = dataset["train"]
sub_ds = train_ds.select(range(300))

sub_ds[0]🍽️ Ejemplo de una Receta
{
  "uid": "000002c809f70f84",
  "name": "pork chop noodle soup",
  "ingredients": "3.0 bone in pork chops, salt, pepper, onion, broth...",
  "steps": "season pork chops with salt and pepper. heat oil in a pot...",
  "description": "A simple hearty soup made with pork chops and noodles.",
  "ner": ["pork", "noodles", "onion"]
}

© Fuente de Datos

Dataset creado por Mehrdad Farahani.
Repositorio oficial:

👉 https://huggingface.co/datasets/m3hrdadfi/recipe_nlg_lite
