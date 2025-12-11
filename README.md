# 🍳 Sistema RAG para Recomendación y Explicación de Recetas
### Recuperación semántica y generación de instrucciones de cocina en español

---

## 👤 Autores
- **Gabriela Zamora**
- **Daniel**
- **Felipe Rosas**
- **Sofía Angulo**

---

## 🎯 Descripción del Proyecto

Este proyecto implementa un **asistente inteligente de cocina** basado en **RAG (Retrieval-Augmented Generation)**.  
El sistema permite que un usuario escriba una consulta en español, por ejemplo:

> “Tengo arroz y huevo, quiero algo rápido para el desayuno y sin horno.”

El asistente combina dos componentes:

- 🔍 **Recuperación semántica:** encuentra recetas relevantes usando un encoder multilingüe.
- ✨ **Generación de texto:** explica la receta paso a paso usando un modelo generativo open-source.

Este proyecto aplica conceptos como **Transformers, embeddings, búsqueda semántica, retrieval, decoders y arquitectura RAG**.

---

## 📚 Dataset

### Características principales
- **Fuente:** Hugging Face  
- **Dataset:** `m3hrdadfi/recipe_nlg_lite`  
- **Tamaño:** 7,000+ recetas  
- **Columnas clave:**
  - name  
  - ingredients  
  - steps  
  - description  

Para el prototipo se usa un subconjunto de 300 recetas.

---

## 🧠 Arquitectura del Sistema

### **1. Encoder (Retriever)**
- Modelo: `paraphrase-multilingual-MiniLM-L12-v2`
- Tipo: Transformer **encoder-only**
- Función: generar **embeddings semánticos** para comparar consultas y recetas.

### **2. Vector Store**
Almacenado temporalmente en memoria (NumPy).  
Contiene:
- embeddings de recetas  
- metadatos (nombre, ingredientes, pasos)

Permite recuperación por **similitud de coseno**.

### **3. Decoder (Generative Model)**
- Modelo: `TinyLlama/TinyLlama-1.1B-Chat-v1.0`
- Tipo: Transformer **decoder-only**
- Función:
  - elegir la receta más adecuada  
  - explicar pasos numerados  
  - usar lenguaje simple  
  - no inventar ingredientes  

---

## 🚀 Flujo de Trabajo

1. Carga y preprocesamiento del dataset  
2. Generación de embeddings con el encoder  
3. Búsqueda semántica  
4. Construcción del prompt RAG  
5. Generación de la respuesta final  
6. Prueba con consultas reales  

---

## 🧪 Ejemplo de Uso

**Entrada:**
> “Tengo pollo y arroz, quiero algo rápido y sin horno.”

**Salida esperada:**
Receta recomendada: Arroz con Pollo Rápido

Corta el pollo en trozos pequeños.

Calienta una sartén y dóralo.

Agrega arroz, caldo y sal.

Cocina a fuego medio por 15 minutos.

Sirve caliente.

Resumen: receta sencilla, económica y sin necesidad de horno.


---

## 🛠️ Instalación y Uso

### Prerrequisitos
```bash
Python 3.9+
pip
torch

Instalación
pip install datasets sentence-transformers transformers accelerate bitsandbytes numpy torch

Clonar el repositorio
git clone https://github.com/<usuario>/<repo>.git

Ejecutar

Abrir:

notebooks/RECETAS.ipynb


Ejecutar todas las celdas.

📦 Modelos Utilizados
Componente	Modelo	Rol
Encoder	paraphrase-multilingual-MiniLM-L12-v2	Embeddings
Vector Store	NumPy	Almacenamiento
Decoder	TinyLlama-1.1B-Chat-v1.0	Generación
Dataset	recipe_nlg_lite	Base de recetas
🎓 Objetivos Académicos

Comprender encoder vs decoder

Construir un sistema RAG real

Aplicar embeddings y similitud semántica

Integrar retrieval + generación

Implementar un asistente funcional de NLP

