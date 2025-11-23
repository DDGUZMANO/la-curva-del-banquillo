# la-curva-del-banquillo
Proyecto de Data Science y Desarrollo Web centrado en el fútbol. Implementa un modelo de Machine Learning para calcular la probabilidad de lesión de jugadores, ofreciendo una visualización de riesgo ("La Curva") y una base de datos de estadísticas detalladas. Cuenta con una sección de trivia interactiva con preguntas generadas por el modelo Llama2

## 🚀 Funcionalidades principales

### 1. 📊 Módulo de Estadísticas de Jugadores
- Información general del jugador.
- Historial de lesiones.
- Partidos jugados, minutos, rendimiento.
- Gráficos y tablas comparativas.

### 2. ❓ Módulo de Juego de Preguntas (Quiz)
- Preguntas generadas dinámicamente con Llama2.
- Cuatro opciones de respuesta.
- Temas: deporte, historia del deporte, reglas y curiosidades.
- Sistema de puntuación.

### 3. 🩺 Módulo de Predicción de Lesiones (ML)
- Modelo basado en **Random Forest** o **árboles de decisión**.
- Input del usuario: edad, peso, estatura, nacionalidad, posición, minutos jugados, lesiones previas, etc.
- Output:
  - Probabilidad de lesionarse en los próximos 3 meses.
  - Número estimado de lesiones en la temporada actual.

---

## 🛠️ Tecnologías

- **Frontend:** HTML, CSS, JS
- **Backend:** PHP 8+
- **Base de datos:** MySQL
- **ML:** Python + scikit-learn
- **IA (Quiz):** Llama2 vía API
- **Infraestructura:** GitHub + servidor local o en la nube

---

## 📁 Estructura del repositorio

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
│   ├── public/
│   ├── app/
│   ├── routes/
│   ├── config/
│   └── composer.json
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
│   ├── api_service.py
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

