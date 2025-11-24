# 🏆 La Curva del Banquillo  
Proyecto de Data Science, Machine Learning y Desarrollo Web centrado en el fútbol.  
Implementa un modelo predictivo para estimar la probabilidad de lesión de jugadores (“La Curva”), una base de datos con estadísticas deportivas y un juego de trivia con preguntas generadas dinámicamente mediante Llama2.

---

## 🚀 Funcionalidades principales

### 1. 📊 Módulo de Estadísticas de Jugadores
- Información general del jugador  
- Historial de lesiones  
- Minutos jugados, rendimiento, historial deportivo  
- Gráficos y comparativas estadísticas  

---

### 2. ❓ Módulo de Juego de Preguntas (Quiz)
- Preguntas generadas automáticamente con **Llama2**  
- 4 opciones por pregunta  
- Temas: reglas, historia, curiosidades, deporte en general  
- Sistema de puntuación y resultados  

---

### 3. 🩺 Módulo de Predicción de Lesiones (ML)
Modelo basado en **Random Forest** o **árboles de decisión**, entrenado en Python.  

**Input del usuario:**
- Edad  
- Estatura  
- Peso  
- Nacionalidad  
- Posición de juego  
- Minutos jugados  
- Historial de lesiones  
- Otros parámetros opcionales  

**Output:**
- Probabilidad de lesionarse en los próximos 3 meses  
- Número estimado de lesiones en la temporada actual  

---

## 🛠️ Tecnologías del Proyecto

### 🔧 Backend
- **Python 3.10+**
- **FastAPI** (o Flask)
- API REST para:
  - Jugadores
  - Estadísticas
  - Predicciones de lesión
  - Generación de preguntas vía LLM

### 💾 Base de datos
- **MySQL 8+**

### 🤖 Machine Learning
- scikit-learn  
- pandas  
- numpy  
- joblib  
- Jupyter Notebooks para exploración y prototipos  

### 🧠 IA para el Quiz
- Llama2 vía API  
- Generación dinámica de preguntas y opciones  

### 🎨 Frontend
- HTML  
- CSS  
- JavaScript  

### 🌐 Infraestructura
- GitHub  
- Entornos locales o servidor en la nube  
- (Opcional) Docker para desplegar backend y ML  

---

## 📁 Estructura del Repositorio

la-curva-del-banquillo/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── architecture.md
│   ├── requirements.md
│   ├── roadmap.md
│   ├── database_schema.md
│   ├── ml_injury_model.md
│   └── llama2_integration.md
│
├── backend/
│   ├── main.py               # API principal (FastAPI)
│   ├── routers/              # Endpoints organizados
│   ├── models/               # Modelos Pydantic
│   ├── services/             # Lógica de negocio
│   ├── database/             # Conexión MySQL + ORM (SQLAlchemy)
│   └── requirements.txt
│
├── frontend/
│   ├── html/
│   ├── css/
│   └── js/
│
├── ml_model/
│   ├── data_samples/
│   ├── notebooks/
│   ├── train_model.py
│   ├── model.pkl
│   ├── api_service.py        # Microservicio ML independiente
│   └── Dockerfile
│
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── schema.sql
│
└── misc/
    ├── mockups/
    └── pdfs/

