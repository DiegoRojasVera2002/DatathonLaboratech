# Sistema de Evaluación de Cumplimiento Normativo con IA

## 🎯 Descripción

Sistema avanzado de evaluación de cumplimiento normativo que combina Machine Learning con procesamiento de lenguaje natural mediante RAG (Retrieval Augmented Generation). El sistema evalúa empresas y asigna calificaciones de 1 a 5 estrellas basándose en datos cuantitativos y análisis de regulaciones.

## 🚀 Características Principales

- **Evaluación Multi-modelo**: Combina LightGBM para datos estructurados con RAG para análisis de regulaciones
- **Calificación por Estrellas**: Sistema de puntuación de 1 a 5 estrellas
- **Análisis Regulatorio**: Procesamiento de normativas mediante RAG con LangChain
- **Recomendaciones Personalizadas**: Generación de sugerencias específicas usando GPT-4
- **Interfaz Interactiva**: Sistema de consulta por ID de empresa
- **Reportes Detallados**: Evaluaciones completas con métricas y recomendaciones

## 📋 Requisitos del Sistema

```bash
Python 3.8+
pandas
numpy
scikit-learn
lightgbm
openai
langchain
faiss-cpu
transformers
torch
```

## 🛠️ Instalación

1. Clonar el repositorio:

```bash
git clone [url-del-repositorio]
cd [nombre-del-repositorio]
```

2. Instalar dependencias:

```bash
pip install -r requirements.txt
```

3. Configurar API key de OpenAI:

```python
OPENAI_API_KEY = "tu-api-key"
```

## 📊 Estructura de Datos Requerida

### Datos de Empresa (CSV)

- `ID_EMPRESA`: Identificador único
- `MONTO_MULTA`: Monto de multas
- `risk_score`: Puntuación de riesgo
- `compliance_score`: Score de cumplimiento
- Otros campos relevantes...

### Regulaciones (TXT)

- Archivo de texto con normativas aplicables
- Formato estructurado para procesamiento RAG

## 🎮 Uso

```python
# Inicializar el sistema
evaluator = EnhancedComplianceEvaluator(OPENAI_API_KEY)

# Cargar datos
evaluator.load_data('data_total.csv', 'normas_ue.txt')

# Entrenar modelo
evaluator.train_model()

# Evaluar una empresa
result = evaluator.evaluate_company('ID_EMPRESA_EJEMPLO')
```

## 📋 Ejemplo de Salida

```
=== Resultado de la Evaluación ===
Empresa ID: EMPRESA123
Calificación: ⭐⭐⭐⭐ (4 estrellas)
Estado: Excelente (Verde)

Evaluación Detallada:
- Nivel de Riesgo: Bajo
- Score de Riesgo: 3.5
- Proporción Indefinidos: 0.85
- Tiempo Operación: 10 años

Recomendaciones:
1. Implementar sistema de gestión de riesgos
2. Mejorar cobertura de seguros
3. Desarrollar plan de capacitación
```

## 🏗️ Arquitectura del Sistema

```
Sistema
├── ML Pipeline (LightGBM)
│   ├── Preprocesamiento
│   ├── Entrenamiento
│   └── Predicción
├── RAG Pipeline
│   ├── Procesamiento de Regulaciones
│   ├── Embeddings (OpenAI)
│   └── Retrieval (FAISS)
└── Agentes IA
    ├── Agente de Regulaciones
    └── Agente de Recomendaciones
```

## 📈 Características del Modelo

- **LightGBM**:

  - Modelo: Clasificación Multiclase
  - Métricas: Multi-logloss, Multi-error
  - Early Stopping: 50 rondas
  - Features Importantes: risk_score, MONTO_MULTA, etc.

- **RAG**:
  - Modelo Base: GPT-4
  - Chunking: 1000 tokens
  - Overlap: 200 tokens
  - Embeddings: OpenAI

## 🔍 Evaluación y Métricas

- Precisión del Modelo ML
- Matriz de Confusión
- Distribución de Estrellas
- Consistencia de Recomendaciones

## 👥 Contribución

Para contribuir al proyecto:

1. Fork el repositorio
2. Crear branch (`git checkout -b feature/AmazingFeature`)
3. Commit cambios (`git commit -m 'Add AmazingFeature'`)
4. Push al branch (`git push origin feature/AmazingFeature`)
5. Abrir Pull Request

## 📝 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE.md para detalles.

## 🤝 Contacto

- Autor: [Tu Nombre]
- Email: [tu@email.com]
- LinkedIn: [Tu perfil]
- GitHub: [Tu perfil]
