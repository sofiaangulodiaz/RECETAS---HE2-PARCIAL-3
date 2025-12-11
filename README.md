# HE2-IA-PARCIAL-3---
Este proyecto implementa un sistema RAG completo para recomendar y explicar recetas en español. Usa sentence-transformers como encoder para recuperar recetas relevantes desde un dataset real de Hugging Face, y un modelo generativo open-source como decoder para producir explicaciones claras, paso a paso y adaptadas a la consulta del usuario.
📘 README — RAG de Recetas en Español
🥘 Asistente de Cocina con Retrieval-Augmented Generation (RAG)

Este proyecto implementa un asistente de recetas en español usando la arquitectura RAG (Retrieval-Augmented Generation).

El sistema:

Recupera recetas relevantes según la consulta del usuario usando un encoder basado en Transformer.

Genera una explicación paso a paso usando un modelo generativo open-source.

Ejemplo de consulta:

“Tengo arroz y huevo. Quiero algo rápido para el desayuno y sin horno.”

Este pipeline demuestra, en la práctica, cómo funcionan los componentes clave de NLP vistos en clase: embeddings, Transformers, recuperación semántica y modelos generativos.

🚀 Tecnologías principales
🔹 Encoder (Retriever)

Modelo: sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2

Tipo: Transformer encoder-only

Uso:

Convierte recetas y consultas en embeddings semánticos

Permite buscar recetas similares usando similitud de coseno

🔹 Vector Store

Construido en memoria usando numpy

Contiene:

Embeddings de recetas

Metadatos (nombre, ingredientes, instrucciones)

Permite recuperación rápida sin base de datos externa

🔹 Decoder (Generative Model)

Modelo recomendado:

TinyLlama/TinyLlama-1.1B-Chat-v1.0 (ligero, open-source y compatible con Colab)

Tipo: Transformer decoder-only

Genera:

explicación paso a paso

recomendaciones adaptadas

lenguaje simple apto para principiantes

🔹 Dataset

Hugging Face: m3hrdadfi/recipe_nlg_lite

Contiene:

nombres

ingredientes

pasos detallados

descripciones

Se utiliza un subconjunto (~300 recetas) para experimentación rápida
